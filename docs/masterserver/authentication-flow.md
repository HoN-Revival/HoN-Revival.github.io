---
layout: default
title: Authentication Flow
parent: Master Server
---

# MasterServer authentication flow

HoN uses a variation of [SRP](https://en.wikipedia.org/wiki/Secure_Remote_Password_protocol).

For an overview of this protocol, I highly recommend the [standford documentation](http://srp.stanford.edu/design.html).

This protocol is fairly complicated and uses a lot of math proofs. It took me a while to grasp,
and I still don't feel like an expert. The good news is that the implementation is fairly
straightforward and libraries to do most of the calculations exist in pretty much every
programming language.

I'll discuss SRP in a nutshell, simply put. And then I'll dive into HoN's implementation details.

For digging in to example implementation details, I recommend the python
[srp](https://github.com/cocagne/pysrp/blob/master/srp/_pysrp.py) library source code It's fairly
straightforward: 

It actually computes a lot of the values as soon as they are available (rather than doing it
1 step at a time like in the standford document. But it doesn't matter that much.)

## SRP overview

SRP is an authentication protocol with the primary benefit being that the password
is never stored by the server. In fact, in proper implementations, it's never even
sent to the server at all.

### Registration

Whenver a new user is registered, the algorithm generates a random `salt` (`s`) value.
It then uses two fixed values `N` and `g` (which are complicated prime numbers
and modulo numbers used in the math proof. You don't need to understand these,
just know that they are public and fixed) alongside the `salt` (`s`), `username` (`I`),
and `password` (`p`) to generate a large numerical value called the `password verifier`
(sometimes referred to simply as `v`).

NOTE: This `v` value is very important. Due to how it's created, it cannot be used
to derive the value of `password` or `Hash(password)`. But it can still be used
by both parties in a bunch of equations (as part of the protocol) to confirm
that they are talking about the same value.

NOTE2: The algorithm works on plain text passwords for `p`. But it also works on hashes
derived from the password, so long as the client derives the hash during authentication.
This is worth calling out, as HoN uses a complicated hash of a hash of a hash to compute
its `p`.

At this point, the `salt` (`s`) and the generated `password verifier` (`v`) are
sent to the server, alongside the username, and stored.

The server therefore never receives or stores any identifiable
version of the password. It simply stores the random value (`salt`)
and the `password verifier` (`v`) -- from which the password or it's
hash cannot be derived.

### Authentication

Now that we know the server only has three pieces of information:

- `salt` (a randomly chosen value sent during registation)
- `password verifier` (a complicatedly computed value that came from the
                       password at one point but cannot be used to derive
                       the password or its hash with just this value)
- `I` (the username. not sure why they represent it with an `I`. but they do)

It also knows the public `N` and `g` constants. There are some predefined constants
that are commonly used. But as we'll see later, HoN defined their own custom ones,
which is also valid.

So the goal of authentication is for both parties to agree that their values match,
without actually sending the password anywhere.

So on the client, you log in by typing your `username` (`I`) and `password` (`p`)
and pressing "log in".

The client then chooses a random value (`a`) and keeps that value private. It uses
this secret `a` and uses it to compute `A`. This will be a public value derived from
`a`.  (NOTE: Both of these values are "ephemeral" meaning that they are only used
for this log in attempt. On each log in new random numbers will be chosen and computed.)

This value `A` is then sent to the server alongside the `username` (`I`).

The server uses the `username` (`I`) to look up the `salt` (`s`) and
`password verifier` (`v`), which were stored during registration.

The server then computes its own public value `B`, derived using the `password verifier`
and a bunch of math -- including a random number `b`  which is a private ephemeral value.
(This means the server's `b` and `B` are also ephemeral values, used only for this session
and recomputed for each other session.)

The server then sends the `salt` (`s`) and `B` down to the client.

At this point, both the client and server have values `A` and `B`. These are ephemeral
values that will change each time a new authentication request occurs.

Both the client and server use `A` and `B` to compute `u`. They will come to the same
calculation for `u` since they both use the same `A` and `B`, which they shared with one
another. This `u` is called the "random scrambling parameter". Idk why, but it's used
in the remaining calculations to ensure both parties mathematically arrive at the same
values.

Then, using complicated math, both sides calculate a `session key` (`S`). The session
key on each side is derived using the parts of the protocol available to them.

For example,

- Client uses values: `a` (it's random secret that derived `A`) as well as the `B` given
                      by the server. Along with other values.
- Server uses values: `A`, which was provided by the client, along with `b` (it's random
                      secret value that derived `B`). Along with other values.
                      
And because math is magical, whenever you take the hash of the `S_client` and `S_server`
calculations from above, you arrive at the same result: a `shared session key` value (`K`).

Now that both parties have derived an agreed upon value, the verification can occur.

The double check that everyone's math adds up and that the client didn't just "guess" some
of the shared values and happen to be right, this value `K` is ran through two equations.

First, the client calculates a proof `M1` using using `K` along with all of its other
variable so far (to sort of "prove" that it actually knows them all).

The client then sends this value to the server. The server can run a similar calculation
to confirm that it matched.

If so, the server can consider this login to be valued.

(Optionally...) The server can use that value `M1` from the client in a second calculation
to compute its own proof called `M2`. This second proof `M2` can be sent down to the client
so that the client can double check the server as well.

At this point, assuming all the `M1` and `M2` matched on both sides, then both parties
know the other is who they say they are and authentication is complete! And, best of all,
the password never left the client at all.

## HoN SRP

### Password hashing

The first thing worth mentioning is that HoN computes a hash value derived from the `password`
for use as `p` in the SRP.

The hashing is very complicated and requires the use of its own salt (refrerred to as `salt2`)
as well as two "magic" value constants:

```
S2_SRP_MAGIC1 = "[!~esTo0}"
S2_SRP_MAGIC2 = "taquzaph_?98phab&junaj=z=kuChusu"
```

I imagine these values were chosen randomly. I'm not entirely sure how folks discovered these,
but I believe it was by using a debugger in the `libcrypto-1_1.dll`.

The `salt2` is a constant that is sent down by the server. For example:

```
S2_SALT2 = 'p^^^&bjRlXi4B=A1y.@Vz)'
```

This value is created during registration and stored on the server along with `I`, `salt` (`s`
for the SRP), and `v`.

The hash function then boils down to this:

```
p = sha256(md5(md5(password + S2_SALT2 + S2_SRP_MAGIC1) + S2_SRP_MAGIC2))
```


### HoN SRP Values

HoN uses a custom `N` and `g`. I'm also unsure how these values were discovered, but I assume
via reverse engineering. They are "public" so to speak, as the server is also aware of the same
constants. However they are never sent over the wire during the protocol exchange. They are just
hardcoded on both sides.

```
# Sefe prime N and generator g crypto parameters for SRP authentication.
S2_N = (
    "DA950C6C97918CAE89E4F5ECB32461032A217D740064BC12FC0723CD204BD02A7AE29B53F3310C13BA998B7910F8B6A14112CBC67BDD2427E"
    "DF494CB8BCA68510C0AAEE5346BD320845981546873069B337C073B9A9369D500873D647D261CCED571826E54C6089E7D5085DC2AF01FD861"
    "AE44C8E64BCA3EA4DCE942C5F5B89E5496C2741A9E7E9F509C261D104D11DD4494577038B33016E28D118AE4FD2E85D9C3557A2346FAECED3"
    "EDBE0F4D694411686BA6E65FEE43A772DC84D394ADAE5A14AF33817351D29DE074740AA263187AB18E3A25665EACAA8267C16CDE064B1D5AF"
    "0588893C89C1556D6AEF644A3BA6BA3F7DEC2F3D6FDC30AE43FBD6D144BB"
)
S2_G = "2"
```

### Nuances

#### Case sensitivity?

HoN allows for case insensitive login. (e.g. logging in to `myaccount` is the same as `MyAccount`).
How this is typically implemented for SRP is by taking the `username` (`I`) value and putting it
into lowercase before performing all the calculations.

However this does not appear to be the case with HoN.

The client will fail its verification if the server attempts to lowercase the username. But if it
performs a case-sensitive verification then it passes.

So either I'm missing something in my implementation of SRP for which `I` needs to be the same
one as used to derive `v` when it was stored. Or HoN is doing something unconventional.

One idea, although seems extreme, would be to cache all permutations of capitalization for each
username. (HoN limits usernames to `12` digits, so it would be at most `2^12` or `4096` permutations.)
This is feasible, and then it could just use the current login `I` to look up the appropriate `s` and
`v` based on the current spelling.

Another option might be if it stores their complicated password hash, as described above. That may
explain why their password hashing is so extreme. Although even then it's not ideal as it's still a
hash (of a hash of a hash) derived from the password itself (especially now that the magic and `salt2`
constants are known). Although even assuming that, `I` is still needed to confirm `M1` from the
client from what I can tell. And just . ¯\\_(ツ)_/¯

Or maybe it's just a quirk of the python `srp` library that I was using to test all of this?

If anyone can figure this out, let me know.

#### Maintaining a session?

HoN uses two HTTP calls (which are stateless) to perform authentication. `pre_auth` and `srp_auth`.
It's unclear how the server maintains the state between these two calls.

The calls include some `SysInfo`, but it doesn't appear to match between the two calls so I have
no idea how that's done.

### HoN SRP Flow

#### pre_auth

The HoN client sends a `pre_auth` function request to `client_requester.php`:

For example:

```
POST /client_requester.php?f=pre_auth HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 705
Content-Type: application/x-www-form-urlencoded

login=happyasthma&A=4c45b21a768b1aa33fbcae0f377f30ad9f7e7a766cb8a8d89d0ed0ddbac7844e402997b
12c545453487403735c4a64490be43ee702645b550c01daf0ef92224ec7c004dec183ef0f6e048442b9f4e598bd
2993d32534a22e30f51f726b40fac1fc74a099f3f2eed81c9de75a170e963705d35c336e73d27295abc698f266a
16aa52d54b04de1beffcb97352024ad25ff52d678453b032c4cc1aa11d8f8b61e5d2852609a71bf2476630a5b3a
bb389c6a79e325e8f6d97c3dd53e5d22620d67139ccc5b014852264f5b0313f756dc81cfc67a8e1a3978c69003a
fb78a20ad356a8d6c2f694a720d2b3ae4742ee55c20df2f6017cb9ba7a2353e7c427d334ea507&SysInfo=f0-2f
-74-f4-73-7b%7CMicrosoft+Windows+10+Home%3B+Version+10.0.19044%7CAMD+Ryzen+7+5800X+8-Core+P
rocessor+%283801+MHz%29%7CAMD+Radeon+RX+6600+%284.00+GB%29%7C2.00+GB
```

You'll notice this includes the `login=` (i.e. the `I`) and `A=` (the `A` value) as the first
part of the SRP.

It also sends a `SysInfo=` but it's unclear what that's used for. My first thought was to
act like an identification (like a 'cookie' would be) to track sessions across the two
HTTP calls. But the following call to `srpAuth` (explained below) does not seem to match.
¯\\_(ツ)_/¯

The server then sends its `salt`, `salt2` (as used to do the password hash on the cleint),
and `B` to the client.

That response looks something like this:

```
HTTP/1.1 200 OK
Date: Wed, 06 Apr 2022 10:05:07 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 1145
Connection: close
Content-Type: text/plain; charset=utf-8

a:5:{s:4:"salt";s:512:"fbc449d04783c07a0ba280af0447a76e7d927275476e2b282333426948ba70f7d4a
843ab8c11b9ad3102cb274ee547a35f3825240a62bbadc356b009173052b0ed946b39a001c4fb4cffd81c8b59a
5c95fe54db10b3baac21e92d915dd72847e5a286e39334d358ab83f7c24b1fb70277ebb3ff8648cebe74ca5943
656c9eb9512137460ee22e7ed7761d0cbd6ca7efcf3b5d6b4165f37520a2133ab8fee154325b21c9348f9874f2
7c99620c8d4d9c554bb8906b4b2ae6881ccb13537bb18dbbcb901d72ad0c639cd495380f1cb0467a018ae55ea4
8a53a7a835a689c17b578c2ea93c2fe22d56b1d08ca13c71a073b8b72aafe96ba21d20bf7c51c5d744945";s:5
:"salt2";s:22:"kf.l06h2j4(l<JOLh1]H0r";s:1:"B";s:512:"114cdcfda8b06d6a10e29cc7c77955df2d93
1961b19c6aa7f7b0ae2cf5c2b72eaa047edf6ed725660174577a64f97cb26d7c1b168ee982c32d4deb298209b9
2d2bc40edf1c4c62ff8f0a0d61f86939bffafe0bcaac863f8499701d4b23641f825c2f2887479d9dad3a184349
1f351f70a88fc94a0a7ff849f231297dadb96efa4fcd53d778af90f9f3cfea28b7d1fb7ef3173209aaad7d2e83
48deca8865306a4715432069ff3b349cd19db2e60dd293e3d88c23f97381f0d45077456fcfd4f05ace8c026eaa
c922747e6032c520093719a030cbc52343188de7ed4c1d9a30180a1beca36839ee5aacff3744ef108db572f9b4
613abbccd1e7b98ac19c1d1c46";s:16:"vested_threshold";i:5;i:0;b:1;}
```

You'll notice this response (like all Master Server responses) is serialized PHP output.

When you deserialize it, it' easier to read:

```
Array
(
    [salt] => fbc449d04783c07a0ba280af0447a76e7d927275476e2b282333426948ba70f7d4a843ab8c11b9
              ad3102cb274ee547a35f3825240a62bbadc356b009173052b0ed946b39a001c4fb4cffd81c8b59
              a5c95fe54db10b3baac21e92d915dd72847e5a286e39334d358ab83f7c24b1fb70277ebb3ff864
              8cebe74ca5943656c9eb9512137460ee22e7ed7761d0cbd6ca7efcf3b5d6b4165f37520a2133ab
              8fee154325b21c9348f9874f27c99620c8d4d9c554bb8906b4b2ae6881ccb13537bb18dbbcb901
              d72ad0c639cd495380f1cb0467a018ae55ea48a53a7a835a689c17b578c2ea93c2fe22d56b1d08
              ca13c71a073b8b72aafe96ba21d20bf7c51c5d744945
    [salt2] => kf.l06h2j4(l<JOLh1]H0r
    [B] => 114cdcfda8b06d6a10e29cc7c77955df2d931961b19c6aa7f7b0ae2cf5c2b72eaa047edf6ed725660
           174577a64f97cb26d7c1b168ee982c32d4deb298209b92d2bc40edf1c4c62ff8f0a0d61f86939bffa
           fe0bcaac863f8499701d4b23641f825c2f2887479d9dad3a1843491f351f70a88fc94a0a7ff849f23
           1297dadb96efa4fcd53d778af90f9f3cfea28b7d1fb7ef3173209aaad7d2e8348deca8865306a4715
           432069ff3b349cd19db2e60dd293e3d88c23f97381f0d45077456fcfd4f05ace8c026eaac922747e6
           032c520093719a030cbc52343188de7ed4c1d9a30180a1beca36839ee5aacff3744ef108db572f9b4
           613abbccd1e7b98ac19c1d1c46
    [vested_threshold] => 5
    [0] => 1
)
```

I have no clue what `vested_threshold` or `0` keys are for. They are in a lot of server
responses but I don't think they are used anywhere that I could find. So just ignore them
for now.

You'll notice that this response contains the `salt`, `salt2`, and `B` as mentioned above.

Now both the client and server can compute all of their math to come to a common `K`
session key value.

The client then uses `K` to derive it's "proof" `M1`.

#### srpAuth`

The client then sends the `M1` value to the server in the `srpAuth` HTTP request to
`client_requester.php`.

You'll notice it contains a field called `proof=` as well as the same `login` identifying
which user is attempting to log in.

```
POST /client_requester.php?f=srpAuth HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 482
Content-Type: application/x-www-form-urlencoded

login=happyasthma&proof=89Zdc37022a5ea8e2b9ba6182b36362052377daefa723a284b95bd55e38c6
ea0&OSType=129&MajorVersion=6&MinorVersion=2&MicroVersion=0&SysInfo=9E98ABAAF7542FD49
A1A69D9137CE907826CF4502F326ABF064661285C53C6A0%7C9E98ABAAF7542FD49A1A69D9137CE907826
CF4502F326ABF064661285C53C6A0%7C9E98ABAAF7542FD49A1A69D9137CE907826CF4502F326ABF06466
1285C53C6A0%7C9E98ABAAF7542FD49A1A69D9137CE907826CF4502F326ABF064661285C53C6A0%7C9E99
ABAAF7542FD49A1A69D9137CE907826CF4502F326ABF064661285C53C6A0
```

You'll notice also that now it includes some other random (maybe identification?)
info:

- `OSType=`
- `MajorVersion=`
- `MinorVersion=`
- `MicroVersion=`
- `SysInfo=`

But I have no clue what values these refer to. Maybe the `SysInfo` is some kind of hash
of the earlier sent one? I haven't really checked that but the thought just occurred to
me.

I can't make heads or tails of the other parameters. The `OSType` doesn't map to any value
I'm aware of. And the versioning values don't map to my PC in any way that I can find and
doesn't match the HoN version. So idk.

Once the server has the `proof` (`M1`). It validates it against it's own calculations.

If it succeeds, it replies back with its own secondary proof `M2`, which the HoN client
DOES validate agains. If the server's proof `M2` is wrong, the client will NOT log in.

It also sends a TON of other information about the account which is used to render the
initial UI, such as the account info, friends list, unlocked content, and more.

It also includes a `cookie=` at this point, which is used by the client in all subsequent
requests to identify itself. It's unclear of how long these cookies are active for, but
presumably after some TTL.

Other important parts of this response are the `chat_url` and `chat_port` for the client
to use to connect to the chat server.

There's tons of info here and I haven't even parsed it all yet.

Example response:

NOTE: This response can be huge. This is for an account with nothing unlocked, few friends,
and no games played. The one from my main account was like 17 pages long in Google Docs when
I dumped it.

```
Date: Wed, 13 Apr 2022 04:52:30 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 5631
Connection: close
Content-Type: text/plain; charset=utf-8

a:60:{s:5:"proof";s:64:"edf525259acda64972f708b0f9713ac9759fb01999efc9cb0dd6ca3ebaa9b263";s:8:
"sec_info";a:3:{s:14:"initial_vector";s:16:"73088db5e71cfb6d";s:9:"hash_code";s:40:"73088db5e7
1cfb6d43ae0bb4abf095dd43862200";s:11:"key_version";s:4:"3e2d";}s:8:"super_id";s:7:"8746589";s:
10:"account_id";s:7:"8941120";s:9:"garena_id";N;s:8:"nickname";s:9:"TwitchBot";s:5:"email";s:2
5:"mrh.appy.asthma@gmail.com";s:12:"account_type";s:1:"3";s:5:"trial";s:1:"0";s:7:"susp_id";s:
1:"0";s:11:"prepay_only";N;s:8:"standing";s:1:"1";s:9:"use_cloud";N;s:8:"pass_exp";N;s:6:"is_n
ew";i:0;s:6:"cookie";s:32:"e371017339a3df2d0cecd31ce185144a";s:2:"ip";s:13:"108.193.2.113";s:20
:"minimum_ranked_level";s:1:"3";s:15:"leaverthreshold";s:3:".05";s:11:"is_under_24";b:0;s:13:"i
s_subaccount";b:0;s:21:"is_current_subaccount";b:0;s:7:"icb_url";s:33:"http://s3.amazonaws.com/
naeu-icb2";s:9:"auth_hash";s:40:"ab5bfc2c9b474413db4506e8f02aea5928f6c572";s:9:"host_time";s:10
:"1649825550";s:8:"chat_url";s:12:"50.22.208.66";s:9:"chat_port";s:5:"11031";s:7:"cafe_id";N;s:
11:"gca_regular";N;s:9:"gca_prime";N;s:14:"commenting_url";s:14:"174.37.182.125";s:15:"commenti
ng_port";i:9000;s:9:"hero_list";a:1:{s:4:"free";s:38:"Hero_Genesis,Hero_Dorin_Tal,Hero_Adeve";}
s:10:"buddy_list";a:1:{i:8941120;a:3:{i:782203;a:8:{s:8:"buddy_id";s:6:"782203";s:5:"group";s:0
:"";s:8:"clan_tag";s:3:"FFX";s:6:"status";s:1:"2";s:8:"nickname";s:11:"happyasthma";s:8:"standi
ng";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8527634;a:8:{s:8:"buddy_id";s:7:"852763
4";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:11:"ParallaxMid";s
:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8974487;a:8:{s:8:"buddy_id";s
:7:"8974487";s:5:"group";s:0:"";s:8:"clan_tag";s:3:"FFX";s:6:"status";s:1:"2";s:8:"nickname";s:
9:"stratkING";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}}}s:12:"ignored_
list";a:1:{i:8941120;a:0:{}}s:11:"banned_list";a:1:{i:8941120;a:0:{}}s:5:"infos";a:1:{i:0;a:32:
{s:10:"account_id";s:7:"8941120";s:8:"standing";s:1:"1";s:5:"level";s:1:"1";s:9:"level_exp";s:1
:"0";s:6:"discos";s:1:"0";s:15:"possible_discos";s:1:"0";s:12:"games_played";s:1:"0";s:17:"num_
bot_games_won";N;s:13:"acc_pub_skill";s:8:"1500.000";s:8:"acc_wins";s:1:"0";s:10:"acc_losses";s
:1:"0";s:16:"acc_games_played";s:1:"0";s:10:"acc_discos";s:1:"0";s:19:"rnk_amm_team_rating";s:8
:"1500.000";s:8:"rnk_wins";s:1:"0";s:10:"rnk_losses";s:1:"0";s:16:"rnk_games_played";s:1:"0";s:
10:"rnk_discos";s:1:"0";s:18:"cs_amm_team_rating";s:8:"1500.000";s:7:"cs_wins";s:1:"0";s:9:"cs_
losses";s:1:"0";s:15:"cs_games_played";s:1:"0";s:9:"cs_discos";s:1:"0";s:16:"mid_games_played";
s:1:"0";s:10:"mid_discos";s:1:"0";s:17:"rift_games_played";s:1:"0";s:11:"rift_discos";s:1:"0";s
:6:"is_new";i:0;s:16:"cam_games_played";i:0;s:10:"cam_discos";i:0;s:19:"cam_cs_games_played";i:
0;s:13:"cam_cs_discos";i:0;}}s:16:"clan_member_info";a:1:{s:5:"error";s:22:"No clan members fou
nd.";}s:9:"chatrooms";a:1:{i:0;s:0:"";}s:13:"notifications";a:3:{i:0;a:2:{s:12:"notification";s
:81:"stratkING||2|notify_buddy_added|notification_generic_info||02/04 00:27 AM|1140756";s:9:"no
tify_id";s:7:"1140756";}i:1;a:2:{s:12:"notification";s:94:"HappyAsthma`||2|notify_buddy_request
ed_adder|notification_generic_info||02/04 00:27 AM|1140757";s:9:"notify_id";s:7:"1140757";}i:2;
a:2:{s:12:"notification";s:84:"HappyAsthma`||2|notify_buddy_added|notification_generic_info||02
/06 00:26 AM|1142460";s:9:"notify_id";s:7:"1142460";}}s:11:"clan_roster";a:1:{s:5:"error";s:22:
"No clan members found.";}s:10:"identities";a:1:{i:0;a:2:{i:0;s:9:"TwitchBot";i:1;s:7:"8941120"
;}}s:6:"points";s:1:"0";s:8:"mmpoints";s:4:"2950";s:11:"dice_tokens";s:1:"0";s:12:"season_level
";i:0;s:11:"my_upgrades";a:4:{i:0;s:15:"m.allmodes.pass";i:1;s:16:"h.AllHeroes.Hero";i:2;s:8:"c
c.white";i:3;s:15:"ai.Default Icon";}s:17:"selected_upgrades";a:2:{i:0;s:8:"cc.white";i:1;s:15:
"ai.Default Icon";}s:11:"game_tokens";i:0;s:16:"my_upgrades_info";a:1:{s:8:"cc.white";a:1:{s:4:
"data";s:0:"";}}s:11:"creep_level";i:0;s:9:"timestamp";i:1649825550;s:14:"awards_tooltip";a:12:
{s:10:"milestones";a:5:{s:11:"heroassists";a:4:{s:5:"aname";s:11:"heroassists";s:3:"exp";s:3:"1
00";s:2:"gc";s:1:"5";s:6:"modulo";s:3:"250";}s:9:"herokills";a:4:{s:5:"aname";s:9:"herokills";s
:3:"exp";s:3:"100";s:2:"gc";s:1:"5";s:6:"modulo";s:3:"250";}s:9:"smackdown";a:4:{s:5:"aname";s:
9:"smackdown";s:3:"exp";s:2:"50";s:2:"gc";s:1:"1";s:6:"modulo";s:2:"10";}s:5:"wards";a:4:{s:5:"a
name";s:5:"wards";s:3:"exp";s:3:"100";s:2:"gc";s:1:"5";s:6:"modulo";s:2:"50";}s:4:"wins";a:4:{s
:5:"aname";s:4:"wins";s:3:"exp";s:3:"200";s:2:"gc";s:2:"10";s:6:"modulo";s:2:"50";}}s:8:"leveli
ng";a:3:{s:3:"2-5";i:6;s:4:"6-10";i:12;s:5:"11-15";i:18;}s:9:"bloodlust";a:2:{s:3:"exp";i:10;s:
2:"gc";i:2;}s:12:"annihilation";a:4:{s:3:"exp";i:75;s:2:"gc";i:15;s:6:"tm_exp";i:25;s:5:"tm_gc"
;i:5;}s:8:"immortal";a:4:{s:3:"exp";i:50;s:2:"gc";i:10;s:6:"tm_exp";i:15;s:5:"tm_gc";i:3;}s:7:
"victory";a:2:{s:3:"exp";i:30;s:2:"gc";i:6;}s:4:"loss";a:2:{s:3:"exp";i:10;s:2:"gc";i:2;}s:5:"
disco";a:2:{s:3:"exp";i:0;s:2:"gc";i:0;}s:5:"quick";a:2:{s:3:"exp";i:0;s:2:"gc";i:2;}s:5:"firs
t";a:2:{s:3:"exp";i:20;s:2:"gc";i:4;}s:10:"consec_win";a:2:{s:3:"exp";i:0;s:2:"gc";s:3:"2-6";}
s:11:"consec_loss";a:2:{s:3:"exp";i:0;s:2:"gc";i:1;}}s:12:"quest_system";a:1:{s:5:"error";a:2:{
s:12:"quest_status";i:0;s:18:"leaderboard_status";i:0;}}s:23:"campaign_current_season";s:2:"12"
;s:8:"mmr_rank";s:99:"1250,1275,1300,1330,1365,1400,1435,1470,1505,1540,1575,1610,1645,1685,172
5,1765,1805,1850,1900,1950";s:26:"account_cloud_storage_info";b:0;s:15:"mute_expiration";i:0;s:
16:"vested_threshold";i:5;i:0;b:1;}
```

The deserialized version is a bit easier on the eyes:

```
Array
(
    [proof] => edf525259acda64972f708b0f9713ac9759fb01999efc9cb0dd6ca3ebaa9b263
    [sec_info] => Array
        (
            [initial_vector] => 73088db5e71cfb6d
            [hash_code] => 73088db5e71cfb6d43ae0bb4abf095dd43862200
            [key_version] => 3e2d
        )

    [super_id] => 8746589
    [account_id] => 8941120
    [garena_id] => 
    [nickname] => TwitchBot
    [email] => mrh.appy.asthma@gmail.com
    [account_type] => 3
    [trial] => 0
    [susp_id] => 0
    [prepay_only] => 
    [standing] => 1
    [use_cloud] => 
    [pass_exp] => 
    [is_new] => 0
    [cookie] => e371017339a3df2d0cecd31ce185144a
    [ip] => 108.193.2.113
    [minimum_ranked_level] => 3
    [leaverthreshold] => .05
    [is_under_24] => 
    [is_subaccount] => 
    [is_current_subaccount] => 
    [icb_url] => http://s3.amazonaws.com/naeu-icb2
    [auth_hash] => ab5bfc2c9b474413db4506e8f02aea5928f6c572
    [host_time] => 1649825550
    [chat_url] => 50.22.208.66
    [chat_port] => 11031
    [cafe_id] => 
    [gca_regular] => 
    [gca_prime] => 
    [commenting_url] => 174.37.182.125
    [commenting_port] => 9000
    [hero_list] => Array
        (
            [free] => Hero_Genesis,Hero_Dorin_Tal,Hero_Adeve
        )

    [buddy_list] => Array
        (
            [8941120] => Array
                (
                    [782203] => Array
                        (
                            [buddy_id] => 782203
                            [group] => 
                            [clan_tag] => FFX
                            [status] => 2
                            [nickname] => happyasthma
                            [standing] => 3
                            [inactive] => 0
                            [new] => 0
                        )

                    [8527634] => Array
                        (
                            [buddy_id] => 8527634
                            [group] => 
                            [clan_tag] => 
                            [status] => 2
                            [nickname] => ParallaxMid
                            [standing] => 3
                            [inactive] => 0
                            [new] => 0
                        )

                    [8974487] => Array
                        (
                            [buddy_id] => 8974487
                            [group] => 
                            [clan_tag] => FFX
                            [status] => 2
                            [nickname] => stratkING
                            [standing] => 3
                            [inactive] => 0
                            [new] => 0
                        )

                )

        )

    [ignored_list] => Array
        (
            [8941120] => Array
                (
                )

        )

    [banned_list] => Array
        (
            [8941120] => Array
                (
                )

        )

    [infos] => Array
        (
            [0] => Array
                (
                    [account_id] => 8941120
                    [standing] => 1
                    [level] => 1
                    [level_exp] => 0
                    [discos] => 0
                    [possible_discos] => 0
                    [games_played] => 0
                    [num_bot_games_won] => 
                    [acc_pub_skill] => 1500.000
                    [acc_wins] => 0
                    [acc_losses] => 0
                    [acc_games_played] => 0
                    [acc_discos] => 0
                    [rnk_amm_team_rating] => 1500.000
                    [rnk_wins] => 0
                    [rnk_losses] => 0
                    [rnk_games_played] => 0
                    [rnk_discos] => 0
                    [cs_amm_team_rating] => 1500.000
                    [cs_wins] => 0
                    [cs_losses] => 0
                    [cs_games_played] => 0
                    [cs_discos] => 0
                    [mid_games_played] => 0
                    [mid_discos] => 0
                    [rift_games_played] => 0
                    [rift_discos] => 0
                    [is_new] => 0
                    [cam_games_played] => 0
                    [cam_discos] => 0
                    [cam_cs_games_played] => 0
                    [cam_cs_discos] => 0
                )

        )

    [clan_member_info] => Array
        (
            [error] => No clan members found.
        )

    [chatrooms] => Array
        (
            [0] => 
        )

    [notifications] => Array
        (
            [0] => Array
                (
                    [notification] => stratkING||2|notify_buddy_added|notification_generic_info||02/04 00:27 AM|1140756
                    [notify_id] => 1140756
                )

            [1] => Array
                (
                    [notification] => HappyAsthma`||2|notify_buddy_requested_adder|notification_generic_info||02/04 00:27 AM|1140757
                    [notify_id] => 1140757
                )

            [2] => Array
                (
                    [notification] => HappyAsthma`||2|notify_buddy_added|notification_generic_info||02/06 00:26 AM|1142460
                    [notify_id] => 1142460
                )

        )

    [clan_roster] => Array
        (
            [error] => No clan members found.
        )

    [identities] => Array
        (
            [0] => Array
                (
                    [0] => TwitchBot
                    [1] => 8941120
                )

        )

    [points] => 0
    [mmpoints] => 2950
    [dice_tokens] => 0
    [season_level] => 0
    [my_upgrades] => Array
        (
            [0] => m.allmodes.pass
            [1] => h.AllHeroes.Hero
            [2] => cc.white
            [3] => ai.Default Icon
        )

    [selected_upgrades] => Array
        (
            [0] => cc.white
            [1] => ai.Default Icon
        )

    [game_tokens] => 0
    [my_upgrades_info] => Array
        (
            [cc.white] => Array
                (
                    [data] => 
                )

        )

    [creep_level] => 0
    [timestamp] => 1649825550
    [awards_tooltip] => Array
        (
            [milestones] => Array
                (
                    [heroassists] => Array
                        (
                            [aname] => heroassists
                            [exp] => 100
                            [gc] => 5
                            [modulo] => 250
                        )

                    [herokills] => Array
                        (
                            [aname] => herokills
                            [exp] => 100
                            [gc] => 5
                            [modulo] => 250
                        )

                    [smackdown] => Array
                        (
                            [aname] => smackdown
                            [exp] => 50
                            [gc] => 1
                            [modulo] => 10
                        )

                    [wards] => Array
                        (
                            [aname] => wards
                            [exp] => 100
                            [gc] => 5
                            [modulo] => 50
                        )

                    [wins] => Array
                        (
                            [aname] => wins
                            [exp] => 200
                            [gc] => 10
                            [modulo] => 50
                        )

                )

            [leveling] => Array
                (
                    [2-5] => 6
                    [6-10] => 12
                    [11-15] => 18
                )

            [bloodlust] => Array
                (
                    [exp] => 10
                    [gc] => 2
                )

            [annihilation] => Array
                (
                    [exp] => 75
                    [gc] => 15
                    [tm_exp] => 25
                    [tm_gc] => 5
                )

            [immortal] => Array
                (
                    [exp] => 50
                    [gc] => 10
                    [tm_exp] => 15
                    [tm_gc] => 3
                )

            [victory] => Array
                (
                    [exp] => 30
                    [gc] => 6
                )

            [loss] => Array
                (
                    [exp] => 10
                    [gc] => 2
                )

            [disco] => Array
                (
                    [exp] => 0
                    [gc] => 0
                )

            [quick] => Array
                (
                    [exp] => 0
                    [gc] => 2
                )

            [first] => Array
                (
                    [exp] => 20
                    [gc] => 4
                )

            [consec_win] => Array
                (
                    [exp] => 0
                    [gc] => 2-6
                )

            [consec_loss] => Array
                (
                    [exp] => 0
                    [gc] => 1
                )

        )

    [quest_system] => Array
        (
            [error] => Array
                (
                    [quest_status] => 0
                    [leaderboard_status] => 0
                )

        )

    [campaign_current_season] => 12
    [mmr_rank] => 1250,1275,1300,1330,1365,1400,1435,1470,1505,1540,1575,1610,1645,1685,1725,1765,1805,1850,1900,1950
    [account_cloud_storage_info] => 
    [mute_expiration] => 0
    [vested_threshold] => 5
    [0] => 1
)
```

### Switching sub accounts

When switching a sub account, HoN issues a `switch_auth` request.

#### Request

```
POST /client_requester.php?f=switch_auth HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 76
Content-Type: application/x-www-form-urlencoded

login=ParallaxMid&account_id=8527634&cookie=98537ad499f1c6b318277a467a9bbc50
```

Fields:

- `login`: The username of the target account to swap to.
- `account_id`: 
- `cookie`: The session cookie

#### Response:

##### Valid

```
HTTP/1.1 200 OK
Date: Sun, 05 Jun 2022 01:45:19 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Connection: close
Transfer-Encoding: chunked
Content-Type: text/plain; charset=utf-8

a:59:{s:12:"client_disco";s:2:"OK";s:8:"sec_info";a:3:{s:14:"initial_vector";s:16:"73088db5e71cfb6d";s:9:"hash_code";s:40:"73088db5e71cfb6d43ae0bb4abf095dd43862200";s:11:"key_version";s:4:"3e2d";}s:8:"super_id";s:6:"782203";s:10:"account_id";s:7:"8527634";s:9:"garena_id";N;s:8:"nickname";s:11:"ParallaxMid";s:5:"email";s:23:"mrhappyasthma@gmail.com";s:12:"account_type";s:1:"3";s:5:"trial";s:1:"0";s:7:"susp_id";s:1:"0";s:11:"prepay_only";N;s:8:"standing";s:1:"3";s:9:"use_cloud";N;s:8:"pass_exp";N;s:6:"is_new";i:0;s:6:"cookie";s:32:"0bd8adae3fa075fc80b16e28321f8283";s:2:"ip";s:13:"108.193.2.113";s:20:"minimum_ranked_level";s:1:"3";s:15:"leaverthreshold";s:3:".05";s:11:"is_under_24";b:0;s:13:"is_subaccount";b:1;s:21:"is_current_subaccount";b:1;s:7:"icb_url";s:33:"http://s3.amazonaws.com/naeu-icb2";s:9:"auth_hash";s:40:"2f63ad9ee4ad8f9e5205aa2eed6b49cdb4f1aa2a";s:9:"host_time";s:10:"1654393519";s:8:"chat_url";s:12:"50.22.208.66";s:9:"chat_port";s:5:"11031";s:7:"cafe_id";N;s:11:"gca_regular";N;s:9:"gca_prime";N;s:14:"commenting_url";s:14:"174.37.182.125";s:15:"commenting_port";i:9000;s:9:"hero_list";a:1:{s:4:"free";s:38:"Hero_Genesis,Hero_Dorin_Tal,Hero_Adeve";}s:10:"buddy_list";a:1:{i:8527634;a:65:{i:353716;a:8:{s:8:"buddy_id";s:6:"353716";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"KingKUupa";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:494431;a:8:{s:8:"buddy_id";s:6:"494431";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"NAAB";s:6:"status";s:1:"2";s:8:"nickname";s:6:"Alelor";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:771142;a:8:{s:8:"buddy_id";s:6:"771142";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:8:"Magician";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:782203;a:8:{s:8:"buddy_id";s:6:"782203";s:5:"group";s:0:"";s:8:"clan_tag";s:3:"FFX";s:6:"status";s:1:"2";s:8:"nickname";s:11:"happyasthma";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:832027;a:8:{s:8:"buddy_id";s:6:"832027";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"Dabuttkicker";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:1193841;a:8:{s:8:"buddy_id";s:7:"1193841";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:5:"stimd";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3022492;a:8:{s:8:"buddy_id";s:7:"3022492";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"Doofensmirtz";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3088502;a:8:{s:8:"buddy_id";s:7:"3088502";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:5:"sinic";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3333772;a:8:{s:8:"buddy_id";s:7:"3333772";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"MeBe";s:6:"status";s:1:"2";s:8:"nickname";s:10:"ColdClimax";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3407649;a:8:{s:8:"buddy_id";s:7:"3407649";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"This`Dick";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3753757;a:8:{s:8:"buddy_id";s:7:"3753757";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"Moosenuckles";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3756772;a:8:{s:8:"buddy_id";s:7:"3756772";s:5:"group";s:0:"";s:8:"clan_tag";s:3:"420";s:6:"status";s:1:"2";s:8:"nickname";s:12:"xX412sWaGGaX";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:3757359;a:8:{s:8:"buddy_id";s:7:"3757359";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:8:"Element7";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:4128552;a:8:{s:8:"buddy_id";s:7:"4128552";s:5:"group";s:0:"";s:8:"clan_tag";s:3:"YSL";s:6:"status";s:1:"2";s:8:"nickname";s:9:"JaeWizzle";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:4684073;a:8:{s:8:"buddy_id";s:7:"4684073";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"StevieSparkZ";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:4946581;a:8:{s:8:"buddy_id";s:7:"4946581";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:10:"iGotcha670";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:5306570;a:8:{s:8:"buddy_id";s:7:"5306570";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"BSBG";s:6:"status";s:1:"2";s:8:"nickname";s:5:"bubly";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:5658764;a:8:{s:8:"buddy_id";s:7:"5658764";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"Mint";s:6:"status";s:1:"2";s:8:"nickname";s:9:"KittyKiss";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:6384254;a:8:{s:8:"buddy_id";s:7:"6384254";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"starseed`";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:6898819;a:8:{s:8:"buddy_id";s:7:"6898819";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"BSBG";s:6:"status";s:1:"2";s:8:"nickname";s:10:"bronypower";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7208832;a:8:{s:8:"buddy_id";s:7:"7208832";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"ptsamurai";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7460038;a:8:{s:8:"buddy_id";s:7:"7460038";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:11:"Shur`tugal`";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7466157;a:8:{s:8:"buddy_id";s:7:"7466157";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"NHBN";s:6:"status";s:1:"2";s:8:"nickname";s:12:"PMILive_Life";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7518122;a:8:{s:8:"buddy_id";s:7:"7518122";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"MaIi";s:6:"status";s:1:"2";s:8:"nickname";s:12:"wellyouknow1";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7608528;a:8:{s:8:"buddy_id";s:7:"7608528";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:8:"Grisette";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7739720;a:8:{s:8:"buddy_id";s:7:"7739720";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"hips";s:6:"status";s:1:"2";s:8:"nickname";s:5:"`PElN";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7778150;a:8:{s:8:"buddy_id";s:7:"7778150";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:6:"glmate";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7796715;a:8:{s:8:"buddy_id";s:7:"7796715";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"mrhappyasthm";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7798482;a:8:{s:8:"buddy_id";s:7:"7798482";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"Crispybyu";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:7853187;a:8:{s:8:"buddy_id";s:7:"7853187";s:5:"group";s:0:"";s:8:"clan_tag";s:2:"sG";s:6:"status";s:1:"2";s:8:"nickname";s:7:"Leoplus";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8046888;a:8:{s:8:"buddy_id";s:7:"8046888";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"TZUN";s:6:"status";s:1:"2";s:8:"nickname";s:12:"HotForSEMPAI";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8085306;a:8:{s:8:"buddy_id";s:7:"8085306";s:5:"group";s:0:"";s:8:"clan_tag";s:3:"GME";s:6:"status";s:1:"2";s:8:"nickname";s:9:"GamesDean";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8162643;a:8:{s:8:"buddy_id";s:7:"8162643";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"TZUN";s:6:"status";s:1:"2";s:8:"nickname";s:10:"HugsForAll";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8270837;a:8:{s:8:"buddy_id";s:7:"8270837";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:10:"PunkDeFunk";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8305346;a:8:{s:8:"buddy_id";s:7:"8305346";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"MyFistUrAnus";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8323850;a:8:{s:8:"buddy_id";s:7:"8323850";s:5:"group";s:0:"";s:8:"clan_tag";s:3:"ECx";s:6:"status";s:1:"2";s:8:"nickname";s:5:"scato";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8350037;a:8:{s:8:"buddy_id";s:7:"8350037";s:5:"group";s:0:"";s:8:"clan_tag";s:1:"A";s:6:"status";s:1:"2";s:8:"nickname";s:8:"thexowoa";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8351169;a:8:{s:8:"buddy_id";s:7:"8351169";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"BALR";s:6:"status";s:1:"2";s:8:"nickname";s:8:"Choopsta";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8406306;a:8:{s:8:"buddy_id";s:7:"8406306";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:11:"lChimpayate";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8436593;a:8:{s:8:"buddy_id";s:7:"8436593";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:7:"REKNITx";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8439826;a:8:{s:8:"buddy_id";s:7:"8439826";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"CHEP";s:6:"status";s:1:"2";s:8:"nickname";s:8:"Jhoppsee";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8540257;a:8:{s:8:"buddy_id";s:7:"8540257";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:8:"DemJukez";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8542329;a:8:{s:8:"buddy_id";s:7:"8542329";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"nom3";s:6:"status";s:1:"2";s:8:"nickname";s:8:"Intrific";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8555977;a:8:{s:8:"buddy_id";s:7:"8555977";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"Casper`87";s:8:"standing";s:1:"3";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8556799;a:8:{s:8:"buddy_id";s:7:"8556799";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:10:"utkatasana";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8562609;a:8:{s:8:"buddy_id";s:7:"8562609";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:8:"Marko_LB";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8575904;a:8:{s:8:"buddy_id";s:7:"8575904";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"BruceLee7";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8676758;a:8:{s:8:"buddy_id";s:7:"8676758";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:11:"ISupportBRs";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8694224;a:8:{s:8:"buddy_id";s:7:"8694224";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"Mint";s:6:"status";s:1:"2";s:8:"nickname";s:9:"DiePlsNow";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8713549;a:8:{s:8:"buddy_id";s:7:"8713549";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:10:"cactusfeet";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8797624;a:8:{s:8:"buddy_id";s:7:"8797624";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:10:"fistofgold";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8867038;a:8:{s:8:"buddy_id";s:7:"8867038";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:6:"Kev2k`";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8874448;a:8:{s:8:"buddy_id";s:7:"8874448";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:7:"NYCPony";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8875308;a:8:{s:8:"buddy_id";s:7:"8875308";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"xBTW";s:6:"status";s:1:"2";s:8:"nickname";s:6:"BuBz93";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:8886562;a:8:{s:8:"buddy_id";s:7:"8886562";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"mattviper";s:8:"standing";s:1:"1";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:8903807;a:8:{s:8:"buddy_id";s:7:"8903807";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"Hennessy`";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:8918241;a:8:{s:8:"buddy_id";s:7:"8918241";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:6:"`xcoca";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:8941120;a:8:{s:8:"buddy_id";s:7:"8941120";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"TwitchBot";s:8:"standing";s:1:"1";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:8971333;a:8:{s:8:"buddy_id";s:7:"8971333";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:12:"HoNTriviaBot";s:8:"standing";s:1:"1";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:9019098;a:8:{s:8:"buddy_id";s:7:"9019098";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:6:"upsbro";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:9050789;a:8:{s:8:"buddy_id";s:7:"9050789";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"xBTW";s:6:"status";s:1:"2";s:8:"nickname";s:7:"`bubz93";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"0";}i:9105199;a:8:{s:8:"buddy_id";s:7:"9105199";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:5:"czlol";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:9107901;a:8:{s:8:"buddy_id";s:7:"9107901";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"Asensio``";s:8:"standing";s:1:"1";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:9260258;a:8:{s:8:"buddy_id";s:7:"9260258";s:5:"group";s:0:"";s:8:"clan_tag";N;s:6:"status";s:1:"2";s:8:"nickname";s:9:"DansonMun";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}i:9263321;a:8:{s:8:"buddy_id";s:7:"9263321";s:5:"group";s:0:"";s:8:"clan_tag";s:4:"g00d";s:6:"status";s:1:"2";s:8:"nickname";s:9:"DansonBun";s:8:"standing";s:1:"2";s:8:"inactive";s:1:"0";s:3:"new";s:1:"1";}}}s:12:"ignored_list";a:1:{i:8527634;a:6:{i:0;a:2:{s:10:"ignored_id";s:7:"7004242";s:8:"nickname";s:6:"hajek2";}i:1;a:2:{s:10:"ignored_id";s:7:"8387298";s:8:"nickname";s:7:"yopopoi";}i:2;a:2:{s:10:"ignored_id";s:7:"8532718";s:8:"nickname";s:12:"Lv100Snorlax";}i:3;a:2:{s:10:"ignored_id";s:7:"8936508";s:8:"nickname";s:6:"Ucilok";}i:4;a:2:{s:10:"ignored_id";s:7:"9069918";s:8:"nickname";s:8:"Sexy4You";}i:5;a:2:{s:10:"ignored_id";s:7:"8796802";s:8:"nickname";s:5:"eudog";}}}s:11:"banned_list";a:1:{i:8527634;a:0:{}}s:5:"infos";a:1:{i:0;a:32:{s:10:"account_id";s:7:"8527634";s:8:"standing";s:1:"3";s:5:"level";s:1:"9";s:9:"level_exp";s:4:"5015";s:6:"discos";s:1:"0";s:15:"possible_discos";s:1:"0";s:12:"games_played";s:3:"125";s:17:"num_bot_games_won";N;s:13:"acc_pub_skill";s:8:"1500.000";s:8:"acc_wins";s:1:"0";s:10:"acc_losses";s:1:"0";s:16:"acc_games_played";s:1:"0";s:10:"acc_discos";s:1:"0";s:19:"rnk_amm_team_rating";s:8:"1640.539";s:8:"rnk_wins";s:2:"37";s:10:"rnk_losses";s:2:"12";s:16:"rnk_games_played";s:2:"49";s:10:"rnk_discos";s:1:"0";s:18:"cs_amm_team_rating";s:8:"1500.000";s:7:"cs_wins";s:1:"0";s:9:"cs_losses";s:1:"0";s:15:"cs_games_played";s:1:"0";s:9:"cs_discos";s:1:"0";s:16:"mid_games_played";s:1:"0";s:10:"mid_discos";s:1:"0";s:17:"rift_games_played";s:1:"0";s:11:"rift_discos";s:1:"0";s:6:"is_new";i:0;s:16:"cam_games_played";i:67;s:10:"cam_discos";i:0;s:19:"cam_cs_games_played";i:0;s:13:"cam_cs_discos";i:0;}}s:16:"clan_member_info";a:1:{s:5:"error";s:22:"No clan members found.";}s:9:"chatrooms";a:1:{i:0;s:0:"";}s:13:"notifications";a:10:{i:0;a:2:{s:12:"notification";s:77:"`PElN||2|notify_buddy_added|notification_generic_info||09/18 03:46 AM|1826019";s:9:"notify_id";s:7:"1826019";}i:1;a:2:{s:12:"notification";s:83:"MarshalKev`||2|notify_buddy_added|notification_generic_info||09/18 05:15 AM|1826034";s:9:"notify_id";s:7:"1826034";}i:2;a:2:{s:12:"notification";s:79:"Marckos||2|notify_buddy_added|notification_generic_info||09/29 04:05 AM|1830289";s:9:"notify_id";s:7:"1830289";}i:3;a:2:{s:12:"notification";s:81:"DansonMun||2|notify_buddy_added|notification_generic_info||03/09 03:32 AM|1893866";s:9:"notify_id";s:7:"1893866";}i:4;a:2:{s:12:"notification";s:94:"MyFistUrAnus||2|notify_buddy_requested_adder|notification_generic_info||07/23 01:31 AM|1939721";s:9:"notify_id";s:7:"1939721";}i:5;a:2:{s:12:"notification";s:84:"MyFistUrAnus||2|notify_buddy_added|notification_generic_info||07/23 01:31 AM|1939722";s:9:"notify_id";s:7:"1939722";}i:6;a:2:{s:12:"notification";s:91:"DansonBun||2|notify_buddy_requested_adder|notification_generic_info||07/24 00:42 AM|1940036";s:9:"notify_id";s:7:"1940036";}i:7;a:2:{s:12:"notification";s:84:"StevieSparkZ||2|notify_buddy_added|notification_generic_info||07/24 01:32 AM|1940041";s:9:"notify_id";s:7:"1940041";}i:8;a:2:{s:12:"notification";s:81:"DansonBun||2|notify_buddy_added|notification_generic_info||07/24 03:40 AM|1940054";s:9:"notify_id";s:7:"1940054";}i:9;a:2:{s:12:"notification";s:81:"starseed`||2|notify_buddy_added|notification_generic_info||06/11 03:49 AM|2061119";s:9:"notify_id";s:7:"2061119";}}s:11:"clan_roster";a:1:{s:5:"error";s:22:"No clan members found.";}s:10:"identities";a:6:{i:0;a:2:{i:0;s:11:"happyasthma";i:1;s:6:"782203";}i:1;a:2:{i:0;s:11:"ParallaxMid";i:1;s:7:"8527634";}i:2;a:2:{i:0;s:9:"stratkING";i:1;s:7:"8974487";}i:3;a:2:{i:0;s:11:"IHateLongQs";i:1;s:7:"9124415";}i:4;a:2:{i:0;s:8:"GameStop";i:1;s:7:"9146854";}i:5;a:2:{i:0;s:10:"LetsGoPens";i:1;s:7:"9190611";}}s:6:"points";s:4:"1315";s:8:"mmpoints";s:5:"15105";s:11:"dice_tokens";s:1:"2";s:12:"season_level";i:0;s:11:"my_upgrades";a:418:{i:0;s:15:"m.allmodes.pass";i:1;s:16:"h.AllHeroes.Hero";i:2;s:25:"aa.Hero_Pyromancer.Female";i:3;s:18:"aa.Hero_Krixi.Sexy";i:4;s:23:"aa.Hero_Magmar.Scorpion";i:5;s:21:"aa.Hero_Frosty.Female";i:6;s:15:"cc.silvershield";i:7;s:10:"t.Standard";i:8;s:13:"av.Flamboyant";i:9;s:8:"cc.white";i:10;s:18:"aa.Hero_Scar.Scary";i:11;s:22:"aa.Hero_Devourer.Clown";i:12;s:24:"aa.Hero_Succubis.Naughty";i:13;s:10:"cc.diamond";i:14;s:24:"aa.Hero_WitchSlayer.Pimp";i:15;s:20:"aa.Hero_Gauntlet.Alt";i:16;s:19:"aa.Hero_Bubbles.Alt";i:17;s:14:"ai.Icon Unlock";i:18;s:21:"aa.Hero_Gladiator.Alt";i:19;s:20:"aa.Hero_Hantumon.Alt";i:20;s:15:"ai.Default Icon";i:21;s:18:"aa.Hero_Treant.Alt";i:22;s:20:"aa.Hero_Deadwood.Alt";i:23;s:10:"cs.belgium";i:24;s:19:"cs.Nightmare Madman";i:25;s:18:"cs.Scorpion Magmus";i:26;s:18:"cs.Sexy Moon Queen";i:27;s:21:"aa.Hero_HellDemon.Alt";i:28;s:18:"aa.Hero_Empath.Alt";i:29;s:23:"aa.Hero_Hellbringer.Alt";i:30;s:19:"aa.Hero_Tempest.Alt";i:31;s:19:"aa.Hero_Rampage.Alt";i:32;s:20:"aa.Hero_Rampage.Alt2";i:33;s:17:"aa.Hero_Nomad.Alt";i:34;s:20:"aa.Hero_BabaYaga.Alt";i:35;s:17:"c.penguin_courier";i:36;s:14:"ai.custom_icon";i:37;s:22:"aa.Hero_Vindicator.Alt";i:38;s:17:"aa.Hero_Kunas.Alt";i:39;s:14:"aa.Hero_Ra.Alt";i:40;s:21:"aa.Hero_DwarfMagi.Alt";i:41;s:25:"aa.Hero_EmeraldWarden.Alt";i:42;s:19:"aa.Hero_Defiler.Alt";i:43;s:12:"cc.tanzanite";i:44;s:12:"ai.Alienware";i:45;s:25:"aa.Hero_DiseasedRider.Alt";i:46;s:13:"c.cat_courier";i:47;s:20:"aa.Hero_Accursed.Alt";i:48;s:21:"aa.Hero_Andromeda.Alt";i:49;s:21:"aa.Hero_Deadwood.Alt2";i:50;s:20:"aa.Hero_Revenant.Alt";i:51;s:17:"aa.Hero_Fairy.Alt";i:52;s:12:"av.BreakyCPK";i:53;s:18:"aa.Hero_Martyr.Alt";i:54;s:18:"aa.Hero_Hunter.Alt";i:55;s:24:"cs.Landshark Bloodhunter";i:56;s:10:"cc.emerald";i:57;s:16:"t.Dumpster_Taunt";i:58;s:9:"cs.legacy";i:59;s:18:"aa.Hero_Voodoo.Alt";i:60;s:24:"aa.Hero_Hydromancer.Alt2";i:61;s:19:"aa.Hero_WolfMan.Alt";i:62;s:24:"aa.Hero_Dreadknight.Alt2";i:63;s:21:"aa.Hero_Predator.Alt2";i:64;s:21:"aa.Hero_Succubis.Alt2";i:65;s:25:"aa.Hero_Cthulhuphant.Alt2";i:66;s:24:"aa.Hero_Electrician.Alt2";i:67;s:18:"aa.Hero_Scout.Alt2";i:68;s:7:"av.Pimp";i:69;s:14:"t.Kongor_Taunt";i:70;s:16:"c.kongor_courier";i:71;s:13:"cc.aquamarine";i:72;s:22:"aa.Hero_Andromeda.Alt2";i:73;s:18:"cs.Alien Andromeda";i:74;s:16:"c.garena_courier";i:75;s:22:"aa.Hero_Berzerker.Alt2";i:76;s:24:"aa.Hero_PuppetMaster.Alt";i:77;s:19:"aa.Hero_Gemini.Alt2";i:78;s:20:"aa.Hero_Prophet.Alt2";i:79;s:10:"cs.Club 10";i:80;s:23:"aa.Hero_Pyromancer.Alt2";i:81;s:22:"aa.Hero_Bephelgor.Alt3";i:82;s:11:"cs.Scorcher";i:83;s:17:"h.Hero_Oogie.Hero";i:84;s:18:"eap.Hero_Oogie.eap";i:85;s:17:"aa.Hero_Oogie.Alt";i:86;s:18:"eap.Hero_Oogie.Alt";i:87;s:7:"cs.Haka";i:88;s:12:"av.Seductive";i:89;s:25:"aa.Hero_Fairy.main_reskin";i:90;s:20:"cs.Unseelie Nymphora";i:91;s:16:"ai.HoN Community";i:92;s:20:"aa.Hero_Bubbles.Alt3";i:93;s:17:"cs.Futbol Bubbles";i:94;s:28:"aa.Hero_Gauntlet.main_reskin";i:95;s:17:"cs.Mummy Gauntlet";i:96;s:28:"aa.Hero_Succubis.main_reskin";i:97;s:18:"aa.Hero_Taint.Alt2";i:98;s:13:"ai.TeamPlayer";i:99;s:23:"aa.Hero_Pyromancer.Alt3";i:100;s:31:"cs.Headless Horseman Pyromancer";i:101;s:28:"aa.Hero_Jereziah.main_reskin";i:102;s:20:"cs.Crusader Jeraziah";i:103;s:27:"aa.Hero_FlintBeastwood.Alt4";i:104;s:21:"cs.Flint Spellslinger";i:105;s:23:"aa.Hero_Pestilence.Alt3";i:106;s:16:"c.turkey_courier";i:107;s:20:"aa.Hero_Maliken.Alt2";i:108;s:16:"cs.Young Maliken";i:109;s:27:"aa.Hero_ForsakenArcher.Alt3";i:110;s:24:"aa.Hero_Hammerstorm.Alt3";i:111;s:21:"aa.Hero_Rhapsody.Alt2";i:112;s:14:"cs.DJ Rap City";i:113;s:7:"av.Thai";i:114;s:21:"aa.Hero_Bushwack.Alt2";i:115;s:24:"ai.Continuum Competitive";i:116;s:18:"ai.Continuum Funny";i:117;s:20:"aa.Hero_WolfMan.Alt2";i:118;s:19:"aa.Hero_Xalynx.Alt3";i:119;s:10:"cs.Celsius";i:120;s:24:"aa.Hero_Valkyrie.Classic";i:121;s:21:"aa.Hero_Krixi.Classic";i:122;s:24:"aa.Hero_Accursed.Classic";i:123;s:22:"aa.Hero_Hunter.Classic";i:124;s:28:"aa.Hero_PuppetMaster.Classic";i:125;s:20:"aa.Hero_Hiro.Classic";i:126;s:26:"aa.Hero_SandWraith.Classic";i:127;s:20:"aa.Hero_Yogi.Classic";i:128;s:23:"aa.Hero_WolfMan.Classic";i:129;s:24:"aa.Hero_Hammerstorm.Alt4";i:130;s:14:"cs.Hammer Lord";i:131;s:21:"aa.Hero_Predator.Alt4";i:132;s:16:"cs.Rift Predator";i:133;s:20:"aa.Hero_Arachna.Alt3";i:134;s:15:"cs.Rift Arachna";i:135;s:25:"aa.Hero_Andromeda.Classic";i:136;s:24:"aa.Hero_Deadwood.Classic";i:137;s:23:"aa.Hero_Defiler.Classic";i:138;s:24:"aa.Hero_Devourer.Classic";i:139;s:22:"aa.Hero_Frosty.Classic";i:140;s:22:"aa.Hero_Treant.Classic";i:141;s:27:"aa.Hero_Legionnaire.Classic";i:142;s:23:"aa.Hero_Javaras.Classic";i:143;s:19:"ai.Runic Shift Icon";i:144;s:18:"aa.Hero_Nomad.Alt4";i:145;s:13:"cs.Elly Nomad";i:146;s:20:"aa.Hero_Prophet.Alt3";i:147;s:14:"cs.Lord Garuda";i:148;s:21:"aa.Hero_Valkyrie.Alt5";i:149;s:15:"cs.Impaler Valk";i:150;s:22:"aa.Hero_Gladiator.Alt4";i:151;s:20:"cs.Matador Gladiator";i:152;s:21:"aa.Hero_Bushwack.Alt3";i:153;s:20:"aa.Hero_Bubbles.Alt4";i:154;s:15:"cs.Rift Bubbles";i:155;s:19:"aa.Hero_Ebulus.Alt3";i:156;s:15:"cs.Rift Slither";i:157;s:21:"aa.Hero_Riftmage.Alt2";i:158;s:19:"cs.Queen Riftwalker";i:159;s:26:"aa.Hero_EmeraldWarden.Alt5";i:160;s:14:"cs.Rift Warden";i:161;s:13:"m.Super-Taunt";i:162;s:24:"aa.Hero_Bubbles.pog_skin";i:163;s:16:"cc.stardustgreen";i:164;s:23:"aa.Hero_Pyromancer.Alt4";i:165;s:20:"aa.Hero_Ravenor.Alt4";i:166;s:15:"cs.Rift Ravenor";i:167;s:20:"aa.Hero_Ravenor.Alt5";i:168;s:12:"cs.El Diablo";i:169;s:21:"t.TreasureChest_Taunt";i:170;s:19:"av.Samuel L Jackson";i:171;s:20:"aa.Hero_Maliken.Alt5";i:172;s:25:"aa.Hero_Accursed.pog_skin";i:173;s:26:"aa.Hero_Andromeda.pog_skin";i:174;s:28:"aa.Hero_Electrician.pog_skin";i:175;s:24:"aa.Hero_Armadon.pog_skin";i:176;s:25:"aa.Hero_Behemoth.pog_skin";i:177;s:26:"aa.Hero_Bephelgor.pog_skin";i:178;s:26:"aa.Hero_DwarfMagi.pog_skin";i:179;s:23:"aa.Hero_Hunter.pog_skin";i:180;s:24:"aa.Hero_Chipper.pog_skin";i:181;s:23:"cs.1st Day of Christmas";i:182;s:23:"cs.2nd Day of Christmas";i:183;s:23:"cs.3rd Day of Christmas";i:184;s:23:"cs.4th Day of Christmas";i:185;s:23:"cs.5th Day of Christmas";i:186;s:23:"cs.6th Day of Christmas";i:187;s:23:"cs.7th Day of Christmas";i:188;s:23:"cs.8th Day of Christmas";i:189;s:23:"cs.9th Day of Christmas";i:190;s:24:"cs.10th Day of Christmas";i:191;s:24:"cs.11th Day of Christmas";i:192;s:24:"cs.12th Day of Christmas";i:193;s:24:"aa.Hero_Hammerstorm.Alt6";i:194;s:15:"aa.Hero_Ra.Alt5";i:195;s:10:"cs.Acolyte";i:196;s:25:"aa.Hero_Succubis.pog_skin";i:197;s:20:"aa.Hero_Riptide.Alt2";i:198;s:25:"aa.Hero_MasterOfArms.Alt5";i:199;s:20:"aa.Hero_Rampage.Alt8";i:200;s:20:"cs.Road Rage Rampage";i:201;s:19:"aa.Hero_Empath.Alt4";i:202;s:7:"cs.Gaia";i:203;s:21:"aa.Hero_Fade.pog_skin";i:204;s:22:"aa.Hero_Krixi.pog_skin";i:205;s:34:"aa.Hero_CorruptedDisciple.pog_skin";i:206;s:18:"c.izbushka_courier";i:207;s:31:"aa.Hero_FlintBeastwood.pog_skin";i:208;s:31:"aa.Hero_ForsakenArcher.pog_skin";i:209;s:23:"aa.Hero_Zephyr.pog_skin";i:210;s:21:"aa.Hero_Prisoner.Alt5";i:211;s:13:"cs.Dark Angel";i:212;s:20:"aa.Hero_Monarch.Alt5";i:213;s:19:"cs.Luna Moth Cherub";i:214;s:22:"aa.Hero_Mumra.pog_skin";i:215;s:23:"aa.Hero_Vindicator.Alt4";i:216;s:17:"cs.Vindi the Gray";i:217;s:20:"aa.Hero_Bubbles.Alt9";i:218;s:15:"ai.Essence Link";i:219;s:13:"ai.Deflection";i:220;s:14:"ai.Thunderbolt";i:221;s:12:"ai.Get Burnt";i:222;s:13:"ai.tarot_rune";i:223;s:27:"aa.Hero_SandWraith.pog_skin";i:224;s:21:"aa.Hero_Riftmage.Alt3";i:225;s:23:"cs.Possessed Riftwalker";i:226;s:21:"aa.Hero_Rhapsody.Alt4";i:227;s:21:"aa.Hero_Devourer.Alt9";i:228;s:20:"cs.Bedsheet Devourer";i:229;s:24:"aa.Hero_Electrician.Alt5";i:230;s:12:"cs.Killawatt";i:231;s:20:"aa.Hero_Chipper.Alt4";i:232;s:10:"cs.Dredger";i:233;s:22:"aa.Hero_Scout.pog_skin";i:234;s:13:"w.cassie_ward";i:235;s:12:"ai.Present 6";i:236;s:12:"ai.Present 7";i:237;s:13:"ai.Present 10";i:238;s:13:"ai.Present 11";i:239;s:18:"aa.Hero_Scout.Alt7";i:240;s:19:"cs.Halfling Warrior";i:241;s:19:"aa.Hero_Empath.Alt5";i:242;s:18:"aa.Hero_Nomad.Alt8";i:243;s:23:"aa.Hero_Kraken.pog_skin";i:244;s:20:"aa.Hero_Maliken.Alt6";i:245;s:23:"aa.Hero_MonkeyKing.Alt7";i:246;s:21:"aa.Hero_Parallax.Alt2";i:247;s:17:"cs.High Priestess";i:248;s:20:"aa.Hero_Riptide.Alt4";i:249;s:24:"aa.Hero_Hiro.trophy_skin";i:250;s:25:"aa.Hero_PuppetMaster.Alt7";i:251;s:24:"aa.Hero_Tempest.pog_skin";i:252;s:28:"aa.Hero_Hammerstorm.pog_skin";i:253;s:21:"aa.Hero_Rhapsody.Alt6";i:254;s:12:"w.nomad_ward";i:255;s:21:"aa.Hero_Prisoner.Alt6";i:256;s:24:"aa.Hero_Maliken.pog_skin";i:257;s:30:"aa.Hero_DiseasedRider.pog_skin";i:258;s:18:"w.devo_pirate_ward";i:259;s:16:"w.rift_devo_ward";i:260;s:22:"aa.Hero_Devourer.Alt11";i:261;s:20:"cs.Keelhaul Devourer";i:262;s:19:"aa.Hero_Scout.Alt10";i:263;s:19:"cs.Adkarna Assassin";i:264;s:21:"aa.Hero_Bubbles.Alt10";i:265;s:21:"cs.Steam Mage Bubbles";i:266;s:23:"aa.Hero_Magmar.pog_skin";i:267;s:21:"aa.Hero_Succubis.Alt7";i:268;s:22:"w.valentines_2016_ward";i:269;s:24:"aa.Hero_Silhouette.Alt10";i:270;s:18:"aa.Hero_Aluna.Alt5";i:271;s:23:"aa.Hero_Bombardier.Alt8";i:272;s:23:"ai.Mastery Icon - Aluna";i:273;s:27:"ai.Mastery Icon - Andromeda";i:274;s:25:"ai.Mastery Icon - Arachna";i:275;s:28:"ai.Mastery Icon - Balphagore";i:276;s:26:"ai.Mastery Icon - Behemoth";i:277;s:29:"ai.Mastery Icon - Bloodhunter";i:278;s:28:"ai.Mastery Icon - Bombardier";i:279;s:25:"ai.Mastery Icon - Bubbles";i:280;s:36:"ai.Mastery Icon - Circe the Deceiver";i:281;s:30:"ai.Mastery Icon - Cthulhuphant";i:282;s:25:"ai.Mastery Icon - Dampeer";i:283;s:26:"ai.Mastery Icon - Deadlift";i:284;s:25:"ai.Mastery Icon - Defiler";i:285;s:33:"ai.Mastery Icon - Demented Shaman";i:286;s:26:"ai.Mastery Icon - Devourer";i:287;s:32:"ai.Mastery Icon - Drunken Master";i:288;s:29:"ai.Mastery Icon - Electrician";i:289;s:27:"ai.Mastery Icon - Geomancer";i:290;s:24:"ai.Mastery Icon - Grinex";i:291;s:29:"ai.Mastery Icon - Legionnaire";i:292;s:27:"ai.Mastery Icon - Lodestone";i:293;s:31:"ai.Mastery Icon - Lord Salforis";i:294;s:24:"ai.Mastery Icon - Magmus";i:295;s:32:"ai.Mastery Icon - Master of Arms";i:296;s:25:"ai.Mastery Icon - Monarch";i:297;s:26:"ai.Mastery Icon - Myrmidon";i:298;s:23:"ai.Mastery Icon - Nitro";i:299;s:26:"ai.Mastery Icon - Nymphora";i:300;s:23:"ai.Mastery Icon - Oogie";i:301;s:26:"ai.Mastery Icon - Parallax";i:302;s:30:"ai.Mastery Icon - Plague Rider";i:303;s:33:"ai.Mastery Icon - Pollywog Priest";i:304;s:30:"ai.Mastery Icon - Prisoner 945";i:305;s:25:"ai.Mastery Icon - Prophet";i:306;s:31:"ai.Mastery Icon - Puppet Master";i:307;s:28:"ai.Mastery Icon - Pyromancer";i:308;s:26:"ai.Mastery Icon - Revenant";i:309;s:28:"ai.Mastery Icon - Riftwalker";i:310;s:25:"ai.Mastery Icon - Salomon";i:311;s:23:"ai.Mastery Icon - Scout";i:312;s:26:"ai.Mastery Icon - Succubus";i:313;s:28:"ai.Mastery Icon - Swiftblade";i:314;s:31:"ai.Mastery Icon - The Dark Lady";i:315;s:31:"ai.Mastery Icon - The Gladiator";i:316;s:26:"ai.Mastery Icon - Torturer";i:317;s:24:"ai.Mastery Icon - Tundra";i:318;s:31:"ai.Mastery Icon - Voodoo Jester";i:319;s:30:"ai.Mastery Icon - Witch Slayer";i:320;s:21:"cs.Iron Mastery Badge";i:321;s:23:"cs.Bronze Mastery Badge";i:322;s:20:"ai.Red Water Balloon";i:323;s:23:"ai.Yellow Water Balloon";i:324;s:18:"ai.Blue Squirt Gun";i:325;s:27:"av.Ascension Announcer Pack";i:326;s:20:"aa.Hero_Magmar.Alt10";i:327;s:10:"cs.Swagmus";i:328;s:13:"ai.1 Year Vet";i:329;s:15:"ai.Beta Warrior";i:330;s:21:"aa.Hero_Riftmage.Alt5";i:331;s:18:"aa.Hero_Ichor.Alt2";i:332;s:8:"cs.Aegis";i:333;s:12:"ai.Bloodrush";i:334;s:11:"ai.Notebook";i:335;s:6:"ai.Pen";i:336;s:11:"ai.Scissors";i:337;s:24:"aa.Hero_ShadowBlade.Alt6";i:338;s:17:"cs.Angel of Death";i:339;s:16:"ai.Merrick's Key";i:340;s:23:"cs.Silver Mastery Badge";i:341;s:12:"av.MsPudding";i:342;s:20:"aa.Hero_Armadon.Alt9";i:343;s:17:"cs.God of Fortune";i:344;s:23:"cs.Trophy EmeraldWarden";i:345;s:35:"aa.Hero_EmeraldWarden.trophy_skin02";i:346;s:21:"ai.CoN_Season1_Normal";i:347;s:21:"aa.Hero_Parallax.Alt4";i:348;s:6:"cs.Ion";i:349;s:19:"aa.Hero_Rocky.Alt10";i:350;s:18:"aa.Hero_Fairy.Alt6";i:351;s:18:"cs.Trophy Nymphora";i:352;s:27:"aa.Hero_Fairy.trophy_skin02";i:353;s:21:"cs.Gold Mastery Badge";i:354;s:21:"cs.Epic Mastery Badge";i:355;s:21:"ai.CoN_Season2_Normal";i:356;s:19:"aa.Hero_Frosty.Alt7";i:357;s:19:"cs.Wildfire Glacius";i:358;s:21:"aa.Hero_Rampage.Alt14";i:359;s:15:"cs.Punk Rampage";i:360;s:22:"aa.Hero_Valkyrie.Alt12";i:361;s:12:"cs.Punk Valk";i:362;s:12:"ai.Punk Good";i:363;s:17:"ai.Punk Explosive";i:364;s:14:"ai.Punk Deadly";i:365;s:17:"cs.Trophy Cthulhu";i:366;s:34:"aa.Hero_Cthulhuphant.trophy_skin02";i:367;s:21:"ai.CoN_Season3_Normal";i:368;s:18:"aa.Hero_Krixi.Alt9";i:369;s:7:"cs.Moon";i:370;s:30:"ai.CtC Sapphire and Warchief 1";i:371;s:30:"ai.CtC Sapphire and Warchief 2";i:372;s:30:"ai.CtC Sapphire and Warchief 3";i:373;s:30:"ai.CtC Sapphire and Warchief 5";i:374;s:30:"ai.CtC Sapphire and Warchief 6";i:375;s:23:"ai.Bronze Chocolate Bar";i:376;s:23:"ai.Silver Chocolate Bar";i:377;s:17:"cs.Trophy Bubbles";i:378;s:29:"aa.Hero_Bubbles.trophy_skin02";i:379;s:18:"ai.Silver Season 5";i:380;s:18:"ai.Silver Season 6";i:381;s:16:"ai.Gold Season 4";i:382;s:19:"ai.Diamond Season 8";i:383;s:19:"ai.Diamond Season 9";i:384;s:21:"ai.Legendary Season 5";i:385;s:27:"aa.Hero_Rocky.trophy_skin01";i:386;s:27:"aa.Hero_Rocky.trophy_skin03";i:387;s:21:"ai.CoN_Season4_Normal";i:388;s:19:"cs.Pebbles Tier ONE";i:389;s:21:"cs.Pebbles Tier THREE";i:390;s:28:"aa.Hero_Empath.trophy_skin01";i:391;s:18:"cs.Empath Tier ONE";i:392;s:15:"te.CoN 6 Silver";i:393;s:21:"ai.CoN Season5 Normal";i:394;s:21:"ai.Mastery Icon - Chi";i:395;s:28:"aa.Hero_ForsakenArcher.Alt10";i:396;s:7:"cs.Yumi";i:397;s:21:"aa.Hero_Parallax.Alt6";i:398;s:11:"cs.Cruxlord";i:399;s:21:"ai.CoN_Season6_Normal";i:400;s:41:"en.pollywog_priest_alt7_ability02_upgrade";i:401;s:41:"en.pollywog_priest_alt7_ability03_upgrade";i:402;s:41:"en.pollywog_priest_alt7_ability04_upgrade";i:403;s:27:"aa.Hero_Oogie.trophy_skin02";i:404;s:16:"te.CoN 8 Diamond";i:405;s:17:"cs.Oogie Tier TWO";i:406;s:29:"aa.Hero_Chronos.trophy_skin02";i:407;s:19:"cs.Chronos Tier TWO";i:408;s:16:"te.CoN 9 Diamond";i:409;s:22:"ai.CoN Season 8 Normal";i:410;s:26:"aa.Hero_MonkeyKing.Classic";i:411;s:21:"aa.Hero_Tarot.Classic";i:412;s:19:"ai.Silver Season 10";i:413;s:20:"ai.Diamond Season 11";i:414;s:16:"ai.custom_icon:1";i:415;s:16:"ai.custom_icon:2";i:416;s:16:"ai.custom_icon:3";i:417;s:16:"ma.Mastery Boost";}s:17:"selected_upgrades";a:5:{i:0;s:10:"t.Standard";i:1;s:13:"av.Flamboyant";i:2;s:10:"cs.belgium";i:3;s:12:"ai.Alienware";i:4;s:10:"cc.emerald";}s:11:"game_tokens";i:0;s:16:"my_upgrades_info";a:366:{s:25:"aa.Hero_Pyromancer.Female";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"aa.Hero_Krixi.Sexy";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Magmar.Scorpion";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Frosty.Female";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"cc.silvershield";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:10:"t.Standard";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:13:"av.Flamboyant";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:8:"cc.white";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"aa.Hero_Scar.Scary";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Devourer.Clown";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:3:"132";}s:24:"aa.Hero_Succubis.Naughty";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"10";}s:10:"cc.diamond";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_WitchSlayer.Pimp";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"38";}s:20:"aa.Hero_Gauntlet.Alt";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Bubbles.Alt";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"24";}s:14:"ai.Icon Unlock";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Gladiator.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"38";}s:20:"aa.Hero_Hantumon.Alt";a:1:{s:4:"data";s:0:"";}s:15:"ai.Default Icon";a:2:{s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"aa.Hero_Treant.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Deadwood.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:10:"cs.belgium";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:19:"cs.Nightmare Madman";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"cs.Scorpion Magmus";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"cs.Sexy Moon Queen";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_HellDemon.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"aa.Hero_Empath.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"15";}s:23:"aa.Hero_Hellbringer.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:19:"aa.Hero_Tempest.Alt";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Rampage.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Rampage.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:17:"aa.Hero_Nomad.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_BabaYaga.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"46";}s:17:"c.penguin_courier";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:14:"ai.custom_icon";a:1:{s:4:"data";s:0:"";}s:22:"aa.Hero_Vindicator.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:17:"aa.Hero_Kunas.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"34";}s:14:"aa.Hero_Ra.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_DwarfMagi.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"14";}s:25:"aa.Hero_EmeraldWarden.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:19:"aa.Hero_Defiler.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:12:"cc.tanzanite";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:12:"ai.Alienware";a:2:{s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:25:"aa.Hero_DiseasedRider.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:1:"6";}s:13:"c.cat_courier";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Accursed.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Andromeda.Alt";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"64";}s:21:"aa.Hero_Deadwood.Alt2";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:1:"4";}s:20:"aa.Hero_Revenant.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:17:"aa.Hero_Fairy.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:12:"av.BreakyCPK";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Martyr.Alt";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Hunter.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"cs.Landshark Bloodhunter";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:10:"cc.emerald";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"t.Dumpster_Taunt";a:1:{s:4:"data";s:0:"";}s:9:"cs.legacy";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"aa.Hero_Voodoo.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Hydromancer.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:19:"aa.Hero_WolfMan.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Dreadknight.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Predator.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Succubis.Alt2";a:1:{s:4:"data";s:0:"";}s:25:"aa.Hero_Cthulhuphant.Alt2";a:1:{s:4:"data";s:0:"";}s:24:"aa.Hero_Electrician.Alt2";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:4:"1512";}s:18:"aa.Hero_Scout.Alt2";a:1:{s:4:"data";s:0:"";}s:7:"av.Pimp";a:1:{s:4:"data";s:0:"";}s:14:"t.Kongor_Taunt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"c.kongor_courier";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:13:"cc.aquamarine";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Andromeda.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"cs.Alien Andromeda";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"c.garena_courier";a:1:{s:4:"data";s:0:"";}s:22:"aa.Hero_Berzerker.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_PuppetMaster.Alt";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Gemini.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Prophet.Alt2";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:4:"1786";}s:10:"cs.Club 10";a:1:{s:4:"data";s:0:"";}s:23:"aa.Hero_Pyromancer.Alt2";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"85";}s:22:"aa.Hero_Bephelgor.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:11:"cs.Scorcher";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:17:"h.Hero_Oogie.Hero";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"eap.Hero_Oogie.eap";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:10:"1348804800";s:10:"start_time";s:10:"1346422459";}s:17:"aa.Hero_Oogie.Alt";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"68";}s:18:"eap.Hero_Oogie.Alt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:10:"1348804800";s:10:"start_time";s:10:"1346422459";}s:7:"cs.Haka";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:12:"av.Seductive";a:1:{s:4:"data";s:0:"";}s:25:"aa.Hero_Fairy.main_reskin";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"58";}s:20:"cs.Unseelie Nymphora";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"ai.HoN Community";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Bubbles.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:17:"cs.Futbol Bubbles";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:28:"aa.Hero_Gauntlet.main_reskin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:17:"cs.Mummy Gauntlet";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:28:"aa.Hero_Succubis.main_reskin";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Taint.Alt2";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"28";}s:13:"ai.TeamPlayer";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Pyromancer.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:31:"cs.Headless Horseman Pyromancer";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:28:"aa.Hero_Jereziah.main_reskin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"cs.Crusader Jeraziah";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:27:"aa.Hero_FlintBeastwood.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"cs.Flint Spellslinger";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Pestilence.Alt3";a:1:{s:4:"data";s:0:"";}s:16:"c.turkey_courier";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Maliken.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"cs.Young Maliken";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:27:"aa.Hero_ForsakenArcher.Alt3";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:1:"4";}s:24:"aa.Hero_Hammerstorm.Alt3";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Rhapsody.Alt2";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:14:"cs.DJ Rap City";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:7:"av.Thai";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Bushwack.Alt2";a:1:{s:4:"data";s:0:"";}s:24:"ai.Continuum Competitive";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"ai.Continuum Funny";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_WolfMan.Alt2";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Xalynx.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:10:"cs.Celsius";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Valkyrie.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Krixi.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Accursed.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Hunter.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:28:"aa.Hero_PuppetMaster.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Hiro.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:26:"aa.Hero_SandWraith.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Yogi.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_WolfMan.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Hammerstorm.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:14:"cs.Hammer Lord";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Predator.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"cs.Rift Predator";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Arachna.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"cs.Rift Arachna";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:25:"aa.Hero_Andromeda.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Deadwood.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Defiler.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Devourer.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Frosty.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Treant.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:27:"aa.Hero_Legionnaire.Classic";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Javaras.Classic";a:1:{s:4:"data";s:0:"";}s:19:"ai.Runic Shift Icon";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"aa.Hero_Nomad.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:13:"cs.Elly Nomad";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Prophet.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:14:"cs.Lord Garuda";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Valkyrie.Alt5";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"cs.Impaler Valk";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Gladiator.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"cs.Matador Gladiator";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Bushwack.Alt3";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Bubbles.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"cs.Rift Bubbles";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:19:"aa.Hero_Ebulus.Alt3";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"cs.Rift Slither";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Riftmage.Alt2";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"51";}s:19:"cs.Queen Riftwalker";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:26:"aa.Hero_EmeraldWarden.Alt5";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:14:"cs.Rift Warden";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:13:"m.Super-Taunt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Bubbles.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:16:"cc.stardustgreen";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Pyromancer.Alt4";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Ravenor.Alt4";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"cs.Rift Ravenor";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Ravenor.Alt5";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:12:"cs.El Diablo";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"t.TreasureChest_Taunt";a:1:{s:4:"data";s:0:"";}s:19:"av.Samuel L Jackson";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Maliken.Alt5";a:1:{s:4:"data";s:0:"";}s:25:"aa.Hero_Accursed.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:26:"aa.Hero_Andromeda.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:28:"aa.Hero_Electrician.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Armadon.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:25:"aa.Hero_Behemoth.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:26:"aa.Hero_Bephelgor.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:26:"aa.Hero_DwarfMagi.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Hunter.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Chipper.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.1st Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.2nd Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.3rd Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.4th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.5th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.6th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.7th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.8th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"cs.9th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"cs.10th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"cs.11th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"cs.12th Day of Christmas";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:24:"aa.Hero_Hammerstorm.Alt6";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:15:"aa.Hero_Ra.Alt5";a:1:{s:4:"data";s:0:"";}s:10:"cs.Acolyte";a:1:{s:4:"data";s:0:"";}s:25:"aa.Hero_Succubis.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"aa.Hero_Riptide.Alt2";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"10";}s:25:"aa.Hero_MasterOfArms.Alt5";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"29";}s:20:"aa.Hero_Rampage.Alt8";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:20:"cs.Road Rage Rampage";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:19:"aa.Hero_Empath.Alt4";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"28";}s:7:"cs.Gaia";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:21:"aa.Hero_Fade.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Krixi.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:34:"aa.Hero_CorruptedDisciple.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:18:"c.izbushka_courier";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:31:"aa.Hero_FlintBeastwood.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:31:"aa.Hero_ForsakenArcher.pog_skin";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:23:"aa.Hero_Zephyr.pog_skin";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Prisoner.Alt5";a:1:{s:4:"data";s:0:"";}s:13:"cs.Dark Angel";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Monarch.Alt5";a:5:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";s:4:"used";i:0;s:5:"score";s:2:"38";}s:19:"cs.Luna Moth Cherub";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:22:"aa.Hero_Mumra.pog_skin";a:1:{s:4:"data";s:0:"";}s:23:"aa.Hero_Vindicator.Alt4";a:1:{s:4:"data";s:0:"";}s:17:"cs.Vindi the Gray";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Bubbles.Alt9";a:1:{s:4:"data";s:0:"";}s:15:"ai.Essence Link";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:13:"ai.Deflection";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:14:"ai.Thunderbolt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:12:"ai.Get Burnt";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:13:"ai.tarot_rune";a:3:{s:4:"data";s:0:"";s:8:"end_time";s:1:"0";s:10:"start_time";s:1:"0";}s:27:"aa.Hero_SandWraith.pog_skin";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Riftmage.Alt3";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:3:"588";}s:23:"cs.Possessed Riftwalker";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Rhapsody.Alt4";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Devourer.Alt9";a:1:{s:4:"data";s:0:"";}s:20:"cs.Bedsheet Devourer";a:1:{s:4:"data";s:0:"";}s:24:"aa.Hero_Electrician.Alt5";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"23";}s:12:"cs.Killawatt";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Chipper.Alt4";a:1:{s:4:"data";s:0:"";}s:10:"cs.Dredger";a:1:{s:4:"data";s:0:"";}s:22:"aa.Hero_Scout.pog_skin";a:1:{s:4:"data";s:0:"";}s:13:"w.cassie_ward";a:1:{s:4:"data";s:0:"";}s:12:"ai.Present 6";a:1:{s:4:"data";s:0:"";}s:12:"ai.Present 7";a:1:{s:4:"data";s:0:"";}s:13:"ai.Present 10";a:1:{s:4:"data";s:0:"";}s:13:"ai.Present 11";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Scout.Alt7";a:1:{s:4:"data";s:0:"";}s:19:"cs.Halfling Warrior";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Empath.Alt5";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Nomad.Alt8";a:1:{s:4:"data";s:0:"";}s:23:"aa.Hero_Kraken.pog_skin";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Maliken.Alt6";a:1:{s:4:"data";s:0:"";}s:23:"aa.Hero_MonkeyKing.Alt7";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Parallax.Alt2";a:1:{s:4:"data";s:0:"";}s:17:"cs.High Priestess";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Riptide.Alt4";a:1:{s:4:"data";s:0:"";}s:24:"aa.Hero_Hiro.trophy_skin";a:1:{s:4:"data";s:0:"";}s:25:"aa.Hero_PuppetMaster.Alt7";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:1:"8";}s:24:"aa.Hero_Tempest.pog_skin";a:1:{s:4:"data";s:0:"";}s:28:"aa.Hero_Hammerstorm.pog_skin";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Rhapsody.Alt6";a:1:{s:4:"data";s:0:"";}s:12:"w.nomad_ward";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Prisoner.Alt6";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:3:"585";}s:24:"aa.Hero_Maliken.pog_skin";a:1:{s:4:"data";s:0:"";}s:30:"aa.Hero_DiseasedRider.pog_skin";a:1:{s:4:"data";s:0:"";}s:18:"w.devo_pirate_ward";a:1:{s:4:"data";s:0:"";}s:16:"w.rift_devo_ward";a:1:{s:4:"data";s:0:"";}s:22:"aa.Hero_Devourer.Alt11";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"28";}s:20:"cs.Keelhaul Devourer";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Scout.Alt10";a:1:{s:4:"data";s:0:"";}s:19:"cs.Adkarna Assassin";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Bubbles.Alt10";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"20";}s:21:"cs.Steam Mage Bubbles";a:1:{s:4:"data";s:0:"";}s:23:"aa.Hero_Magmar.pog_skin";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Succubis.Alt7";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"34";}s:22:"w.valentines_2016_ward";a:1:{s:4:"data";s:0:"";}s:24:"aa.Hero_Silhouette.Alt10";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Aluna.Alt5";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"15";}s:23:"aa.Hero_Bombardier.Alt8";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"39";}s:27:"ai.Mastery Icon - Geomancer";a:1:{s:4:"data";s:0:"";}s:21:"cs.Iron Mastery Badge";a:1:{s:4:"data";s:0:"";}s:23:"cs.Bronze Mastery Badge";a:1:{s:4:"data";s:0:"";}s:20:"ai.Red Water Balloon";a:1:{s:4:"data";s:0:"";}s:23:"ai.Yellow Water Balloon";a:1:{s:4:"data";s:0:"";}s:18:"ai.Blue Squirt Gun";a:1:{s:4:"data";s:0:"";}s:27:"av.Ascension Announcer Pack";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Magmar.Alt10";a:1:{s:4:"data";s:0:"";}s:10:"cs.Swagmus";a:1:{s:4:"data";s:0:"";}s:13:"ai.1 Year Vet";a:1:{s:4:"data";s:0:"";}s:15:"ai.Beta Warrior";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Riftmage.Alt5";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:3:"274";}s:18:"aa.Hero_Ichor.Alt2";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:1:"9";}s:8:"cs.Aegis";a:1:{s:4:"data";s:0:"";}s:12:"ai.Bloodrush";a:1:{s:4:"data";s:0:"";}s:11:"ai.Notebook";a:1:{s:4:"data";s:0:"";}s:6:"ai.Pen";a:1:{s:4:"data";s:0:"";}s:11:"ai.Scissors";a:1:{s:4:"data";s:0:"";}s:24:"aa.Hero_ShadowBlade.Alt6";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:2:"23";}s:17:"cs.Angel of Death";a:1:{s:4:"data";s:0:"";}s:16:"ai.Merrick's Key";a:1:{s:4:"data";s:0:"";}s:23:"cs.Silver Mastery Badge";a:1:{s:4:"data";s:0:"";}s:12:"av.MsPudding";a:1:{s:4:"data";s:0:"";}s:20:"aa.Hero_Armadon.Alt9";a:1:{s:4:"data";s:0:"";}s:17:"cs.God of Fortune";a:1:{s:4:"data";s:0:"";}s:23:"cs.Trophy EmeraldWarden";a:1:{s:4:"data";s:0:"";}s:35:"aa.Hero_EmeraldWarden.trophy_skin02";a:1:{s:4:"data";s:0:"";}s:21:"ai.CoN_Season1_Normal";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Parallax.Alt4";a:3:{s:4:"data";s:0:"";s:4:"used";i:0;s:5:"score";s:4:"4676";}s:6:"cs.Ion";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Rocky.Alt10";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Fairy.Alt6";a:1:{s:4:"data";s:0:"";}s:18:"cs.Trophy Nymphora";a:1:{s:4:"data";s:0:"";}s:27:"aa.Hero_Fairy.trophy_skin02";a:1:{s:4:"data";s:0:"";}s:21:"cs.Gold Mastery Badge";a:1:{s:4:"data";s:0:"";}s:21:"cs.Epic Mastery Badge";a:1:{s:4:"data";s:0:"";}s:21:"ai.CoN_Season2_Normal";a:1:{s:4:"data";s:0:"";}s:19:"aa.Hero_Frosty.Alt7";a:1:{s:4:"data";s:0:"";}s:19:"cs.Wildfire Glacius";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Rampage.Alt14";a:1:{s:4:"data";s:0:"";}s:15:"cs.Punk Rampage";a:1:{s:4:"data";s:0:"";}s:22:"aa.Hero_Valkyrie.Alt12";a:1:{s:4:"data";s:0:"";}s:12:"cs.Punk Valk";a:1:{s:4:"data";s:0:"";}s:12:"ai.Punk Good";a:1:{s:4:"data";s:0:"";}s:17:"ai.Punk Explosive";a:1:{s:4:"data";s:0:"";}s:14:"ai.Punk Deadly";a:1:{s:4:"data";s:0:"";}s:17:"cs.Trophy Cthulhu";a:1:{s:4:"data";s:0:"";}s:34:"aa.Hero_Cthulhuphant.trophy_skin02";a:1:{s:4:"data";s:0:"";}s:21:"ai.CoN_Season3_Normal";a:1:{s:4:"data";s:0:"";}s:18:"aa.Hero_Krixi.Alt9";a:1:{s:4:"data";s:0:"";}s:7:"cs.Moon";a:1:{s:4:"data";s:0:"";}s:30:"ai.CtC Sapphire and Warchief 1";a:1:{s:4:"data";s:0:"";}s:30:"ai.CtC Sapphire and Warchief 2";a:1:{s:4:"data";s:0:"";}s:30:"ai.CtC Sapphire and Warchief 3";a:1:{s:4:"data";s:0:"";}s:30:"ai.CtC Sapphire and Warchief 5";a:1:{s:4:"data";s:0:"";}s:30:"ai.CtC Sapphire and Warchief 6";a:1:{s:4:"data";s:0:"";}s:23:"ai.Bronze Chocolate Bar";a:1:{s:4:"data";s:0:"";}s:23:"ai.Silver Chocolate Bar";a:1:{s:4:"data";s:0:"";}s:17:"cs.Trophy Bubbles";a:1:{s:4:"data";s:0:"";}s:29:"aa.Hero_Bubbles.trophy_skin02";a:1:{s:4:"data";s:0:"";}s:18:"ai.Silver Season 5";a:1:{s:4:"data";s:0:"";}s:18:"ai.Silver Season 6";a:1:{s:4:"data";s:0:"";}s:16:"ai.Gold Season 4";a:1:{s:4:"data";s:0:"";}s:19:"ai.Diamond Season 8";a:1:{s:4:"data";s:0:"";}s:19:"ai.Diamond Season 9";a:1:{s:4:"data";s:0:"";}s:21:"ai.Legendary Season 5";a:1:{s:4:"data";s:0:"";}s:27:"aa.Hero_Rocky.trophy_skin01";a:1:{s:4:"data";s:0:"";}s:27:"aa.Hero_Rocky.trophy_skin03";a:1:{s:4:"data";s:0:"";}s:21:"ai.CoN_Season4_Normal";a:1:{s:4:"data";s:0:"";}s:19:"cs.Pebbles Tier ONE";a:1:{s:4:"data";s:0:"";}s:21:"cs.Pebbles Tier THREE";a:1:{s:4:"data";s:0:"";}s:28:"aa.Hero_Empath.trophy_skin01";a:1:{s:4:"data";s:0:"";}s:18:"cs.Empath Tier ONE";a:1:{s:4:"data";s:0:"";}s:15:"te.CoN 6 Silver";a:1:{s:4:"data";s:0:"";}s:21:"ai.CoN Season5 Normal";a:1:{s:4:"data";s:0:"";}s:21:"ai.Mastery Icon - Chi";a:1:{s:4:"data";s:0:"";}s:28:"aa.Hero_ForsakenArcher.Alt10";a:1:{s:4:"data";s:0:"";}s:7:"cs.Yumi";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Parallax.Alt6";a:1:{s:4:"data";s:0:"";}s:11:"cs.Cruxlord";a:1:{s:4:"data";s:0:"";}s:21:"ai.CoN_Season6_Normal";a:1:{s:4:"data";s:0:"";}s:41:"en.pollywog_priest_alt7_ability02_upgrade";a:1:{s:4:"data";s:0:"";}s:41:"en.pollywog_priest_alt7_ability03_upgrade";a:1:{s:4:"data";s:0:"";}s:41:"en.pollywog_priest_alt7_ability04_upgrade";a:1:{s:4:"data";s:0:"";}s:27:"aa.Hero_Oogie.trophy_skin02";a:1:{s:4:"data";s:0:"";}s:16:"te.CoN 8 Diamond";a:1:{s:4:"data";s:0:"";}s:17:"cs.Oogie Tier TWO";a:1:{s:4:"data";s:0:"";}s:29:"aa.Hero_Chronos.trophy_skin02";a:1:{s:4:"data";s:0:"";}s:19:"cs.Chronos Tier TWO";a:1:{s:4:"data";s:0:"";}s:16:"te.CoN 9 Diamond";a:1:{s:4:"data";s:0:"";}s:22:"ai.CoN Season 8 Normal";a:1:{s:4:"data";s:0:"";}s:26:"aa.Hero_MonkeyKing.Classic";a:1:{s:4:"data";s:0:"";}s:21:"aa.Hero_Tarot.Classic";a:1:{s:4:"data";s:0:"";}s:19:"ai.Silver Season 10";a:1:{s:4:"data";s:0:"";}s:20:"ai.Diamond Season 11";a:1:{s:4:"data";s:0:"";}s:16:"ma.Mastery Boost";a:3:{s:8:"quantity";s:1:"2";s:8:"discount";s:4:"1.00";s:12:"mmp_discount";s:4:"1.00";}}s:11:"creep_level";i:0;s:9:"timestamp";i:1654393519;s:14:"awards_tooltip";a:12:{s:10:"milestones";a:5:{s:11:"heroassists";a:4:{s:5:"aname";s:11:"heroassists";s:3:"exp";s:3:"100";s:2:"gc";s:1:"5";s:6:"modulo";s:3:"250";}s:9:"herokills";a:4:{s:5:"aname";s:9:"herokills";s:3:"exp";s:3:"100";s:2:"gc";s:1:"5";s:6:"modulo";s:3:"250";}s:9:"smackdown";a:4:{s:5:"aname";s:9:"smackdown";s:3:"exp";s:2:"50";s:2:"gc";s:1:"1";s:6:"modulo";s:2:"10";}s:5:"wards";a:4:{s:5:"aname";s:5:"wards";s:3:"exp";s:3:"100";s:2:"gc";s:1:"5";s:6:"modulo";s:2:"50";}s:4:"wins";a:4:{s:5:"aname";s:4:"wins";s:3:"exp";s:3:"200";s:2:"gc";s:2:"10";s:6:"modulo";s:2:"50";}}s:8:"leveling";a:3:{s:3:"2-5";i:6;s:4:"6-10";i:12;s:5:"11-15";i:18;}s:9:"bloodlust";a:2:{s:3:"exp";i:10;s:2:"gc";i:2;}s:12:"annihilation";a:4:{s:3:"exp";i:75;s:2:"gc";i:15;s:6:"tm_exp";i:25;s:5:"tm_gc";i:5;}s:8:"immortal";a:4:{s:3:"exp";i:50;s:2:"gc";i:10;s:6:"tm_exp";i:15;s:5:"tm_gc";i:3;}s:7:"victory";a:2:{s:3:"exp";i:30;s:2:"gc";i:6;}s:4:"loss";a:2:{s:3:"exp";i:10;s:2:"gc";i:2;}s:5:"disco";a:2:{s:3:"exp";i:0;s:2:"gc";i:0;}s:5:"quick";a:2:{s:3:"exp";i:0;s:2:"gc";i:2;}s:5:"first";a:2:{s:3:"exp";i:20;s:2:"gc";i:4;}s:10:"consec_win";a:2:{s:3:"exp";i:0;s:2:"gc";s:3:"2-6";}s:11:"consec_loss";a:2:{s:3:"exp";i:0;s:2:"gc";i:1;}}s:12:"quest_system";a:1:{s:5:"error";a:2:{s:12:"quest_status";i:0;s:18:"leaderboard_status";i:0;}}s:23:"campaign_current_season";s:2:"12";s:8:"mmr_rank";s:99:"1250,1275,1300,1330,1365,1400,1435,1470,1505,1540,1575,1610,1645,1685,1725,1765,1805,1850,1900,1950";s:26:"account_cloud_storage_info";b:0;s:16:"vested_threshold";i:5;i:0;b:1;}
```

This response is nearly identical to the `srpAuth` response.

It does not contain keys for `proof` or `mute_expiration`. And it adds a new key for `client_disco`.

- `client_disco`: This seems to always be `"OK"`. Its possible in some error case it returns something else but it's unclear.

##### Error

```
a:2:{s:4:"auth";s:16:"Invalid cookie.1";i:0;b:0;}
```

```
Array
(
    [auth] => Invalid cookie.1
    [0] => 
)

```

It seems like a bug that `auth` has a `.1` after the "Invalid cookie" text.
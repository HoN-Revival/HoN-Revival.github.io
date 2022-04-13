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
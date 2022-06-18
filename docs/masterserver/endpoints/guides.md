---
layout: default
title: Guide Endpoints
parent: PHP Endpoints
grand_parent: Master Server
---

# Guides

Guides can be created using the HoN website. Any private servers will need to create their own UI.

For posterity, here are images of what guides looked like on the website. There is no way to create guide in game.

![Guide webpage (viewer)](https://i.imgur.com/nABZbxN.png)

![Guide webpage (editor)](https://i.imgur.com/UA4DzCN.png)

In game the guides can be viewed in a few locations:

1. The learnitorium
2. In game, this is requested when opening up the shop.

The starting item gold for the guides is fixed at `603`.

"Premium" guides authored by `_WhatYouGot` are going to be used as seed data for any private servers, since
he has given us his permission.

## f=get_guide_list_filtered

### Request

```
f=get_guide_list_filtered&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&hero=Hero_Parallax&hosttime=5963205
```

### Response

Returns a list of 20 guides, ranked by the filtered percentage.

The ordering goes:

1. Default guide (if any is set)
2. Premium guide(s)
3. The rest ranked in order of upvote percentage.

It's unclear if/how `favorite` guides filter in, if at all.

```
a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:10:"guide_list";s:1965:"415077|05/09/21 03:18:47pm|happyasthma|happyasthma\'s legendary 90% win|is_def|not_fav|0.98|is_yours|0`438490|06/13/21 09:00:53pm|_WhatYouGot|_WhatYouGot\'s Parallax Guide|not_def|not_fav|0.97|not_yours|1`401767|12/16/15 01:56:16am|Asian00000|Midwars Parallax Guide|not_def|not_fav|1.00|not_yours|0`437349|02/05/21 08:56:18pm|_Tontuen_|_Tontuen_\'s Parallax Guide|not_def|not_fav|0.99|not_yours|0`404897|05/28/16 04:38:24am|SactoMentor|2000+MMR parallax [SactoMentor]|not_def|not_fav|0.99|not_yours|0`424541|06/21/20 04:07:52am|Zlapped|Zlapped\'s Parallax Guide|not_def|not_fav|0.99|not_yours|0`431632|05/08/19 08:28:10am|slyonez|slyonez\'s Parallax Guide|not_def|not_fav|0.98|not_yours|0`431580|10/17/20 02:46:05pm|__Paradise__|^:^cParadise ^mParallax ^oMid|not_def|not_fav|0.98|not_yours|0`405107|06/05/15 06:47:18pm|JukeGalore|Middle win guaranteed :)|not_def|not_fav|0.98|not_yours|0`404563|05/23/15 05:12:00am|BACKSLASH_0|BACKSLASH_0\'s Parallax Guide|not_def|not_fav|0.98|not_yours|0`433608|09/05/21 11:33:12pm|CtrlAltDFeat|CtrlAltDfeat\'s Parallax Guide|not_def|not_fav|0.98|not_yours|0`404461|12/11/15 03:58:51am|_The_Batman|GzLvee\'s Parallax Guide|not_def|not_fav|0.97|not_yours|0`427193|12/13/17 05:03:25am|DaZniZn|DaZniZn\'s Parallax Guide|not_def|not_fav|0.97|not_yours|0`402687|10/24/17 12:17:18pm|Aruaua|Aruaua\'s Mid Parallax Guide|not_def|not_fav|0.97|not_yours|0`429215|01/19/19 03:43:13am|JabamiYumeko|^R^:^%969PARALLAX GUIDE|not_def|not_fav|0.97|not_yours|0`405256|05/08/17 06:58:49pm|Mr_SolariOoM|_SkiZ_\'s Parallax Guide|not_def|not_fav|0.97|not_yours|0`415717|07/03/16 07:17:30am|Glax|Glax\'s Parallax Guide|not_def|not_fav|0.96|not_yours|0`406459|06/27/15 08:00:34am|I_m_Kris|I_m_Kris\'s Parallax Guide|not_def|not_fav|0.96|not_yours|0`405726|06/10/15 11:27:13pm|iMonkeyMan|iMonkeyMan\'s Parallax Guide|not_def|not_fav|0.96|not_yours|0`409112|03/09/16 07:38:32pm|RawsLy_|RawsLy_\'s Parallax the Hard-Carry Gu|not_def|not_fav|0.95|not_yours|0";s:8:"hosttime";s:7:"5963205";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [guide_list] => 415077|05/09/21 03:18:47pm|happyasthma|happyasthma\'s legendary 90% win|is_def|not_fav|0.98|is_yours|0`438490|06/13/21 09:00:53pm|_WhatYouGot|_WhatYouGot\'s Parallax Guide|not_def|not_fav|0.97|not_yours|1`401767|12/16/15 01:56:16am|Asian00000|Midwars Parallax Guide|not_def|not_fav|1.00|not_yours|0`437349|02/05/21 08:56:18pm|_Tontuen_|_Tontuen_\'s Parallax Guide|not_def|not_fav|0.99|not_yours|0`404897|05/28/16 04:38:24am|SactoMentor|2000+MMR parallax [SactoMentor]|not_def|not_fav|0.99|not_yours|0`424541|06/21/20 04:07:52am|Zlapped|Zlapped\'s Parallax Guide|not_def|not_fav|0.99|not_yours|0`431632|05/08/19 08:28:10am|slyonez|slyonez\'s Parallax Guide|not_def|not_fav|0.98|not_yours|0`431580|10/17/20 02:46:05pm|__Paradise__|^:^cParadise ^mParallax ^oMid|not_def|not_fav|0.98|not_yours|0`405107|06/05/15 06:47:18pm|JukeGalore|Middle win guaranteed :)|not_def|not_fav|0.98|not_yours|0`404563|05/23/15 05:12:00am|BACKSLASH_0|BACKSLASH_0\'s Parallax Guide|not_def|not_fav|0.98|not_yours|0`433608|09/05/21 11:33:12pm|CtrlAltDFeat|CtrlAltDfeat\'s Parallax Guide|not_def|not_fav|0.98|not_yours|0`404461|12/11/15 03:58:51am|_The_Batman|GzLvee\'s Parallax Guide|not_def|not_fav|0.97|not_yours|0`427193|12/13/17 05:03:25am|DaZniZn|DaZniZn\'s Parallax Guide|not_def|not_fav|0.97|not_yours|0`402687|10/24/17 12:17:18pm|Aruaua|Aruaua\'s Mid Parallax Guide|not_def|not_fav|0.97|not_yours|0`429215|01/19/19 03:43:13am|JabamiYumeko|^R^:^%969PARALLAX GUIDE|not_def|not_fav|0.97|not_yours|0`405256|05/08/17 06:58:49pm|Mr_SolariOoM|_SkiZ_\'s Parallax Guide|not_def|not_fav|0.97|not_yours|0`415717|07/03/16 07:17:30am|Glax|Glax\'s Parallax Guide|not_def|not_fav|0.96|not_yours|0`406459|06/27/15 08:00:34am|I_m_Kris|I_m_Kris\'s Parallax Guide|not_def|not_fav|0.96|not_yours|0`405726|06/10/15 11:27:13pm|iMonkeyMan|iMonkeyMan\'s Parallax Guide|not_def|not_fav|0.96|not_yours|0`409112|03/09/16 07:38:32pm|RawsLy_|RawsLy_\'s Parallax the Hard-Carry Gu|not_def|not_fav|0.95|not_yours|0
    [hosttime] => 5963205
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

The most important field is the `guide_list`. The guides appear to be delimited with a backtick. Within a given guide, elements are delimited with a vertical bar.

Individual guide example:

```
415077|05/09/21 03:18:47pm|happyasthma|happyasthma\'s legendary 90% win|is_def|not_fav|0.98|is_yours|0
```

0. The ID of the guide. (`415077`)
1. The second is the authored (last edited) date of the guide (`05/09/21 03:18:47pm`)
2. Is the username of the user who authored the guide. (`happyasthma`)
3. The third element is the name of the guide, limited to 36 characters. (`happyasthma\'s legendary 90% win`)
4. A textual representation of the boolean as to whether the guide is the `default` or not. Values are ONE_OF(`not_def`, `is_def`).
5. A textual representation of the boolean as to whether the guide is a `favorite` or not. Values are ONE_OF(`not_fav`, `is_fav`).
6. A decimal representation of the percentage of upvotes relative to downvotes (`0.98` or 98%)
7. A textual representation of the boolean as to whether the guide is authored by the current user or not. Values are ONE_OF(`not_yours`, `is_yours`)
8. Unknown. Not sure what this value is. Maybe for `premium`? Seems to only be `1` for `_WhatYouGot` guides. Values are ONE_OF(`0`, `1`)

## f=get_guide

Requests a specific guide for a specific user's account

### Typical

#### Request

```
f=get_guide&account=9146854&cookie=bd805dda770577426fa4ebf4b9c38b52&hero=Hero_MasterOfArms&hosttime=5772605&gid=408866
```

#### Response

```
a:22:{s:6:"errors";s:0:"";s:7:"success";i:1;s:8:"datetime";s:19:"07/14/17 07:08:35pm";s:11:"author_name";s:6:"Shades";s:13:"hero_cli_name";s:17:"Hero_MasterOfArms";s:10:"guide_name";s:20:"Best MoA guide 1800+";s:9:"hero_name";s:14:"Master Of Arms";s:7:"default";i:0;s:8:"favorite";i:0;s:6:"rating";s:4:"1.00";s:5:"thumb";s:6:"noVote";s:7:"premium";s:1:"0";s:7:"i_start";s:103:"Item_RunesOfTheBlight|Item_DuckBoots|Item_DuckBoots|Item_MinorTotem|Item_MinorTotem|Item_HealthPotion||";s:8:"i_laning";s:59:"Item_EnhancedMarchers|Item_PowerSupply|Item_Lightning1|||||";s:6:"i_core";s:113:"Item_ManaBurn1|Item_Weapon3|Item_Evasion|Item_Dawnbringer|Item_Pierce|Item_LifeSteal4|Item_Critical1|Item_Damage9";s:8:"i_luxury";s:54:"Item_Sasuke|Item_Protect|Item_Immunity|Item_Freeze||||";s:5:"abilQ";s:559:"Ability_MasterOfArms3|Ability_MasterOfArms1|Ability_MasterOfArms3|Ability_MasterOfArms2|Ability_MasterOfArms3|Ability_MasterOfArms4|Ability_MasterOfArms3|Ability_MasterOfArms2|Ability_MasterOfArms2|Ability_MasterOfArms2|Ability_MasterOfArms4|Ability_MasterOfArms1|Ability_MasterOfArms1|Ability_MasterOfArms1|Ability_AttributeBoost|Ability_MasterOfArms4|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost";s:9:"txt_intro";s:161:"Master of Arms is a carry with incredibly high attack speed. Try to play defensively early on until you get your core items, then proceed to push with your team.";s:9:"txt_guide";s:0:"";s:8:"hosttime";s:7:"5772605";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [datetime] => 07/14/17 07:08:35pm
    [author_name] => Shades
    [hero_cli_name] => Hero_MasterOfArms
    [guide_name] => Best MoA guide 1800+
    [hero_name] => Master Of Arms
    [default] => 0
    [favorite] => 0
    [rating] => 1.00
    [thumb] => noVote
    [premium] => 0
    [i_start] => Item_RunesOfTheBlight|Item_DuckBoots|Item_DuckBoots|Item_MinorTotem|Item_MinorTotem|Item_HealthPotion||
    [i_laning] => Item_EnhancedMarchers|Item_PowerSupply|Item_Lightning1|||||
    [i_core] => Item_ManaBurn1|Item_Weapon3|Item_Evasion|Item_Dawnbringer|Item_Pierce|Item_LifeSteal4|Item_Critical1|Item_Damage9
    [i_luxury] => Item_Sasuke|Item_Protect|Item_Immunity|Item_Freeze||||
    [abilQ] => Ability_MasterOfArms3|Ability_MasterOfArms1|Ability_MasterOfArms3|Ability_MasterOfArms2|Ability_MasterOfArms3|Ability_MasterOfArms4|Ability_MasterOfArms3|Ability_MasterOfArms2|Ability_MasterOfArms2|Ability_MasterOfArms2|Ability_MasterOfArms4|Ability_MasterOfArms1|Ability_MasterOfArms1|Ability_MasterOfArms1|Ability_AttributeBoost|Ability_MasterOfArms4|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost|Ability_AttributeBoost
    [txt_intro] => Master of Arms is a carry with incredibly high attack speed. Try to play defensively early on until you get your core items, then proceed to push with your team.
    [txt_guide] => 
    [hosttime] => 5772605
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

- `txt_guide` appears to never be used
- `txt_intro` is the guide description text, with a limit of 200 characters.

NOTE: The `hero_name` field is empty in some cases. It seems to be for the following fields, so it must not be used:

- `Chi`, `Adrenaline`, `Apex`, `Ichor`, `Goldenvale`, `Mimix`, `Sapphire`, `Shellshock`, `Warchief`, `King Klout`


### Error

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 110
Content-Type: application/x-www-form-urlencoded

f=get_guide&account=782203&cookie=bd29f2cfe8787828c78d2808cf00fbaf&hero=Hero_Parallax&hosttime=37995&gid=99999HTTP/1.1 200 OK
Date: Mon, 30 May 2022 06:10:44 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 123
Connection: close
Content-Type: text/plain; charset=utf-8

a:5:{s:6:"errors";s:15:"no_guides_found";s:7:"success";i:0;s:8:"hosttime";s:5:"37995";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => no_guides_found
    [success] => 0
    [hosttime] => 37995
    [vested_threshold] => 5
    [0] => 1
)
```

## f=guide_default_set

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 102
Content-Type: application/x-www-form-urlencoded

f=guide_default_set&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&hosttime=6053289&gid=437349HTTP/1.1 200 OK
Date: Fri, 15 Apr 2022 04:35:01 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 123
Connection: close
Content-Type: text/plain; charset=utf-8

a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:3:"set";i:1;s:8:"hosttime";s:7:"6053289";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [set] => 1
    [hosttime] => 6053289
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

- `set` appears to be the boolean of what value to set, even though this uses its own endpoint. `1` for true.

## f=guide_default_remove

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 105
Content-Type: application/x-www-form-urlencoded

f=guide_default_remove&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&hosttime=6085249&gid=437349HTTP/1.1 200 OK
Date: Fri, 15 Apr 2022 04:35:33 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 123
Connection: close
Content-Type: text/plain; charset=utf-8

a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:3:"set";i:0;s:8:"hosttime";s:7:"6085249";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [set] => 0
    [hosttime] => 6085249
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

- `set` appears to be the boolean of what value to set, even though this uses its own endpoint. `0` for false.

## f=guide_favorite_set

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 103
Content-Type: application/x-www-form-urlencoded

f=guide_favorite_set&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&hosttime=6142768&gid=437349HTTP/1.1 200 OK
Date: Fri, 15 Apr 2022 04:36:30 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 123
Connection: close
Content-Type: text/plain; charset=utf-8

a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:3:"set";i:1;s:8:"hosttime";s:7:"6142768";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [set] => 1
    [hosttime] => 6142768
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

- `set` appears to be the boolean of what value to set, even though this uses its own endpoint. `1` for true.

## f=guide_favorite_remove

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 106
Content-Type: application/x-www-form-urlencoded

f=guide_favorite_remove&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&hosttime=6119145&gid=437349HTTP/1.1 200 OK
Date: Fri, 15 Apr 2022 04:36:06 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 123
Connection: close
Content-Type: text/plain; charset=utf-8

a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:3:"set";i:0;s:8:"hosttime";s:7:"6119145";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [set] => 0
    [hosttime] => 6119145
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

- `set` appears to be the boolean of what value to set, even though this uses its own endpoint. `0` for false.

## f=guide_vote

The most important field here is `vote`, which is either `1` for upvote of `0` for downvote. Recasting the vote is "allowed"
but the backend must de-duplicate because it doesn't inflate the upvote percentage.

### Upvote

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 123
Content-Type: application/x-www-form-urlencoded

f=guide_vote&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&v=1&compendium_guide=415077&gid=415077&hosttime=6174392HTTP/1.1 200 OK
Date: Fri, 15 Apr 2022 04:37:02 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 124
Connection: close
Content-Type: text/plain; charset=utf-8

a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:4:"vote";i:1;s:8:"hosttime";s:7:"6174392";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [vote] => 1
    [hosttime] => 6174392
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.

### Downvote

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 123
Content-Type: application/x-www-form-urlencoded

f=guide_vote&account=782203&cookie=886da9f0da2017899f8ae06e111df51f&v=0&compendium_guide=415077&gid=415077&hosttime=6192736HTTP/1.1 200 OK
Date: Fri, 15 Apr 2022 04:37:20 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 124
Connection: close
Content-Type: text/plain; charset=utf-8

a:6:{s:6:"errors";s:0:"";s:7:"success";i:1;s:4:"vote";i:0;s:8:"hosttime";s:7:"6192736";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [errors] => 
    [success] => 1
    [vote] => 0
    [hosttime] => 6192736
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: The `hosttime` from the request must be forwarded as part of the response as well.
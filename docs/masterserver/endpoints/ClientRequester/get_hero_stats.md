---
layout: default
title: client_requester.php?f=get_hero_stats
parent: PHP Endpoints
grand_parent: Master Server
---

## client_requester.php?f=get_hero_stats

### Overview

This endpoint is used to fetch specific hero stats.

### Request

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 70
Content-Type: application/x-www-form-urlencoded

f=get_hero_stats&hosttime=5896197&nickname=happyasthma&account_id=782203&cookie=886da9f0da2017899f8ae06e111df51f&hero=Hero_Parallax
```

- `hosttime`: 
- `cookie`: Used to validate the client's session.
- `account_id`: The account ID to fetch the stats for (this should match the cookie, I believe)
- `hero`: The hero ID to look up the stats for

### Response

```
a:193:{s:7:"success";i:1;s:6:"errors";s:0:"";s:11:"rnk_ph_used";s:3:"173";s:11:"rnk_ph_wins";s:3:"118";s:13:"rnk_ph_losses";s:2:"55";s:15:"rnk_ph_concedes";s:2:"44";s:19:"rnk_ph_concedevotes";s:3:"114";s:15:"rnk_ph_buybacks";s:2:"44";s:13:"rnk_ph_discos";s:1:"1";s:13:"rnk_ph_kicked";s:1:"0";s:16:"rnk_ph_pub_skill";s:1:"0";s:16:"rnk_ph_pub_count";s:1:"0";s:22:"rnk_ph_amm_solo_rating";s:1:"0";s:21:"rnk_ph_amm_solo_count";s:1:"0";s:22:"rnk_ph_amm_team_rating";s:3:"266";s:21:"rnk_ph_amm_team_count";s:3:"173";s:16:"rnk_ph_avg_score";s:4:"0.00";s:16:"rnk_ph_herokills";s:4:"1696";s:14:"rnk_ph_herodmg";s:7:"2975972";s:14:"rnk_ph_heroexp";s:7:"1683285";s:20:"rnk_ph_herokillsgold";s:6:"877863";s:18:"rnk_ph_heroassists";s:4:"1573";s:13:"rnk_ph_deaths";s:3:"684";s:21:"rnk_ph_goldlost2death";s:6:"178256";s:16:"rnk_ph_secs_dead";s:5:"38623";s:21:"rnk_ph_teamcreepkills";s:5:"18463";s:19:"rnk_ph_teamcreepdmg";s:7:"8949923";s:19:"rnk_ph_teamcreepexp";s:7:"1351740";s:20:"rnk_ph_teamcreepgold";s:6:"765535";s:24:"rnk_ph_neutralcreepkills";s:4:"2127";s:22:"rnk_ph_neutralcreepdmg";s:7:"1586069";s:22:"rnk_ph_neutralcreepexp";s:6:"142369";s:23:"rnk_ph_neutralcreepgold";s:5:"87023";s:11:"rnk_ph_bdmg";s:6:"226177";s:14:"rnk_ph_bdmgexp";s:1:"0";s:12:"rnk_ph_razed";s:3:"161";s:12:"rnk_ph_bgold";s:6:"281435";s:13:"rnk_ph_denies";s:4:"1005";s:17:"rnk_ph_exp_denied";s:5:"40388";s:11:"rnk_ph_gold";s:7:"2231200";s:17:"rnk_ph_gold_spent";s:7:"2195734";s:10:"rnk_ph_exp";s:7:"3184527";s:14:"rnk_ph_actions";s:6:"805396";s:11:"rnk_ph_secs";s:6:"334112";s:18:"rnk_ph_consumables";s:3:"929";s:12:"rnk_ph_wards";s:2:"74";s:23:"rnk_ph_time_earning_exp";s:6:"322455";s:16:"rnk_ph_bloodlust";s:2:"44";s:17:"rnk_ph_doublekill";s:3:"268";s:17:"rnk_ph_triplekill";s:2:"57";s:15:"rnk_ph_quadkill";s:1:"9";s:19:"rnk_ph_annihilation";s:1:"2";s:10:"rnk_ph_ks3";s:3:"138";s:10:"rnk_ph_ks4";s:3:"108";s:10:"rnk_ph_ks5";s:2:"79";s:10:"rnk_ph_ks6";s:2:"66";s:10:"rnk_ph_ks7";s:2:"46";s:10:"rnk_ph_ks8";s:2:"34";s:10:"rnk_ph_ks9";s:2:"27";s:11:"rnk_ph_ks10";s:2:"24";s:11:"rnk_ph_ks15";s:1:"5";s:16:"rnk_ph_smackdown";s:1:"6";s:18:"rnk_ph_humiliation";s:1:"5";s:14:"rnk_ph_nemesis";s:4:"4222";s:18:"rnk_ph_retribution";s:1:"7";s:10:"cs_ph_used";i:0;s:10:"cs_ph_wins";i:0;s:12:"cs_ph_losses";i:0;s:14:"cs_ph_concedes";i:0;s:18:"cs_ph_concedevotes";i:0;s:14:"cs_ph_buybacks";i:0;s:12:"cs_ph_discos";i:0;s:12:"cs_ph_kicked";i:0;s:15:"cs_ph_pub_skill";i:0;s:15:"cs_ph_pub_count";i:0;s:21:"cs_ph_amm_solo_rating";i:0;s:20:"cs_ph_amm_solo_count";i:0;s:21:"cs_ph_amm_team_rating";i:0;s:20:"cs_ph_amm_team_count";i:0;s:15:"cs_ph_avg_score";i:0;s:15:"cs_ph_herokills";i:0;s:13:"cs_ph_herodmg";i:0;s:13:"cs_ph_heroexp";i:0;s:19:"cs_ph_herokillsgold";i:0;s:17:"cs_ph_heroassists";i:0;s:12:"cs_ph_deaths";i:0;s:20:"cs_ph_goldlost2death";i:0;s:15:"cs_ph_secs_dead";i:0;s:20:"cs_ph_teamcreepkills";i:0;s:18:"cs_ph_teamcreepdmg";i:0;s:18:"cs_ph_teamcreepexp";i:0;s:19:"cs_ph_teamcreepgold";i:0;s:23:"cs_ph_neutralcreepkills";i:0;s:21:"cs_ph_neutralcreepdmg";i:0;s:21:"cs_ph_neutralcreepexp";i:0;s:22:"cs_ph_neutralcreepgold";i:0;s:10:"cs_ph_bdmg";i:0;s:13:"cs_ph_bdmgexp";i:0;s:11:"cs_ph_razed";i:0;s:11:"cs_ph_bgold";i:0;s:12:"cs_ph_denies";i:0;s:16:"cs_ph_exp_denied";i:0;s:10:"cs_ph_gold";i:0;s:16:"cs_ph_gold_spent";i:0;s:9:"cs_ph_exp";i:0;s:13:"cs_ph_actions";i:0;s:10:"cs_ph_secs";i:0;s:17:"cs_ph_consumables";i:0;s:11:"cs_ph_wards";i:0;s:22:"cs_ph_time_earning_exp";i:0;s:15:"cs_ph_bloodlust";i:0;s:16:"cs_ph_doublekill";i:0;s:16:"cs_ph_triplekill";i:0;s:14:"cs_ph_quadkill";i:0;s:18:"cs_ph_annihilation";i:0;s:9:"cs_ph_ks3";i:0;s:9:"cs_ph_ks4";i:0;s:9:"cs_ph_ks5";i:0;s:9:"cs_ph_ks6";i:0;s:9:"cs_ph_ks7";i:0;s:9:"cs_ph_ks8";i:0;s:9:"cs_ph_ks9";i:0;s:10:"cs_ph_ks10";i:0;s:10:"cs_ph_ks15";i:0;s:15:"cs_ph_smackdown";i:0;s:17:"cs_ph_humiliation";i:0;s:13:"cs_ph_nemesis";i:0;s:17:"cs_ph_retribution";i:0;s:7:"ph_used";i:0;s:7:"ph_wins";i:0;s:9:"ph_losses";i:0;s:11:"ph_concedes";i:0;s:15:"ph_concedevotes";i:0;s:11:"ph_buybacks";i:0;s:9:"ph_discos";i:0;s:9:"ph_kicked";i:0;s:12:"ph_pub_skill";i:0;s:12:"ph_pub_count";i:0;s:18:"ph_amm_solo_rating";i:0;s:17:"ph_amm_solo_count";i:0;s:18:"ph_amm_team_rating";i:0;s:17:"ph_amm_team_count";i:0;s:12:"ph_avg_score";i:0;s:12:"ph_herokills";i:0;s:10:"ph_herodmg";i:0;s:10:"ph_heroexp";i:0;s:16:"ph_herokillsgold";i:0;s:14:"ph_heroassists";i:0;s:9:"ph_deaths";i:0;s:17:"ph_goldlost2death";i:0;s:12:"ph_secs_dead";i:0;s:17:"ph_teamcreepkills";i:0;s:15:"ph_teamcreepdmg";i:0;s:15:"ph_teamcreepexp";i:0;s:16:"ph_teamcreepgold";i:0;s:20:"ph_neutralcreepkills";i:0;s:18:"ph_neutralcreepdmg";i:0;s:18:"ph_neutralcreepexp";i:0;s:19:"ph_neutralcreepgold";i:0;s:7:"ph_bdmg";i:0;s:10:"ph_bdmgexp";i:0;s:8:"ph_razed";i:0;s:8:"ph_bgold";i:0;s:9:"ph_denies";i:0;s:13:"ph_exp_denied";i:0;s:7:"ph_gold";i:0;s:13:"ph_gold_spent";i:0;s:6:"ph_exp";i:0;s:10:"ph_actions";i:0;s:7:"ph_secs";i:0;s:14:"ph_consumables";i:0;s:8:"ph_wards";i:0;s:19:"ph_time_earning_exp";i:0;s:12:"ph_bloodlust";i:0;s:13:"ph_doublekill";i:0;s:13:"ph_triplekill";i:0;s:11:"ph_quadkill";i:0;s:15:"ph_annihilation";i:0;s:6:"ph_ks3";i:0;s:6:"ph_ks4";i:0;s:6:"ph_ks5";i:0;s:6:"ph_ks6";i:0;s:6:"ph_ks7";i:0;s:6:"ph_ks8";i:0;s:6:"ph_ks9";i:0;s:7:"ph_ks10";i:0;s:7:"ph_ks15";i:0;s:12:"ph_smackdown";i:0;s:14:"ph_humiliation";i:0;s:10:"ph_nemesis";i:0;s:14:"ph_retribution";i:0;s:16:"vested_threshold";i:5;i:0;b:1;}
```

Formatted response:

```
Array
(
    [success] => 1
    [errors] => 
    [rnk_ph_used] => 173
    [rnk_ph_wins] => 118
    [rnk_ph_losses] => 55
    [rnk_ph_concedes] => 44
    [rnk_ph_concedevotes] => 114
    [rnk_ph_buybacks] => 44
    [rnk_ph_discos] => 1
    [rnk_ph_kicked] => 0
    [rnk_ph_pub_skill] => 0
    [rnk_ph_pub_count] => 0
    [rnk_ph_amm_solo_rating] => 0
    [rnk_ph_amm_solo_count] => 0
    [rnk_ph_amm_team_rating] => 266
    [rnk_ph_amm_team_count] => 173
    [rnk_ph_avg_score] => 0.00
    [rnk_ph_herokills] => 1696
    [rnk_ph_herodmg] => 2975972
    [rnk_ph_heroexp] => 1683285
    [rnk_ph_herokillsgold] => 877863
    [rnk_ph_heroassists] => 1573
    [rnk_ph_deaths] => 684
    [rnk_ph_goldlost2death] => 178256
    [rnk_ph_secs_dead] => 38623
    [rnk_ph_teamcreepkills] => 18463
    [rnk_ph_teamcreepdmg] => 8949923
    [rnk_ph_teamcreepexp] => 1351740
    [rnk_ph_teamcreepgold] => 765535
    [rnk_ph_neutralcreepkills] => 2127
    [rnk_ph_neutralcreepdmg] => 1586069
    [rnk_ph_neutralcreepexp] => 142369
    [rnk_ph_neutralcreepgold] => 87023
    [rnk_ph_bdmg] => 226177
    [rnk_ph_bdmgexp] => 0
    [rnk_ph_razed] => 161
    [rnk_ph_bgold] => 281435
    [rnk_ph_denies] => 1005
    [rnk_ph_exp_denied] => 40388
    [rnk_ph_gold] => 2231200
    [rnk_ph_gold_spent] => 2195734
    [rnk_ph_exp] => 3184527
    [rnk_ph_actions] => 805396
    [rnk_ph_secs] => 334112
    [rnk_ph_consumables] => 929
    [rnk_ph_wards] => 74
    [rnk_ph_time_earning_exp] => 322455
    [rnk_ph_bloodlust] => 44
    [rnk_ph_doublekill] => 268
    [rnk_ph_triplekill] => 57
    [rnk_ph_quadkill] => 9
    [rnk_ph_annihilation] => 2
    [rnk_ph_ks3] => 138
    [rnk_ph_ks4] => 108
    [rnk_ph_ks5] => 79
    [rnk_ph_ks6] => 66
    [rnk_ph_ks7] => 46
    [rnk_ph_ks8] => 34
    [rnk_ph_ks9] => 27
    [rnk_ph_ks10] => 24
    [rnk_ph_ks15] => 5
    [rnk_ph_smackdown] => 6
    [rnk_ph_humiliation] => 5
    [rnk_ph_nemesis] => 4222
    [rnk_ph_retribution] => 7
    [cs_ph_used] => 0
    [cs_ph_wins] => 0
    [cs_ph_losses] => 0
    [cs_ph_concedes] => 0
    [cs_ph_concedevotes] => 0
    [cs_ph_buybacks] => 0
    [cs_ph_discos] => 0
    [cs_ph_kicked] => 0
    [cs_ph_pub_skill] => 0
    [cs_ph_pub_count] => 0
    [cs_ph_amm_solo_rating] => 0
    [cs_ph_amm_solo_count] => 0
    [cs_ph_amm_team_rating] => 0
    [cs_ph_amm_team_count] => 0
    [cs_ph_avg_score] => 0
    [cs_ph_herokills] => 0
    [cs_ph_herodmg] => 0
    [cs_ph_heroexp] => 0
    [cs_ph_herokillsgold] => 0
    [cs_ph_heroassists] => 0
    [cs_ph_deaths] => 0
    [cs_ph_goldlost2death] => 0
    [cs_ph_secs_dead] => 0
    [cs_ph_teamcreepkills] => 0
    [cs_ph_teamcreepdmg] => 0
    [cs_ph_teamcreepexp] => 0
    [cs_ph_teamcreepgold] => 0
    [cs_ph_neutralcreepkills] => 0
    [cs_ph_neutralcreepdmg] => 0
    [cs_ph_neutralcreepexp] => 0
    [cs_ph_neutralcreepgold] => 0
    [cs_ph_bdmg] => 0
    [cs_ph_bdmgexp] => 0
    [cs_ph_razed] => 0
    [cs_ph_bgold] => 0
    [cs_ph_denies] => 0
    [cs_ph_exp_denied] => 0
    [cs_ph_gold] => 0
    [cs_ph_gold_spent] => 0
    [cs_ph_exp] => 0
    [cs_ph_actions] => 0
    [cs_ph_secs] => 0
    [cs_ph_consumables] => 0
    [cs_ph_wards] => 0
    [cs_ph_time_earning_exp] => 0
    [cs_ph_bloodlust] => 0
    [cs_ph_doublekill] => 0
    [cs_ph_triplekill] => 0
    [cs_ph_quadkill] => 0
    [cs_ph_annihilation] => 0
    [cs_ph_ks3] => 0
    [cs_ph_ks4] => 0
    [cs_ph_ks5] => 0
    [cs_ph_ks6] => 0
    [cs_ph_ks7] => 0
    [cs_ph_ks8] => 0
    [cs_ph_ks9] => 0
    [cs_ph_ks10] => 0
    [cs_ph_ks15] => 0
    [cs_ph_smackdown] => 0
    [cs_ph_humiliation] => 0
    [cs_ph_nemesis] => 0
    [cs_ph_retribution] => 0
    [ph_used] => 0
    [ph_wins] => 0
    [ph_losses] => 0
    [ph_concedes] => 0
    [ph_concedevotes] => 0
    [ph_buybacks] => 0
    [ph_discos] => 0
    [ph_kicked] => 0
    [ph_pub_skill] => 0
    [ph_pub_count] => 0
    [ph_amm_solo_rating] => 0
    [ph_amm_solo_count] => 0
    [ph_amm_team_rating] => 0
    [ph_amm_team_count] => 0
    [ph_avg_score] => 0
    [ph_herokills] => 0
    [ph_herodmg] => 0
    [ph_heroexp] => 0
    [ph_herokillsgold] => 0
    [ph_heroassists] => 0
    [ph_deaths] => 0
    [ph_goldlost2death] => 0
    [ph_secs_dead] => 0
    [ph_teamcreepkills] => 0
    [ph_teamcreepdmg] => 0
    [ph_teamcreepexp] => 0
    [ph_teamcreepgold] => 0
    [ph_neutralcreepkills] => 0
    [ph_neutralcreepdmg] => 0
    [ph_neutralcreepexp] => 0
    [ph_neutralcreepgold] => 0
    [ph_bdmg] => 0
    [ph_bdmgexp] => 0
    [ph_razed] => 0
    [ph_bgold] => 0
    [ph_denies] => 0
    [ph_exp_denied] => 0
    [ph_gold] => 0
    [ph_gold_spent] => 0
    [ph_exp] => 0
    [ph_actions] => 0
    [ph_secs] => 0
    [ph_consumables] => 0
    [ph_wards] => 0
    [ph_time_earning_exp] => 0
    [ph_bloodlust] => 0
    [ph_doublekill] => 0
    [ph_triplekill] => 0
    [ph_quadkill] => 0
    [ph_annihilation] => 0
    [ph_ks3] => 0
    [ph_ks4] => 0
    [ph_ks5] => 0
    [ph_ks6] => 0
    [ph_ks7] => 0
    [ph_ks8] => 0
    [ph_ks9] => 0
    [ph_ks10] => 0
    [ph_ks15] => 0
    [ph_smackdown] => 0
    [ph_humiliation] => 0
    [ph_nemesis] => 0
    [ph_retribution] => 0
    [vested_threshold] => 5
    [0] => 1
)
```

- `success`: `1` if success, otherwise empty
- `errors`: Unclear, as I don't have a capture. It's empty if success. Otherwise it probably contains an error string or something?
- `rnk_ph_used`: 
- `rnk_ph_wins`: 
- `rnk_ph_losses`: 
- `rnk_ph_concedes`: 
- `rnk_ph_concedevotes`: 
- `rnk_ph_buybacks`: 
- `rnk_ph_discos`: 
- `rnk_ph_kicked`: 
- `rnk_ph_pub_skill`: 
- `rnk_ph_pub_count`: 
- `rnk_ph_amm_solo_rating`: 
- `rnk_ph_amm_solo_count`: 
- `rnk_ph_amm_team_rating`: 
- `rnk_ph_amm_team_count`: 
- `rnk_ph_avg_score`: 
- `rnk_ph_herokills`: 
- `rnk_ph_herodmg`: 
- `rnk_ph_heroexp`: 
- `rnk_ph_herokillsgold`: 
- `rnk_ph_heroassists`: 
- `rnk_ph_deaths`: 
- `rnk_ph_goldlost2death`: 
- `rnk_ph_secs_dead`: 
- `rnk_ph_teamcreepkills`: 
- `rnk_ph_teamcreepdmg`: 
- `rnk_ph_teamcreepexp`: 
- `rnk_ph_teamcreepgold`: 
- `rnk_ph_neutralcreepkills`: 
- `rnk_ph_neutralcreepdmg`: 
- `rnk_ph_neutralcreepexp`: 
- `rnk_ph_neutralcreepgold`: 
- `rnk_ph_bdmg`: 
- `rnk_ph_bdmgexp`: 
- `rnk_ph_razed`: 
- `rnk_ph_bgold`: 
- `rnk_ph_denies`: 
- `rnk_ph_exp_denied`: 
- `rnk_ph_gold`: 
- `rnk_ph_gold_spent`: 
- `rnk_ph_exp`: 
- `rnk_ph_actions`: 
- `rnk_ph_secs`: 
- `rnk_ph_consumables`: 
- `rnk_ph_wards`: 
- `rnk_ph_time_earning_exp`: 
- `rnk_ph_bloodlust`: 
- `rnk_ph_doublekill`: 
- `rnk_ph_triplekill`: 
- `rnk_ph_quadkill`: 
- `rnk_ph_annihilation`: 
- `rnk_ph_ks3`: 
- `rnk_ph_ks4`: 
- `rnk_ph_ks5`: 
- `rnk_ph_ks6`: 
- `rnk_ph_ks7`: 
- `rnk_ph_ks8`: 
- `rnk_ph_ks9`: 
- `rnk_ph_ks10`: 
- `rnk_ph_ks15`: 
- `rnk_ph_smackdown`: 
- `rnk_ph_humiliation`: 
- `rnk_ph_nemesis`: 
- `rnk_ph_retribution`: 
- `cs_ph_used`: 
- `cs_ph_wins`: 
- `cs_ph_losses`: 
- `cs_ph_concedes`: 
- `cs_ph_concedevotes`: 
- `cs_ph_buybacks`: 
- `cs_ph_discos`: 
- `cs_ph_kicked`: 
- `cs_ph_pub_skill`: 
- `cs_ph_pub_count`: 
- `cs_ph_amm_solo_rating`: 
- `cs_ph_amm_solo_count`: 
- `cs_ph_amm_team_rating`: 
- `cs_ph_amm_team_count`: 
- `cs_ph_avg_score`: 
- `cs_ph_herokills`: 
- `cs_ph_herodmg`: 
- `cs_ph_heroexp`: 
- `cs_ph_herokillsgold`: 
- `cs_ph_heroassists`: 
- `cs_ph_deaths`: 
- `cs_ph_goldlost2death`: 
- `cs_ph_secs_dead`: 
- `cs_ph_teamcreepkills`: 
- `cs_ph_teamcreepdmg`: 
- `cs_ph_teamcreepexp`: 
- `cs_ph_teamcreepgold`: 
- `cs_ph_neutralcreepkills`: 
- `cs_ph_neutralcreepdmg`: 
- `cs_ph_neutralcreepexp`: 
- `cs_ph_neutralcreepgold`: 
- `cs_ph_bdmg`: 
- `cs_ph_bdmgexp`: 
- `cs_ph_razed`: 
- `cs_ph_bgold`: 
- `cs_ph_denies`: 
- `cs_ph_exp_denied`: 
- `cs_ph_gold`: 
- `cs_ph_gold_spent`: 
- `cs_ph_exp`: 
- `cs_ph_actions`: 
- `cs_ph_secs`: 
- `cs_ph_consumables`: 
- `cs_ph_wards`: 
- `cs_ph_time_earning_exp`: 
- `cs_ph_bloodlust`: 
- `cs_ph_doublekill`: 
- `cs_ph_triplekill`: 
- `cs_ph_quadkill`: 
- `cs_ph_annihilation`: 
- `cs_ph_ks3`: 
- `cs_ph_ks4`: 
- `cs_ph_ks5`: 
- `cs_ph_ks6`: 
- `cs_ph_ks7`: 
- `cs_ph_ks8`: 
- `cs_ph_ks9`: 
- `cs_ph_ks10`: 
- `cs_ph_ks15`: 
- `cs_ph_smackdown`: 
- `cs_ph_humiliation`: 
- `cs_ph_nemesis`: 
- `cs_ph_retribution`: 
- `ph_used`: 
- `ph_wins`: 
- `ph_losses`: 
- `ph_concedes`: 
- `ph_concedevotes`: 
- `ph_buybacks`: 
- `ph_discos`: 
- `ph_kicked`: 
- `ph_pub_skill`: 
- `ph_pub_count`: 
- `ph_amm_solo_rating`: 
- `ph_amm_solo_count`: 
- `ph_amm_team_rating`: 
- `ph_amm_team_count`: 
- `ph_avg_score`: 
- `ph_herokills`: 
- `ph_herodmg`: 
- `ph_heroexp`: 
- `ph_herokillsgold`: 
- `ph_heroassists`: 
- `ph_deaths`: 
- `ph_goldlost2death`: 
- `ph_secs_dead`: 
- `ph_teamcreepkills`: 
- `ph_teamcreepdmg`: 
- `ph_teamcreepexp`: 
- `ph_teamcreepgold`: 
- `ph_neutralcreepkills`: 
- `ph_neutralcreepdmg`: 
- `ph_neutralcreepexp`: 
- `ph_neutralcreepgold`: 
- `ph_bdmg`: 
- `ph_bdmgexp`: 
- `ph_razed`: 
- `ph_bgold`: 
- `ph_denies`: 
- `ph_exp_denied`: 
- `ph_gold`: 
- `ph_gold_spent`: 
- `ph_exp`: 
- `ph_actions`: 
- `ph_secs`: 
- `ph_consumables`: 
- `ph_wards`: 
- `ph_time_earning_exp`: 
- `ph_bloodlust`: 
- `ph_doublekill`: 
- `ph_triplekill`: 
- `ph_quadkill`: 
- `ph_annihilation`: 
- `ph_ks3`: 
- `ph_ks4`: 
- `ph_ks5`: 
- `ph_ks6`: 
- `ph_ks7`: 
- `ph_ks8`: 
- `ph_ks9`: 
- `ph_ks10`: 
- `ph_ks15`: 
- `ph_smackdown`: 
- `ph_humiliation`: 
- `ph_nemesis`: 
- `ph_retribution`: 
- `vested_threshold`: Unknown but always `5`
- `0`: Unkown but always `1` on sucess or `0` on error`.
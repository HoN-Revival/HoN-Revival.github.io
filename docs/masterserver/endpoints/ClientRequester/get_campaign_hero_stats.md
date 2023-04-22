---
layout: default
title: client_requester.php?f=get_campaign_hero_stats
parent: PHP Endpoints
grand_parent: Master Server
---

## client_requester.php?f=get_campaign_hero_stats

### Overview

This endpoint is used to fetch specific hero stats for "campaign" but I'm not sure
what that is exactly.

NOTE: It's requested twice. Once for casual and once for non-casual.

### Request

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 70
Content-Type: application/x-www-form-urlencoded

f=get_campaign_hero_stats&cookie=886da9f0da2017899f8ae06e111df51f&nickname=happyasthma&hero_name=Hero_Parallax&is_casual=0
```

- `cookie`: Used to validate the client's session.
- `nickname`: The account to fetch the stats for.
- `hero`: The hero ID to look up the stats for.
- `is_casual`: A boolean determining if it should fetch casual stats or not. (It is requested twice, once for each state).

### Response

```
a:68:{s:6:"season";s:2:"12";s:10:"account_id";s:6:"782203";s:7:"hero_id";s:3:"243";s:11:"cam_ph_used";s:1:"4";s:11:"cam_ph_wins";s:1:"2";s:13:"cam_ph_losses";s:1:"2";s:15:"cam_ph_concedes";s:1:"2";s:19:"cam_ph_concedevotes";s:1:"0";s:15:"cam_ph_buybacks";s:1:"2";s:13:"cam_ph_discos";s:1:"0";s:13:"cam_ph_kicked";s:1:"0";s:16:"cam_ph_pub_skill";s:1:"0";s:16:"cam_ph_pub_count";s:1:"0";s:22:"cam_ph_amm_solo_rating";s:1:"0";s:21:"cam_ph_amm_solo_count";s:1:"0";s:22:"cam_ph_amm_team_rating";s:1:"1";s:21:"cam_ph_amm_team_count";s:1:"4";s:16:"cam_ph_avg_score";s:4:"0.00";s:16:"cam_ph_herokills";s:2:"50";s:14:"cam_ph_herodmg";s:5:"67625";s:14:"cam_ph_heroexp";s:5:"39766";s:20:"cam_ph_herokillsgold";s:5:"16116";s:18:"cam_ph_heroassists";s:2:"28";s:13:"cam_ph_deaths";s:2:"20";s:21:"cam_ph_goldlost2death";s:4:"7356";s:16:"cam_ph_secs_dead";s:3:"847";s:21:"cam_ph_teamcreepkills";s:3:"576";s:19:"cam_ph_teamcreepdmg";s:6:"298802";s:19:"cam_ph_teamcreepexp";s:5:"38499";s:20:"cam_ph_teamcreepgold";s:5:"25247";s:24:"cam_ph_neutralcreepkills";s:2:"31";s:22:"cam_ph_neutralcreepdmg";s:5:"23504";s:22:"cam_ph_neutralcreepexp";s:4:"2132";s:23:"cam_ph_neutralcreepgold";s:4:"1163";s:11:"cam_ph_bdmg";s:4:"7630";s:14:"cam_ph_bdmgexp";s:1:"0";s:12:"cam_ph_razed";s:2:"11";s:12:"cam_ph_bgold";s:4:"9865";s:13:"cam_ph_denies";s:1:"9";s:17:"cam_ph_exp_denied";s:3:"348";s:11:"cam_ph_gold";s:5:"55248";s:17:"cam_ph_gold_spent";s:5:"56956";s:10:"cam_ph_exp";s:5:"80681";s:14:"cam_ph_actions";s:5:"29114";s:11:"cam_ph_secs";s:4:"8577";s:18:"cam_ph_consumables";s:2:"43";s:12:"cam_ph_wards";s:1:"1";s:23:"cam_ph_time_earning_exp";s:4:"8577";s:16:"cam_ph_bloodlust";s:1:"0";s:17:"cam_ph_doublekill";s:1:"6";s:17:"cam_ph_triplekill";s:1:"3";s:15:"cam_ph_quadkill";s:1:"0";s:19:"cam_ph_annihilation";s:1:"0";s:10:"cam_ph_ks3";s:1:"4";s:10:"cam_ph_ks4";s:1:"3";s:10:"cam_ph_ks5";s:1:"2";s:10:"cam_ph_ks6";s:1:"2";s:10:"cam_ph_ks7";s:1:"1";s:10:"cam_ph_ks8";s:1:"1";s:10:"cam_ph_ks9";s:1:"1";s:11:"cam_ph_ks10";s:1:"1";s:11:"cam_ph_ks15";s:1:"0";s:16:"cam_ph_smackdown";s:1:"0";s:18:"cam_ph_humiliation";s:1:"0";s:14:"cam_ph_nemesis";s:2:"61";s:18:"cam_ph_retribution";s:1:"0";s:16:"vested_threshold";i:5;i:0;b:1;}
```

Formatted response:

```
Array
(
    [season] => 12
    [account_id] => 782203
    [hero_id] => 243
    [cam_ph_used] => 4
    [cam_ph_wins] => 2
    [cam_ph_losses] => 2
    [cam_ph_concedes] => 2
    [cam_ph_concedevotes] => 0
    [cam_ph_buybacks] => 2
    [cam_ph_discos] => 0
    [cam_ph_kicked] => 0
    [cam_ph_pub_skill] => 0
    [cam_ph_pub_count] => 0
    [cam_ph_amm_solo_rating] => 0
    [cam_ph_amm_solo_count] => 0
    [cam_ph_amm_team_rating] => 1
    [cam_ph_amm_team_count] => 4
    [cam_ph_avg_score] => 0.00
    [cam_ph_herokills] => 50
    [cam_ph_herodmg] => 67625
    [cam_ph_heroexp] => 39766
    [cam_ph_herokillsgold] => 16116
    [cam_ph_heroassists] => 28
    [cam_ph_deaths] => 20
    [cam_ph_goldlost2death] => 7356
    [cam_ph_secs_dead] => 847
    [cam_ph_teamcreepkills] => 576
    [cam_ph_teamcreepdmg] => 298802
    [cam_ph_teamcreepexp] => 38499
    [cam_ph_teamcreepgold] => 25247
    [cam_ph_neutralcreepkills] => 31
    [cam_ph_neutralcreepdmg] => 23504
    [cam_ph_neutralcreepexp] => 2132
    [cam_ph_neutralcreepgold] => 1163
    [cam_ph_bdmg] => 7630
    [cam_ph_bdmgexp] => 0
    [cam_ph_razed] => 11
    [cam_ph_bgold] => 9865
    [cam_ph_denies] => 9
    [cam_ph_exp_denied] => 348
    [cam_ph_gold] => 55248
    [cam_ph_gold_spent] => 56956
    [cam_ph_exp] => 80681
    [cam_ph_actions] => 29114
    [cam_ph_secs] => 8577
    [cam_ph_consumables] => 43
    [cam_ph_wards] => 1
    [cam_ph_time_earning_exp] => 8577
    [cam_ph_bloodlust] => 0
    [cam_ph_doublekill] => 6
    [cam_ph_triplekill] => 3
    [cam_ph_quadkill] => 0
    [cam_ph_annihilation] => 0
    [cam_ph_ks3] => 4
    [cam_ph_ks4] => 3
    [cam_ph_ks5] => 2
    [cam_ph_ks6] => 2
    [cam_ph_ks7] => 1
    [cam_ph_ks8] => 1
    [cam_ph_ks9] => 1
    [cam_ph_ks10] => 1
    [cam_ph_ks15] => 0
    [cam_ph_smackdown] => 0
    [cam_ph_humiliation] => 0
    [cam_ph_nemesis] => 61
    [cam_ph_retribution] => 0
    [vested_threshold] => 5
    [0] => 1
)
```

NOTE: My casual one was returning nothing because there was no casual seasons on NA. Maybe on Garena?

```
a:2:{s:16:"vested_threshold";i:5;i:0;b:1;}
```

- `season`: The current season number.
- `account_id`: The account ID corresponding to the stats that were fetched.
- `hero_id`:  The ID of the hero whose stats were fetched.
- `cam_ph_used`: 
- `cam_ph_wins`: 
- `cam_ph_losses`: 
- `cam_ph_concedes`: 
- `cam_ph_concedevotes`: 
- `cam_ph_buybacks`: 
- `cam_ph_discos`: 
- `cam_ph_kicked`: 
- `cam_ph_pub_skill`: 
- `cam_ph_pub_count`: 
- `cam_ph_amm_solo_rating`: 
- `cam_ph_amm_solo_count`: 
- `cam_ph_amm_team_rating`: 
- `cam_ph_amm_team_count`: 
- `cam_ph_avg_score`: 
- `cam_ph_herokills`: 
- `cam_ph_herodmg`: 
- `cam_ph_heroexp`: 
- `cam_ph_herokillsgold`: 
- `cam_ph_heroassists`: 
- `cam_ph_deaths`: 
- `cam_ph_goldlost2death`: 
- `cam_ph_secs_dead`: 
- `cam_ph_teamcreepkills`: 
- `cam_ph_teamcreepdmg`: 
- `cam_ph_teamcreepexp`: 
- `cam_ph_teamcreepgold`: 
- `cam_ph_neutralcreepkills`: 
- `cam_ph_neutralcreepdmg`: 
- `cam_ph_neutralcreepexp`: 
- `cam_ph_neutralcreepgold`: 
- `cam_ph_bdmg`: 
- `cam_ph_bdmgexp`: 
- `cam_ph_razed`: 
- `cam_ph_bgold`: 
- `cam_ph_denies`: 
- `cam_ph_exp_denied`: 
- `cam_ph_gold`: 
- `cam_ph_gold_spent`: 
- `cam_ph_exp`: 
- `cam_ph_actions`: 
- `cam_ph_secs`: 
- `cam_ph_consumables`: 
- `cam_ph_wards`: 
- `cam_ph_time_earning_exp`: 
- `cam_ph_bloodlust`: 
- `cam_ph_doublekill`: 
- `cam_ph_triplekill`: 
- `cam_ph_quadkill`: 
- `cam_ph_annihilation`: 
- `cam_ph_ks3`: 
- `cam_ph_ks4`: 
- `cam_ph_ks5`: 
- `cam_ph_ks6`: 
- `cam_ph_ks7`: 
- `cam_ph_ks8`: 
- `cam_ph_ks9`: 
- `cam_ph_ks10`: 
- `cam_ph_ks15`: 
- `cam_ph_smackdown`: 
- `cam_ph_humiliation`: 
- `cam_ph_nemesis`: 
- `cam_ph_retribution`: 
- `vested_threshold`: Unknown but always `5`
- `0`: Unkown but always `1` on sucess or `0` on error`.
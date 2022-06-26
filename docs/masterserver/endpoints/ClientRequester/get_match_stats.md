---
layout: default
title: client_requester.php?f=get_match_stats
parent: PHP Endpoints
grand_parent: Master Server
---

# get_match_stats

## Request

```
POST /client_requester.php?f=get_match_stats HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 58
Content-Type: application/x-www-form-urlencoded

match_id=163305199&cookie=479f0e0ae3e7785e9d1550c184814fee
```

- `match_id`: The ID for the match_id
- `cookie`: The authentication cookie for the user's session

## Response

```
a:20:{s:6:"points";s:4:"1570";s:8:"mmpoints";s:5:"12859";s:11:"dice_tokens";s:1:"2";s:12:"season_level";i:0;s:7:"slot_id";s:1:"3";s:11:"my_upgrades";a:3:{i:0;s:15:"m.allmodes.pass";i:1;s:16:"h.AllHeroes.Hero";i:2;s:13:"m.Super-Taunt";}s:17:"selected_upgrades";a:3:{i:0;s:16:"ai.custom_icon:3";i:1;s:12:"cc.tanzanite";i:2;s:16:"ai.custom_icon:3";}s:11:"game_tokens";i:0;s:16:"my_upgrades_info";a:0:{}s:11:"creep_level";i:0;s:9:"timestamp";i:1650180476;s:10:"match_summ";a:1:{i:163305199;a:79:{s:8:"match_id";s:9:"163305199";s:9:"server_id";s:7:"9440663";s:3:"map";s:8:"caldavar";s:11:"map_version";s:5:"0.0.0";s:11:"time_played";s:4:"2867";s:9:"file_host";s:28:"replaydl.heroesofnewerth.com";s:9:"file_size";s:1:"0";s:9:"file_name";s:29:"~/replays/163305199.honreplay";s:7:"c_state";s:1:"5";s:7:"version";s:8:"4.10.1.0";s:6:"avgpsr";s:1:"0";s:4:"date";s:9:"4/17/2022";s:4:"time";s:11:"07:48:41 AM";s:5:"mname";s:20:"TMM Match #163305199";s:5:"class";s:2:"11";s:7:"private";s:1:"1";s:2:"nm";s:1:"0";s:2:"sd";s:1:"0";s:2:"rd";s:1:"0";s:2:"dm";s:1:"0";s:2:"bd";s:1:"0";s:2:"bp";s:1:"0";s:2:"ar";s:1:"0";s:2:"cd";s:1:"0";s:2:"cm";s:1:"0";s:2:"lp";s:1:"0";s:2:"bb";s:1:"0";s:2:"bm";s:1:"0";s:2:"km";s:1:"0";s:6:"league";s:1:"0";s:11:"max_players";s:1:"5";s:4:"tier";s:1:"0";s:9:"no_repick";s:1:"0";s:6:"no_agi";s:1:"0";s:7:"drp_itm";s:1:"0";s:8:"no_timer";s:1:"0";s:6:"rev_hs";s:1:"0";s:7:"no_swap";s:1:"0";s:6:"no_int";s:1:"0";s:8:"alt_pick";s:1:"0";s:4:"veto";s:1:"0";s:4:"shuf";s:1:"0";s:6:"no_str";s:1:"0";s:7:"no_pups";s:1:"0";s:5:"dup_h";s:1:"0";s:2:"ap";s:1:"0";s:2:"br";s:1:"0";s:2:"em";s:1:"0";s:3:"cas";s:1:"0";s:2:"rs";s:1:"0";s:2:"nl";s:1:"1";s:6:"officl";s:1:"1";s:8:"no_stats";s:1:"0";s:2:"ab";s:1:"0";s:8:"hardcore";s:1:"0";s:10:"dev_heroes";s:1:"0";s:13:"verified_only";s:1:"0";s:5:"gated";s:1:"0";s:9:"rapidfire";s:1:"0";s:9:"timestamp";i:1650196121;s:3:"url";s:89:"http://replaydl.heroesofnewerth.com/ovh2USW26/saves/replays/20220416/M163305199.honreplay";s:4:"size";s:8:"13845139";s:4:"name";s:5:"USW26";s:3:"dir";s:23:"/saves/replays/20220416";s:6:"s3_url";s:81:"http://s3.amazonaws.com/naeu-icb2/replays/20220416/ovh2USW26/M163305199.honreplay";s:12:"winning_team";s:1:"2";s:8:"gamemode";s:2:"cp";s:3:"mvp";s:7:"9190611";s:8:"awd_mann";s:2:"-1";s:7:"awd_mqk";s:2:"-1";s:8:"awd_lgks";s:7:"9190611";s:7:"awd_msd";s:2:"-1";s:9:"awd_mkill";s:7:"9190611";s:9:"awd_masst";s:7:"3133223";s:9:"awd_ledth";s:7:"9190611";s:9:"awd_mbdmg";s:7:"5695194";s:7:"awd_mwk";s:2:"-1";s:8:"awd_mhdd";s:7:"3133223";s:7:"awd_hcs";s:7:"9190611";}}s:18:"match_player_stats";a:1:{i:163305199;a:10:{i:9190611;a:115:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9190611";s:7:"clan_id";s:6:"127744";s:7:"hero_id";s:3:"243";s:8:"position";s:1:"7";s:4:"team";s:1:"2";s:5:"level";s:2:"25";s:4:"wins";s:1:"1";s:6:"losses";s:1:"0";s:8:"concedes";s:1:"0";s:12:"concedevotes";s:1:"0";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:5:"4.704";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:2:"25";s:7:"herodmg";s:5:"39233";s:7:"heroexp";s:5:"14443";s:13:"herokillsgold";s:5:"10166";s:11:"heroassists";s:1:"5";s:6:"deaths";s:1:"4";s:14:"goldlost2death";s:4:"1133";s:9:"secs_dead";s:3:"168";s:14:"teamcreepkills";s:3:"390";s:12:"teamcreepdmg";s:6:"262306";s:12:"teamcreepexp";s:5:"16808";s:13:"teamcreepgold";s:5:"17692";s:17:"neutralcreepkills";s:2:"44";s:15:"neutralcreepdmg";s:5:"33434";s:15:"neutralcreepexp";s:4:"1122";s:16:"neutralcreepgold";s:4:"1960";s:4:"bdmg";s:4:"2733";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"2";s:5:"bgold";s:4:"2720";s:6:"denies";s:1:"9";s:10:"exp_denied";s:3:"386";s:4:"gold";s:5:"34731";s:10:"gold_spent";s:5:"40190";s:3:"exp";s:5:"32373";s:7:"actions";s:4:"5916";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"11";s:5:"wards";s:1:"5";s:16:"time_earning_exp";s:4:"2200";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"5";s:10:"triplekill";s:1:"1";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"1";s:3:"ks4";s:1:"1";s:3:"ks5";s:1:"1";s:3:"ks6";s:1:"1";s:3:"ks7";s:1:"1";s:3:"ks8";s:1:"1";s:3:"ks9";s:1:"1";s:4:"ks10";s:1:"1";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"4";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:13:"Hero_Parallax";s:3:"tag";s:4:"Eldr";s:8:"nickname";s:10:"LetsGoPens";s:15:"alt_avatar_name";s:0:"";s:20:"perf_amm_team_rating";s:7:"1500.00";s:26:"perf_amm_team_rating_delta";s:4:"4.70";s:16:"perf_victory_exp";s:2:"30";s:15:"perf_victory_gc";s:2:"60";s:14:"perf_first_exp";s:1:"0";s:13:"perf_first_gc";s:1:"0";s:14:"perf_quick_exp";s:1:"0";s:13:"perf_quick_gc";s:1:"0";s:18:"perf_consec_played";s:1:"0";s:15:"perf_consec_exp";s:1:"0";s:14:"perf_consec_gc";s:1:"0";s:21:"perf_annihilation_exp";s:1:"0";s:20:"perf_annihilation_gc";s:1:"0";s:18:"perf_bloodlust_exp";s:1:"0";s:17:"perf_bloodlust_gc";s:1:"0";s:13:"perf_ks15_exp";s:1:"0";s:12:"perf_ks15_gc";s:1:"0";s:20:"perf_social_bonus_gc";s:2:"40";s:9:"perf_wins";s:2:"16";s:15:"perf_wins_delta";s:1:"1";s:12:"perf_wins_gc";s:1:"0";s:14:"perf_herokills";s:3:"150";s:20:"perf_herokills_delta";s:2:"25";s:17:"perf_herokills_gc";s:1:"0";s:16:"perf_heroassists";s:3:"145";s:22:"perf_heroassists_delta";s:1:"5";s:19:"perf_heroassists_gc";s:1:"0";s:10:"perf_wards";s:2:"49";s:16:"perf_wards_delta";s:1:"5";s:13:"perf_wards_gc";s:2:"50";s:14:"perf_smackdown";s:1:"0";s:20:"perf_smackdown_delta";s:1:"0";s:17:"perf_smackdown_gc";s:1:"0";s:10:"perf_level";s:1:"5";s:14:"perf_level_exp";s:4:"1785";s:16:"perf_level_delta";s:3:"130";s:13:"perf_level_gc";s:1:"0";s:14:"perf_legacy_gc";s:1:"2";s:24:"perf_multiplier_mmpoints";s:1:"0";s:19:"perf_multiplier_exp";s:1:"0";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9190611";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1715.09";s:9:"mmr_after";s:7:"1719.79";s:12:"medal_before";s:2:"14";s:11:"medal_after";s:2:"14";s:6:"season";s:2:"12";s:17:"placement_matches";i:23;s:14:"placement_wins";s:6:"111111";}}i:9491038;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9491038";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:3:"120";s:8:"position";s:1:"8";s:4:"team";s:1:"2";s:5:"level";s:2:"20";s:4:"wins";s:1:"1";s:6:"losses";s:1:"0";s:8:"concedes";s:1:"0";s:12:"concedevotes";s:1:"0";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:5:"5.008";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"8";s:7:"herodmg";s:5:"10099";s:7:"heroexp";s:4:"9304";s:13:"herokillsgold";s:4:"6919";s:11:"heroassists";s:2:"13";s:6:"deaths";s:1:"8";s:14:"goldlost2death";s:4:"2144";s:9:"secs_dead";s:3:"320";s:14:"teamcreepkills";s:2:"66";s:12:"teamcreepdmg";s:5:"33078";s:12:"teamcreepexp";s:4:"9333";s:13:"teamcreepgold";s:4:"2917";s:17:"neutralcreepkills";s:2:"20";s:15:"neutralcreepdmg";s:5:"11353";s:15:"neutralcreepexp";s:4:"3370";s:16:"neutralcreepgold";s:4:"1044";s:4:"bdmg";s:3:"435";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"0";s:5:"bgold";s:4:"2250";s:6:"denies";s:1:"5";s:10:"exp_denied";s:3:"219";s:4:"gold";s:5:"14362";s:10:"gold_spent";s:5:"15165";s:3:"exp";s:5:"22007";s:7:"actions";s:4:"7548";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"21";s:5:"wards";s:2:"12";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"1";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"1";s:3:"ks4";s:1:"1";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:16:"Hero_WitchSlayer";s:3:"tag";s:0:"";s:8:"nickname";s:7:"Gonzo``";s:15:"alt_avatar_name";s:21:"Hero_WitchSlayer.Alt6";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9491038";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1625.64";s:9:"mmr_after";s:7:"1630.65";s:12:"medal_before";s:2:"12";s:11:"medal_after";s:2:"12";s:6:"season";s:2:"12";s:17:"placement_matches";i:166;s:14:"placement_wins";s:6:"110110";}}i:3133223;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"3133223";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:2:"18";s:8:"position";s:1:"3";s:4:"team";s:1:"1";s:5:"level";s:2:"24";s:4:"wins";s:1:"0";s:6:"losses";s:1:"1";s:8:"concedes";s:1:"1";s:12:"concedevotes";s:1:"0";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:6:"-4.753";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:2:"12";s:7:"herodmg";s:5:"59906";s:7:"heroexp";s:5:"12531";s:13:"herokillsgold";s:4:"6279";s:11:"heroassists";s:2:"14";s:6:"deaths";s:1:"7";s:14:"goldlost2death";s:4:"2201";s:9:"secs_dead";s:3:"354";s:14:"teamcreepkills";s:3:"238";s:12:"teamcreepdmg";s:6:"126116";s:12:"teamcreepexp";s:5:"16646";s:13:"teamcreepgold";s:5:"10754";s:17:"neutralcreepkills";s:2:"38";s:15:"neutralcreepdmg";s:5:"31333";s:15:"neutralcreepexp";s:4:"1865";s:16:"neutralcreepgold";s:4:"1274";s:4:"bdmg";s:3:"273";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"0";s:5:"bgold";s:3:"770";s:6:"denies";s:1:"4";s:10:"exp_denied";s:3:"136";s:4:"gold";s:5:"20152";s:10:"gold_spent";s:5:"19265";s:3:"exp";s:5:"31042";s:7:"actions";s:4:"6433";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"14";s:5:"wards";s:1:"2";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"1";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"1";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:10:"Hero_Kunas";s:3:"tag";s:0:"";s:8:"nickname";s:12:"way2addictin";s:15:"alt_avatar_name";s:15:"Hero_Kunas.Alt6";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"3133223";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1700.87";s:9:"mmr_after";s:7:"1696.12";s:12:"medal_before";s:2:"14";s:11:"medal_after";s:2:"14";s:6:"season";s:2:"12";s:17:"placement_matches";i:482;s:14:"placement_wins";s:6:"100111";}}i:282635;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:6:"282635";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:3:"127";s:8:"position";s:1:"2";s:4:"team";s:1:"1";s:5:"level";s:2:"17";s:4:"wins";s:1:"0";s:6:"losses";s:1:"1";s:8:"concedes";s:1:"1";s:12:"concedevotes";s:1:"2";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:6:"-5.031";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"5";s:7:"herodmg";s:5:"10087";s:7:"heroexp";s:4:"7818";s:13:"herokillsgold";s:4:"3378";s:11:"heroassists";s:2:"10";s:6:"deaths";s:2:"15";s:14:"goldlost2death";s:4:"3016";s:9:"secs_dead";s:3:"567";s:14:"teamcreepkills";s:2:"68";s:12:"teamcreepdmg";s:5:"26201";s:12:"teamcreepexp";s:4:"7042";s:13:"teamcreepgold";s:4:"3074";s:17:"neutralcreepkills";s:1:"3";s:15:"neutralcreepdmg";s:4:"7059";s:15:"neutralcreepexp";s:3:"488";s:16:"neutralcreepgold";s:3:"118";s:4:"bdmg";s:2:"19";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"0";s:5:"bgold";s:3:"770";s:6:"denies";s:1:"1";s:10:"exp_denied";s:2:"62";s:4:"gold";s:4:"7900";s:10:"gold_spent";s:4:"7700";s:3:"exp";s:5:"15348";s:7:"actions";s:4:"7315";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"12";s:5:"wards";s:1:"2";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"1";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"0";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"1";s:10:"used_token";s:1:"0";s:8:"cli_name";s:14:"Hero_Bephelgor";s:3:"tag";s:0:"";s:8:"nickname";s:6:"DaveYo";s:15:"alt_avatar_name";s:19:"Hero_Bephelgor.Alt4";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:6:"282635";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1618.97";s:9:"mmr_after";s:7:"1613.94";s:12:"medal_before";s:2:"12";s:11:"medal_after";s:2:"12";s:6:"season";s:2:"12";s:17:"placement_matches";i:515;s:14:"placement_wins";s:6:"101110";}}i:9486470;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9486470";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:2:"42";s:8:"position";s:1:"0";s:4:"team";s:1:"1";s:5:"level";s:2:"21";s:4:"wins";s:1:"0";s:6:"losses";s:1:"1";s:8:"concedes";s:1:"1";s:12:"concedevotes";s:1:"1";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:6:"-4.821";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"4";s:7:"herodmg";s:5:"14505";s:7:"heroexp";s:4:"6766";s:13:"herokillsgold";s:4:"3697";s:11:"heroassists";s:1:"6";s:6:"deaths";s:1:"9";s:14:"goldlost2death";s:4:"2263";s:9:"secs_dead";s:3:"434";s:14:"teamcreepkills";s:3:"202";s:12:"teamcreepdmg";s:6:"111585";s:12:"teamcreepexp";s:5:"13888";s:13:"teamcreepgold";s:4:"8919";s:17:"neutralcreepkills";s:2:"59";s:15:"neutralcreepdmg";s:5:"40088";s:15:"neutralcreepexp";s:4:"3296";s:16:"neutralcreepgold";s:4:"2005";s:4:"bdmg";s:3:"321";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"0";s:5:"bgold";s:3:"770";s:6:"denies";s:1:"7";s:10:"exp_denied";s:3:"238";s:4:"gold";s:5:"16704";s:10:"gold_spent";s:5:"17055";s:3:"exp";s:5:"23950";s:7:"actions";s:4:"7774";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"23";s:5:"wards";s:1:"1";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"0";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"0";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"1";s:10:"used_token";s:1:"0";s:8:"cli_name";s:9:"Hero_Scar";s:3:"tag";s:0:"";s:8:"nickname";s:8:"DONOFRlO";s:15:"alt_avatar_name";s:0:"";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9486470";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1680.84";s:9:"mmr_after";s:7:"1676.02";s:12:"medal_before";s:2:"13";s:11:"medal_after";s:2:"13";s:6:"season";s:2:"12";s:17:"placement_matches";i:63;s:14:"placement_wins";s:6:"111101";}}i:9188454;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9188454";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:3:"125";s:8:"position";s:1:"1";s:4:"team";s:1:"1";s:5:"level";s:2:"20";s:4:"wins";s:1:"0";s:6:"losses";s:1:"1";s:8:"concedes";s:1:"1";s:12:"concedevotes";s:1:"1";s:8:"buybacks";s:1:"1";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:6:"-5.046";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:2:"10";s:7:"herodmg";s:5:"19060";s:7:"heroexp";s:4:"8264";s:13:"herokillsgold";s:4:"6057";s:11:"heroassists";s:1:"9";s:6:"deaths";s:2:"10";s:14:"goldlost2death";s:4:"3311";s:9:"secs_dead";s:3:"438";s:14:"teamcreepkills";s:3:"129";s:12:"teamcreepdmg";s:5:"95951";s:12:"teamcreepexp";s:5:"12171";s:13:"teamcreepgold";s:4:"5750";s:17:"neutralcreepkills";s:2:"21";s:15:"neutralcreepdmg";s:5:"15438";s:15:"neutralcreepexp";s:4:"1458";s:16:"neutralcreepgold";s:3:"674";s:4:"bdmg";s:3:"391";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"1";s:5:"bgold";s:3:"770";s:6:"denies";s:1:"5";s:10:"exp_denied";s:3:"209";s:4:"gold";s:5:"13566";s:10:"gold_spent";s:5:"13429";s:3:"exp";s:5:"21893";s:7:"actions";s:4:"5351";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"13";s:5:"wards";s:1:"7";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"1";s:10:"doublekill";s:1:"2";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"1";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"1";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:12:"Hero_Bubbles";s:3:"tag";s:0:"";s:8:"nickname";s:11:"larjazznuts";s:15:"alt_avatar_name";s:18:"Hero_Bubbles.Alt12";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"9188454";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1614.60";s:9:"mmr_after";s:7:"1609.55";s:12:"medal_before";s:2:"12";s:11:"medal_after";s:2:"12";s:6:"season";s:2:"12";s:17:"placement_matches";i:572;s:14:"placement_wins";s:6:"111100";}}i:4064050;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"4064050";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:2:"17";s:8:"position";s:1:"9";s:4:"team";s:1:"2";s:5:"level";s:2:"20";s:4:"wins";s:1:"1";s:6:"losses";s:1:"0";s:8:"concedes";s:1:"0";s:12:"concedevotes";s:1:"0";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:5:"5.095";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"3";s:7:"herodmg";s:4:"9669";s:7:"heroexp";s:4:"6914";s:13:"herokillsgold";s:4:"2690";s:11:"heroassists";s:2:"10";s:6:"deaths";s:1:"8";s:14:"goldlost2death";s:4:"2912";s:9:"secs_dead";s:3:"448";s:14:"teamcreepkills";s:3:"162";s:12:"teamcreepdmg";s:5:"89637";s:12:"teamcreepexp";s:5:"13730";s:13:"teamcreepgold";s:4:"7441";s:17:"neutralcreepkills";s:2:"12";s:15:"neutralcreepdmg";s:5:"12283";s:15:"neutralcreepexp";s:4:"1120";s:16:"neutralcreepgold";s:3:"853";s:4:"bdmg";s:3:"836";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"0";s:5:"bgold";s:4:"2250";s:6:"denies";s:1:"2";s:10:"exp_denied";s:3:"108";s:4:"gold";s:5:"13598";s:10:"gold_spent";s:5:"14535";s:3:"exp";s:5:"21764";s:7:"actions";s:4:"4486";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"24";s:5:"wards";s:1:"2";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"1";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"0";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:11:"Hero_Kraken";s:3:"tag";s:0:"";s:8:"nickname";s:12:"luigiofdahud";s:15:"alt_avatar_name";s:16:"Hero_Kraken.Alt6";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"4064050";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1544.76";s:9:"mmr_after";s:7:"1549.86";s:12:"medal_before";s:2:"10";s:11:"medal_after";s:2:"10";s:6:"season";s:2:"12";s:17:"placement_matches";i:1554;s:14:"placement_wins";s:6:"011011";}}i:5695194;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"5695194";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:3:"210";s:8:"position";s:1:"6";s:4:"team";s:1:"2";s:5:"level";s:2:"18";s:4:"wins";s:1:"1";s:6:"losses";s:1:"0";s:8:"concedes";s:1:"0";s:12:"concedevotes";s:1:"0";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:5:"5.095";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"6";s:7:"herodmg";s:5:"10567";s:7:"heroexp";s:4:"4941";s:13:"herokillsgold";s:4:"3326";s:11:"heroassists";s:1:"9";s:6:"deaths";s:2:"11";s:14:"goldlost2death";s:4:"2845";s:9:"secs_dead";s:3:"491";s:14:"teamcreepkills";s:3:"145";s:12:"teamcreepdmg";s:5:"51815";s:12:"teamcreepexp";s:4:"9892";s:13:"teamcreepgold";s:4:"6124";s:17:"neutralcreepkills";s:2:"29";s:15:"neutralcreepdmg";s:5:"37523";s:15:"neutralcreepexp";s:4:"2448";s:16:"neutralcreepgold";s:4:"1851";s:4:"bdmg";s:4:"4936";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"6";s:5:"bgold";s:4:"3290";s:6:"denies";s:2:"13";s:10:"exp_denied";s:3:"682";s:4:"gold";s:5:"15022";s:10:"gold_spent";s:5:"13470";s:3:"exp";s:5:"17281";s:7:"actions";s:4:"4048";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"27";s:5:"wards";s:1:"0";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"1";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"0";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:16:"Hero_ShadowBlade";s:3:"tag";s:0:"";s:8:"nickname";s:5:"Jogia";s:15:"alt_avatar_name";s:20:"Hero_ShadowBlade.Alt";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"5695194";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1574.23";s:9:"mmr_after";s:7:"1579.33";s:12:"medal_before";s:2:"11";s:11:"medal_after";s:2:"11";s:6:"season";s:2:"12";s:17:"placement_matches";i:172;s:14:"placement_wins";s:6:"111010";}}i:7342714;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"7342714";s:7:"clan_id";s:5:"80273";s:7:"hero_id";s:3:"226";s:8:"position";s:1:"5";s:4:"team";s:1:"2";s:5:"level";s:2:"23";s:4:"wins";s:1:"1";s:6:"losses";s:1:"0";s:8:"concedes";s:1:"0";s:12:"concedevotes";s:1:"0";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:5:"4.841";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"9";s:7:"herodmg";s:5:"14349";s:7:"heroexp";s:4:"7149";s:13:"herokillsgold";s:4:"4423";s:11:"heroassists";s:1:"5";s:6:"deaths";s:1:"6";s:14:"goldlost2death";s:4:"2285";s:9:"secs_dead";s:4:"3532";s:14:"teamcreepkills";s:2:"62";s:12:"teamcreepdmg";s:5:"41510";s:12:"teamcreepexp";s:4:"3414";s:13:"teamcreepgold";s:4:"2902";s:17:"neutralcreepkills";s:3:"292";s:15:"neutralcreepdmg";s:6:"251539";s:15:"neutralcreepexp";s:5:"17944";s:16:"neutralcreepgold";s:5:"10561";s:4:"bdmg";s:4:"2872";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"3";s:5:"bgold";s:4:"2250";s:6:"denies";s:1:"0";s:10:"exp_denied";s:1:"0";s:4:"gold";s:5:"21127";s:10:"gold_spent";s:5:"22150";s:3:"exp";s:5:"28507";s:7:"actions";s:4:"5406";s:4:"secs";s:4:"2867";s:11:"consumables";s:2:"18";s:5:"wards";s:1:"0";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"0";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"1";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:13:"Hero_Solstice";s:3:"tag";s:4:"ANHI";s:8:"nickname";s:10:"CraZ_Killa";s:15:"alt_avatar_name";s:18:"Hero_Solstice.Alt6";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:7:"7342714";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1674.85";s:9:"mmr_after";s:7:"1679.69";s:12:"medal_before";s:2:"13";s:11:"medal_after";s:2:"13";s:6:"season";s:2:"12";s:17:"placement_matches";i:502;s:14:"placement_wins";s:6:"011101";}}i:422280;a:75:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:6:"422280";s:7:"clan_id";s:1:"0";s:7:"hero_id";s:3:"224";s:8:"position";s:1:"4";s:4:"team";s:1:"1";s:5:"level";s:2:"17";s:4:"wins";s:1:"0";s:6:"losses";s:1:"1";s:8:"concedes";s:1:"1";s:12:"concedevotes";s:1:"1";s:8:"buybacks";s:1:"0";s:6:"discos";s:1:"0";s:6:"kicked";s:1:"0";s:9:"pub_skill";s:5:"0.000";s:9:"pub_count";s:1:"0";s:15:"amm_solo_rating";s:5:"0.000";s:14:"amm_solo_count";s:1:"0";s:15:"amm_team_rating";s:6:"-5.095";s:14:"amm_team_count";s:1:"1";s:9:"avg_score";s:4:"0.00";s:9:"herokills";s:1:"4";s:7:"herodmg";s:4:"6550";s:7:"heroexp";s:4:"5479";s:13:"herokillsgold";s:4:"3391";s:11:"heroassists";s:1:"8";s:6:"deaths";s:2:"10";s:14:"goldlost2death";s:4:"2273";s:9:"secs_dead";s:3:"457";s:14:"teamcreepkills";s:2:"66";s:12:"teamcreepdmg";s:5:"33000";s:12:"teamcreepexp";s:4:"8117";s:13:"teamcreepgold";s:4:"2812";s:17:"neutralcreepkills";s:2:"15";s:15:"neutralcreepdmg";s:5:"10282";s:15:"neutralcreepexp";s:4:"1379";s:16:"neutralcreepgold";s:3:"570";s:4:"bdmg";s:3:"252";s:7:"bdmgexp";s:1:"0";s:5:"razed";s:1:"1";s:5:"bgold";s:3:"950";s:6:"denies";s:1:"3";s:10:"exp_denied";s:2:"95";s:4:"gold";s:4:"8876";s:10:"gold_spent";s:4:"9380";s:3:"exp";s:5:"14975";s:7:"actions";s:4:"5896";s:4:"secs";s:4:"2867";s:11:"consumables";s:1:"5";s:5:"wards";s:1:"4";s:16:"time_earning_exp";s:4:"2867";s:9:"bloodlust";s:1:"0";s:10:"doublekill";s:1:"0";s:10:"triplekill";s:1:"0";s:8:"quadkill";s:1:"0";s:12:"annihilation";s:1:"0";s:3:"ks3";s:1:"0";s:3:"ks4";s:1:"0";s:3:"ks5";s:1:"0";s:3:"ks6";s:1:"0";s:3:"ks7";s:1:"0";s:3:"ks8";s:1:"0";s:3:"ks9";s:1:"0";s:4:"ks10";s:1:"0";s:4:"ks15";s:1:"0";s:9:"smackdown";s:1:"0";s:11:"humiliation";s:1:"0";s:7:"nemesis";s:1:"0";s:11:"retribution";s:1:"0";s:10:"used_token";s:1:"0";s:8:"cli_name";s:10:"Hero_Rally";s:3:"tag";s:0:"";s:8:"nickname";s:5:"enkai";s:15:"alt_avatar_name";s:0:"";s:13:"campaign_info";a:10:{s:8:"match_id";s:9:"163305199";s:10:"account_id";s:6:"422280";s:9:"is_casual";s:1:"0";s:10:"mmr_before";s:7:"1540.52";s:9:"mmr_after";s:7:"1535.42";s:12:"medal_before";s:2:"10";s:11:"medal_after";s:2:"10";s:6:"season";s:2:"12";s:17:"placement_matches";i:957;s:14:"placement_wins";s:6:"010011";}}}}s:9:"inventory";a:1:{i:163305199;a:10:{i:282635;a:8:{s:10:"account_id";s:6:"282635";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:18:"Item_PlatedGreaves";s:6:"slot_2";s:16:"Item_BarrierIdol";s:6:"slot_3";s:19:"Item_LoggersHatchet";s:6:"slot_4";N;s:6:"slot_5";N;s:6:"slot_6";s:17:"Item_BloodChalice";}i:422280;a:8:{s:10:"account_id";s:6:"422280";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:14:"Item_Platemail";s:6:"slot_2";s:20:"Item_MysticVestments";s:6:"slot_3";s:14:"Item_Glowstone";s:6:"slot_4";s:16:"Item_GraveLocket";s:6:"slot_5";s:16:"Item_SolsBulwark";s:6:"slot_6";s:15:"Item_Steamboots";}i:3133223;a:8:{s:10:"account_id";s:7:"3133223";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:13:"Item_Striders";s:6:"slot_2";s:17:"Item_Spell_Sunder";s:6:"slot_3";s:16:"Item_SpellShards";s:6:"slot_4";s:21:"Item_RestorationStone";s:6:"slot_5";s:20:"Item_MysticVestments";s:6:"slot_6";s:20:"Item_GrimoireOfPower";}i:4064050;a:8:{s:10:"account_id";s:7:"4064050";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:14:"Item_PortalKey";s:6:"slot_2";s:16:"Item_Excruciator";s:6:"slot_3";s:24:"Item_DaemonicBreastplate";s:6:"slot_4";N;s:6:"slot_5";s:15:"Item_Steamboots";s:6:"slot_6";s:20:"Item_MysticVestments";}i:5695194;a:8:{s:10:"account_id";s:7:"5695194";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:16:"Item_IronBuckler";s:6:"slot_2";s:14:"Item_ManaBurn1";s:6:"slot_3";s:15:"Item_Steamboots";s:6:"slot_4";s:14:"Item_ManaBurn2";s:6:"slot_5";s:20:"Item_MysticVestments";s:6:"slot_6";N;}i:7342714;a:8:{s:10:"account_id";s:7:"7342714";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:15:"Item_Hypercrown";s:6:"slot_2";s:21:"Item_EnhancedMarchers";s:6:"slot_3";s:16:"Item_Dawnbringer";s:6:"slot_4";s:11:"Item_Pierce";s:6:"slot_5";N;s:6:"slot_6";s:20:"Item_MysticVestments";}i:9188454;a:8:{s:10:"account_id";s:7:"9188454";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:12:"Item_Protect";s:6:"slot_2";s:17:"Item_BloodChalice";s:6:"slot_3";s:16:"Item_GraveLocket";s:6:"slot_4";s:18:"Item_LuminousPrism";s:6:"slot_5";s:15:"Item_Steamboots";s:6:"slot_6";s:20:"Item_MysticVestments";}i:9190611;a:8:{s:10:"account_id";s:7:"9190611";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:14:"Item_PostHaste";s:6:"slot_2";s:13:"Item_Immunity";s:6:"slot_3";s:10:"Item_Morph";s:6:"slot_4";s:16:"Item_HealthMana2";s:6:"slot_5";s:18:"Item_Intelligence7";s:6:"slot_6";s:16:"Item_SpellShards";}i:9486470;a:8:{s:10:"account_id";s:7:"9486470";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:13:"Item_Immunity";s:6:"slot_2";s:14:"Item_ManaBurn1";s:6:"slot_3";s:17:"Item_BloodChalice";s:6:"slot_4";s:11:"Item_Splash";s:6:"slot_5";s:11:"Item_Bottle";s:6:"slot_6";s:15:"Item_Steamboots";}i:9491038;a:8:{s:10:"account_id";s:7:"9491038";s:8:"match_id";s:9:"163305199";s:6:"slot_1";s:18:"Item_Intelligence7";s:6:"slot_2";N;s:6:"slot_3";s:13:"Item_Striders";s:6:"slot_4";s:14:"Item_PortalKey";s:6:"slot_5";s:9:"Item_Nuke";s:6:"slot_6";s:20:"Item_MysticVestments";}}}s:12:"quest_system";a:1:{s:5:"error";a:2:{s:12:"quest_status";i:0;s:18:"leaderboard_status";i:0;}}s:10:"con_reward";a:7:{s:7:"old_lvl";i:3;s:8:"curr_lvl";i:3;s:8:"next_lvl";i:4;s:12:"require_rank";i:15;s:14:"need_more_play";i:4;s:17:"percentage_before";s:4:"0.00";s:10:"percentage";s:4:"0.00";}s:13:"match_mastery";a:16:{s:8:"cli_name";s:0:"";s:20:"mastery_exp_original";i:0;s:17:"mastery_exp_match";i:0;s:17:"mastery_exp_bonus";i:0;s:17:"mastery_exp_boost";i:0;s:23:"mastery_exp_super_boost";i:0;s:24:"mastery_exp_heroes_count";i:0;s:24:"mastery_exp_heroes_addon";i:0;s:20:"mastery_exp_to_boost";i:0;s:17:"mastery_exp_event";i:0;s:16:"mastery_canboost";b:0;s:22:"mastery_super_canboost";b:0;s:24:"mastery_boost_product_id";i:0;s:30:"mastery_super_boost_product_id";i:0;s:16:"mastery_boostnum";i:0;s:22:"mastery_super_boostnum";i:0;}s:13:"season_system";a:3:{s:13:"drop_diamonds";i:0;s:12:"cur_diamonds";i:0;s:9:"box_price";a:0:{}}s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [points] => 1570
    [mmpoints] => 12859
    [dice_tokens] => 2
    [season_level] => 0
    [slot_id] => 3
    [my_upgrades] => Array
        (
            [0] => m.allmodes.pass
            [1] => h.AllHeroes.Hero
            [2] => m.Super-Taunt
        )

    [selected_upgrades] => Array
        (
            [0] => ai.custom_icon:3
            [1] => cc.tanzanite
            [2] => ai.custom_icon:3
        )

    [game_tokens] => 0
    [my_upgrades_info] => Array
        (
        )

    [creep_level] => 0
    [timestamp] => 1650180476
    [match_summ] => Array
        (
            [163305199] => Array
                (
                    [match_id] => 163305199
                    [server_id] => 9440663
                    [map] => caldavar
                    [map_version] => 0.0.0
                    [time_played] => 2867
                    [file_host] => replaydl.heroesofnewerth.com
                    [file_size] => 0
                    [file_name] => ~/replays/163305199.honreplay
                    [c_state] => 5
                    [version] => 4.10.1.0
                    [avgpsr] => 0
                    [date] => 4/17/2022
                    [time] => 07:48:41 AM
                    [mname] => TMM Match #163305199
                    [class] => 11
                    [private] => 1
                    [nm] => 0
                    [sd] => 0
                    [rd] => 0
                    [dm] => 0
                    [bd] => 0
                    [bp] => 0
                    [ar] => 0
                    [cd] => 0
                    [cm] => 0
                    [lp] => 0
                    [bb] => 0
                    [bm] => 0
                    [km] => 0
                    [league] => 0
                    [max_players] => 5
                    [tier] => 0
                    [no_repick] => 0
                    [no_agi] => 0
                    [drp_itm] => 0
                    [no_timer] => 0
                    [rev_hs] => 0
                    [no_swap] => 0
                    [no_int] => 0
                    [alt_pick] => 0
                    [veto] => 0
                    [shuf] => 0
                    [no_str] => 0
                    [no_pups] => 0
                    [dup_h] => 0
                    [ap] => 0
                    [br] => 0
                    [em] => 0
                    [cas] => 0
                    [rs] => 0
                    [nl] => 1
                    [officl] => 1
                    [no_stats] => 0
                    [ab] => 0
                    [hardcore] => 0
                    [dev_heroes] => 0
                    [verified_only] => 0
                    [gated] => 0
                    [rapidfire] => 0
                    [timestamp] => 1650196121
                    [url] => http://replaydl.heroesofnewerth.com/ovh2USW26/saves/replays/20220416/M163305199.honreplay
                    [size] => 13845139
                    [name] => USW26
                    [dir] => /saves/replays/20220416
                    [s3_url] => http://s3.amazonaws.com/naeu-icb2/replays/20220416/ovh2USW26/M163305199.honreplay
                    [winning_team] => 2
                    [gamemode] => cp
                    [mvp] => 9190611
                    [awd_mann] => -1
                    [awd_mqk] => -1
                    [awd_lgks] => 9190611
                    [awd_msd] => -1
                    [awd_mkill] => 9190611
                    [awd_masst] => 3133223
                    [awd_ledth] => 9190611
                    [awd_mbdmg] => 5695194
                    [awd_mwk] => -1
                    [awd_mhdd] => 3133223
                    [awd_hcs] => 9190611
                )

        )

    [match_player_stats] => Array
        (
            [163305199] => Array
                (
                    [9190611] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 9190611
                            [clan_id] => 127744
                            [hero_id] => 243
                            [position] => 7
                            [team] => 2
                            [level] => 25
                            [wins] => 1
                            [losses] => 0
                            [concedes] => 0
                            [concedevotes] => 0
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => 4.704
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 25
                            [herodmg] => 39233
                            [heroexp] => 14443
                            [herokillsgold] => 10166
                            [heroassists] => 5
                            [deaths] => 4
                            [goldlost2death] => 1133
                            [secs_dead] => 168
                            [teamcreepkills] => 390
                            [teamcreepdmg] => 262306
                            [teamcreepexp] => 16808
                            [teamcreepgold] => 17692
                            [neutralcreepkills] => 44
                            [neutralcreepdmg] => 33434
                            [neutralcreepexp] => 1122
                            [neutralcreepgold] => 1960
                            [bdmg] => 2733
                            [bdmgexp] => 0
                            [razed] => 2
                            [bgold] => 2720
                            [denies] => 9
                            [exp_denied] => 386
                            [gold] => 34731
                            [gold_spent] => 40190
                            [exp] => 32373
                            [actions] => 5916
                            [secs] => 2867
                            [consumables] => 11
                            [wards] => 5
                            [time_earning_exp] => 2200
                            [bloodlust] => 0
                            [doublekill] => 5
                            [triplekill] => 1
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 1
                            [ks4] => 1
                            [ks5] => 1
                            [ks6] => 1
                            [ks7] => 1
                            [ks8] => 1
                            [ks9] => 1
                            [ks10] => 1
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 4
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_Parallax
                            [tag] => Eldr
                            [nickname] => LetsGoPens
                            [alt_avatar_name] => 
                            [perf_amm_team_rating] => 1500.00
                            [perf_amm_team_rating_delta] => 4.70
                            [perf_victory_exp] => 30
                            [perf_victory_gc] => 60
                            [perf_first_exp] => 0
                            [perf_first_gc] => 0
                            [perf_quick_exp] => 0
                            [perf_quick_gc] => 0
                            [perf_consec_played] => 0
                            [perf_consec_exp] => 0
                            [perf_consec_gc] => 0
                            [perf_annihilation_exp] => 0
                            [perf_annihilation_gc] => 0
                            [perf_bloodlust_exp] => 0
                            [perf_bloodlust_gc] => 0
                            [perf_ks15_exp] => 0
                            [perf_ks15_gc] => 0
                            [perf_social_bonus_gc] => 40
                            [perf_wins] => 16
                            [perf_wins_delta] => 1
                            [perf_wins_gc] => 0
                            [perf_herokills] => 150
                            [perf_herokills_delta] => 25
                            [perf_herokills_gc] => 0
                            [perf_heroassists] => 145
                            [perf_heroassists_delta] => 5
                            [perf_heroassists_gc] => 0
                            [perf_wards] => 49
                            [perf_wards_delta] => 5
                            [perf_wards_gc] => 50
                            [perf_smackdown] => 0
                            [perf_smackdown_delta] => 0
                            [perf_smackdown_gc] => 0
                            [perf_level] => 5
                            [perf_level_exp] => 1785
                            [perf_level_delta] => 130
                            [perf_level_gc] => 0
                            [perf_legacy_gc] => 2
                            [perf_multiplier_mmpoints] => 0
                            [perf_multiplier_exp] => 0
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 9190611
                                    [is_casual] => 0
                                    [mmr_before] => 1715.09
                                    [mmr_after] => 1719.79
                                    [medal_before] => 14
                                    [medal_after] => 14
                                    [season] => 12
                                    [placement_matches] => 23
                                    [placement_wins] => 111111
                                )

                        )

                    [9491038] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 9491038
                            [clan_id] => 0
                            [hero_id] => 120
                            [position] => 8
                            [team] => 2
                            [level] => 20
                            [wins] => 1
                            [losses] => 0
                            [concedes] => 0
                            [concedevotes] => 0
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => 5.008
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 8
                            [herodmg] => 10099
                            [heroexp] => 9304
                            [herokillsgold] => 6919
                            [heroassists] => 13
                            [deaths] => 8
                            [goldlost2death] => 2144
                            [secs_dead] => 320
                            [teamcreepkills] => 66
                            [teamcreepdmg] => 33078
                            [teamcreepexp] => 9333
                            [teamcreepgold] => 2917
                            [neutralcreepkills] => 20
                            [neutralcreepdmg] => 11353
                            [neutralcreepexp] => 3370
                            [neutralcreepgold] => 1044
                            [bdmg] => 435
                            [bdmgexp] => 0
                            [razed] => 0
                            [bgold] => 2250
                            [denies] => 5
                            [exp_denied] => 219
                            [gold] => 14362
                            [gold_spent] => 15165
                            [exp] => 22007
                            [actions] => 7548
                            [secs] => 2867
                            [consumables] => 21
                            [wards] => 12
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 1
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 1
                            [ks4] => 1
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_WitchSlayer
                            [tag] => 
                            [nickname] => Gonzo``
                            [alt_avatar_name] => Hero_WitchSlayer.Alt6
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 9491038
                                    [is_casual] => 0
                                    [mmr_before] => 1625.64
                                    [mmr_after] => 1630.65
                                    [medal_before] => 12
                                    [medal_after] => 12
                                    [season] => 12
                                    [placement_matches] => 166
                                    [placement_wins] => 110110
                                )

                        )

                    [3133223] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 3133223
                            [clan_id] => 0
                            [hero_id] => 18
                            [position] => 3
                            [team] => 1
                            [level] => 24
                            [wins] => 0
                            [losses] => 1
                            [concedes] => 1
                            [concedevotes] => 0
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => -4.753
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 12
                            [herodmg] => 59906
                            [heroexp] => 12531
                            [herokillsgold] => 6279
                            [heroassists] => 14
                            [deaths] => 7
                            [goldlost2death] => 2201
                            [secs_dead] => 354
                            [teamcreepkills] => 238
                            [teamcreepdmg] => 126116
                            [teamcreepexp] => 16646
                            [teamcreepgold] => 10754
                            [neutralcreepkills] => 38
                            [neutralcreepdmg] => 31333
                            [neutralcreepexp] => 1865
                            [neutralcreepgold] => 1274
                            [bdmg] => 273
                            [bdmgexp] => 0
                            [razed] => 0
                            [bgold] => 770
                            [denies] => 4
                            [exp_denied] => 136
                            [gold] => 20152
                            [gold_spent] => 19265
                            [exp] => 31042
                            [actions] => 6433
                            [secs] => 2867
                            [consumables] => 14
                            [wards] => 2
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 1
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 1
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_Kunas
                            [tag] => 
                            [nickname] => way2addictin
                            [alt_avatar_name] => Hero_Kunas.Alt6
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 3133223
                                    [is_casual] => 0
                                    [mmr_before] => 1700.87
                                    [mmr_after] => 1696.12
                                    [medal_before] => 14
                                    [medal_after] => 14
                                    [season] => 12
                                    [placement_matches] => 482
                                    [placement_wins] => 100111
                                )

                        )

                    [282635] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 282635
                            [clan_id] => 0
                            [hero_id] => 127
                            [position] => 2
                            [team] => 1
                            [level] => 17
                            [wins] => 0
                            [losses] => 1
                            [concedes] => 1
                            [concedevotes] => 2
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => -5.031
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 5
                            [herodmg] => 10087
                            [heroexp] => 7818
                            [herokillsgold] => 3378
                            [heroassists] => 10
                            [deaths] => 15
                            [goldlost2death] => 3016
                            [secs_dead] => 567
                            [teamcreepkills] => 68
                            [teamcreepdmg] => 26201
                            [teamcreepexp] => 7042
                            [teamcreepgold] => 3074
                            [neutralcreepkills] => 3
                            [neutralcreepdmg] => 7059
                            [neutralcreepexp] => 488
                            [neutralcreepgold] => 118
                            [bdmg] => 19
                            [bdmgexp] => 0
                            [razed] => 0
                            [bgold] => 770
                            [denies] => 1
                            [exp_denied] => 62
                            [gold] => 7900
                            [gold_spent] => 7700
                            [exp] => 15348
                            [actions] => 7315
                            [secs] => 2867
                            [consumables] => 12
                            [wards] => 2
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 1
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 0
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 1
                            [used_token] => 0
                            [cli_name] => Hero_Bephelgor
                            [tag] => 
                            [nickname] => DaveYo
                            [alt_avatar_name] => Hero_Bephelgor.Alt4
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 282635
                                    [is_casual] => 0
                                    [mmr_before] => 1618.97
                                    [mmr_after] => 1613.94
                                    [medal_before] => 12
                                    [medal_after] => 12
                                    [season] => 12
                                    [placement_matches] => 515
                                    [placement_wins] => 101110
                                )

                        )

                    [9486470] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 9486470
                            [clan_id] => 0
                            [hero_id] => 42
                            [position] => 0
                            [team] => 1
                            [level] => 21
                            [wins] => 0
                            [losses] => 1
                            [concedes] => 1
                            [concedevotes] => 1
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => -4.821
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 4
                            [herodmg] => 14505
                            [heroexp] => 6766
                            [herokillsgold] => 3697
                            [heroassists] => 6
                            [deaths] => 9
                            [goldlost2death] => 2263
                            [secs_dead] => 434
                            [teamcreepkills] => 202
                            [teamcreepdmg] => 111585
                            [teamcreepexp] => 13888
                            [teamcreepgold] => 8919
                            [neutralcreepkills] => 59
                            [neutralcreepdmg] => 40088
                            [neutralcreepexp] => 3296
                            [neutralcreepgold] => 2005
                            [bdmg] => 321
                            [bdmgexp] => 0
                            [razed] => 0
                            [bgold] => 770
                            [denies] => 7
                            [exp_denied] => 238
                            [gold] => 16704
                            [gold_spent] => 17055
                            [exp] => 23950
                            [actions] => 7774
                            [secs] => 2867
                            [consumables] => 23
                            [wards] => 1
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 0
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 0
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 1
                            [used_token] => 0
                            [cli_name] => Hero_Scar
                            [tag] => 
                            [nickname] => DONOFRlO
                            [alt_avatar_name] => 
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 9486470
                                    [is_casual] => 0
                                    [mmr_before] => 1680.84
                                    [mmr_after] => 1676.02
                                    [medal_before] => 13
                                    [medal_after] => 13
                                    [season] => 12
                                    [placement_matches] => 63
                                    [placement_wins] => 111101
                                )

                        )

                    [9188454] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 9188454
                            [clan_id] => 0
                            [hero_id] => 125
                            [position] => 1
                            [team] => 1
                            [level] => 20
                            [wins] => 0
                            [losses] => 1
                            [concedes] => 1
                            [concedevotes] => 1
                            [buybacks] => 1
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => -5.046
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 10
                            [herodmg] => 19060
                            [heroexp] => 8264
                            [herokillsgold] => 6057
                            [heroassists] => 9
                            [deaths] => 10
                            [goldlost2death] => 3311
                            [secs_dead] => 438
                            [teamcreepkills] => 129
                            [teamcreepdmg] => 95951
                            [teamcreepexp] => 12171
                            [teamcreepgold] => 5750
                            [neutralcreepkills] => 21
                            [neutralcreepdmg] => 15438
                            [neutralcreepexp] => 1458
                            [neutralcreepgold] => 674
                            [bdmg] => 391
                            [bdmgexp] => 0
                            [razed] => 1
                            [bgold] => 770
                            [denies] => 5
                            [exp_denied] => 209
                            [gold] => 13566
                            [gold_spent] => 13429
                            [exp] => 21893
                            [actions] => 5351
                            [secs] => 2867
                            [consumables] => 13
                            [wards] => 7
                            [time_earning_exp] => 2867
                            [bloodlust] => 1
                            [doublekill] => 2
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 1
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 1
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_Bubbles
                            [tag] => 
                            [nickname] => larjazznuts
                            [alt_avatar_name] => Hero_Bubbles.Alt12
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 9188454
                                    [is_casual] => 0
                                    [mmr_before] => 1614.60
                                    [mmr_after] => 1609.55
                                    [medal_before] => 12
                                    [medal_after] => 12
                                    [season] => 12
                                    [placement_matches] => 572
                                    [placement_wins] => 111100
                                )

                        )

                    [4064050] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 4064050
                            [clan_id] => 0
                            [hero_id] => 17
                            [position] => 9
                            [team] => 2
                            [level] => 20
                            [wins] => 1
                            [losses] => 0
                            [concedes] => 0
                            [concedevotes] => 0
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => 5.095
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 3
                            [herodmg] => 9669
                            [heroexp] => 6914
                            [herokillsgold] => 2690
                            [heroassists] => 10
                            [deaths] => 8
                            [goldlost2death] => 2912
                            [secs_dead] => 448
                            [teamcreepkills] => 162
                            [teamcreepdmg] => 89637
                            [teamcreepexp] => 13730
                            [teamcreepgold] => 7441
                            [neutralcreepkills] => 12
                            [neutralcreepdmg] => 12283
                            [neutralcreepexp] => 1120
                            [neutralcreepgold] => 853
                            [bdmg] => 836
                            [bdmgexp] => 0
                            [razed] => 0
                            [bgold] => 2250
                            [denies] => 2
                            [exp_denied] => 108
                            [gold] => 13598
                            [gold_spent] => 14535
                            [exp] => 21764
                            [actions] => 4486
                            [secs] => 2867
                            [consumables] => 24
                            [wards] => 2
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 1
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 0
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_Kraken
                            [tag] => 
                            [nickname] => luigiofdahud
                            [alt_avatar_name] => Hero_Kraken.Alt6
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 4064050
                                    [is_casual] => 0
                                    [mmr_before] => 1544.76
                                    [mmr_after] => 1549.86
                                    [medal_before] => 10
                                    [medal_after] => 10
                                    [season] => 12
                                    [placement_matches] => 1554
                                    [placement_wins] => 011011
                                )

                        )

                    [5695194] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 5695194
                            [clan_id] => 0
                            [hero_id] => 210
                            [position] => 6
                            [team] => 2
                            [level] => 18
                            [wins] => 1
                            [losses] => 0
                            [concedes] => 0
                            [concedevotes] => 0
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => 5.095
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 6
                            [herodmg] => 10567
                            [heroexp] => 4941
                            [herokillsgold] => 3326
                            [heroassists] => 9
                            [deaths] => 11
                            [goldlost2death] => 2845
                            [secs_dead] => 491
                            [teamcreepkills] => 145
                            [teamcreepdmg] => 51815
                            [teamcreepexp] => 9892
                            [teamcreepgold] => 6124
                            [neutralcreepkills] => 29
                            [neutralcreepdmg] => 37523
                            [neutralcreepexp] => 2448
                            [neutralcreepgold] => 1851
                            [bdmg] => 4936
                            [bdmgexp] => 0
                            [razed] => 6
                            [bgold] => 3290
                            [denies] => 13
                            [exp_denied] => 682
                            [gold] => 15022
                            [gold_spent] => 13470
                            [exp] => 17281
                            [actions] => 4048
                            [secs] => 2867
                            [consumables] => 27
                            [wards] => 0
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 1
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 0
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_ShadowBlade
                            [tag] => 
                            [nickname] => Jogia
                            [alt_avatar_name] => Hero_ShadowBlade.Alt
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 5695194
                                    [is_casual] => 0
                                    [mmr_before] => 1574.23
                                    [mmr_after] => 1579.33
                                    [medal_before] => 11
                                    [medal_after] => 11
                                    [season] => 12
                                    [placement_matches] => 172
                                    [placement_wins] => 111010
                                )

                        )

                    [7342714] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 7342714
                            [clan_id] => 80273
                            [hero_id] => 226
                            [position] => 5
                            [team] => 2
                            [level] => 23
                            [wins] => 1
                            [losses] => 0
                            [concedes] => 0
                            [concedevotes] => 0
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => 4.841
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 9
                            [herodmg] => 14349
                            [heroexp] => 7149
                            [herokillsgold] => 4423
                            [heroassists] => 5
                            [deaths] => 6
                            [goldlost2death] => 2285
                            [secs_dead] => 3532
                            [teamcreepkills] => 62
                            [teamcreepdmg] => 41510
                            [teamcreepexp] => 3414
                            [teamcreepgold] => 2902
                            [neutralcreepkills] => 292
                            [neutralcreepdmg] => 251539
                            [neutralcreepexp] => 17944
                            [neutralcreepgold] => 10561
                            [bdmg] => 2872
                            [bdmgexp] => 0
                            [razed] => 3
                            [bgold] => 2250
                            [denies] => 0
                            [exp_denied] => 0
                            [gold] => 21127
                            [gold_spent] => 22150
                            [exp] => 28507
                            [actions] => 5406
                            [secs] => 2867
                            [consumables] => 18
                            [wards] => 0
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 0
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 1
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_Solstice
                            [tag] => ANHI
                            [nickname] => CraZ_Killa
                            [alt_avatar_name] => Hero_Solstice.Alt6
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 7342714
                                    [is_casual] => 0
                                    [mmr_before] => 1674.85
                                    [mmr_after] => 1679.69
                                    [medal_before] => 13
                                    [medal_after] => 13
                                    [season] => 12
                                    [placement_matches] => 502
                                    [placement_wins] => 011101
                                )

                        )

                    [422280] => Array
                        (
                            [match_id] => 163305199
                            [account_id] => 422280
                            [clan_id] => 0
                            [hero_id] => 224
                            [position] => 4
                            [team] => 1
                            [level] => 17
                            [wins] => 0
                            [losses] => 1
                            [concedes] => 1
                            [concedevotes] => 1
                            [buybacks] => 0
                            [discos] => 0
                            [kicked] => 0
                            [pub_skill] => 0.000
                            [pub_count] => 0
                            [amm_solo_rating] => 0.000
                            [amm_solo_count] => 0
                            [amm_team_rating] => -5.095
                            [amm_team_count] => 1
                            [avg_score] => 0.00
                            [herokills] => 4
                            [herodmg] => 6550
                            [heroexp] => 5479
                            [herokillsgold] => 3391
                            [heroassists] => 8
                            [deaths] => 10
                            [goldlost2death] => 2273
                            [secs_dead] => 457
                            [teamcreepkills] => 66
                            [teamcreepdmg] => 33000
                            [teamcreepexp] => 8117
                            [teamcreepgold] => 2812
                            [neutralcreepkills] => 15
                            [neutralcreepdmg] => 10282
                            [neutralcreepexp] => 1379
                            [neutralcreepgold] => 570
                            [bdmg] => 252
                            [bdmgexp] => 0
                            [razed] => 1
                            [bgold] => 950
                            [denies] => 3
                            [exp_denied] => 95
                            [gold] => 8876
                            [gold_spent] => 9380
                            [exp] => 14975
                            [actions] => 5896
                            [secs] => 2867
                            [consumables] => 5
                            [wards] => 4
                            [time_earning_exp] => 2867
                            [bloodlust] => 0
                            [doublekill] => 0
                            [triplekill] => 0
                            [quadkill] => 0
                            [annihilation] => 0
                            [ks3] => 0
                            [ks4] => 0
                            [ks5] => 0
                            [ks6] => 0
                            [ks7] => 0
                            [ks8] => 0
                            [ks9] => 0
                            [ks10] => 0
                            [ks15] => 0
                            [smackdown] => 0
                            [humiliation] => 0
                            [nemesis] => 0
                            [retribution] => 0
                            [used_token] => 0
                            [cli_name] => Hero_Rally
                            [tag] => 
                            [nickname] => enkai
                            [alt_avatar_name] => 
                            [campaign_info] => Array
                                (
                                    [match_id] => 163305199
                                    [account_id] => 422280
                                    [is_casual] => 0
                                    [mmr_before] => 1540.52
                                    [mmr_after] => 1535.42
                                    [medal_before] => 10
                                    [medal_after] => 10
                                    [season] => 12
                                    [placement_matches] => 957
                                    [placement_wins] => 010011
                                )

                        )

                )

        )

    [inventory] => Array
        (
            [163305199] => Array
                (
                    [282635] => Array
                        (
                            [account_id] => 282635
                            [match_id] => 163305199
                            [slot_1] => Item_PlatedGreaves
                            [slot_2] => Item_BarrierIdol
                            [slot_3] => Item_LoggersHatchet
                            [slot_4] => 
                            [slot_5] => 
                            [slot_6] => Item_BloodChalice
                        )

                    [422280] => Array
                        (
                            [account_id] => 422280
                            [match_id] => 163305199
                            [slot_1] => Item_Platemail
                            [slot_2] => Item_MysticVestments
                            [slot_3] => Item_Glowstone
                            [slot_4] => Item_GraveLocket
                            [slot_5] => Item_SolsBulwark
                            [slot_6] => Item_Steamboots
                        )

                    [3133223] => Array
                        (
                            [account_id] => 3133223
                            [match_id] => 163305199
                            [slot_1] => Item_Striders
                            [slot_2] => Item_Spell_Sunder
                            [slot_3] => Item_SpellShards
                            [slot_4] => Item_RestorationStone
                            [slot_5] => Item_MysticVestments
                            [slot_6] => Item_GrimoireOfPower
                        )

                    [4064050] => Array
                        (
                            [account_id] => 4064050
                            [match_id] => 163305199
                            [slot_1] => Item_PortalKey
                            [slot_2] => Item_Excruciator
                            [slot_3] => Item_DaemonicBreastplate
                            [slot_4] => 
                            [slot_5] => Item_Steamboots
                            [slot_6] => Item_MysticVestments
                        )

                    [5695194] => Array
                        (
                            [account_id] => 5695194
                            [match_id] => 163305199
                            [slot_1] => Item_IronBuckler
                            [slot_2] => Item_ManaBurn1
                            [slot_3] => Item_Steamboots
                            [slot_4] => Item_ManaBurn2
                            [slot_5] => Item_MysticVestments
                            [slot_6] => 
                        )

                    [7342714] => Array
                        (
                            [account_id] => 7342714
                            [match_id] => 163305199
                            [slot_1] => Item_Hypercrown
                            [slot_2] => Item_EnhancedMarchers
                            [slot_3] => Item_Dawnbringer
                            [slot_4] => Item_Pierce
                            [slot_5] => 
                            [slot_6] => Item_MysticVestments
                        )

                    [9188454] => Array
                        (
                            [account_id] => 9188454
                            [match_id] => 163305199
                            [slot_1] => Item_Protect
                            [slot_2] => Item_BloodChalice
                            [slot_3] => Item_GraveLocket
                            [slot_4] => Item_LuminousPrism
                            [slot_5] => Item_Steamboots
                            [slot_6] => Item_MysticVestments
                        )

                    [9190611] => Array
                        (
                            [account_id] => 9190611
                            [match_id] => 163305199
                            [slot_1] => Item_PostHaste
                            [slot_2] => Item_Immunity
                            [slot_3] => Item_Morph
                            [slot_4] => Item_HealthMana2
                            [slot_5] => Item_Intelligence7
                            [slot_6] => Item_SpellShards
                        )

                    [9486470] => Array
                        (
                            [account_id] => 9486470
                            [match_id] => 163305199
                            [slot_1] => Item_Immunity
                            [slot_2] => Item_ManaBurn1
                            [slot_3] => Item_BloodChalice
                            [slot_4] => Item_Splash
                            [slot_5] => Item_Bottle
                            [slot_6] => Item_Steamboots
                        )

                    [9491038] => Array
                        (
                            [account_id] => 9491038
                            [match_id] => 163305199
                            [slot_1] => Item_Intelligence7
                            [slot_2] => 
                            [slot_3] => Item_Striders
                            [slot_4] => Item_PortalKey
                            [slot_5] => Item_Nuke
                            [slot_6] => Item_MysticVestments
                        )

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

    [con_reward] => Array
        (
            [old_lvl] => 3
            [curr_lvl] => 3
            [next_lvl] => 4
            [require_rank] => 15
            [need_more_play] => 4
            [percentage_before] => 0.00
            [percentage] => 0.00
        )

    [match_mastery] => Array
        (
            [cli_name] => 
            [mastery_exp_original] => 0
            [mastery_exp_match] => 0
            [mastery_exp_bonus] => 0
            [mastery_exp_boost] => 0
            [mastery_exp_super_boost] => 0
            [mastery_exp_heroes_count] => 0
            [mastery_exp_heroes_addon] => 0
            [mastery_exp_to_boost] => 0
            [mastery_exp_event] => 0
            [mastery_canboost] => 
            [mastery_super_canboost] => 
            [mastery_boost_product_id] => 0
            [mastery_super_boost_product_id] => 0
            [mastery_boostnum] => 0
            [mastery_super_boostnum] => 0
        )

    [season_system] => Array
        (
            [drop_diamonds] => 0
            [cur_diamonds] => 0
            [box_price] => Array
                (
                )

        )

    [vested_threshold] => 5
    [0] => 1
)
```

## Replays

Replays appear to be fetched from the `s3_url` field. (There are also other fields that are maybe legacy or used
as a fallback. Such as `url`, `file_host`, `file_name`, and `dir`.)

The client somehow checks for the existence of the replay. I'm not exactly
sure how this is done. Otherwise you get a "replay unavailable" message.

When `requesting` a replay, it pings the endpiont with `HEAD`.

When pressing `download replay`, the replay is downloaded from the endpoint via `GET`.

The payload is too large to include, so I included the start and end but
omitted much of the middle

```
GET /naeu-icb2/replays/20220416/ovh2USW26/M163305199.honreplay HTTP/1.1
Host: s3.amazonaws.com
Accept: */*

HTTP/1.1 200 OK
x-amz-id-2: +eaI+3mCg9dRknOPcPfY+ue0vpFcIFafaXVBqC59nteRk4EH26+XTn5WczE3Ep3y+dIicia+Ps0=
x-amz-request-id: 9P3C3F6A7ZC7XDGR
Date: Sun, 17 Apr 2022 07:28:33 GMT
Last-Modified: Sun, 17 Apr 2022 07:27:55 GMT
x-amz-expiration: expiry-date="Thu, 28 Apr 2022 00:00:00 GMT", rule-id="remove-replays-and-gamelogs"
ETag: "4cb09c5ca5b2790e43439b710cedfd63"
x-amz-version-id: AmY3bI0s1LuU7QZTEYFgpRO_Yl6urLCs
Accept-Ranges: bytes
Content-Type: binary/octet-stream
Server: AmazonS3
Content-Length: 13845139

PK........\..T%.N.*?...[l.
...replaydata...xT....MMB... ..*..T."".d...@
.,4....;v..;.X...;`...
H..3I...'...=..w.....Z.Z.....gf...8...VE. (\.@P....&D............J.....%..OM	
.	...+.....LNJ...=I...R..PB(&5../....WP.L.a.^blhvP4.9[jtj.a~|......T...v|...Pb...i.-.`.f...-.......@...{&D..4,:q.a.......sn7....:..7(:5f....Q.	i..+..RR.+.zFO...?)q`hf(!k..[.>.n.N
e.	9o....P...E.....JJ
.A...?0:%5...NH..?-..~;PMJ.	....0 >f.a....;.].>|V..a..i...H.yp..L...O.449iRr(%%(.......wk.-..2...;%.OZB......X+NMNJ..........Gi.../.0=....7)!6.M..&......\.C...@.\.O........x.............#.R..R....}L.a....>b|..............e.a{...G.._k...........z...O,cp..#.u..O-|p...k..a#...;.........G......{..|.g.....F.........cd...r..|...o.....>...^..7.g.C..IH.N=.Q.....}{....v.A.nz.....{0.&....~..O........z..P.'....{J
%G.Q.~......V.(...Cy.z...$%&z.....))..wsV..........
E.N.U.....=}P|b....J.........)CC.}..........B1^+..P.A.{1-....[5.....1................tf..e...2..l..u...:[.{.....V.^g....u...:..l..u...:..{.m...6.^g....m...6..l..u...:..{.....v.^.a.}.g..T..].<C.....*.T...[.g|.#.o.....<.u~..>..6...&.x/...:.O..T8..}.._..LJHJ.]....%/..m..xBRjP02....3.S....s^.e]+.

<omitted>

..	L!s..S..)...2..1...W.b
..)L!s..S..Q..S........0.S.....2.o0.\...1...,..9..)...0.S...a
y./...2..0...{L!?B..L!s..)......2..0..."..W..?L!s..S....?L!s..)d..1{......1.:.......
J1g..!.F..U....r6	_.l...8.....9F8.	^.'<.s..i...o}.W.	o..@..S..Ox:.x....
g=.+...qn$.............M.]...Ox.....9...\.+.....J.....Ox	....sn-<p
........6ky..p.Z...D.Sk......xJ.....
.Oi+
6...........S8..>...p....Px5.da..^.(<.s..a...m.y...
.i.?s.,<.y^.(...U..&^.(...].,g.p......9..[m.Ev......q...x...	o..E8n./.....&....
gl.|..S.o.6l..l......9g#.......9wG....a.e.9...{"..B...8...... .o..Y...s.._..Y...oC....a.5^..0.9.a|./.B..<.a.s>..N^..0....q....wQ..0..VE.A....v....+...4.>u.U..Q[0.....&..Y..._../X.......<.	..+..;.b..UbH1..*1....#......bp.@........J...."...x..r....-8.BnQ....[p.An..W.!..<....q.-..Ub.-8O@n.......J....2....J....I.-8OFn....Cn.y
r...J....{.[p....m^%........y..r..3.[p.@nq.W.!..<...;a.?PK........a..T^`.m........
...replayinfo..mO.0....),..........lc.
...P.$n...+.ii?......).....~.;;...%Ck"K*x........).'..........$Y1.R>...a.s{..sX...I.%I...E...+....N..F%.z;...~{.G.-a.|g.rX...f..mc?..KU"1Cg..49..H.X.t.].M...n<FcPY.>xQ..}o8.cj...._m.(U.1.P..LpA.KE%9....u<.rP:..:^...NK.,(...h2>Df..U.`?..n...G..........,..?.*/....#.2QqUC
...y^s&..YP....W.(..WZ.....M.oz5.......hV.....tV....=5..v
.i.....|'..L.p..Alg..6..vOuqn.)lx.Z..{.#...>.9....g...../...8...e.....j.#..X.....c?
.v&..A.....D...r..........].im.......xa..6.+Y..........J...q..C;.gp..e....k3.F.JW.9....*7.B7
.Kn......'M..p.....p?...A....Y..Tf...f....)..X{...Z.........3	...T.@.. ......9wq.U.R...y.:B...j.......avv..../..FU?..w.F.......PK..........\..T%.N.*?...[l.
.................replaydataPK..........a..T^`.m........
.............R?..replayinfoPK..........p...
B....
```

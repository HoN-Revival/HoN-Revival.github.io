---
layout: default
title: client_requester.php?f=autocompleteNicks
parent: PHP Endpoints
grand_parent: Master Server
---

## client_requester.php?f=autocompleteNicks

### Overview

Endpoint is used to autocomplete nicknames. It's used for gifting items,
adding friends, etc. Basically anywhere where you can autocomplete a nickname.

It returns a max of 100 matches. If there is an exact match, it is always the
first result. The result list should be sorted.

### Request

```
POST /client_requester.php?f=autocompleteNicks HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 15
Content-Type: application/x-www-form-urlencoded

nickname=soccer
```

### Response

```
nickname=soccermaniac
a:3:{s:5:"nicks";a:1:{i:0;s:12:"Soccermaniac";}s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
nickname=soccermaniacs

a:2:{i:0;b:0;s:5:"error";s:5:"FALSE";}
```

```
nickname=socer

a:3:{s:5:"nicks";a:8:{i:0;s:5:"Socer";i:1;s:7:"socer12";i:2;s:12:"SOCEREAAAAAL";i:3;s:11:"SOCEREAAAAL";i:4;s:9:"SOCEREAAL";i:5;s:8:"SOCEREAL";i:6;s:8:"Socereee";i:7;s:7:"Socerer";}s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
nickname=soccer

a:3:{s:5:"nicks";a:100:{i:0;s:6:"Soccer";i:1;s:12:"Soccer_Chick";i:2;s:12:"soccer_freak";i:3;s:10:"soccer_man";i:4;s:12:"soccer_mom69";i:5;s:11:"soccer01012";i:6;s:10:"soccer0330";i:7;s:8:"Soccer10";i:8;s:8:"soccer12";i:9;s:9:"soccer14u";i:10;s:9:"soccer199";i:11;s:10:"soccer1996";i:12;s:9:"soccer1mt";i:13;s:7:"Soccer2";i:14;s:10:"soccer2000";i:15;s:9:"soccer313";i:16;s:8:"soccer37";i:17;s:11:"soccer77628";i:18;s:7:"soccer8";i:19;s:8:"soccer90";i:20;s:8:"Soccer92";i:21;s:9:"SoccerAce";i:22;s:11:"soccerant17";i:23;s:11:"soccerant18";i:24;s:11:"soccerant20";i:25;s:10:"SoccerBabe";i:26;s:12:"soccerbabe26";i:27;s:10:"soccerball";i:28;s:11:"SoccerBible";i:29;s:12:"SoccerBlaze3";i:30;s:12:"soccerblaze8";i:31;s:11:"soccerboi12";i:32;s:11:"soccerboiii";i:33;s:12:"soccerboiii2";i:34;s:10:"Soccerboy1";i:35;s:12:"soccerboy242";i:36;s:11:"soccerboy60";i:37;s:12:"soccerboy658";i:38;s:11:"soccerboy66";i:39;s:11:"soccerboy95";i:40;s:11:"SoccerBoyTy";i:41;s:10:"soccerbro4";i:42;s:11:"SOCCERBRO69";i:43;s:9:"soccerbub";i:44;s:9:"SoccerCat";i:45;s:11:"soccercoach";i:46;s:9:"soccerd21";i:47;s:9:"soccerdad";i:48;s:11:"Soccerdad02";i:49;s:11:"SOCCERDAD69";i:50;s:11:"Soccerdad98";i:51;s:11:"SoccerDad99";i:52;s:11:"soccerdash6";i:53;s:12:"soccerdeer12";i:54;s:10:"soccerdev3";i:55;s:9:"Soccerdew";i:56;s:10:"Soccerdood";i:57;s:11:"soccerdude1";i:58;s:12:"soccerdude12";i:59;s:12:"soccerdude13";i:60;s:12:"soccerdude15";i:61;s:12:"SoccerDude69";i:62;s:8:"Soccerer";i:63;s:10:"Soccerer15";i:64;s:8:"Socceres";i:65;s:10:"SoccerFace";i:66;s:12:"Soccerfan580";i:67;s:10:"soccerfan8";i:68;s:12:"SoccerFather";i:69;s:10:"soccerfive";i:70;s:9:"Soccerfox";i:71;s:11:"soccerfreak";i:72;s:12:"Soccerfreak1";i:73;s:11:"soccerfreaz";i:74;s:12:"soccergirl13";i:75;s:12:"soccergirl17";i:76;s:10:"SoccerGOAL";i:77;s:12:"Soccergoal10";i:78;s:11:"SoccergoalE";i:79;s:10:"Soccergurl";i:80;s:9:"SoccerGuy";i:81;s:12:"soccerguy410";i:82;s:10:"soccerguy8";i:83;s:10:"SoccerHero";i:84;s:12:"soccerhunk48";i:85;s:10:"Soccerinfo";i:86;s:12:"SoccerIsCool";i:87;s:11:"soccerisfun";i:88;s:11:"Soccerisgay";i:89;s:8:"Soccerj7";i:90;s:11:"SoccerJoker";i:91;s:10:"soccerjonp";i:92;s:9:"SoCCerKiD";i:93;s:11:"SoccerKid02";i:94;s:12:"soccerkid255";i:95;s:11:"soccerkid98";i:96;s:11:"soccerkid99";i:97;s:12:"Soccerkiller";i:98;s:10:"soccerking";i:99;s:11:"soccerking1";}s:16:"vested_threshold";i:5;i:0;b:1;}
```
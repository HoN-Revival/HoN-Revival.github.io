---
layout: default
title: Report a Player
parent: Heroesofnewerth.com
---

## /rap/report2.php

This endpoint is called for reports when `cl_Rap2Enable` is `false`.

I find this very confusing since this is `report2` yet `Rap2Enable` is `false`... yeah that makes sense...

This appears to be the default at least on my client.

### Request

```
POST /rap/report2.php HTTP/1.1
Host: heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 160
Content-Type: application/x-www-form-urlencoded

account_id=2&cookie=86C79287456AC956C103C7B2F8287153&offenderName%5B%5D=way2addictin&match_id%5B%5D=163305199&type%5B%5D=4&body%5B%5D=i+report+you&time%5B%5D=13
```

- `account_id`: Account ID of the person filing the report
- `cookie`: The cookie for the users session
- `offenderName`: The name of the offende who is being reported.
    - This field appears to have an empty index as if it 'could' support multiple offenders.
      e.g. `offenderName[]=someUsername`
- `match_id`: The match ID for the report
    - This field appears to have an empty index as if it 'could' support multiple matches
      e.g. `match_id[]=12345`
- `type`: The report type option selected in the popup. (1-based index)
    - Index 1 => Chat Abuse
    - Index 2 => Feeding / Stat Manipulation
    - Index 3 => Impersonating Staff
    - Index 4 => Ability / Item Abuse
    - Index 5 => Bad Nickname / Clan Name
    - Index 6 => Refusal to Participate / Avoiding AFK
    - This field appears to have an empty index as if it 'could' support multiple offenders.
      e.g. `offenderName[]=someUsername`
- `body`: The string of text in the report description
    - The in-game UI limits this to 210 characters. (Ironically it overflows the visual
      text field in the new UI... typical S2/Frostburn)
    - This field appears to have an empty index as if it 'could' support multiple offenders.
      e.g. `body[]=i+report+you` where the text was "I report you"
- `time`: The time set by the slider in the report popup.
    - This appears to just show the minute of the game. Even though the in-game UI shows
      second granularity, it's not sent over the wire.
    - This field appears to have an empty index as if it 'could' support multiple offenders.
      e.g. `time[]=13` (for 13 minutes)
      
      
## /master/report/reportinforequest

This seems to get requested when `cl_Rap2Enable` is `true`.

I don't have captures for the response.

### Request

```
POST /master/report/reportinforequest HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 52
Content-Type: application/x-www-form-urlencoded

account_id=2&cookie=1F13DE2A137C5ABA7D39B4EAD09A075D
```

- `account_id`: The current users account.
- `cookie`: The session cookie for the user.

## /master/report/report

This endpoint is called for reports when `cl_Rap2Enable` is `true`.

I find this very confusing since this is `report2.php` is called instead when its `false`...

### Request

```
POST /master/report/report HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 120
Content-Type: application/x-www-form-urlencoded

reporter_id=2&cookie=1F13DE2A137C5ABA7D39B4EAD09A075D&reportee_name=DONOFRlO&reason_type=4&report_description=abc+def%27
```

- `reporter_id`: The ID of the user issuing the report
- `cookie`: The cookie for the user's session.
- `reportee_name`: The name of the person being reported in the form
- `reason_type`: The report type option selected in the popup. (1-based index)
    - Index 1 => Chat Abuse
    - Index 2 => Feeding / Stat Manipulation
    - Index 3 => Impersonating Staff
    - Index 4 => Ability / Item Abuse
    - Index 5 => Bad Nickname / Clan Name
    - Index 6 => Refusal to Participate / Avoiding AFK
- `report_description`: The string of text in the report description
    - The in-game UI limits this to 210 characters. (Ironically it overflows the visual
      text field in the new UI... typical S2/Frostburn)

## Unused?

### /rap/report.php

This does not appear to be used anywhere in code anymore.

### /rap/player_list.php

Unknown where this is called. I can't find anywhere it's used in the UI.

```
<!-- Query for player list from match
		[0] Boolean for success (0 or 1)
		[1-10] Nicknames of players in match.  If slot is not taken, that value will be missing from
		[11-20] Slot id for players respectively.  Slot id is 0-9, 0 being blue, and 5 being pink
	-->
	<trigger name="RAPGetPlayersFromMatchIDStatus"/>
	<trigger name="RAPGetPlayersFromMatchIDResult"/>
	<form
		name="GetPlayersFromMatchID"
		host="!hon"
		target="/rap/player_list.php"
		ssl="true"
		method="post"
		statustrigger="RAPGetPlayersFromMatchIDStatus"
		resulttrigger="RAPGetPlayersFromMatchIDResult"
		resultparam0="0"
		resultparam1="1"
		resultparam2="2"
		resultparam3="3"
		resultparam4="4"
		resultparam5="5"
		resultparam6="6"
		resultparam7="7"
		resultparam8="8"
		resultparam9="9"
		resultparam10="10"
		resultparam11="11"
		resultparam12="12"
		resultparam13="13"
		resultparam14="14"
		resultparam15="15"
		resultparam16="16"
		resultparam17="17"
		resultparam18="18"
		resultparam19="19"
		resultparam20="20"
		resultparam21="21"
		resultparam22="22"
		resultparam23="23"
		resultparam24="24"
		resultparam25="25"
		resultparam26="26"
		resultparam27="27"
		resultparam28="28"
		resultparam29="29"
		resultparam30="30"
	/>
```

### /rap/match_list2.php

Unknown where this is called. I can't find anywhere it's used in the UI.

```
	<!-- Match List for Account 
		 Param0 is success/error.  The rest are matches
	-->
	<trigger name="RAPGetRecentMatchesStatus"/>
	<trigger name="RAPGetRecentMatchesResult"/>	
	<form
		name="RAPGetRecentMatches"
		host="!hon"
		target="/rap/match_list2.php"
		ssl="true"
		method="post"
		statustrigger="RAPGetRecentMatchesStatus"
		resulttrigger="RAPGetRecentMatchesResult"
		resultparam0="0"
		resultparam1="1"
		resultparam2="2"
		resultparam3="3"
		resultparam4="4"
		resultparam5="5"
		resultparam6="6"
		resultparam7="7"
		resultparam8="8"
		resultparam9="9"
		resultparam10="10"
		resultparam11="11"
		resultparam12="12"
		resultparam13="13"
		resultparam14="14"
		resultparam15="15"
		resultparam16="16"
		resultparam17="17"
		resultparam18="18"
		resultparam19="19"
		resultparam20="20"
		resultparam21="21"
		resultparam22="22"
		resultparam23="23"
		resultparam24="24"
		resultparam25="25"
		resultparam26="26"
		resultparam27="27"
		resultparam28="28"
		resultparam29="29"
		resultparam30="30"
		resultparam31="31"
		resultparam32="32"
		resultparam33="33"
		resultparam34="34"
		resultparam35="35"
		resultparam36="36"
		resultparam37="37"
		resultparam38="38"
		resultparam39="39"
		resultparam40="40"
	/>
```
---
layout: default
title: /master/storage
parent: PHP Endpoints
grand_parent: Master Server
---

# /master/storage

This endpoint supports cloud storage of settings. The settings are part of
`startup.cfg`. A subset of these settings are uploaded/downloaded via
`cloud.cfg` from the user's documents folder.

It's uploaded as a `zip`.

## /master/cloud/set-user-enrollment

- Request

`enroll` maps to `use_cloud`.

```
POST /master/cloud/set-user-enrollment HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 375
Content-Type: multipart/form-data; boundary=------------------------6b83cb4e6823383a

--------------------------6b83cb4e6823383a
Content-Disposition: form-data; name="cookie"

d1ec673fac4dcccee1d1910f6a337cd7
--------------------------6b83cb4e6823383a
Content-Disposition: form-data; name="enroll"

1
--------------------------6b83cb4e6823383a
Content-Disposition: form-data; name="cloud_autoupload"

0
--------------------------6b83cb4e6823383a--
```

- Response

```
HTTP/1.1 200 OK
Date: Sat, 23 Apr 2022 23:47:40 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 155
Connection: close
Content-Type: text/plain; charset=UTF-8

a:2:{s:7:"success";b:1;s:4:"data";a:4:{s:10:"account_id";s:7:"9445002";s:9:"use_cloud";s:1:"1";s:16:"cloud_autoupload";s:1:"0";s:16:"file_modify_time";N;}}
```

```
Array
(
    [success] => 1
    [data] => Array
        (
            [account_id] => 9445002
            [use_cloud] => 1
            [cloud_autoupload] => 0
            [file_modify_time] => 
        )

)
```

## /master/storage/status

This returns the status for a given user regarding their cloud
storage status.

- Request

```
POST /master/storage/status HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 284
Content-Type: multipart/form-data; boundary=------------------------a5f0afc0cadd3c91

--------------------------a5f0afc0cadd3c91
Content-Disposition: form-data; name="cookie"

c67462151f977564c8dd37aac3e27e46
--------------------------a5f0afc0cadd3c91
Content-Disposition: form-data; name="bucket"

hon-game-configs
--------------------------a5f0afc0cadd3c91--
```

- Response

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2022 04:45:52 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 229
Connection: close
Content-Type: text/plain; charset=UTF-8

a:4:{s:7:"success";b:1;s:4:"data";N;s:18:"cloud_storage_info";a:4:{s:10:"account_id";s:6:"782203";s:9:"use_cloud";s:1:"1";s:16:"cloud_autoupload";s:1:"0";s:16:"file_modify_time";s:19:"2021-04-05 23:54:46";}s:8:"messages";s:0:"";}
```

```
Array
(
    [success] => 1
    [data] => 
    [cloud_storage_info] => Array
        (
            [account_id] => 782203
            [use_cloud] => 1
            [cloud_autoupload] => 0
            [file_modify_time] => 2021-04-05 23:54:46
        )

    [messages] => 
)
```

- Response if no data

```
HTTP/1.1 200 OK
Date: Sat, 23 Apr 2022 23:04:06 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 89
Connection: close
Content-Type: text/plain; charset=UTF-8

a:4:{s:7:"success";b:1;s:4:"data";N;s:18:"cloud_storage_info";b:0;s:8:"messages";s:0:"";}
```

- Response on error:

```
HTTP/1.1 200 OK
Date: Sat, 23 Apr 2022 23:13:11 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 15
Connection: close
Content-Type: text/html; charset=UTF-8

invalid_request
```

## /master/storage/store

- Request

```
POST /master/storage/store HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 4952
Content-Type: multipart/form-data; boundary=------------------------0802479efdec8804

--------------------------0802479efdec8804
Content-Disposition: form-data; name="cookie"

c67462151f977564c8dd37aac3e27e46
--------------------------0802479efdec8804
Content-Disposition: form-data; name="bucket"

hon-game-configs
--------------------------0802479efdec8804
Content-Disposition: form-data; name="file_modify_time"

2022-04-09 21:49:07
--------------------------0802479efdec8804
Content-Disposition: form-data; name="cloud.zip"; filename="cloud.zip"
Content-Type: application/octet-stream

PK........#..T.l......v...	...cloud.cfg..Ys.6....U.......y.z........X.x.T..C.....dO.....F..(.T......I....q6@.....q....m...}...{.{....C......2../.s.).p.
W..!..g...\.*#a.,...-.......~.
.>..[...N.Y...?.."x....G..2b...E.90.g....TR.~.,.}8^.5}...]...wp$R....$>.9\{.s.`.....#...3+..w..@..D.	.w......7.pt.).........H......e.	...K.=..lu...m.C87..!.E.......9.....YZ.BC..*W-.w.~. .8..'....\..G6..(q....%umY........s..-?*/....%..	.h......T.v...Ke.........R....8z...K...8w.....O..'.......y..vRr..}.V.U......W.iNs./.......C>{..]83A..c..#..ms...]%..;]4.2...6a.?A.]y)...[..+>..u^......u].*..2.0.~.Zq.l;..y...P......	J..R.`>..Y....!.M0.l..6m..j.N.....Fi...@K.`m....eOK..g.)....v....N.t.[.Uw.g.m...i.IZw...n.D{w.5.l.f.ey.m..s.L.....+.M2u0.6R.Y.F..q....R>`/Y.....\A~....gh..X.......s..f.?..e..m....s.....H...X~.[..H.!.......nZ.....[.[...X.>c.n.O`..R...Zm.4;Z.A..aS.S...6.A.4.Q
-S..e.7F..U..D..v|.v.....gk.>.[8...].X?.,..-k.,:.1..q.....z.{.-..l/k.e.....).gk..+.&..Q.....,x......U,?.X~R....kf...2=z..P..{zWCT...r
I....khV..Z.....;g..UF:....5..Lqm...45j...4]`....G8.Vy...../..&&.D.Q...H..Q....kl.d..]....Jmz]k..	.Y=...W5....7.......SG.e.t\...XB.$..G..(.$.....m-$..Q....q.P>..O.........3q.a.g.#7o..R....(.H....%.......>...h..0v2V.|j..1..W,."...=..t|}.u........{....tL5../..r.H.....@{...S:..y......W..o+IM.zB..*,......<.EQUY.....#...6b....4.[.....|n	.Q.....F2.U.p..'...G.t.O.8K\. ...r^,............S.Vw[......%.~.g..v[.J......{h.~.j3...=.a..t....3...g.?..g................|m...m..L=..s.f.#.?	
.m...H.J...D....k......-...>i....e..du2O.CV.QV........R.....bO.bo..."..|=c......L<>e..S6."\...+.M.O.....G...>e..S.<z3....m.....J...I.....d...i.?......W.....`..-6.....!........}....]bH...._...........F(a.
#.[..uv....\<6.3...u.i......k.....)..Q:O...+H...=G.!A...?{`.b.c...H.}.UQ.
..s....6i....X...U.0.._...lH..=0..lX.gC.g.Z=.......<0..lT.g#.g.Z=.n..kA.=....R....Y...R.7...>o..7.rz.......v1..u.t	...`.t.....Vo&Lo.5z.Ax.Q+..g..z...l..l..m.,=g...l...&......".."X>;.w.f.Vo...l...6..6.2r....v..l3...........'g...............?.......f..ap..=...4
../4..Y|.W.../b.E^.b.....{.K...._...a..`.5..5
..,..W..._......6.k...^.:.|.._..O....6L..|P....Y...[..NM.-...(...I.q....%.....M.....{K...yp.....`.......CJ*....".J.#+5rV.fRp....J1.];4.R3g.c&.7JuX....J......>2).V
k..........4dRp...j.&i...Jq.J\
.....g..:.wbf.g...R...........c..*....j.....=..>W..Eg..r.\......_.e..../...|.....GU[..K....R$...>.|.C.|w..X#.c.;../.9...../..r..;...:....I\..qg..t?...)4NE.....SF..(J.U...q*.Q...	..T....:.fz.5.t.>....W....xw.o.M..?...._..y..T.......b...}....W..z..zP..J....{....Yt...'..
~.n.>}.[.y6.s|./.v..0.e....../.
{Mb7.............W...-4f...-6`....^........#....Xc...J...,.vw.-;[u...	.#..3t.m7.....%z........W...N...3.....V.T.i..r...r..)h8. ........~S.m.Y*:....p
....T.<.2...t?\.4..._.pf..c.{8.M....-..#...Yw...X..R.e.y'T.b......#........5>...#.
k6....k..w.+?o2..g.F...;'j...T4..._.
G./_......q..[.:.Tq...&m.=....E.9....{.5......2.....3...	...&i...4.n.ns..=pk.5...m. v.S^k...[....#K..khE.>..0...z.
....@..+2.....g.....	....#.:*.x.j.q.+:....F\.J..g..........m.E..l{...q.+6;.\...f.k*>[....*.V=f5.#M...,.[.L....g]..@:.Y[X.z.VD...CK.."..E.Y.G...,...>..>a.'..IE.
.}...Q.}.E...oVD.b..,.[...Y.mK.vE...}......P;p..g.c^1.(.;LU._...r.Ik..g.e.."j,..~R...^;.{...Q......,my.........;.
.>Y..M.....x..k.<.Me....S..!...w........../p%.
.
w...9/;OG....!...l..+Z`.....5z....C.U.h..#YH.qF..G..$...#.d1I..........;O<.5H2N.....I.qz.M.d-...cny$k.d..p.#Y.$..t;.d..]..S....{7...[..U.F.>.....v....N..|<.....c.b..~7.Qq.CF=......l..................O....hG_H..r.....H}.....}1...A_cG_B..8.k..k..N...v.5I}?9.k..k..~v.....&......>J......mt]&..9..?.. 1j>.&..}...[...{.._Z...y....u..;].?Z.....An.../.t)..?..8].{.....VH..
R..wV.....=F4.}q..../..Z....[.w5.........|..... .|......9.....Ri..W...o.h#k.....mck.........v.~...v........O.....H..f.3%.t"......;Mi.V.f..p|..fF.R...ET....$..D....$..D....$J.D....I.`.5<.5I.&.....E...D-.Dm... j;.m.H~-.{.iM...+f..0Yn......9.l.....@3V....{c.....f..0'...@.....}.2...k.u...[|..N..1......4]..1ew.....?....,.....T.[.;.i$....a....'_..3....V'.>....^........8M.2{T....;8.....
...-.s{.......v.......9.^......^..j..5.......
s.....vw..Z%.. ZH.t...K..d..f.Y.uo.yp...^i.....-1..R_......ow...g..(
:............^...^q|!W...Z..........w.U.]...<.E..'../).....7O...9Q~^b.#..r].h..gI..7..vo..vo.d1D$EbD..Q..R....*..}D..n;1km..D......\Z....m......y.}.M.lr.i..H...nqd.1w?....}..#..U.....cl|..PK..........#..T.l......v...	.................cloud.cfgPK..........7.........
--------------------------0802479efdec8804--
```

- Response

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2022 04:49:07 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 46
Connection: close
Content-Type: text/plain; charset=UTF-8

a:2:{s:7:"success";b:1;s:8:"messages";s:0:"";}
```

## /master/storage/retrieve

- Request

```
POST /master/storage/retrieve HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 284
Content-Type: multipart/form-data; boundary=------------------------84f955735abb55f9

--------------------------84f955735abb55f9
Content-Disposition: form-data; name="cookie"

c67462151f977564c8dd37aac3e27e46
--------------------------84f955735abb55f9
Content-Disposition: form-data; name="bucket"

hon-game-configs
--------------------------84f955735abb55f9--
```

- Response

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2022 04:51:20 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Description: File Transfer
Content-Disposition: attachment; filename=782203.zip
Content-Transfer-Encoding: binary
Expires: 0
Cache-Control: must-revalidate
Pragma: public
Content-Length: 4384
Connection: close
Content-Type: application/octet-stream

PK........#..T.l......v...	...cloud.cfg..Ys.6....U.......y.z........X.x.T..C.....dO.....F..(.T......I....q6@.....q....m...}...{.{....C......2../.s.).p.
W..!..g...\.*#a.,...-.......~.
.>..[...N.Y...?.."x....G..2b...E.90.g....TR.~.,.}8^.5}...]...wp$R....$>.9\{.s.`.....#...3+..w..@..D.	.w......7.pt.).........H......e.	...K.=..lu...m.C87..!.E.......9.....YZ.BC..*W-.w.~. .8..'....\..G6..(q....%umY........s..-?*/....%..	.h......T.v...Ke.........R....8z...K...8w.....O..'.......y..vRr..}.V.U......W.iNs./.......C>{..]83A..c..#..ms...]%..;]4.2...6a.?A.]y)...[..+>..u^......u].*..2.0.~.Zq.l;..y...P......	J..R.`>..Y....!.M0.l..6m..j.N.....Fi...@K.`m....eOK..g.)....v....N.t.[.Uw.g.m...i.IZw...n.D{w.5.l.f.ey.m..s.L.....+.M2u0.6R.Y.F..q....R>`/Y.....\A~....gh..X.......s..f.?..e..m....s.....H...X~.[..H.!.......nZ.....[.[...X.>c.n.O`..R...Zm.4;Z.A..aS.S...6.A.4.Q
-S..e.7F..U..D..v|.v.....gk.>.[8...].X?.,..-k.,:.1..q.....z.{.-..l/k.e.....).gk..+.&..Q.....,x......U,?.X~R....kf...2=z..P..{zWCT...r
I....khV..Z.....;g..UF:....5..Lqm...45j...4]`....G8.Vy...../..&&.D.Q...H..Q....kl.d..]....Jmz]k..	.Y=...W5....7.......SG.e.t\...XB.$..G..(.$.....m-$..Q....q.P>..O.........3q.a.g.#7o..R....(.H....%.......>...h..0v2V.|j..1..W,."...=..t|}.u........{....tL5../..r.H.....@{...S:..y......W..o+IM.zB..*,......<.EQUY.....#...6b....4.[.....|n	.Q.....F2.U.p..'...G.t.O.8K\. ...r^,............S.Vw[......%.~.g..v[.J......{h.~.j3...=.a..t....3...g.?..g................|m...m..L=..s.f.#.?	
.m...H.J...D....k......-...>i....e..du2O.CV.QV........R.....bO.bo..."..|=c......L<>e..S6."\...+.M.O.....G...>e..S.<z3....m.....J...I.....d...i.?......W.....`..-6.....!........}....]bH...._...........F(a.
#.[..uv....\<6.3...u.i......k.....)..Q:O...+H...=G.!A...?{`.b.c...H.}.UQ.
..s....6i....X...U.0.._...lH..=0..lX.gC.g.Z=.......<0..lT.g#.g.Z=.n..kA.=....R....Y...R.7...>o..7.rz.......v1..u.t	...`.t.....Vo&Lo.5z.Ax.Q+..g..z...l..l..m.,=g...l...&......".."X>;.w.f.Vo...l...6..6.2r....v..l3...........'g...............?.......f..ap..=...4
../4..Y|.W.../b.E^.b.....{.K...._...a..`.5..5
..,..W..._......6.k...^.:.|.._..O....6L..|P....Y...[..NM.-...(...I.q....%.....M.....{K...yp.....`.......CJ*....".J.#+5rV.fRp....J1.];4.R3g.c&.7JuX....J......>2).V
k..........4dRp...j.&i...Jq.J\
.....g..:.wbf.g...R...........c..*....j.....=..>W..Eg..r.\......_.e..../...|.....GU[..K....R$...>.|.C.|w..X#.c.;../.9...../..r..;...:....I\..qg..t?...)4NE.....SF..(J.U...q*.Q...	..T....:.fz.5.t.>....W....xw.o.M..?...._..y..T.......b...}....W..z..zP..J....{....Yt...'..
~.n.>}.[.y6.s|./.v..0.e....../.
{Mb7.............W...-4f...-6`....^........#....Xc...J...,.vw.-;[u...	.#..3t.m7.....%z........W...N...3.....V.T.i..r...r..)h8. ........~S.m.Y*:....p
....T.<.2...t?\.4..._.pf..c.{8.M....-..#...Yw...X..R.e.y'T.b......#........5>...#.
k6....k..w.+?o2..g.F...;'j...T4..._.
G./_......q..[.:.Tq...&m.=....E.9....{.5......2.....3...	...&i...4.n.ns..=pk.5...m. v.S^k...[....#K..khE.>..0...z.
....@..+2.....g.....	....#.:*.x.j.q.+:....F\.J..g..........m.E..l{...q.+6;.\...f.k*>[....*.V=f5.#M...,.[.L....g]..@:.Y[X.z.VD...CK.."..E.Y.G...,...>..>a.'..IE.
.}...Q.}.E...oVD.b..,.[...Y.mK.vE...}......P;p..g.c^1.(.;LU._...r.Ik..g.e.."j,..~R...^;.{...Q......,my.........;.
.>Y..M.....x..k.<.Me....S..!...w........../p%.
.
w...9/;OG....!...l..+Z`.....5z....C.U.h..#YH.qF..G..$...#.d1I..........;O<.5H2N.....I.qz.M.d-...cny$k.d..p.#Y.$..t;.d..]..S....{7...[..U.F.>.....v....N..|<.....c.b..~7.Qq.CF=......l..................O....hG_H..r.....H}.....}1...A_cG_B..8.k..k..N...v.5I}?9.k..k..~v.....&......>J......mt]&..9..?.. 1j>.&..}...[...{.._Z...y....u..;].?Z.....An.../.t)..?..8].{.....VH..
R..wV.....=F4.}q..../..Z....[.w5.........|..... .|......9.....Ri..W...o.h#k.....mck.........v.~...v........O.....H..f.3%.t"......;Mi.V.f..p|..fF.R...ET....$..D....$..D....$J.D....I.`.5<.5I.&.....E...D-.Dm... j;.m.H~-.{.iM...+f..0Yn......9.l.....@3V....{c.....f..0'...@.....}.2...k.u...[|..N..1......4]..1ew.....?....,.....T.[.;.i$....a....'_..3....V'.>....^........8M.2{T....;8.....
...-.s{.......v.......9.^......^..j..5.......
s.....vw..Z%.. ZH.t...K..d..f.Y.uo.yp...^i.....-1..R_......ow...g..(
:............^...^q|!W...Z..........w.U.]...<.E..'../).....7O...9Q~^b.#..r].h..gI..7..vo..vo.d1D$EbD..Q..R....*..}D..n;1km..D......\Z....m......y.}.M.lr.i..H...nqd.1w?....}..#..U.....cl|..PK..........#..T.l......v...	.................cloud.cfgPK..........7.........
```

- Response (not found)

```
HTTP/1.1 200 OK
Date: Sat, 23 Apr 2022 23:49:18 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 80
Connection: close
Content-Type: text/plain; charset=UTF-8

a:2:{s:7:"success";b:0;s:8:"messages";s:33:"The specified key does not exist.";}
```

## Example settings

```
SetSave "cam_edgeScroll" "true" "0"
SetSave "cam_scrollSpeed" "2999.9998" "0"
SetSave "cg_altInfoAlpha" "false" "0"
SetSave "cg_altInfoColorScheme" "2" "1"
SetSave "cg_altInfoLarge" "false" "0"
SetSave "cg_altInfoNameAboveHP" "0" "1"
SetSave "cg_altInfoNegativeEffects" "true" "0"
SetSave "cg_altInfoPips" "true" "1"
SetSave "cg_alwaysShowHealthBars" "true" "0"
SetSave "cg_alwaysShowHeroSelectionRings" "true" "0"
SetSave "cg_autoSelectSummonings" "true" "0"
SetSave "cg_banjo_sound" "1" "0"
SetSave "cg_cameraCenterOnRespawn" "true" "0"
SetSave "cg_censorChat" "false" "0"
SetSave "cg_cmdrDoubleActivate" "true" "0"
SetSave "cg_constrainCursor" "true" "0"
SetSave "cg_current_weather" "" "0"
SetSave "cg_defaultInterface" "/ui/game_legacy.interface" "0"
SetSave "cg_disableBackgroundEffects" "true" "0"
SetSave "cg_drawPopupCritical" "true" "0"
SetSave "cg_drawPopupDamage" "true" "0"
SetSave "cg_drawPopupNegativeEffect" "true" "0"
SetSave "cg_drawRewardExp" "false" "0"
SetSave "cg_drawRewardGold" "true" "0"
SetSave "cg_enableClientInfo" "true" "0"
SetSave "cg_enableLoginAnimation" "true" "0"
SetSave "cg_enableMinimapRightclick" "true" "0"
SetSave "cg_enableSelfDiffColor" "true" "1"
SetSave "cg_heroIndicators" "false" "1"
SetSave "cg_hideFullHealthBars" "false" "0"
SetSave "cg_lockCameraGame" "false" "0"
SetSave "cg_minimapPathEnabled" "true" "0"
SetSave "cg_moveHeroToSpawnOnDisconnect" "true" "0"
SetSave "cg_muteAnnouncerVoice" "false" "0"
SetSave "cg_muteMinimapPing_VoiceMutedAllies" "true" "0"
SetSave "cg_muteUIPing" "false" "0"
SetSave "cg_noSwitchToNoRenderUnits" "false" "0"
SetSave "cg_restrictTeleportEffectToAllies" "false" "0"
SetSave "cg_rightClickDeny" "true" "0"
SetSave "cg_safeChannel" "false" "0"
SetSave "cg_sendNegativeEffectPopup" "true" "0"
SetSave "cg_sendPingToUIDelay" "150" "0"
SetSave "cg_showExperienceRangeIndicator" "true" "0"
SetSave "cg_showHeroHealthLerp" "true" "0"
SetSave "cg_showLineCast" "true" "0"
SetSave "cg_showPlayerSelectionRings" "true" "0"
SetSave "cg_showSelectionRings" "true" "1"
SetSave "cg_showSelectionRingsWhenHovered" "false" "0"
SetSave "cg_smartcastingAbility_1" "false" "0"
SetSave "cg_smartcastingAbility_2" "false" "0"
SetSave "cg_smartcastingAbility_3" "false" "0"
SetSave "cg_smartcastingAbility_4" "false" "0"
SetSave "cg_smartcastingAbility_Taunt" "false" "0"
SetSave "cg_smartcastingBackpack_1" "false" "0"
SetSave "cg_smartcastingBackpack_2" "false" "0"
SetSave "cg_smartcastingBackpack_3" "false" "0"
SetSave "cg_smartcastingBackpack_4" "false" "0"
SetSave "cg_smartcastingBackpack_5" "false" "0"
SetSave "cg_smartcastingBackpack_6" "false" "0"
SetSave "cg_smartcastingBackpack_Ward" "false" "0"
SetSave "cg_smartcastingBackpack_Ward2" "false" "0"
SetSave "cg_smartcastingExtraAbility_1" "false" "0"
SetSave "cg_smartcastingExtraAbility_2" "false" "0"
SetSave "cg_smartcastingExtraAbility_3" "false" "0"
SetSave "cg_smartcastingExtraAbility_4" "false" "0"
SetSave "cg_smartcastingExtraAbility_5" "false" "0"
SetSave "cg_smartcastingExtraAbility_6" "false" "0"
SetSave "cg_smartcastingOrderAttack" "false" "0"
SetSave "cg_smartcastingType" "1" "0"
SetSave "cg_toolPersistantTargetIndicatorEnable" "true" "0"
SetSave "cg_towerTargetEffect" "true" "0"
SetSave "cg_unitPlayerColors" "true" "0"
SetSave "cg_unitVoiceResponses" "true" "0"
SetSave "cg_unitVoiceResponsesDelay" "5000" "0"
SetSave "cg_useHeroIcon2" "false" "0"
SetSave "cg_useLongTooltips" "true" "0"
SetSave "chat_filterChatSounds" "true" "0"
SetSave "chat_filterHeroIcons" "true" "0"
SetSave "chat_filterHeroNames" "false" "0"
SetSave "chat_filterShortFormat" "true" "0"
SetSave "chat_showChatTimestamps" "true" "0"
SetSave "ebuff_cfgActive_blinkenabled" "false" "0"
SetSave "ebuff_cfgActive_dectimer" "1" "0"
SetSave "ebuff_cfgActive_overheadlbl" "true" "0"
SetSave "ebuff_cfgActive_popdispassive" "false" "0"
SetSave "ebuff_cfgActive_popenabled" "false" "0"
SetSave "ebuff_cfgActive_showlbl" "true" "0"
SetSave "ebuff_cfgActive_timerbar" "true" "0"
SetSave "g_minimapPortraitAndColorType" "2" "0"
SetSave "g_unitPlayDenyAnims" "true" "0"
SetSave "hero_holdAfterMove" "false" "0"
SetSave "shop_confirm_buyall" "false" "0"
SetSave "social_customColors" "true" "0"
SetSave "social_offlineInGames" "false" "0"
SetSave "social_sortOnlineFirst" "true" "0"
SetSave "sound_disable" "false" "0"
SetSave "sound_mute" "false" "0"
SetSave "sound_muteMusic" "true" "0"
SetSave "sound_numChannels" "128" "0"
SetSave "ui_game_chat_sounds" "true" "0"
SetSave "ui_hideGameHeroTips" "1" "0"
SetSave "ui_minimap_rightside" "false" "0"
SetSave "ui_not_opt_17_1" "false" "0"
SetSave "ui_not_opt_17_2" "true" "0"
SetSave "ui_not_opt_17_3" "true" "0"
SetSave "ui_not_opt_19_1" "true" "0"
SetSave "ui_not_opt_19_2" "true" "0"
SetSave "ui_not_opt_19_3" "false" "0"
SetSave "ui_not_opt_20_1" "false" "0"
SetSave "ui_not_opt_20_2" "true" "0"
SetSave "ui_not_opt_20_3" "true" "0"
SetSave "ui_not_opt_23_1" "true" "0"
SetSave "ui_not_opt_23_2" "true" "0"
SetSave "ui_not_opt_23_3" "true" "0"
SetSave "ui_not_opt_24_1" "false" "0"
SetSave "ui_not_opt_24_2" "true" "0"
SetSave "ui_not_opt_24_3" "true" "0"
SetSave "ui_not_opt_25_1" "false" "0"
SetSave "ui_not_opt_25_2" "false" "0"
SetSave "ui_not_opt_25_3" "false" "0"
SetSave "ui_not_opt_26_1" "false" "0"
SetSave "ui_not_opt_26_2" "true" "0"
SetSave "ui_not_opt_26_3" "true" "0"
SetSave "ui_not_opt_27_1" "false" "0"
SetSave "ui_not_opt_27_2" "true" "0"
SetSave "ui_not_opt_27_3" "false" "0"
SetSave "ui_not_opt_sound" "true" "0"
SetSave "ui_notifications_toastDuration" "7.0000" "0"
SetSave "ui_unlimitedPings" "1" "0"
SetSave "voice_audioDampen" "0.4000" "0"
SetSave "voice_disabled" "false" "0"
SetSave "voice_pushToTalk" "true" "0"
GameReBind Ability1 ActivateTool "0" button game "Q" "INVALID"
GameReBind Ability10 ActivateTool "10" button game "K" "INVALID"
GameReBind Ability10Secondary ActivateToolSecondary "10" impulse game "INVALID" "INVALID"
GameReBind Ability10Self ActivateToolSelf "10" button game "INVALID" "INVALID"
GameReBind Ability11 ActivateTool "11" button game "L" "INVALID"
GameReBind Ability11Secondary ActivateToolSecondary "11" impulse game "INVALID" "INVALID"
GameReBind Ability11Self ActivateToolSelf "11" button game "INVALID" "INVALID"
GameReBind Ability12 ActivateTool "12" button game "~" "INVALID"
GameReBind Ability12Secondary ActivateToolSecondary "12" impulse game "INVALID" "INVALID"
GameReBind Ability12Self ActivateToolSelf "12" button game "INVALID" "INVALID"
GameReBind Ability1Secondary ActivateToolSecondary "0" impulse game "INVALID" "INVALID"
GameReBind Ability1Self ActivateToolSelf "0" button game "INVALID" "INVALID"
GameReBind Ability2 ActivateTool "1" button game "W" "INVALID"
GameReBind Ability2Secondary ActivateToolSecondary "1" impulse game "INVALID" "INVALID"
GameReBind Ability2Self ActivateToolSelf "1" button game "INVALID" "INVALID"
GameReBind Ability3 ActivateTool "2" button game "E" "INVALID"
GameReBind Ability3Secondary ActivateToolSecondary "2" impulse game "INVALID" "INVALID"
GameReBind Ability3Self ActivateToolSelf "2" button game "INVALID" "INVALID"
GameReBind Ability4 ActivateTool "3" button game "R" "INVALID"
GameReBind Ability4Secondary ActivateToolSecondary "3" impulse game "INVALID" "INVALID"
GameReBind Ability4Self ActivateToolSelf "3" button game "INVALID" "INVALID"
GameReBind Ability5 ActivateTool "5" button game "INVALID" "INVALID"
GameReBind Ability5Secondary ActivateToolSecondary "5" impulse game "INVALID" "INVALID"
GameReBind Ability5Self ActivateToolSelf "5" button game "INVALID" "INVALID"
GameReBind Ability6 ActivateTool "6" button game "F" "INVALID"
GameReBind Ability6Secondary ActivateToolSecondary "6" impulse game "INVALID" "INVALID"
GameReBind Ability6Self ActivateToolSelf "6" button game "INVALID" "INVALID"
GameReBind Ability7 ActivateTool "7" button game "G" "INVALID"
GameReBind Ability7Secondary ActivateToolSecondary "7" impulse game "INVALID" "INVALID"
GameReBind Ability7Self ActivateToolSelf "7" button game "INVALID" "INVALID"
GameReBind Ability8 ActivateTool "8" button game "T" "INVALID"
GameReBind Ability8Secondary ActivateToolSecondary "8" impulse game "INVALID" "INVALID"
GameReBind Ability8Self ActivateToolSelf "8" button game "INVALID" "INVALID"
GameReBind Ability9 ActivateTool "9" button game "J" "INVALID"
GameReBind Ability9Secondary ActivateToolSecondary "9" impulse game "INVALID" "INVALID"
GameReBind Ability9Self ActivateToolSelf "9" button game "INVALID" "INVALID"
GameReBind AddToSelection0 AddToSelection "0" impulse game "SHIFT+0" "INVALID"
GameReBind AddToSelection1 AddToSelection "1" impulse game "SHIFT+1" "INVALID"
GameReBind AddToSelection2 AddToSelection "2" impulse game "SHIFT+2" "INVALID"
GameReBind AddToSelection3 AddToSelection "3" impulse game "SHIFT+3" "INVALID"
GameReBind AddToSelection4 AddToSelection "4" impulse game "SHIFT+4" "INVALID"
GameReBind AddToSelection5 AddToSelection "5" impulse game "SHIFT+5" "INVALID"
GameReBind AddToSelection6 AddToSelection "6" impulse game "SHIFT+6" "INVALID"
GameReBind AddToSelection7 AddToSelection "7" impulse game "SHIFT+7" "INVALID"
GameReBind AddToSelection8 AddToSelection "8" impulse game "SHIFT+8" "INVALID"
GameReBind AddToSelection9 AddToSelection "9" impulse game "SHIFT+9" "INVALID"
GameReBind AlternateModifier AlternateModifier "" button game "INVALID" "INVALID"
GameReBind AltInfoAllies AltInfoAllies "" button game "[" "INVALID"
GameReBind AltInfoEnemies AltInfoEnemies "" button game "]" "INVALID"
GameReBind Backpack1 ActivateTool "48" button game "NUM4" "ALT+Q"
GameReBind Backpack1Self ActivateToolSelf "48" button game "INVALID" "INVALID"
GameReBind Backpack2 ActivateTool "49" button game "NUM5" "ALT+W"
GameReBind Backpack2Self ActivateToolSelf "49" button game "INVALID" "INVALID"
GameReBind Backpack3 ActivateTool "50" button game "NUM6" "ALT+E"
GameReBind Backpack3Self ActivateToolSelf "50" button game "INVALID" "INVALID"
GameReBind Backpack4 ActivateTool "51" button game "NUM1" "ALT+A"
GameReBind Backpack4Self ActivateToolSelf "51" button game "INVALID" "INVALID"
GameReBind Backpack5 ActivateTool "52" button game "NUM2" "ALT+S"
GameReBind Backpack5Self ActivateToolSelf "52" button game "INVALID" "INVALID"
GameReBind Backpack6 ActivateTool "53" button game "NUM3" "ALT+D"
GameReBind Backpack6Self ActivateToolSelf "53" button game "INVALID" "INVALID"
GameReBind CameraDown CameraDown "" impulse game "CTRL+WHEELUP" "INVALID"
GameReBind CameraDrag CameraDrag "" button game "INVALID" "INVALID"
GameReBind CameraUp CameraUp "" impulse game "CTRL+WHEELDOWN" "INVALID"
GameReBind Cancel Cancel "" button game "ESC" "INVALID"
GameReBind Center Center "" button game "INVALID" "INVALID"
GameReBind CenterInfo CenterInfo "" button game "???" "INVALID"
GameReBind ChatAll ChatAll "" impulse game "SHIFT+ENTER" "INVALID"
GameReBind ChatMentor ChatMentor "" impulse game "CTRL+ENTER" "INVALID"
GameReBind ChatTeam ChatTeam "" impulse game "ENTER" "INVALID"
GameReBind CommanderModifier1 CommanderModifier1 "" button game "SHIFT" "INVALID"
GameReBind CommanderModifier2 CommanderModifier2 "" button game "CTRL" "INVALID"
GameReBind CommanderModifier3 CommanderModifier3 "" button game "ALT" "INVALID"
GameReBind CommanderModifier4 CommanderModifier4 "" button game "D" "INVALID"
GameReBind CommanderPing CommanderPing "" impulse game "ALT+MOUSEL" "INVALID"
GameReBind CommanderPrimary CommanderPrimary "" button game "MOUSEL" "INVALID"
GameReBind CommanderSecondary CommanderSecondary "" button game "MOUSER" "INVALID"
GameReBind FocusLastEvent FocusLastEvent "" impulse game "INVALID" "INVALID"
GameReBind FreeLook FreeLook "" button game "BACK_SLASH" "INVALID"
GameReBind FrontQueueModifier FrontQueueModifier "" button game "INVALID" "INVALID"
GameReBind LevelupAbility1 LevelupAbility "0" impulse game "ALT+Z" "INVALID"
GameReBind LevelupAbility2 LevelupAbility "1" impulse game "ALT+X" "INVALID"
GameReBind LevelupAbility3 LevelupAbility "2" impulse game "ALT+C" "INVALID"
GameReBind LevelupAbility4 LevelupAbility "3" impulse game "ALT+V" "INVALID"
GameReBind LevelupStats LevelupAbility "4" impulse game "ALT+O" "INVALID"
GameReBind LockCamera LockCamera "" impulse game "INVALID" "INVALID"
GameReBind MoveBack MoveBack "" button game "DOWN" "INVALID"
GameReBind MoveForward MoveForward "" button game "UP" "INVALID"
GameReBind MoveLeft MoveLeft "" button game "LEFT" "INVALID"
GameReBind MoveRight MoveRight "" button game "RIGHT" "INVALID"
GameReBind NextAttackModifier NextAttackModifier "" impulse game "PERIOD" "INVALID"
GameReBind NextInventoryUnit NextInventoryUnit "" impulse game "SHIFT+~" "INVALID"
GameReBind NextInventoryUnitCentered NextInventoryUnitCentered "" impulse game "CTRL+~" "INVALID"
GameReBind NextUnit NextUnit "" impulse game "TAB" "INVALID"
GameReBind NextUnitCentered NextUnitCentered "" impulse game "CTRL+TAB" "INVALID"
GameReBind options_keybind_cameralock ToggleCvar "cg_lockCameraGame" impulse game "INVALID" "INVALID"
GameReBind OrderAttack OrderAttack "" impulse game "A" "INVALID"
GameReBind OrderCancelAndHold OrderCancelAndHold "" impulse game "H" "INVALID"
GameReBind OrderHold OrderHold "" impulse game "INVALID" "INVALID"
GameReBind OrderMove OrderMove "" impulse game "M" "INVALID"
GameReBind OrderPatrol OrderPatrol "" impulse game "P" "INVALID"
GameReBind OrderStop OrderStop "" impulse game "S" "INVALID"
GameReBind PrevAttackModifier PrevAttackModifier "" impulse game "COMMA" "INVALID"
GameReBind PrevInventoryUnit PrevInventoryUnit "" impulse game "INVALID" "INVALID"
GameReBind PrevInventoryUnitCentered PrevInventoryUnitCentered "" impulse game "CTRL+SHIFT+~" "INVALID"
GameReBind PrevUnit PrevUnit "" impulse game "SHIFT+TAB" "INVALID"
GameReBind PrevUnitCentered PrevUnitCentered "" impulse game "CTRL+SHIFT+TAB" "INVALID"
GameReBind RecallSelection0 RecallSelection "0" impulse game "0" "INVALID"
GameReBind RecallSelection1 RecallSelection "1" impulse game "1" "INVALID"
GameReBind RecallSelection2 RecallSelection "2" impulse game "2" "INVALID"
GameReBind RecallSelection3 RecallSelection "3" impulse game "3" "INVALID"
GameReBind RecallSelection4 RecallSelection "4" impulse game "4" "INVALID"
GameReBind RecallSelection5 RecallSelection "5" impulse game "5" "INVALID"
GameReBind RecallSelection6 RecallSelection "6" impulse game "6" "INVALID"
GameReBind RecallSelection7 RecallSelection "7" impulse game "7" "INVALID"
GameReBind RecallSelection8 RecallSelection "8" impulse game "8" "INVALID"
GameReBind RecallSelection9 RecallSelection "9" impulse game "9" "INVALID"
GameReBind RecipeBack RecipeBack "" impulse shop "[" "INVALID"
GameReBind RecipeForward RecipeForward "" impulse shop "]" "INVALID"
GameReBind RemoveFromSelection0 RemoveFromSelection "0" impulse game "CTRL+SHIFT+0" "INVALID"
GameReBind RemoveFromSelection1 RemoveFromSelection "1" impulse game "CTRL+SHIFT+1" "INVALID"
GameReBind RemoveFromSelection2 RemoveFromSelection "2" impulse game "CTRL+SHIFT+2" "INVALID"
GameReBind RemoveFromSelection3 RemoveFromSelection "3" impulse game "CTRL+SHIFT+3" "INVALID"
GameReBind RemoveFromSelection4 RemoveFromSelection "4" impulse game "CTRL+SHIFT+4" "INVALID"
GameReBind RemoveFromSelection5 RemoveFromSelection "5" impulse game "CTRL+SHIFT+5" "INVALID"
GameReBind RemoveFromSelection6 RemoveFromSelection "6" impulse game "CTRL+SHIFT+6" "INVALID"
GameReBind RemoveFromSelection7 RemoveFromSelection "7" impulse game "CTRL+SHIFT+7" "INVALID"
GameReBind RemoveFromSelection8 RemoveFromSelection "8" impulse game "CTRL+SHIFT+8" "INVALID"
GameReBind RemoveFromSelection9 RemoveFromSelection "9" impulse game "CTRL+SHIFT+9" "INVALID"
GameReBind ReplayFFStepA Cmd "ReplayFFStep" impulse replay "]" "INVALID"
GameReBind ReplayFFToggle TriggerToggle "ReplayFFToggle" button replay "F" "INVALID"
GameReBind ReplayLockToggle TriggerToggle "ReplayLockToggle" button replay "E" "INVALID"
GameReBind ReplayPauseA Cmd "ReplayPause" impulse replay "P" "INVALID"
GameReBind ReplayRWStepA Cmd "ReplayRWStep" impulse replay "[" "INVALID"
GameReBind ReplayToggle1 TriggerToggle "ReplayToggle1" button replay "CAPS_LOCK" "INVALID"
GameReBind ResetCamera ResetCamera "" impulse game "BACKSPACE" "INVALID"
GameReBind Ruler Ruler "" button game "INVALID" "INVALID"
GameReBind SaveSelection0 SaveSelection "0" impulse game "CTRL+0" "INVALID"
GameReBind SaveSelection1 SaveSelection "1" impulse game "CTRL+1" "INVALID"
GameReBind SaveSelection2 SaveSelection "2" impulse game "CTRL+2" "INVALID"
GameReBind SaveSelection3 SaveSelection "3" impulse game "CTRL+3" "INVALID"
GameReBind SaveSelection4 SaveSelection "4" impulse game "CTRL+4" "INVALID"
GameReBind SaveSelection5 SaveSelection "5" impulse game "CTRL+5" "INVALID"
GameReBind SaveSelection6 SaveSelection "6" impulse game "CTRL+6" "INVALID"
GameReBind SaveSelection7 SaveSelection "7" impulse game "CTRL+7" "INVALID"
GameReBind SaveSelection8 SaveSelection "8" impulse game "CTRL+8" "INVALID"
GameReBind SaveSelection9 SaveSelection "9" impulse game "CTRL+9" "INVALID"
GameReBind SelectControllable SelectControllable "" impulse game "F2" "INVALID"
GameReBind SelectControllableNonHero SelectControllableNonHero "" impulse game "F3" "INVALID"
GameReBind SelectHero SelectHero "" impulse game "F1" "INVALID"
GameReBind Shared1 ActivateTool "45" button game "INVALID" "INVALID"
GameReBind Shop1 Shop "0" impulse shop "Q" "INVALID"
GameReBind Shop10 Shop "9" impulse shop "G" "INVALID"
GameReBind Shop11 Shop "10" impulse shop "Y" "INVALID"
GameReBind Shop12 Shop "11" impulse shop "U" "INVALID"
GameReBind Shop13 Shop "12" impulse shop "I" "INVALID"
GameReBind Shop14 Shop "13" impulse shop "O" "INVALID"
GameReBind Shop15 Shop "14" impulse shop "P" "INVALID"
GameReBind Shop16 Shop "15" impulse shop "H" "INVALID"
GameReBind Shop17 Shop "16" impulse shop "J" "INVALID"
GameReBind Shop18 Shop "17" impulse shop "K" "INVALID"
GameReBind Shop19 Shop "18" impulse shop "L" "INVALID"
GameReBind Shop2 Shop "1" impulse shop "W" "INVALID"
GameReBind Shop20 Shop "19" impulse shop "SEMI-COLON" "INVALID"
GameReBind Shop3 Shop "2" impulse shop "E" "INVALID"
GameReBind Shop4 Shop "3" impulse shop "R" "INVALID"
GameReBind Shop5 Shop "4" impulse shop "T" "INVALID"
GameReBind Shop6 Shop "5" impulse shop "A" "INVALID"
GameReBind Shop7 Shop "6" impulse shop "S" "INVALID"
GameReBind Shop8 Shop "7" impulse shop "D" "INVALID"
GameReBind Shop9 Shop "8" impulse shop "F" "INVALID"
GameReBind ShopClosePanel Shop "-1" impulse shop "BACKSPACE" "INVALID"
GameReBind ShowChat ShowChat "" button game "Z" "INVALID"
GameReBind ShowScoreboard ShowScoreboard "" button game "C" "INVALID"
GameReBind SpecUICombat1 TriggerToggle "SpecUICombat1" button spectator "X" "INVALID"
GameReBind SpecUICombat2 TriggerToggle "SpecUICombat2" button spectator "C" "INVALID"
GameReBind SpecUICombat3 TriggerToggle "SpecUICombat3" button spectator "V" "INVALID"
GameReBind SpecUIHideAll TriggerToggle "SpecUISHideAll" button spectator "Q" "INVALID"
GameReBind SpecUIJumpIn TriggerToggle "SpecUIJumpIn" button spectator "R" "INVALID"
GameReBind SpecUIShowAll TriggerToggle "SpecUIShowAll" button spectator "TAB" "INVALID"
GameReBind SpecUITab1A Cmd "SpecUITab1" impulse spectator "1" "INVALID"
GameReBind SpecUITab2A Cmd "SpecUITab2" impulse spectator "2" "INVALID"
GameReBind SpecUITab3A Cmd "SpecUITab3" impulse spectator "3" "INVALID"
GameReBind SpecUITab4A Cmd "SpecUITab4" impulse spectator "4" "INVALID"
GameReBind SpecUITab5A Cmd "SpecUITab5" impulse spectator "5" "INVALID"
GameReBind SpecUITab6A Cmd "SpecUITab6" impulse spectator "6" "INVALID"
GameReBind SpecUITab7A Cmd "SpecUITab7" impulse spectator "7" "INVALID"
GameReBind SpecUITab8A Cmd "SpecUITab8" impulse spectator "8" "INVALID"
GameReBind SpecUIToggleAll TriggerToggle "SpecUIToggleAll" button spectator "INVALID" "INVALID"
GameReBind SpecUIToggleInfoA Cmd "SpecUIToggleInfo" impulse spectator "F2" "INVALID"
GameReBind SpecUITogglePushA Cmd "SpecUITogglePush" impulse spectator "F3" "INVALID"
GameReBind SpecUIToggleReplayA Cmd "SpecUIToggleReplay" impulse spectator "F4" "INVALID"
GameReBind SpecUIToggleUFA Cmd "SpecUIToggleUF" impulse spectator "F1" "INVALID"
GameReBind StartFacebookStream StartFacebookStream "" impulse game "INVALID" "INVALID"
GameReBind Stats ActivateTool "4" button game "O" "INVALID"
GameReBind StopFacebookStream StopFacebookStream "" impulse game "INVALID" "INVALID"
GameReBind SwitchScore SwitchScore "" impulse game "INVALID" "INVALID"
GameReBind ToggleAltInfo ToggleAltInfo "" impulse game "INVALID" "INVALID"
GameReBind ToggleFacebookStreamMenu ToggleFacebookStreamMenu "" impulse game "INVALID" "INVALID"
GameReBind ToggleLevelupInterface ToggleLevelupInterface "" impulse game "ALT+L" "INVALID"
GameReBind ToggleMusic ToggleCvar "sound_muteMusic" impulse game "CTRL+M" "INVALID"
GameReBind ToggleOverlayMenuGame ToggleOverlayMenuGame "" impulse game "F6" "F10"
GameReBind ToggleOverlayMenuSpectator ToggleOverlayMenuSpectator "" impulse spectator "F6" "F10"
GameReBind ToggleOverlayMenuUI ToggleOverlayMenuUI "" impulse ui "F6" "F10"
GameReBind ToggleShop ToggleShop "" impulse game "B" "INVALID"
GameReBind ToggleSound ToggleCvar "sound_mute" impulse game "CTRL+S" "INVALID"
GameReBind TransmitMentorCursor TransmitMentorCursor "" button mentor "MOUSER" "INVALID"
GameReBind UseBestCourier UseBestCourier "" button game "INVALID" "INVALID"
GameReBind VoicePushToLaneTalk VoicePushToLaneTalk "" button game "Y" "INVALID"
GameReBind VoicePushToMentorTalk VoicePushToMentorTalk "" button game "X" "INVALID"
GameReBind VoicePushToTalk VoicePushToTalk "" button game "SPACE" "MOUSEM"
GameReBind WardSlot ActivateTool "63" button game "NUM9" "ALT+R"
GameReBind WardSlot2 ActivateTool "64" button game "NUM8" "ALT+F"
GameReBind ZoomIn ZoomIn "" impulse game "WHEELUP" "INVALID"
GameReBind ZoomOut ZoomOut "" impulse game "WHEELDOWN" "INVALID"
BindButton game INVALID ActivateToolSelf "1" true
BindButton game SPACE VoicePushToTalk "" true
BindButton game C ShowScoreboard "" true
BindButton game D CommanderModifier4 "" true
BindButton game T ActivateTool "8" true
BindButton game X VoicePushToMentorTalk "" true
BindButton game MOUSEM VoicePushToTalk "" true
```
---
layout: default
title: Authentication Flow
parent: Master Server Endpoints
---

## patcher/patcher.php

### Overview

This endpoint is pinged periodically by the client to check to see if a new
update is available.

The server responds the latest version, the base URL to download the patch
from, the manifest checksum, as well as the current version and current
manifest checksum.

If there is a mismatch, the client prompts the user to update.

### Request

The client issues a request containing its current version, os,
architecture, and cookie:

  - `current_version`: the current HoN version in
     <major>.<minor>.<patch>(.<hotfix>) format. e.g. `1.0.6.2`
  - `os`: the current operating system. Valid values are `wac`
          (windows), `mac`, `linux`
  - `arch`: the current HoN client architecture. Valid values
            are `i686` (32-bit), `x86_64` (64-bit)

It also has the following parameters that are likely ignored:
  - `update`: it seems to always be `1`.
  - `version`: appears to always be `0.0.0.0`

Example request:

```
POST /patcher/patcher.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.9.5.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 105
Content-Type: application/x-www-form-urlencoded

update=1&version=0.0.0.0&current_version=4.9.5&os=wac&arch=x86_64&cookie=d883603589bebfec93175bf7fbc272ca
```

This request alerts the server that the current version is
`4.9.5` on Windows (`wac`) using the 64-bit client (`x86_64`).

### Response

The server replies with the download URLs, manifest sizes, and
manifest checksums for each version -- even if they are the same.

The client must validate these.

For some reason it includes two URLs. One must map to the
`current_version` and the other must map to the `latest_version`.
However in every case I can find, the values are the same. So
it's unclear which applies to which. This could be validated
by sending the client a fake packet (or intercepting and modifying
the actual packet) to change one of the URLs and see what happens.

It seems like maybe you could request patches that aren't the latest.
Perhaps that's what the difference in `version` and `latest_version`
are. Otherwise I'm not sure.

Parameters:

  - `version`: a version number (it's not clear how this differs from
               `latest_version`)
  - `os`: the current operating system, as specified by the request.
          Valid values are `wac` (windows), `mac`, `linux`
  - `arch`: the current HoN client architecture, as specified by the
            request. Valid values are `i686` (32-bit), `x86_64` (64-bit)
  - `url`: the download URL (not sure how this differs from URL2)
  - `url2`: the download URL (not sure how this differs from URL)
  - `latest_version`: the latest HoN version available
  - `latest_manifest_checksum`: the `md5` checksum of the manifest zip
                                file (e.g. `4.10.1.manifest.xml.zip`)
  - `latest_manigest_size`: the size (in bites) of the manifest zip
                            file (e.g. `4.10.1.manifest.xml.zip`)
  - `current_version`: the current version as sent up by the client
  - `current_manifest_checksum`: the `md5` checksum of the manifest
                                 zip file (e.g. `4.9.5.manifest.xml.zip`)
  - `current_manifest_size`: the size (in bites) of the manifest zip
                             file (e.g. `4.9.5.manifest.xml.zip`)

- Example response when already up-to-date

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2022 03:16:33 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 555
Connection: close
Content-Type: text/html; charset=UTF-8

a:5:{i:0;a:8:{s:7:"version";s:6:"4.10.1";s:2:"os";s:3:"wac";s:4:"arch";s:6:"x86_64";s:3:"url";s:42:"http://cdn.naeu.patch.heroesofnewerth.com/";s:4:"url2";s:42:"http://cdn.naeu.patch.heroesofnewerth.com/";s:14:"latest_version";s:6:"4.10.1";s:24:"latest_manifest_checksum";s:40:"33b5151fca1704aff892cf76e41f3986634d38bb";s:20:"latest_manifest_size";s:7:"3628533";}s:7:"version";s:8:"4.10.1.0";s:15:"current_version";s:8:"4.10.1.0";s:25:"current_manifest_checksum";s:40:"33b5151fca1704aff892cf76e41f3986634d38bb";s:21:"current_manifest_size";s:7:"3628533";}
```

Deserialized payload:

```
Array
(
    [0] => Array
        (
            [version] => 4.10.1
            [os] => wac
            [arch] => x86_64
            [url] => http://cdn.naeu.patch.heroesofnewerth.com/
            [url2] => http://cdn.naeu.patch.heroesofnewerth.com/
            [latest_version] => 4.10.1
            [latest_manifest_checksum] => 33b5151fca1704aff892cf76e41f3986634d38bb
            [latest_manifest_size] => 3628533
        )

    [version] => 4.10.1.0
    [current_version] => 4.10.1.0
    [current_manifest_checksum] => 33b5151fca1704aff892cf76e41f3986634d38bb
    [current_manifest_size] => 3628533
)
```

- Example response when an update is needed

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2022 19:24:05 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 554
Connection: close
Content-Type: text/html; charset=UTF-8

a:5:{i:0;a:8:{s:7:"version";s:6:"4.10.1";s:2:"os";s:3:"wac";s:4:"arch";s:6:"x86_64";s:3:"url";s:42:"http://cdn.naeu.patch.heroesofnewerth.com/";s:4:"url2";s:42:"http://cdn.naeu.patch.heroesofnewerth.com/";s:14:"latest_version";s:6:"4.10.1";s:24:"latest_manifest_checksum";s:40:"33b5151fca1704aff892cf76e41f3986634d38bb";s:20:"latest_manifest_size";s:7:"3628533";}s:7:"version";s:8:"4.10.1.0";s:15:"current_version";s:7:"4.9.5.0";s:25:"current_manifest_checksum";s:40:"91a4686467c841cfd940c2a81ca0932df117d5a5";s:21:"current_manifest_size";s:7:"3624758";}
```

Deserialized payload:

```
Array
(
    [0] => Array
        (
            [version] => 4.10.1
            [os] => wac
            [arch] => x86_64
            [url] => http://cdn.naeu.patch.heroesofnewerth.com/
            [url2] => http://cdn.naeu.patch.heroesofnewerth.com/
            [latest_version] => 4.10.1
            [latest_manifest_checksum] => 33b5151fca1704aff892cf76e41f3986634d38bb
            [latest_manifest_size] => 3628533
        )

    [version] => 4.10.1.0
    [current_version] => 4.9.5.0
    [current_manifest_checksum] => 91a4686467c841cfd940c2a81ca0932df117d5a5
    [current_manifest_size] => 3624758
)
```
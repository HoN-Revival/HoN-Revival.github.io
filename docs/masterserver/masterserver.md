---
layout: default
title: Master Server
has_children: true
permalink: docs/masterserver
nav_order: 2
---

# Master Server
{:toc}

## Background

The HoN masterserver is used for login, updating (patching), as well as controlling
much of the UI functionality in the game.

Some examples include:

- Hosted games list
- Providing stats information to the client
- Sending the friends list to the client
- Store (displaying and purchasing)
- Plinko and ticket redemption
- Cloud store/retrieval of settings

And more.

The server uses port `80`. The official endpoint was
`masterserver.naeu.heroesofnewerth.com`, but will be offline in June 2022.

To specify the custom URL or IP address to use with HoN, simply make
a shortcut of the game and add the `-masterserver IP:port`.

For example, if I want to connect to the `localhost` at port `666`,
I created a shortcut with the following info:

```
"C:\Program Files\Heroes of Newerth x64\hon_x64.exe" -masterserver 127.0.0.1:666
```

Then you can just use this custom shortcut to launch HoN connecting to a specific
master server address.

## Client <-> Server interaction

The server is basically just a REST API written in PHP. The client sends HTTP
[POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) requests
to the server and the server responds. Since HTTP is relatively stateless, the
server provides the client with a `cookie` value to identify itself for
subsequent requests upon login.

The client begins the [authentication flow](authentication-flow.md).

After authentication, the masterserver provides the client with the IP
and port for the chat server (which the client then connects to using TCP).

Throughout the session, the client uses numerous HTTP requests over the same
port `80` connection. These are 
requests that target `.php` endpoints.

The function that the PHP endpoint should respond to is set using
the query parameter `f=`. E.g. `/some_endpoint.php?f=something`
would call the `something` function on the `some_endpoint.php`
endpoint.

For example, one such request might look like this:

```
POST /client_requester.php?f=pre_auth HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 705
Content-Type: application/x-www-form-urlencoded

<data_would_be_here_but_was_ommitted_to_be_condensed>
```

This is a `pre_auth` request to the `client_requester.php` endpoint,
which is used during the [authentication flow](authentication-flow.md),

The server then responds over HTTP with a `HTTP/1.1 200 OK` in the
following format:

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2022 03:16:33 GMT
Server: Apache/2.2.15 (CentOS)
X-Powered-By: PHP/5.4.23 ZendServer/6.3.0
Content-Length: 555
Connection: close
Content-Type: text/html; charset=UTF-8

<data_would_be_here_but_was_ommitted_to_be_condensed>
```

The data is [PHP serialized](https://en.wikipedia.org/wiki/PHP_serialization_format#:~:text=The%20PHP%20serialization%20format%20is,first%20introduced%20in%20PHP%204.).

The data may look like this (from a real patcher request):

```
a:5:{i:0;a:8:{s:7:"version";s:6:"4.10.1";s:2:"os";s:3:"wac";s:4:"arch";s:6:"x86_64";s:3:"url";s:42:"http://cdn.naeu.patch.heroesofnewerth.com/";s:4:"url2";s:42:"http://cdn.naeu.patch.heroesofnewerth.com/";s:14:"latest_version";s:6:"4.10.1";s:24:"latest_manifest_checksum";s:40:"33b5151fca1704aff892cf76e41f3986634d38bb";s:20:"latest_manifest_size";s:7:"3628533";}s:7:"version";s:8:"4.10.1.0";s:15:"current_version";s:8:"4.10.1.0";s:25:"current_manifest_checksum";s:40:"33b5151fca1704aff892cf76e41f3986634d38bb";s:21:"current_manifest_size";s:7:"3628533";}
```

For working with these packets yourself, there are dozens of online tools
to deserialize the data into a human readable format ([example](https://www.unserialize.com/).)

The deserialized version is much more managable:

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

For more information on these endpoints, see [Endpoints](endpoints.md).
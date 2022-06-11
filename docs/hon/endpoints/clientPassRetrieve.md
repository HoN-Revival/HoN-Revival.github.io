---
layout: default
title: clientPassRetrieve.php
parent: Heroesofnewerth.com
---

# clientPassRetrieve.php

This form is requested in `ui/fe2/account.package` and
`ui/fe2/newui/account_v2.package`.

```
	<form
		name="PassReset"
		host="!hon"
		method="post"
		target="/clientPassRetrieve.php"
		statustrigger="PassResetStatus"
		resulttrigger="PassResetResults"
		resultparam0="0"
		resultparam1="1"
		ssl="true"
	/>
```

NOTE: This request uses `ssl`, but I disabled it to capture request.

```
POST /clientPassRetrieve.php HTTP/1.1
Host: 127.0.0.1:666
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 70
Content-Type: application/x-www-form-urlencoded

retrieve_email=&retrieve_nickname=happyasthma&retrieve_nickname_email=
```

The UI requests one of three of these keys based on what the client
entered.

- `retrieve_email`: For `Lost Password` requests via email
- `retrieve_nickname`: For `Lost Password` requests via nickname
- `retrieve_nickname_email`: For `Lost Username` requests via email

![UI form](https://i.imgur.com/P6fHbN5.png)

The emails look like this:

## Password Change

![Password change example email](https://i.imgur.com/MrT4Fok.png)

## Username lookup

![Username lookup example email](https://i.imgur.com/7t4vflY.png)


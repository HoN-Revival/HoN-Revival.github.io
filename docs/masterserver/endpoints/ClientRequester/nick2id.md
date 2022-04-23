---
layout: default
title: client_requester.php?f=nick2id
parent: PHP Endpoints
grand_parent: Master Server
---

## client_requester.php?f=nick2id

### Overview

This endpoint returns the account ID for a given nickname. 

### Request

This is just an HTTP request with an array parameter for key `nickname`.

Example requests:

```
http://masterserver.naeu.heroesofnewerth.com/client_requester.php?f=nick2id&nickname%5B0%5D=happyasthma

http://masterserver.naeu.heroesofnewerth.com/client_requester.php?f=nick2id&nickname[0]=happyasthma&nickname[1]=gamesdean
```


### Response

The server replies with key-value pairs for each username to ID.

Additional Parameters:

  - `vested_threshold`: Unknown. Seems to alawys be `5`.
  - `0`: Unknown boolean. Seems to be `1` on true (success) and `0` on false (failure).

- Example response

```
a:4:{s:9:"GamesDean";s:7:"8085306";s:11:"happyasthma";s:6:"782203";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [GamesDean] => 8085306
    [happyasthma] => 782203
    [vested_threshold] => 5
    [0] => 1
)
```

- Example response with bad inputs

If any in the array are there, returns just the successes

```
// http://masterserver.naeu.heroesofnewerth.com/client_requester.php?f=nick2id&nickname[0]=happyasthma&nickname[1]=gamesd

a:3:{s:11:"happyasthma";s:6:"782203";s:16:"vested_threshold";i:5;i:0;b:1;}
```

```
Array
(
    [happyasthma] => 782203
    [vested_threshold] => 5
    [0] => 1
)
```

- No usernames valid

```
a:2:{i:0;b:0;s:5:"error";s:19:"Nicknames not found";}
```

```
Array
(
    [0] => 
    [error] => Nicknames not found
)
```
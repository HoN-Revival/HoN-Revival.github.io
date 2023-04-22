---
layout: default
title: client_requester.php?f=get_hero_usage_graph
parent: PHP Endpoints
grand_parent: Master Server
---

## client_requester.php?f=get_hero_usage_graph

### Overview

Endpoint is used to generate the usage stats. (Click on an individual hero
in the Learnitorium and click "View Usage History Graph...".)

### Request

```
POST /client_requester.php HTTP/1.1
Host: masterserver.naeu.heroesofnewerth.com
User-Agent: S2 Games/Heroes of Newerth/4.10.1.0/wac/x86_64
Accept: */*
Accept-Encoding: gzip,deflate
Content-Length: 15
Content-Type: application/x-www-form-urlencoded

f=get_hero_usage_graph&cookie=bd805dda770577426fa4ebf4b9c38b52&hero=Hero_MasterOfArms&limit=45&days=90
```

- `cookie`: Used to validate the client's session.
- `hero`: The ID of the hero to fetch the stats for.
- `limit`: The number of entries to return, i.e. granularity (e.g. in this case it's 45
           entries of 'every 2 days'). This Appears to be fixed in the client even though the
           UI supports up to 180 days
- `days`: The span of days to compute the number of entries from. (e.g. "last 90 days").

### Response

```
a:9:{s:7:"success";i:1;s:6:"errors";s:0:"";s:4:"days";i:90;s:4:"high";s:4:"1.02";s:10:"high_total";s:4:"3.57";s:5:"count";i:45;s:4:"data";s:942:"March 9th, 2022`0.92|March 11th, 2022`0.77|March 13th, 2022`0.87|March 15th, 2022`0.91|March 17th, 2022`0.78|March 19th, 2022`0.84|March 21st, 2022`0.75|March 23rd, 2022`0.89|March 25th, 2022`0.79|March 27th, 2022`0.86|March 29th, 2022`0.81|March 31st, 2022`0.73|April 2nd, 2022`0.76|April 4th, 2022`0.78|April 6th, 2022`0.78|April 8th, 2022`0.81|April 10th, 2022`0.86|April 12th, 2022`0.84|April 14th, 2022`0.99|April 16th, 2022`0.79|April 18th, 2022`0.76|April 20th, 2022`0.86|April 22nd, 2022`0.76|April 24th, 2022`0.71|April 26th, 2022`0.81|April 28th, 2022`0.81|April 30th, 2022`0.79|May 2nd, 2022`0.76|May 4th, 2022`0.73|May 6th, 2022`0.65|May 8th, 2022`0.91|May 10th, 2022`0.83|May 12th, 2022`0.78|May 14th, 2022`0.8|May 16th, 2022`0.79|May 18th, 2022`0.79|May 20th, 2022`0.8|May 22nd, 2022`0.75|May 24th, 2022`0.72|May 26th, 2022`0.78|May 28th, 2022`0.84|May 30th, 2022`0.79|June 1st, 2022`0.86|June 3rd, 2022`1.02|June 5th, 2022`0.77";s:16:"vested_threshold";i:5;i:0;b:1;}
```

Formatted response:

```
Array
(
    [success] => 1
    [errors] => 
    [days] => 90
    [high] => 1.02
    [high_total] => 3.57
    [count] => 45
    [data] => March 9th, 2022`0.92|March 11th, 2022`0.77|March 13th, 2022`0.87|March 15th, 2022`0.91|March 17th, 2022`0.78|March 19th, 2022`0.84|March 21st, 2022`0.75|March 23rd, 2022`0.89|March 25th, 2022`0.79|March 27th, 2022`0.86|March 29th, 2022`0.81|March 31st, 2022`0.73|April 2nd, 2022`0.76|April 4th, 2022`0.78|April 6th, 2022`0.78|April 8th, 2022`0.81|April 10th, 2022`0.86|April 12th, 2022`0.84|April 14th, 2022`0.99|April 16th, 2022`0.79|April 18th, 2022`0.76|April 20th, 2022`0.86|April 22nd, 2022`0.76|April 24th, 2022`0.71|April 26th, 2022`0.81|April 28th, 2022`0.81|April 30th, 2022`0.79|May 2nd, 2022`0.76|May 4th, 2022`0.73|May 6th, 2022`0.65|May 8th, 2022`0.91|May 10th, 2022`0.83|May 12th, 2022`0.78|May 14th, 2022`0.8|May 16th, 2022`0.79|May 18th, 2022`0.79|May 20th, 2022`0.8|May 22nd, 2022`0.75|May 24th, 2022`0.72|May 26th, 2022`0.78|May 28th, 2022`0.84|May 30th, 2022`0.79|June 1st, 2022`0.86|June 3rd, 2022`1.02|June 5th, 2022`0.77
    [vested_threshold] => 5
    [0] => 1
)
```

- `success`: `1` if success, otherwise empty
- `errors`: Unclear, as I don't have a capture. It's empty if success. Otherwise it probably contains an error string or something?
- `days`: The number of days spanning across the response (not sure if this has to match the one from the request).
- `high`: The max value on any given day in the `data` set.
- `high_total`: (Unconfirmed) - the highest value in any heroes' data set, likely used as the axis value
- `count`: The number of entires in `data`. (not sure if this has to match the one from the request)
- `data`: A pipe-separated list of data points for the graph. The format for each entry is `<date_string>\`<percentage>`.
- `vested_threshold`: Unknown but always `5`
- `0`: Unkown but always `1` on sucess or `0` on error`.
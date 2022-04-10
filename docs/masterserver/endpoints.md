---
layout: default
title: PHP Endpoints
parent: Master Server
has_children: true
---

## Master Server Endpoints

Below is a (maybe incomplete?) list of endpoints used (as of version `4.10.1`)
as well as a short summary of their behavior.

- [/patcher/patcher.php](endpoints/patcher.php.md)

This endpoint is pinged periodically by the client to check to see if a new
update is available.

The server responds the latest version, the base URL to download the patch
from, the manifest checksum, as well as the current version and current
manifest checksum.

If there is a mismatch, the client prompts the user to update.
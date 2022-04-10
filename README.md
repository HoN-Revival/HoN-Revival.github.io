---
layout: default
title: Homepage
nav_order: 1
---

# HoN Revival documentation

[hon-revival.github.io](https://hon-revival.github.io/)

The goal of HoN Revival is to keep HoN playable after the official servers
shut down in June 2022.

## How to play after the servers shut down?

### Installation

A custom installer is being built as part of the HoN-Revival project.

You can find information about it on GitHub at
[HoN Installer](https://github.com/HoN-Revival/HoN-Installer).

### Server Setup

#### Background

Thanks to those that have come before us and the GitHub user
[honserver](https://github.com/honserver/honserver), there is now a way
to host your own HoN games.

A fork of that repo can also be found in the
[HoN-Revival GitHub](https://github.com/HoN-Revival/honserver). However
the goal is to just treat this as a mirror rather than a divergent fork.

#### Setup

At this time, the only known way to host a game server involves using
modified `.dll` files that were patched to allow for hosting a game that
other people are eligible to join.

NOTE: You can still use the same HoN client with the modified `.dll` files
as your main client to connect to the server. But if you want to keep your
primary install unmodified, then re-install HoN to a separate directory and
and use that one as the 'server' directory and place the modified DLLs there.
However for the sake of simplicity, I will use a typical `C` drive install
path in the examples below.

NOTE: The server uses UDP port `11235` by default. This port may need to
be unblocked or port-forwarded to allow for external traffic.
(At this time it is not clear how to change that.)

To run the server, simply use a terminal (or PowerShell) to pass the 
the `-dedicated` flag to your modified HoN directory's `.exe`.

It is also recommended to run the process as 'high priority' to minimize
skipped frames. On Windows, you can run this command as:

```
C:\Windows\System32\cmd.exe /c start /high "C:\Program Files\Heroes of Newerth x64\hon_x64.exe" -dedicated
```

#### Known Issues

Due to the hacky nature of this server hosting process, it is recommended to
restart the server between games.

Known Issues:

  - No disconnect timeout
  - Reconnecting is very unreliable

### How to connect to the server?

If you have someone to host a game already, then you can just use the
vanilla install.

We will eventually use HoN Mods to make connecting to servers easier,
but for now it's primarily done with in-game commands.

To connect to a game, open the HoN command window by pressing `ctrl + F8`.

Then type `connect <IP>` where `<IP>` is the IP address of the hosted game
server.

To start (i.e. host) the game lobby, issue one of the `startgame` commands.
(NOTE: this only needs to be done by the first person hosting the lobby
on that game server)

For example:

```
startgame local_automatic game_name map:caldavar
```

Then press `ctrl + F8` again to close the command window. You should now
be in the game lobby.

For other players that want to connect, they simply just need to use the
`connect <IP>` command and they will automatically enter the lobby.

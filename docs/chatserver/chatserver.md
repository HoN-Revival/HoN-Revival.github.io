# Chat Server

Shout out to `theli-ua` on GitHub for capturing all this data.
Taken from [honpurple](https://github.com/theli-ua/honpurple)
and [pyHoNbot](https://github.com/theli-ua/pyHoNBot).

NOTE: The repositories are fairly old, so some of the data may
be stale. This is largely just a dump until I can confirm:

## Background

HoN chat server and port are sent from the [Master Server](masterserver.md)
after a successful authorization.

By convention, the port is `11031` but presumably this could changed
since it's provided by the Master Server.

The client connects to the IP and port using TCP.

After a successful connection, a chat authorization packet is
sent (`HON_CS_AUTH_INFO`).

This packet forwards a bunch of info that the Master Server sent
after successful authorization, such as `cookie`, `ip`, `account_id`

The chat server uses a `protocol version`. It's unclear when and
why this value changes over the years but presumably some of the
packet structure changed.

The latest protocol version (as of `4.10.1`) is `68`.

```
#define HON_PROTOCOL_VERSION 68
```

The client and server also keep alive using a ping/pong heartbeat.

The server periodically sends `HON_SC_PING` messages, and the client
must reply back with `HON_CS_PONG` to prove it's still active.

## Packets

Some additional parsing logic is in `honpurple`. It may be a good
starting point for a chat server emulator:
https://github.com/theli-ua/honpurple/blob/692111754fc75abc3033f7b5d6ac98edf42119fa/src/hon.c

### server -> client

```
#define	 HON_SC_AUTH_ACCEPTED 	 0x1C00
#define	 HON_SC_PING 	 0x2A00
#define	 HON_SC_CHANNEL_MSG 	 0x03
#define	 HON_SC_CHANGED_CHANNEL 	 0x04
#define	 HON_SC_JOINED_CHANNEL 	 0x05
#define	 HON_SC_LEFT_CHANNEL 	 0x06
#define	 HON_SC_WHISPER 	 0x08
#define	 HON_SC_WHISPER_FAILED 	 0x09
#define	 HON_SC_INITIAL_STATUS 	 0x0B
#define	 HON_SC_UPDATE_STATUS 	 0x0C
#define	 HON_SC_CLAN_MESSAGE 	 0x13
#define	 HON_SC_LOOKING_FOR_CLAN 	 0x18
#define	 HON_SC_PM 	 0x1C
#define	 HON_SC_PM_FAILED 	 0x1D
#define	 HON_SC_WHISPER_BUDDIES 	 0x20
#define	 HON_SC_MAX_CHANNELS 	 0x21
#define	 HON_SC_USER_INFO_NO_EXIST 	 0x2B
#define	 HON_SC_USER_INFO_OFFLINE 	 0x2C
#define	 HON_SC_USER_INFO_ONLINE 	 0x2D
#define	 HON_SC_USER_INFO_IN_GAME 	 0x2E
#define	 HON_SC_CHANNEL_UPDATE 	 0x2F
#define	 HON_SC_UPDATE_TOPIC 	 0x30
#define	 HON_SC_CHANNEL_KICK 	 0x31
#define	 HON_SC_CHANNEL_BAN 	 0x32
#define	 HON_SC_CHANNEL_UNBAN 	 0x33
#define	 HON_SC_CHANNEL_BANNED 	 0x34
#define	 HON_SC_CHANNEL_SILENCED 	 0x35
#define	 HON_SC_CHANNEL_SILENCE_LIFTED 	 0x36
#define	 HON_SC_CHANNEL_SILENCE_PLACED 	 0x37
#define	 HON_SC_MESSAGE_ALL 	 0x39
#define	 HON_SC_CHANNEL_PROMOTE 	 0x3A
#define	 HON_SC_CHANNEL_DEMOTE 	 0x3B
#define	 HON_SC_CHANNEL_AUTH_ENABLE 	 0x3E
#define	 HON_SC_CHANNEL_AUTH_DISABLE		0x3F
#define	 HON_SC_CHANNEL_AUTH_ADD 	 0x40
#define	 HON_SC_CHANNEL_AUTH_DELETE		0x41
#define	 HON_SC_CHANNEL_AUTH_LIST 	 0x42
#define	 HON_SC_CHANNEL_PASSWORD_CHANGED 	 0x43
#define	 HON_SC_CHANNEL_ADD_AUTH_FAIL	0x44
#define	 HON_SC_CHANNEL_DEL_AUTH_FAIL	0x45
#define	 HON_SC_JOIN_CHANNEL_PASSWORD 	 0x46
#define	 HON_SC_CHANNEL_ROLL 	 0x64
#define	 HON_SC_CHANNEL_EMOTE 	 0x65
#define	 HON_SC_TOTAL_ONLINE 	 0x68
#define	 HON_SC_REQUEST_NOTIFICATION 	 0xB2
#define	 HON_SC_NOTIFICATION 	 0xB4
#define	 HON_SC_TMM_INVITE	 0xC0D
```

Potential formats:

https://docs.python.org/3/library/struct.html#format-characters

```
sc_structs = {
        ID.HON_SC_PING : '',
        ID.HON_SC_PM    : parse_pm,
        ID.HON_SC_WHISPER : 'ss',
        ID.HON_SC_CHANNEL_MSG : 'IIs',
        ID.HON_SC_CHANNEL_EMOTE : 'IIs',
        ID.HON_SC_CHANNEL_ROLL : 'IIs',
        ID.HON_SC_CHANGED_CHANNEL : parse_channel_join,
        ID.HON_SC_INITIAL_STATUS  : parse_initiall_statuses,
        ID.HON_SC_UPDATE_STATUS : parse_user_status,
        ID.HON_SC_JOINED_CHANNEL : 'IsIBBsssI', #chat_id,nick,id,status,flags,chatsymbol,shield,icon,ascension
        ID.HON_SC_CLAN_MEMBER_ADDED : 'I',
        ID.HON_SC_CLAN_MEMBER_CHANGE : 'IBI', #whom,wat,who (theli, promoted to officer, by visions)
        ID.HON_SC_NAME_CHANGE : 'Is',
        ID.HON_SC_CLAN_MESSAGE : 'Is',
        ID.HON_SC_LEFT_CHANNEL : 'II',
        ID.HON_SC_TOTAL_ONLINE : 'Is',
        ID.HON_SC_USER_INFO_NO_EXIST : 's',
        ID.HON_SC_USER_INFO_OFFLINE : 'ss',
        ID.HON_SC_USER_INFO_IN_GAME : 'sss',
        ID.HON_SC_CHANNEL_PROMOTE : 'III',
        ID.HON_SC_CHANNEL_DEMOTE : 'III'
        }
```

### client -> server

```
#define	 HON_CS_PONG 	 0x2A01
#define	 HON_CS_CHANNEL_MSG 	 0x03
#define	 HON_CS_WHISPER 	 0x08
#define	 HON_CS_AUTH_INFO 	 0x0C00
#define	 HON_CS_BUDDY_ADD_NOTIFY 	 0x0D
#define	 HON_CS_JOIN_GAME 	 0x10
#define	 HON_CS_CLAN_MESSAGE 	 0x13
#define	 HON_CS_PM 	 0x1C
#define	 HON_CS_JOIN_CHANNEL 	 0x1E
#define	 HON_CS_WHISPER_BUDDIES 	 0x20
#define	 HON_CS_LEAVE_CHANNEL 	 0x22
#define	 HON_CS_USER_INFO 	 0x2A
#define	 HON_CS_UPDATE_TOPIC 	 0x30
#define	 HON_CS_CHANNEL_KICK 	 0x31
#define	 HON_CS_CHANNEL_BAN 	 0x32
#define	 HON_CS_CHANNEL_UNBAN 	 0x33
#define	 HON_CS_CHANNEL_SILENCE_USER 	 0x38
#define	 HON_CS_CHANNEL_PROMOTE 	 0x3A
#define	 HON_CS_CHANNEL_DEMOTE 	 0x3B
#define	 HON_CS_CHANNEL_AUTH_ENABLE 	 0x3E
#define	 HON_CS_CHANNEL_AUTH_DISABLE		0x3F
#define	 HON_CS_CHANNEL_AUTH_ADD 	 0x40
#define	 HON_CS_CHANNEL_AUTH_DELETE		0x41
#define	 HON_CS_CHANNEL_AUTH_LIST 	 0x42
#define	 HON_CS_CHANNEL_SET_PASSWORD 	 0x43
#define	 HON_CS_JOIN_CHANNEL_PASSWORD 	 0x46
#define	 HON_CS_CLAN_ADD_MEMBER 	 0x47
#define	 HON_CS_CLAN_REMOVE_MEMBER 	 0x17
#define	 HON_CS_CHANNEL_ROLL 	 0x64
#define	 HON_CS_CHANNEL_EMOTE 	 0x65
#define	 HON_CS_BUDDY_ACCEPT 	 0xB3
```

Potential formats:

https://docs.python.org/3/library/struct.html#format-characters

```
cs_structs = {
        ID.HON_CS_AUTH_INFO : 'IsssIIBIIsI',
        ID.HON_CS_PONG      : '',
        ID.HON_CS_JOIN_CHANNEL : 's',
        ID.HON_CS_PM : 'ss',
        ID.HON_CS_WHISPER : 'ss',
        ID.HON_CS_CHANNEL_MSG : 'sI',
        ID.HON_CS_CHANNEL_EMOTE : 'sI',
        ID.HON_CS_CHANNEL_ROLL : 'sI',
        ID.HON_CS_JOIN_CHANNEL : 's',
        ID.HON_CS_LEAVE_CHANNEL : 's',
        ID.HON_CS_USER_INFO : 's',
        ID.HON_CS_START_MM_GROUP : 'sHsssH',
        ID.HON_CS_INVITE_TO_MM : 's',
        ID.HON_CS_CHANNEL_KICK : 'II',
        ID.HON_CS_CHANNEL_BAN : 'Is',
        ID.HON_CS_CHANNEL_UNBAN : 'Is',
        ID.HON_CS_CHANNEL_SILENCE_USER : 'IsI',
        ID.HON_CS_UPDATE_TOPIC : 'Is',
        ID.HON_CS_CHANNEL_AUTH_ENABLE : 'I',
        ID.HON_CS_CHANNEL_AUTH_DISABLE : 'I',
        ID.HON_CS_CHANNEL_AUTH_ADD : 'Is',
        ID.HON_CS_CHANNEL_AUTH_DELETE : 'Is',
        ID.HON_CS_CHANNEL_PROMOTE : 'II',
        ID.HON_CS_CHANNEL_DEMOTE : 'II',
        ID.HON_CS_CLAN_ADD_MEMBER : 's',
        ID.HON_CS_CLAN_MESSAGE : 's',
        ID.HON_CS_GLOBAL_MESSAGE : 'IBs',
        ID.HON_CS_CLAN_REMOVE_MEMBER : 'I',
        ID.HON_CS_KICK_FROM_MM : 'B',
        }
```
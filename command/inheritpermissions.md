---
title: vc/inheritpermissions
description: Set where secondaries get their permissions from
published: true
date: 2020-07-28T17:08:28.203Z
tags: 
editor: undefined
---

Choose where new channels created by a certain primary channel get their permissions from. You can use this to allow only certain people to create channels, but anyone to join them.

Available options are:

-  `primary`/`parent`: (default) New channels will use the same permissions as the "+ New session" channel they are created from.
-  `category`: New channels will use whatever permissions are set up for the category they are in (the same behavior as creating channels manually).
-  `CHANNEL_ID`: Specify an existing voice channel whose permissions new channels will copy. Must be a permanent channel that the bot can see - if the channel is ever deleted or becomes inaccessible, the primary channel's permissions will silently be used instead (as is the default).
# Usage

>vc/inheritpermissions `primary/category/CHANNEL ID`


# Examples

- `vc/inheritpermissions primary`
- `vc/inheritpermissions category`
- `vc/inheritpermissions 603174408957198347`


---
title: vc/logging
description: Log voice channel activity in your server to a chosen text channel.
published: true
date: 2020-07-13T14:00:06.624Z
tags: 
editor: undefined
---

Log voice channel activity in your server to a chosen text channel.

Use `vc/logging here` to enable logging to this channel, or enter a channel ID instead of here to use a different channel.
Use `vc/logging off` to disable logging.

You can optionally specify a logging level by adding `1`/`2`/`3` after your command (e.g. `vc/logging here 3`). The higher the level, the more info is logged:

* **Level 1** (default):
Someone creates a new channel; Someone tries creating channels too quickly and is temporarily put on cooldown; Someone initiates a votekick.
* **Level 2:**
Someone sets/removes the user limit of their channel; Someone sets a custom bitrate for themselves; Someone renames their own channel; An empty channel is deleted.
* **Level 3:**
Someone joins or leaves an existing channel.

Level 3 logging is only available to 💎 Sapphire Patron servers, as it may generate a large number of messages which could overload the bot and trigger Discord's rate limiting.

If you don't specify a logging level and haven't done so before, level 1 will be assumed.


# Usage

> vc/logging `CHANNEL_ID/here/off`

# Examples

* `vc/logging here`
Enable logging in the channel you typed the command in.
* `vc/logging here 3`
Enable logging in this channel at level 3.
* `vc/logging 601032893002940436 2`
Enable logging in the text channel with the ID `601032893002940436` at level 2.
* `vc/logging off`
Turn off logging.
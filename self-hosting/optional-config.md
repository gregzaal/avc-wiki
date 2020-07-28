---
title: Optional Configuration
description: 
published: true
date: 2020-06-30T15:09:45.983Z
tags: 
editor: undefined
---

The `config.json` file accepts a number of extra options to customize your admin experience:

* `"disable_ready_message"`: (*bool*, default `false`) Use to prevent the bot spamming you "Ready" when it regains connection, which may be quite often if your internet is unstable.
* `"admin_channel"`: (*int*, channel ID) Define a channel for admin messages (such as the "Ready" message and errors) instead of using DMs. Beware that anyone who has permission to send messages in this channel can use all the [admin commands](https://github.com/gregzaal/Auto-Voice-Channels/blob/master/commands/admin_commands.py) such as shutting down the bot, disabling it, changing the status, and fetching/changing potentially sensitive user data.
* `"disable_creation_loop"`: (*bool*, default `false`) For extremely large servers, set this to `true` if your bot starts creating multiple channels for one person even though they only wanted one. This will disable the background loop that watches primary channels, so the only way a new channel will be created is if the event of the user joining a primary channel is caught.
* `"heartbeat_timeout"`: (*int*, default 60) For *extremely* extremely large servers, if your bot is having trouble connecting and repeatedly timing out before it can finish processing all members, set this to some higher number.
* `"b2_key_id"`, `"b2_key"`, and `"b2_destination"`: (*string*) Set up automated backups of the bot (including config & guild settings) to [Backblaze B2](https://www.backblaze.com/b2/cloud-storage.html) cloud storage in case of catastrophic server or harddrive failure. If you do this, you can download the entire `b2_destination` folder to a new server and immediately get the bot running again. The cost of using B2 this way for a single bot is probably under $0.10 per month. `b2_destination` should be in the form `b2://bucketname/subfolder`. The bot itself doesn't run any backups, but `backup.py` uses this information (which you need to run separately, preferably setting up a cronjob similar to what's shown in `backup_cron.txt` for automated regular backups).
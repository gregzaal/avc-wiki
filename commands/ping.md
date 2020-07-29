---
title: vc/ping
description: Test the bot and its response time.
published: true
date: 2020-07-02T15:33:05.915Z
tags: 
editor: undefined
---

Test if the bot is alive, and see the delay (in seconds) between your command and its response.

* 0.1s to 1s response time is normal.
* Higher than 1s indicates it's struggling to keep up, but you should try again to see if the delay was only temporary.
* Higher than 10s indicates something is probably very, very wrong.
* No response means you either typed the command incorrectly, the bot don't have permission to read and respond to messages in that channel, or it's dead.

Also shows the shard ID for debugging purposes, the guild (discord server) region, and the region of the server/device that the bot is hosted on.
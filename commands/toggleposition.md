---
title: vc/toggleposition
description: Toggle whether secondaries are created above or below their primaries.
published: true
date: 2020-09-15T10:11:38.569Z
tags: 
editor: markdown
---

Toggle whether new channels are placed above (default) or below the primary one.
First join a voice channel and then run the command to toggle the position of future channels created by the same primary ("+ New Session") channel.

> Does not affect existing channels, wait for those to become empty and get deleted, or move them manually.
{.is-info}

> Channel positioning in discord is extremely unpredictable. We do our best and hackiest methods to get it as reliable as possible, but it's not always enough.
> 
> If a new channel is going to be the lowest voice channel in your server, it will be placed second from the bottom instead. To work around this, just make an AFK channel, or an invisible voice channel at the bottom of your server.
> 
> If things still don't behave the way they should, you can try manually moving channels around or deleting them to force the bot's cache to update, which may improve things for you. Otherwise there's nothing anyone can do because the bot already thinks things are correct, discord is simply giving it false information.
{.is-warning}



#  Usage

>vc/toggleposition
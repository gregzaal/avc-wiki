---
title: vc/bitrate
description: Set a server-wide custom bitrate for yourself that will be used for any channels you join.
published: true
date: 2020-07-14T10:44:09.661Z
tags: 
editor: undefined
---

Set a server-wide custom bitrate (in kbps) for yourself that will be used for any channels you join.

This can be used either to improve audio quality (e.g. for music channels), or to lower the bandwidth used for those with limited/expensive internet.

> Note: The bitrate is for the entire channel, not just you. If there are other users in the channel that have set custom bitrates, the average bitrate setting will be used.
{.is-info}

If no one in the channel has set a custom bitrate, the bitrate of the primary ('New Session') channel will be used.

Use [vc/channelinfo](/command/channelinfo) to check the current bitrate of the channel you're in.

# Usage

> vc/bitrate `NUMBER/reset`

# Examples

* `vc/bitrate 80`
Any channels you join will have a bitrate of 80kbps

* `vc/bitrate reset`
Forget your previous bitrate setting and use the channel default.
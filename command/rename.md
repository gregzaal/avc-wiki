---
title: vc/rename
description: Rename someone else's channel
published: true
date: 2020-07-12T14:26:24.229Z
tags: 
editor: undefined
---

Just like [vc/name](/command/name), but you can rename someone else's voice channel without having to be in that channel yourself.

Only server admins can use this command.

Like [vc/name](/command/name) it supports all variables from the [template](/command/template) command.

# Usage

> vc/rename `CHANNEL_ID` `NAME/reset`

If you don't know how to find the channel ID, enable Developer Mode in your User Settings in discord, then right click the channel and select *Copy ID*.

# Examples

* `vc/rename 603174408957198347 Pix's den`
The channel name will be "Pix's den".

* `vc/rename 603174408957198347 @@num@@ blind mice`
Depending on the number of users in the channel, will be something like "3 blind mice".

* `vc/rename 603174408957198347 reset`
Removes any custom name so the channel will use the original template.
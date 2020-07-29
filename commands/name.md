---
title: vc/name
description: Directly change the name of the channel you're in.
published: true
date: 2020-07-12T14:18:55.987Z
tags:
editor: undefined
---

Directly change the name of the channel you're in. Supports all variables from the [template](/commands/template) command.

> **Note:** Discord has strict rate limiting in place that prevents channels from being renamed too often. At the time of writing this, it allows renaming only twice every 10 minutes. Because of this, your channel may not be renamed as often as you like, but just be patient, the bot will rename it eventually.
{.is-warning}

# Usage

> vc/name `NAME/reset`

# Examples

* `vc/name Pix's den`
Your channel name will be "Pix's den".

* `vc/name @@num@@ blind mice`
Depending on the number of users in the channel, will be something like "3 blind mice".

* `vc/name reset`
Removes your custom name so your channel will use the original template.
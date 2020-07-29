---
title: vc/create
description: 
published: true
date: 2020-07-01T13:28:38.909Z
tags: 
editor: undefined
---

Make a new primary voice channel. When users join this channel, the bot will make a new one for them and move them into it. By default primary channels are named "+ New Session" and placed at the top of your server, but you can safely rename it, move it around and change its permissions.

You can create as many primary channels as you want and place them in different areas of your server. They (and the secondary channels created with them) will inherit the permissions of the category they are in by default.

> If you move a primary channel into a private/restricted category, make sure the bot has permission to create and edit voice channels there.
{.is-warning}

Secondary channels will copy the perimissions, bitrate and user limit of their primary channel.

By default secondary channels will be placed above their primary channel. Use [vc/toggleposition](/command/toggleposition) to place them below instead.

To set the name template of new secondary channels created using this primary channel, first join the primary channel and wait to be moved into a new channel, then use [vc/template](/command/template).

> If you're still unclear what the difference between a "Primary" and "Secondary" channel is, read [How it Works](/how-it-works).
{.is-info}

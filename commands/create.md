---
title: vc/create
description: 
published: true
date: 2020-10-21T15:15:34.606Z
tags: 
editor: markdown
---

Make a new primary voice channel. When users join this channel, the bot will make a new one for them and move them into it. By default primary channels are named "+ New Session" and placed at the top of your server, but you can safely rename it, move it around and change its permissions.

You can create as many primary channels as you want and place them in different areas of your server. 

> If you move a primary channel into a private/restricted category, make sure the bot has permission to create and edit voice channels there.
{.is-warning}

Secondary channels will copy the perimissions, bitrate and user limit of their primary channel.

By default secondary channels will be placed above their primary channel. Use [vc/toggleposition](/commands/toggleposition) to place them below instead.

To set the name template of new secondary channels created using this primary channel, first join the primary channel and wait to be moved into a new channel, then use [vc/template](/commands/template).

> If you're still unclear what the difference between a "Primary" and "Secondary" channel is, read [How it Works](/how-it-works).
{.is-info}

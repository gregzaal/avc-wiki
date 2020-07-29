---
title: vc/private
description: Make your voice channel private, preventing anyone from joining you directly.
published: true
date: 2020-07-25T13:45:02.039Z
tags:
editor: undefined
---

Make your voice channel private, preventing anyone from joining you directly.

Creates a "⇩ Join (username)" channel above yours so people can request to join you. When someone joins that channel, The bot will send you a message asking you to approve/deny/block their request.

> Note: It's currently not possible to create private channels by default. [Read why in the FAQ](/FAQ#can-i-make-private-channels-by-default).
{.is-info}

To make your private channel public again, use [vc/public](/commands/public).

If you simply want to prevent users from joining you at all, even by request, simply use [vc/lock](/commands/lock).

# Usage

> vc/private

To make your private channel public again, use [vc/public](/commands/public).

# How it works

The private command performs the following steps:

* Denies permission for the `@everyone` role to join your channel.
* Gives you explicit permission to join your own channel (so you can safely leave and come back).
* Creates a "🠋 Join (username)" channel above your channel.
* When someone joins the "🠋 Join" channel, the bot sends you a message to approve their request.
* If you approve it, the bot moves them into your channel and grants them permission.
* If you deny it, the bot notifies them and kicks them from the "🠋 Join" channel.
* If you block the request, the bot not only kicks them from the "🠋 Join" channel but also denies them permission to join it again, preventing them from requesting to join again.
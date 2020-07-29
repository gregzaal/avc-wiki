---
title: vc/uniquenames
description: Toggle whether custom channel names set with vc/name have to be unique or not
published: true
date: 2020-07-12T13:59:29.518Z
tags: 
editor: undefined
---

Toggle whether custom channel names set with the gvc/name or gvc/rename commands have to be unique or not.

**OFF by default.**

When turned on, users will be unable to rename their channel if there is another voice channel with the same custom name anywhere in the server.

> The check is only done once when renaming the channel, and compares only the name/template itself, not the result of the template being evaluated. E.g. `We love @@game_name@@` will be seen as identical to another channel with the same template, even if the game they are playing is different.
{.is-info}

# Usage

> `vc/uniquenames` to toggle on/off.
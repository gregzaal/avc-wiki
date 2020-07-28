---
title: vc/asip
description: Short for "Assume Sneaky is Playing"
published: true
date: 2020-07-28T16:13:40.560Z
tags: 
editor: undefined
---

Short for "Assume Sneaky is Playing" - This affects the behavior of the @@num_playing@@ template variable.

@@num_playing@@ is determined firstly by any party information found in Discord Rich Presence, however most games do not use Rich Presence so it has to take a guess based on the activity status of members in the voice channel.
However some users choose not to display their game activity as a status message for privacy reasons, or set themselves to "Invisible". Because of this, @@num_playing@@ might be inaccurate.

This command toggles whether or not channel members without any activity status are assumed to be playing the most popular game in the channel.

Use this command if your server plays primarily only one or a handful of games, and you use @@num_playing@@ in your channel template.

> **OFF** by default
{.is-info}

# Usage

>vc/asip





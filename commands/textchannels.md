---
title: vc/textchannels
description: Create temporary private text channels for each voice chat
published: true
date: 2020-07-29T08:49:13.007Z
tags: 
editor: markdown
---

> **Premium Feature**
> This feature is only available to [Gold Patrons](https://www.patreon.com/pixaal), unless you are self-hosting.
{.is-info}


Toggle whether or not to create temporary private text channels for each voice chat, for people to spam links, music bot commands, `/tts` (text-to-speech) commands, or for people without mics to type in. These channels are only visible to members of each voice chat and get deleted along with the VC once everyone leaves.

This setting is **OFF** by default.

To set the channel name for all future text channels, use the [vc/textchannelname](/command/textchannelname) command.

It's not currently possible to change the text channel names independently based on the template or VC name, all text channel names will be the same.

> Discord has an internal limit of 50 channels (of any type) per category. I.e. 50 voice channels, or 25 voice + 25 text channels.
> 
> To get over this limit, you can always [create](/command/create) more primary channels in other categories.
{.is-warning}

> Note: As an admin it may be tricky to discern which text channel is yours, since you can see all of them and they all have the same name. 
> 
> Simply look at the user list on the right when selecting the channel - the one with the same members as the voice you're in is the one for you.
> 
> You can safely rename your specific channel to make it easier to find again, but do not change the channel topic as this is used to find and delete the channel in some cases.
{.is-info}

# Usage

> `vc/textchannels` to toggle on/off.
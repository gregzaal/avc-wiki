---
title: How it Works
description: Explanations of various concepts
published: true
date: 2020-07-18T21:59:44.114Z
tags:
editor: undefined
---

# The Basics

This bot is intended to solve the issue of having an unpredictable or variable number of voice channels needed depending on activity in your server.

Sometimes nobody's playing anything and you have a huge list of empty channels. Then maybe a game gets updated and suddenly all your old friends come back online to play and you don't have enough voice channels for every squad.

This bot lets your users create voice channels on the fly, meaning you can have both a clean channel list when no one is online, and hundreds of channels when things get busy.

## Primary and Secondary Channels

To accomplish this, you create "Primary" channels, which act as a kind of button to create new channels for your users. When someone clicks on the Primary channel to join it, the bot will create a new "Secondary" channel for them and move them into that.

Secondary channels are named dynamically based on a number of factors, such as what game the channel members are playing, the creators name, etc. [A full list of these options is available here](/commands/template).

You can also have as many Primary channels as you want, each with its own name template, permissions, limits, default bitrate, etc - and each Primary channel can be used to create as many secondary channels as you want, which will get deleted automatically when they're no longer used.

Use [vc/create](/commands/create) to create a new Primary channel, and [vc/template](/commands/template) to set the name template for Secondary channels that your users spawn in.

Once everybody leaves a Secondary channel, the bot will delete it.

# The Creator

When a new secondary channel is created, the user who made it is assigned as the "creator" of that channel.

There are certain commands like [vc/private](/commands/private) that only the creator is allowed to use.

If the original creator ever leaves their channel, the person who is at the top of the channel (alphabetically first) is assigned as the new creator, gaining access to those restricted commands.

# How Secondary Channels Work

## Channel Creation

The primary way channels get created is when the bot detects someone joining a primary channel.

However there are a number of ways people can abuse the bot by spam-creating channels, which could result in discord banning the bot for abusing their API.

To counter this, there's an abuse-detection system that prevents users from creating channels too quickly:

1. The bot sets a lock for a few seconds on the user so they will be ignored if they really spam-click the primary channels.
2. If the user successfully creates several channels in short succession, it will set an even longer lock on them, send them a warning message, and log the event if [logging](/commands/logging) is enabled.

There is also a background loop that checks for occupants of any primary channels that have been sitting there for a few seconds at least, and will create a channel if there aren't any locks in place for them.

> Discord has an internal limit of 50 channels per category, this doesn't have anything to do with the bot. If you need more than 50 channels, just use multiple Primary channels in different categories.
{.is-info}


## Channel Renaming

Channel renaming works off a continuous background loop that checks every few minutes* if a channel needs to be renamed.

On each loop iteration, it calculates what the channel name should currently be according to your [template](/commands/template) and the various data about the members of the channel. If this calculated name differs from the current name then it renames the channel.

> *Note: Discord's rate-limiting prevents the bot from renaming a channel more than twice every 10 minutes. To be safe while we implement a more immediate event-based renaming system, it will currently only rename channels once every 5 minutes.
{.is-info}

> If you are self-hosting and modify the code to increase the rename interval, you risk worsening your performance even further and getting your bot banned by Discord.
{.is-warning}

## Channel Deletion

When the last user in a secondary channel disconnects from it, the bot will delete the channel.

If the channel was created very recently, it will not be deleted immediately, but instead deleted a minute or two later once the bot realizes it's still not in use.

You can safely delete secondary channels manually too, however this may temporarily screw with the numbering and positioning of other secondary channels. It will take a few minutes for the bot to realize the channel no longer exists and remove it from it's memory.
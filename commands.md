---
title: Commands
description: A list of all bot commands with links to more detailed documentation for each.
published: true
date: 2020-07-28T17:39:49.694Z
tags: 
editor: undefined
---

The default prefix for all commands is `vc/`, e.g. `vc/create`. You can also @mention the bot instead, like `@Auto Voice Channels create`.

If you change your prefix and then forget what it is, the only way to use the bot again would be to @mention it with the prefix command, e.g. `@Auto Voice Channels prefix vc/`.

To get more info about a particular command, type `vc/help commandname`.


# Common Commands

Here are the most commonly used commands. Further down this page is also a full alphabetical list of [all commands](/commands#list-of-all-commands).


### [vc/create](/command/create)
Create a new [primary](/how-it-works#primary-and-secondary-channels) voice channel.

Primary channels are "button" channels that you click on to create a new secondary channels. The default channel name is "➕ New Session", but you can rename it to whatever you like by right clicking on it and editing it as usual. Discord supports [standard emoji](http://www.unicode.org/emoji/charts/full-emoji-list.html) in voice channel names, but not custom or discord-specific emoji.

The primary channel will be created somewhere near the top of your server, you can move it down to wherever you like. Just **make sure that the bot has permission to create and edit voice channels there.**


### [vc/template](/command/template)
Secondary channels that get created with primary channels will be named according to your template. This command lets you change the template. The default template is `## [@@game_name@@]`.

See here for a [full list of available template variables](/command/template) that you can use to customize your channel names, including examples.


### [vc/private](/command/private)
Make your voice channel private, preventing anyone from joining you directly.

Creates a "⇩ Join (username)" channel above you so people can request to join you. When someone joins that channel, the bot will send you a message asking you to approve/deny/block their request.


### [vc/lock](/command/limit) or [vc/limit](/command/limit)
Lock or set the user limit of your channel to prevent any more people from being able to join.

These two are actually the same command and are duplicated for convenience. If you do not add a number at the end (e.g. running `vc/lock`), it will set the user limit to the current number of users in the channel. If you do add a number (e.g. `vc/limit 5`), it will set the limit to that number.

If you want to do this permanently for all secondaries created by the same primary channel, either just edit the user limit of the primary channel itself, or use [vc/defaultlimit](/command/defaultlimit).


### [vc/ping](/command/ping)
A quick test command to check the bot is working, and show its response time. Frequently high response times (>2s) may indicate performance issues.

Also displays the server region and region the bot is hosted in. The closer together these regions are the better your response times should be.


# List of All Commands

Below is a list of all commands grouped by Setup commands and Usage commands.

If you are using the free public bot, "💳" indicates that the command can only be used by Gold [patrons](https://patreon.com/pixaal). If you're hosting your own bot, all commands can be used.

## Setup Commands

Commands that you'll probably only use a couple times when setting your channels up.

All of these commands can only be used by server staff (people with both *manage channels* and *manage roles* permissions).

* [alias](/command/alias) - Set an alias for a game name.
* [aliases](/command/aliases) - List all the game name aliases you've set.
* [asip](/command/asip) - Assume offline/no-status users are playing the same game.
* [create](/command/create) - Create a new primary channel.
* [dcnf](/command/dcnf) - Disable "command not found" errors.
* [defaultlimit](/command/defaultlimit) - Set the default user limit for secondaries from a certain primary.
* [disable](/command/disable) - Disable the bot.
* [ecnf](/command/ecnf) - Enable "command not found" errors.
* [enable](/command/enable) - Enable the bot (enabled by default).
* [general](/command/general)💳 - Set the word to use instead of "General" in channel names.
* [inheritpermissions](/command/inheritpermissions) - Set where secondaries get their permissions from (default from their primary).
* [listroles](/command/listroles) - List all the roles in your server and their IDs.
* [logging](/command/logging)💳 - Configure channel activity logging.
* [prefix](/command/prefix) - Set the bot prefix in your server (default `vc/`).
* [removealias](/command/removealias) - Remove a game name alias.
* [restrict](/command/restrict)💳 - Prevent users without a specific role from using certain commands.
* [restrictions](/command/restrictions)💳 - List the command restrictions you've set.
* [servercheck](/command/servercheck) - Display info about your server and the channels the bot knows about.
* [showtextchannelsto](/command/showtextchannelsto)💳 - Set a role that text channels created by the bot will also be visible to.
* [template](/command/template) - Set the name template for secondary channels.
* [textchannelname](/command/textchannelname)💳 - Set the name of text channels created by the bot.
* [textchannels](/command/textchannels)💳 - Tell the bot to create a private text channel for every secondary voice channel.
* [toggleposition](/command/toggleposition) - Toggle whether secondaries are created above or below their primaries.
* [uniquenames](/command/uniquenames)💳 - Force names set with [vc/name](/command/name) to be unique.

## Usage Commands

Commands that you may use regularly for controlling and modifying the channels you're in.

Most of these commands can be used by everyone in your server. Use the [restrict](/command/restrict) command to prevent this if you don't want it.

Commands that modify a voice channel usually require you to be the creator of the channel, or an admin.

* [allyourbase](/command/allyourbase) - (admin only) Assume ownership of the channel you're in.
* [bitrate](/command/bitrate)💳 - Set a server-wide custom bitrate for yourself.
* [channelinfo](/command/channelinfo) - A debugging command to show game/bitrate info about users in your channel.
* [help](/command/help) - Show info on how to use the bot.
* [invite](/command/invite) - Gives you a link to invite the bot to a new server.
* [kick](/command/kick) - Initiate a votekick to remove someone from your channel.
* [limit](/command/limit)/[lock](/command/limit) - Set the user limit of your channel.
* [name](/command/name)💳 - Rename your voice channel (supports all template options).
* [nick](/command/nick)💳 - Change how your name is shown in the channel name.
* [patreon](/command/patreon) - Gives you a link to the bot developers patreon page.
* [ping](/command/ping) - Test the response time of the bot.
* [private](/command/private) - Prevent users from being able to join you directly.
* [public](/command/public) - Make your channel public again after being private.
* [rename](/command/rename)💳 - (admin only) Like [vc/name](/command/name), but you can rename someone else's channel.
* [source](/command/source) - Get a link to the source code of the bot.
* [transfer](/command/transfer) - Give ownership of your channel to someone else.
* [unlimit](/command/unlimit)/[unlock](/command/unlimit) - Remove the user limit of your channel.

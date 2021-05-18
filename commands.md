---
title: Commands
description: A list of all bot commands with links to more detailed documentation for each.
published: true
date: 2021-05-18T08:24:02.448Z
tags: 
editor: markdown
---

The default prefix for all commands is `vc/`, e.g. `vc/create`. You can also @mention the bot instead, like `@Auto Voice Channels create`.

If you change your prefix and then forget what it is, the only way to use the bot again would be to @mention it with the prefix command, e.g. `@Auto Voice Channels prefix vc/`.

To get more info about a particular command, type `vc/help commandname`.


# Common Commands

Here are the most commonly used commands. Further down this page is also a full alphabetical list of [all commands](/commands#list-of-all-commands).


### [vc/create](/commands/create)
Create a new [primary](/how-it-works#primary-and-secondary-channels) voice channel.

Primary channels are "button" channels that you click on to create a new secondary channels. The default channel name is "➕ New Session", but you can rename it to whatever you like by right clicking on it and editing it as usual. Discord supports [standard emoji](http://www.unicode.org/emoji/charts/full-emoji-list.html) in voice channel names, but not custom or discord-specific emoji.

The primary channel will be created somewhere near the top of your server, you can move it down to wherever you like. Just **make sure that the bot has permission to create and edit voice channels there.**


### [vc/template](/commands/template)
Secondary channels that get created with primary channels will be named according to your template. This command lets you change the template. The default template is `## [@@game_name@@]`.

See here for a [full list of available template variables](/commands/template) that you can use to customize your channel names, including examples.


### [vc/private](/commands/private)
Make your voice channel private, preventing anyone from joining you directly.

Creates a "⇩ Join (username)" channel above you so people can request to join you. When someone joins that channel, the bot will send you a message asking you to approve/deny/block their request.


### [vc/lock](/commands/limit) or [vc/limit](/commands/limit)
Lock or set the user limit of your channel to prevent any more people from being able to join.

These two are actually the same command and are duplicated for convenience. If you do not add a number at the end (e.g. running `vc/lock`), it will set the user limit to the current number of users in the channel. If you do add a number (e.g. `vc/limit 5`), it will set the limit to that number.

If you want to do this permanently for all secondaries created by the same primary channel, either just edit the user limit of the primary channel itself, or use [vc/defaultlimit](/commands/defaultlimit).


### [vc/ping](/commands/ping)
A quick test command to check the bot is working, and show its response time. Frequently high response times (>2s) may indicate performance issues.

Also displays the server region and region the bot is hosted in. The closer together these regions are the better your response times should be.


# List of All Commands

Below is a list of all commands grouped by Setup commands and Usage commands.

If you are using the free public bot, "💳" indicates that the command can only be used by Gold [patrons](https://patreon.com/pixaal). If you're hosting your own bot, all commands can be used.

## Setup Commands

Commands that you'll probably only use a couple times when setting your channels up.

All of these commands can only be used by server staff (people with both *manage channels* and *manage roles* permissions).

* [alias](/commands/alias) - Set an alias for a game name.
* [aliases](/commands/aliases) - List all the game name aliases you've set.
* [asip](/commands/asip) - Assume offline/no-status users are playing the same game.
* [create](/commands/create) - Create a new primary channel.
* [dcnf](/commands/dcnf) - Disable "command not found" errors.
* [defaultlimit](/commands/defaultlimit) - Set the default user limit for secondaries from a certain primary.
* [disable](/commands/disable) - Disable the bot.
* [ecnf](/commands/ecnf) - Enable "command not found" errors.
* [enable](/commands/enable) - Enable the bot (enabled by default).
* [general](/commands/general)💳 - Set the word to use instead of "General" in channel names.
* [inheritpermissions](/commands/inheritpermissions) - Set where secondaries get their permissions from (default from their primary).
* [listroles](/commands/listroles) - List all the roles in your server and their IDs.
* [logging](/commands/logging)💳 - Configure channel activity logging.
* [prefix](/commands/prefix) - Set the bot prefix in your server (default `vc/`).
* [removealias](/commands/removealias) - Remove a game name alias.
* [restrict](/commands/restrict)💳 - Prevent users without a specific role from using certain commands.
* [restrictions](/commands/restrictions)💳 - List the command restrictions you've set.
* [servercheck](/commands/servercheck) - Display info about your server and the channels the bot knows about.
* [showtextchannelsto](/commands/showtextchannelsto)💳 - Set a role that text channels created by the bot will also be visible to.
* [template](/commands/template) - Set the name template for secondary channels.
* [textchannelname](/commands/textchannelname)💳 - Set the name of text channels created by the bot.
* [textchannels](/commands/textchannels)💳 - Tell the bot to create a private text channel for every secondary voice channel.
* [toggleposition](/commands/toggleposition) - Toggle whether secondaries are created above or below their primaries.
* [uniquenames](/commands/uniquenames)💳 - Force names set with [vc/name](/commands/name) to be unique.

## Usage Commands

Commands that you may use regularly for controlling and modifying the channels you're in.

Most of these commands can be used by everyone in your server. Use the [restrict](/commands/restrict) command to prevent this if you don't want it.

Commands that modify a voice channel usually require you to be the creator of the channel, or an admin.

* [allyourbase](/commands/allyourbase) - (admin only) Assume ownership of the channel you're in.
* [bitrate](/commands/bitrate)💳 - Set a server-wide custom bitrate for yourself.
* [channelinfo](/commands/channelinfo) - A debugging command to show game/bitrate info about users in your channel.
* [help](/commands/help) - Show info on how to use the bot.
* [invite](/commands/invite) - Gives you a link to invite the bot to a new server.
* [kick](/commands/kick) - Initiate a votekick to remove someone from your channel.
* [limit](/commands/limit)/[lock](/commands/limit) - Set the user limit of your channel.
* [name](/commands/name)💳 - Rename your voice channel (supports all template options).
* [nick](/commands/nick)💳 - Change how your name is shown in the channel name.
* [patreon](/commands/patreon) - Gives you a link to the bot developers patreon page.
* [ping](/commands/ping) - Test the response time of the bot.
* [private](/commands/private) - Prevent users from being able to join you directly.
* [public](/commands/public) - Make your channel public again after being private.
* [rename](/commands/rename)💳 - (admin only) Like [vc/name](/commands/name), but you can rename someone else's channel.
* [source](/commands/source) - Get a link to the source code of the bot.
* [transfer](/commands/transfer) - Give ownership of your channel to someone else.
* [unlimit](/commands/unlimit)/[unlock](/commands/unlimit) - Remove the user limit of your channel.

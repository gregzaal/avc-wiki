---
title: vc/showtextchannelsto
description: For moderation, show all text channels that are made with vc/textchannels to users with a certain role
published: true
date: 2020-07-14T10:41:06.918Z
tags: 
editor: undefined
---

Show the text channels that are made for each voice channel (when [vc/textchannels](/command/textchannels) is enabled) to users that have the specified role, e.g. moderators, or **@everyone** if you want them to be public.

> Only one role can be specified, using this command multiple times will overwrite the previous setting.
{.is-warning}

> Note: Text channels will still be deleted once everyone leaves the associated voice chat.
{.is-info}

# Usage

> vc/showtextchannelsto `ROLE_ID`
> vc/showtextchannelsto `@Role`
> vc/showtextchannelsto `none`

# Examples

* `vc/showtextchannelsto 615086491235909643`
Show all AVC text channels to users that have the role with ID `615086491235909643`.
* `vc/showtextchannelsto @everyone`
Show all AVC text channels to all users in your server, making them public instead of only readable by members of their associated voice channel.
* `vc/showtextchannelsto @Moderators`
Show all AVC text channels to users that have the **@Moderator** role.
* `vc/showtextchannelsto none`
Remove any previous setting and don't show AVC text channels to anyone other than the occupants of the associated voice channel.
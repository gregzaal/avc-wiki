---
title: vc/kick
description: Initiate a votekick to remove someone from your channel.
published: true
date: 2020-08-19T16:23:42.487Z
tags: 
editor: markdown
---

Initiate a votekick to remove a user from your channel and prevent them from joining again.

> More than half of the remaining users must vote yes in order for the member to be kicked.
{.is-info}

If you wish to allow a kicked user to return to the channel, you will all have to leave and create a new channel instead, or if you are a server admin, manually edit the channel permissions.

> The person who initially created the channel cannot be kicked (unless they leave voluntarily and later return, in which case the "creator" of the channel is reassigned to the person who was at the top of the channel when they left.)
{.is-warning}

# Usage

vc/kick `@USER`

vc/kick `@USER`
`REASON`

# Examples

* `vc/kick @pixaal`
 Initaites a votekick to remove the user @pixaal from your channel
- `vc/kick pixaal#1774`
   `Being mean`
Initaites a votekick to remove the user pixaal#1774 from your channel while also mentioning them in a message telling them the reason , in this case *being mean*
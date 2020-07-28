---
title: vc/defaultlimit 
description: Set the default user limit for secondaries from a certain primary.
published: true
date: 2020-07-28T16:37:33.348Z
tags: 
editor: undefined
---

Set the default user limit for channels created by a particular primary channel, without editing the primary channel itself.

First join a voice channel, then run the command to set the limit for that channel and all other secondary channels created by the same primary ("+ New Session") channel.

Doesn't affect any existing sibling channels, only future channels. 
Users can still run "vc/limit" or "vc/unlimit" to temporarily change/remove the limit of their own channel.


# Usage

vc/defaultlimit `N`
> Remove the limit by running `vc/defaultlimit 0`
{.is-info}


# Examples

- vc/defaultlimit 4
 Sets the default user limit for channels created by a particular primary channel to 4 


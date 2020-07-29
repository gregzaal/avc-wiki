---
title: vc/lock & vc/limit
description: Limit the number of users allowed in your channel.
published: true
date: 2020-07-14T10:48:09.546Z
tags: 
editor: undefined
---

Limit the number of users allowed in your channel to either the current number of users, or the specified number.

`vc/lock` and `vc/limit` are actually the same command and can be used interchangably.

To remove any limit, use [vc/unlock](/command/unlimit).

# Usage

> vc/lock
> vc/limit `NUMBER`

# Examples

* `vc/lock`
Sets the user limit of your channel to the number of people who are currently in it, preventing any more people from joining.
* `vc/lock 5`
Set the user limit to 5.
* `vc/limit`
Same as `vc/lock`
* `vc/limit 5`
Same as `vc/lock 5`
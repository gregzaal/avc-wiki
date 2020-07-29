---
title: vc/restrict
description: Restrict a particular command so that only users with a certain role can use it.
published: true
date: 2020-07-28T17:38:48.706Z
tags: 
editor: undefined
---

Restrict a particular command so that only users with a certain role can use it. Server admins will always be able to use any command regardless of their roles.

Use [vc/listroles @user](/command/listroles) to get a list of roles (and their IDs) that a user has.
Use [vc/restrictions](/command/restrictions) to see any existing restrictions that are in place.

# Usage

> vc/restrict `COMMAND` `ROLE_ID`
> vc/restrict `COMMAND` `none`

# Examples

* `vc/restrict name 615086491235909643`
Only users that have the role with ID 615086491235909643 can use the name command.

* `vc/restrict lock 582927946004693000 615086491235909643`
Only users that have **either** the role with ID `582927946004693000` or `615086491235909643` can use the lock command.

* `vc/restrict name none`
Remove all restrictions for the name command.
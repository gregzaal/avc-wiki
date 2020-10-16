---
title: Expressions
description: Expressions are a powerful way to set the channel name based on certain conditions.
published: true
date: 2020-10-16T15:28:19.537Z
tags: 
editor: markdown
---

> Note: Since Discord increased their rate limit and channels are only renamed once every 10 minutes, expressions are significantly less useful than before - the information in the channel name can be up to 10 minutes out of date.
{.is-warning}


Expressions are a powerful way to set the channel name based on certain conditions, such as whether or not the creator has a particular role, what game is being played, and the party size.

Expressions must be in the following form:
>`{{CONDITION ?? TRUE // FALSE}}`
{.is-info}

If the `CONDITION` part is met, whatever you wrote in the `TRUE` part will be added to the channel name, otherwise the `FALSE` part will be used instead. The `FALSE` part is optional and can be left out (e.g. `{{CONDITION ?? TRUE}}`).

Anything at all can be written inside the `TRUE/FALSE` parts, including other template variables like `@@num@@` or `@@game_name@@`, or even other nested expressions, however only a certain things may be used as the `CONDITION`:

- `ROLE:role id`
Check whether or not the creator has a particular role.
- `GAME=game name`
Check if the game that users in the channel are playing (the same one that `@@game_name@@` returns, including aliases) matches **exactly** the text provided.
You can also use `!=` instead of `=` to match anything **other** than exactly the text provided, or `:` to match anything that **contains** the text provided. E.g. `GAME:Call of Duty` will match with *"Call of Duty: Modern Warfare"*, but `GAME=Call of Duty` will not.
- `LIVE`
Whether or not the creator of the channel is streaming. Use `LIVE_DISCORD` to only detect discord's "Go Live" streams, or `LIVE_EXTERNAL` for Twitch. `LIVE` will include both.
- `PLAYERS>number`
💎[*Patrons only*](https://www.patreon.com/pixaal). Check if the number of players in your game (determined either by Discord Rich Presence or the game activity statuses of members in the channel) is greater than the number provided. You can also use `<`, `<=`, `>=`, `=` and `!=`
- `MAX>number`
💎[*Patrons only*](https://www.patreon.com/pixaal). Check if the maximum number of players allowed in your game (determined by Discord Rich Presence or the channel limit) is greater than the number provided. You can also use `<`, `<=`, `>=`, `=` and `!=`
- `RICH`
💎[*Patrons only*](https://www.patreon.com/pixaal). Whether or not the current game uses Discord Rich Presence, which means `@@num_playing@@`, `@@party_size@@`, `@@party_state@@`, and `@@party_details@@` should have reliable values.
 
##  EXAMPLES

`{{GAME:Left 4 Dead ?? [@@num_playing@@/4]}}`

`{{LIVE??🔴 @@stream_name@@}}`

`{{PLAYERS=1 ?? LFG}}`

`{{PLAYERS<=20 ?? ## [@@game_name@@] // It's a party!}}`

`{{MAX=@@num_playing@@ ?? (Full) // (@@num_playing@@)}}`

`{{RICH??@@party_details@@{{MAX>1?? (@@num_playing@@/@@party_size@@)}}}}`

`{{ROLE:601025860614750229 ?? {{ROLE:615086491235909643??[UK] // {{ROLE:607913610139664444??[DE] // [EU]}}}}}}`

The spaces around the `??` and `//` improve readability but may not be desired if you do not want any spaces around the result.

If you have a question or need any help setting up an expression, please ask me in the [support server](https://discord.io/DotsBotsSupport). I'd be happy to add any extra variables you need.
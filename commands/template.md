---
title: vc/template
description: Automatically name your voice channels using dynamic variables
published: true
date: 2020-08-26T15:39:26.893Z
tags: 
editor: markdown
---

Change the name template for [secondary](/how-it-works#primary-and-secondary-channels) channels dynamically using variables.

The default template is `## [@@game_name@@]`.

# Usage

To use the command, first join a [primary](/how-it-works#primary-and-secondary-channels) channel and wait for the bot to create a new secondary channel for you. Then run the command.

> vc/template `TEMPLATE`

See [examples](/commands/template#examples) below.


# Template Variables

Variables are "keywords" that you can use in your template that then get replaced with some data dynamically, such as the name of the game that users in the channel are playing, which can change over time.

Secondary channels will rename themselves every few minutes according to your template if necessary (e.g. when members of the channel start playing a different game).

> **Note:** Discord has strict rate limiting in place that prevents channels from being renamed too often. At the time of writing this, it allows renaming only twice every 10 minutes. Because of this, your channel may not be renamed as often as you like, but just be patient, the bot will rename it eventually.
{.is-warning}

If you don't really understand the concept of what a "variable" is, check out the example templates at the bottom of this page.

Remember, this bot is open source. If you don't like the behavior of a template variable or you want to add a new one, you can change whatever you like. If you think other people will appreciate your changes, please [submit a pull request](https://github.com/gregzaal/Auto-Voice-Channels/pulls) :)

Here are the variables you can use:


## Names

### `@@game_name@@`
Replaced with the game that most people in the channel are playing. If no one is playing anything or there is too much variety (more than 2 games with an equal number of players), "General" will be shown instead. Use [vc/general](/commands/general) to use a different word than "General".

### `@@creator@@`
The name of the person who first joined the channel. This person has control over the channel and can use commands such as [vc/private](/commands/private) and [vc/name](/commands/name). If they leave, the person at the top of the channel (alphabetically) becomes the new creator.

### `@@stream_name@@`
If the creator is streaming to Twitch and have their Twitch account connected to Discord (purple status), this is replaced with their stream name. If they are not streaming, it's simply removed.


## Numbering

### `##`
The channel number with a `#` in front. The first channel created will be "#1", the next "#2", etc. If the people from the first channel leave and it's deleted, channel #2 will be renamed to #1.

### `$#`
The channel number just like `##`, but without a `#` in front. e.g. "1", "2", "3" instead of "#1", "#2", "#3".

### `$0#`, `$00#`, `$000#`, etc.
Just like `$#` above but with padded zeros (e.g. "001", "002", etc.)

### `@@nato@@` (💳\*)
Use the NATO Phonetic Alphabet as the channel number. The first channel will be "Alpha", the next one "Bravo", the third on "Charlie", etc.

### `@@num@@`
The total number of users in the channel.

### `@@num_others@@`
The total number of users in the channel, excluding the creator.


## Advanced

### `<<singular/plural>>`
Use the word before the slash if `@@num@@` is 1, or the word after it if it's more than 1.

Using a back-slash (`\`) between the singular and plural form instead of a forward-slash will check `@@num_others@@` instead of `@@num@@`, which is probably what you want if you are using `@@num_others@@` in your template.

### `""operation:Text to Manipulate""` - [String Manipulation](/string-manipulation)
Any text (including the result of other template variables) can be further manipulated in a number of ways, such as modifying upper/lower case, making abbreviations, or removing certain words. These options are [explained separately here](/string-manipulation).

### `[[group/squad/team/clan]]` - Random word or phrase selection (💳\*)
Pick a random word between the slashes when the channel is created. Use a back-slash (`\`) instead of a forward-slash if you want it to select a random word every few minutes instead of only once when the channel is created.

### `{{EXPRESSION ?? TRUE // FALSE}}` - [Expressions](/expressions) (💳\*)
Expressions are a powerful way to set the channel name based on certain conditions, such as whether or not the creator has a particular role, what game is being played, the party size, etc. [Read more here](/expressions).


## Rich Presence

Certain games provide discord with detailed information about the game a user is currently playing, such as the map name, character info, level progress, party size and number of actual players in the party. This is discord "Rich Presence".

Not all games support this, in fact most of them don't, but some do and the bot can utilize this information in the channel name if it's available.

What information is provided in which variables is up to the game developer, and there's no real standard, so it can be quite unpredictable from game to game. You'll just have to experiment with the options for different games to see what happens. You can run [vc/channelinfo](/commands/channelinfo) to get a detailed list of Rich Presence data for each player if it's available.

You may want to use the `{{RICH}}` [expression](/expressions) to check if the current game uses Rich Presence.

### `@@num_playing@@` (💎\*)
The number of users playing in the same game session. Uses the game's Rich Presence info if it's available, otherwise it makes a guess from the game activity of users in the voice chat.

### `@@party_size@@` (💎\*)
The maximum number of players allowed in the game. Uses the game's Rich Presence info if it's available, otherwise it uses the channel's user limit. Defaults to `0` if no size is found.

### `@@party_details@@` (💎\*)
The party details provided by Rich Presence, which varies by game. Usually the game mode, difficulty and/or mission name.

### `@@party_state@@` (💎\*)
The party state information provided by Rich Presence, which varies by game. May be character played, team info, game mode, etc.


## \*💳/💎 Restrictions
If you are using the free public bot (not self-hosting or supporting us on Patreon), certain template options marked with **(💳\*)** or **(💎\*)** are disabled, as they are either have a high performance impact and would cripple the public bot (even further) if everyone could use them, or are meant as a fun Thank-You to patrons.

Variables marked with "💳" are only usable by Gold level patrons and up. Variables marked with "💎" are only usable by Sapphire level patrons and up.

If you are hosting the bot yourself, all variables are enabled by default.

# Examples

Template: `vc/template ## [@@game_name@@]`\
Example results: "#1 [Skyrim]", "#2 [Apex Legends]"

Template: `vc/template @@num@@ blind <<mouse/mice>>`\
Example results: "1 blind mouse", "3 blind mice"

Template: `vc/template @@creator@@ and the @@num_others@@ <<Dwarf\Dwarves>>`\
Example results: "Snow White and the 7 Dwarves", "pewdiepie and the 1 Dwarf"

Template: `vc/template @@nato@@ [[Squad/Team/Party/Noobs]]`\
Example results: "Alpha Team", "Charlie Squad"

Template: `vc/template @@game_name@@ {{GAME:Left 4 Dead ?? [@@num_playing@@/4]}}`\
Example results: "Left 4 Dead 2 [3/4]", "PUBG"

Template: `vc/template @@game_name@@ {{ROLE:601025860614750229 ?? {{ROLE:615086491235909643??[UK] // {{ROLE:607913610139664444??[EU] // [Unknown]}}}}}}`\
Example results: "PUBG [UK]", "PUBG [EU]"

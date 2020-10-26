---
title: Frequently Asked Questions
description: Questions that we're tired of answering a thousand times :)
published: true
date: 2020-10-26T15:04:16.601Z
tags: 
editor: markdown
---

# Why are the free public bots unstable/slow/offline sometimes?

The free public bots are simply struggling with popularity. So many people are using them that they're getting stuck and taking a long time to do anything, like creating channels or responding to commands.

Sometimes they'll take so long trying to do something that they'll actually just give up and never do it at all.

They might also get stuck in an infinite loop of creating channels for you and flood your server with broken channels, though this is less common.

The only current solutions for this instability are:

1. [Host your own bot](https://github.com/gregzaal/Auto-Voice-Channels). You can do this on your own computer for free, but a VPS with a decent connection that's on 24/7 is recommended. These usually start from $5/m.
2. [Support us on Patreon](https://www.patreon.com/pixaal) ($3/m) and use our stable Gold bot, or let us host a private bot just for you ($7/m).

# Why isn't my channel renaming itself?

Discord has strict rate-limiting that prevents the bot from renaming channels too often. If we consistently hit these limits, the bot would get banned. To prevent this, channels are only checked for renaming once every 10 minutes. [More info here](/how-it-works#channel-renaming)

# What is the difference between the *Alpha*, *Beta*, and *Asia* bots?

*Alpha* and *Beta* are the same, these are 2 copies of the same bot in an attempt to spread the load and improve performance.

*Asia* is the same too, just hosted in Singapore for better response time to Asian discord servers.

Alpha is the original "Auto Voice Channels" bot, and is merely referred to as "Alpha" in our support server.

# Why does the [toggleposition](/commands/toggleposition) command not work?

Channel positioning in discord is extremely unpredictable. We do our best and hackiest methods to get it as reliable as possible, but it's not always enough.

If a new channel is going to be the lowest voice channel in your server, it will be placed second from the bottom instead. To work around this, just make an AFK channel, or an invisible voice channel at the bottom of your server.

# Why is the channel order sometimes wrong?

Channel positioning in discord is extremely unpredictable. We do our best and hackiest methods to get it as reliable as possible, but it's not always enough.

You can try manually moving channels around or deleting them to force the bot's cache to update, which may improve things for you. Otherwise there's nothing anyone can do because the bot already thinks things are correct, discord is simply giving it false information.

# Can I make [private](/commands/private) channels by default?

No. Private channels are very api-heavy and often hit discord's rate limit as it is. In their current implementation. making private channels by default would get the public bots banned.

This is a highly requested feature though, so it's quite likely we'll have a solution for it in future, but it may be limited to Sapphire patrons and self-hosters only.

# Why won't the bot respond to my command?

This is usually because the bot doesn't have permission to see (or reply in) the channel where you typed the command. Check the bot permissions in these three locations: The server, the category that the channel is in, and the channel itself.

You should see the bot in the user list on the right, though it may still not have permission to send messages there. The most common cause of this is that you're hiding that channel from the everyone role, which includes the bot.

# Why can't I see the bot in the user list?

This is usually because the bot doesn't have permission to see the channel you're looking at. Check the bot permissions in these three locations: The server, the category that the channel is in, and the channel itself.

# Nothing happens when I join the "+ New Session" channel

This is usually because the bot doesn't have permission to create a new channel in that category. Make sure you add the bot's role to that category's permissions and enable the following:
- Read Text Channels & See Voice Channels
- Manage Channel
- Send Messages
- Move Members
- Connect

# I'm self-hosting and the bot is spamming "Ready" messages every few minutes

This is usually caused by hosting the bot on a poor internet connection, such as your home network. Every "Ready" message indicates the bot lost connection and then reconnected.

We recommend using a cheap VPS as these are usually located in a datacenter with a stable internet connection, but you can also set `"disable_ready_message": true` in your [config file](/en/self-hosting/optional-config).
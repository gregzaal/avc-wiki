---
title: Comandos
description: Una lista de todos los comandos del Bot con enlaces a la documentación más detallada para cada uno.
published: true
date: 2020-10-30T12:50:14.876Z
tags: 
editor: markdown
---

El prefix predeterminado para todos los comandos es `vc/`, por ejemplo: `vc/create`. En su lugar, también puede @mencionar el Bot, como por ejemplo: `@Auto Voice Channels create`.

Si cambia su prefijo y luego olvida cuál es, la única forma de usar el Bot nuevamente sería @mencionarlo con el comando de prefix, por ejemplo: `@Auto Voice Channels prefijo vc/`.

Para obtener más información sobre un comando en particular, escriba `vc/help nombrecomando`.


#  Comandos comunes

Estos son los comandos más utilizados. Más abajo en esta página también hay una lista alfabética completa de [todos los comandos](/commands#lista-de-todos-los-comandos).


### [vc/create](/commands/create)
Cree un nuevo canal de voz [principal](/how-it-works#canales-principales-y-secundarios).

Los canales principales son canales de "botón" en los que hace clic para crear nuevos canales secundarios. El nombre del canal predeterminado es "➕ New Session", pero puede cambiarle el nombre por el que desee haciendo clic derecho sobre él y editándolo como de costumbre. Discord admite [emoji estándar](http://www.unicode.org/emoji/charts/full-emoji-list.html) en los nombres de los canales de voz, pero no emoji personalizados o específicos de discord.

El canal principal se creará en algún lugar cerca de la parte superior de su servidor, puede moverlo hacia abajo a donde quiera. Solo asegúrese de que el bot tenga permiso para crear y editar canales de voz allí.


### [vc/template](/commands/template)
Los canales secundarios que se crean con canales primarios se nombrarán de acuerdo con su plantilla. Este comando le permite cambiar la plantilla. La plantilla predeterminada es `## [@@game_name@@]`.

Consulte aquí para obtener una [lista completa de las variables de plantilla disponibles](/commands/template) que puede utilizar para personalizar los nombres de sus canales, incluidos ejemplos.


### [vc/private](/commands/private)
Haga que su canal de voz sea privado, evitando que nadie se una a usted directamente.

Crea un canal "⇩ Join (username)" encima de ti para que las personas puedan solicitar unirse a ti. Cuando alguien se une a ese canal, el bot le enviará un mensaje pidiéndole que apruebe/rechace/bloquee su solicitud.


### [vc/lock](/commands/limit) o [vc/limit](/commands/limit)
Bloquea o establece el límite de usuarios de tu canal para evitar que más personas puedan unirse.

Estos dos son en realidad el mismo comando y están duplicados por conveniencia. Si no agrega un número al final (por ejemplo: ejecutando `vc/lock`), establecerá el límite de usuarios al número actual de usuarios en el canal. Si agrega un número (por ejemplo: `vc/limit 5`), establecerá el límite para ese número.

Si desea hacer esto permanentemente para todos los secundarios creados por el mismo canal principal, simplemente edite el límite de usuario del canal principal en sí, o use [vc/defaultlimit](/commands/defaultlimit).


### [vc/ping](/commands/ping)
Un comando de prueba rápida para verificar que el bot está funcionando y mostrar su tiempo de respuesta. Con frecuencia, los tiempos de respuesta altos (>2s) pueden indicar problemas de rendimiento.

También muestra la región del servidor y la región en la que está alojado el bot. Cuanto más juntas estén estas regiones, mejores serán los tiempos de respuesta.


# Lista de todos los comandos

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
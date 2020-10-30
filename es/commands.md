---
title: Comandos
description: Una lista de todos los comandos del Bot con enlaces a la documentación más detallada para cada uno.
published: true
date: 2020-10-30T12:34:45.723Z
tags: 
editor: markdown
---

El prefix predeterminado para todos los comandos es `vc/`, por ejemplo: `vc/create`. En su lugar, también puede @mencionar el Bot, como por ejemplo: `@Auto Voice Channels create`.

Si cambia su prefijo y luego olvida cuál es, la única forma de usar el Bot nuevamente sería @mencionarlo con el comando de prefix, por ejemplo: `@Auto Voice Channels prefijo vc/`.

Para obtener más información sobre un comando en particular, escriba `vc/help nombrecomando`.


#  Comandos comunes

Estos son los comandos más utilizados. Más abajo en esta página también hay una lista alfabética completa de [todos los comandos](/commands#list-de-todos-los-comandos).


### [vc/create](/commands/create)
Cree un nuevo canal de voz [principal](/how-it-works#canales-principales-y-secundarios).

Los canales principales son canales de "botón" en los que hace clic para crear nuevos canales secundarios. El nombre del canal predeterminado es "➕ New Session", pero puede cambiarle el nombre por el que desee haciendo clic derecho sobre él y editándolo como de costumbre. Discord admite [emoji estándar](http://www.unicode.org/emoji/charts/full-emoji-list.html) en los nombres de los canales de voz, pero no emoji personalizados o específicos de discord.

El canal principal se creará en algún lugar cerca de la parte superior de su servidor, puede moverlo hacia abajo a donde quiera. Solo asegúrese de que el bot tenga permiso para crear y editar canales de voz allí.


### [vc/template](/commands/template)
Los canales secundarios que se crean con canales primarios se nombrarán de acuerdo con su plantilla. Este comando le permite cambiar la plantilla. La plantilla predeterminada es `## [@@game_name@@]`.

Consulte aquí para obtener una [lista completa de las variables de plantilla disponibles](/commands/template) que puede utilizar para personalizar los nombres de sus canales, incluidos ejemplos.


### [vc/private](/commands/private)
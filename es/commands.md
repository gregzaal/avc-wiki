---
title: Comandos
description: Una lista de todos los comandos del Bot con enlaces a la documentación más detallada para cada uno.
published: true
date: 2020-10-30T15:18:05.300Z
tags: 
editor: markdown
---

El prefix predeterminado para todos los comandos es `vc/`, por ejemplo: `vc/create`. En su lugar, también puede @mencionar el Bot, como por ejemplo: `@Auto Voice Channels create`.

Si cambia su prefijo y luego olvida cuál es, la única forma de usar el Bot nuevamente sería @mencionarlo con el comando de prefix, por ejemplo: `@Auto Voice Channels prefix vc/`.

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

A continuación se muestra una lista de todos los comandos agrupados por comandos de configuración y comandos de uso.

Si está utilizando el bot público gratuito, "💳" indica que el comando solo puede ser utilizado por usuarios con la [Versión oro](https://patreon.com/pixaal). Si aloja su propio bot, se pueden usar todos los comandos.

## Comandos de configuración

Comandos que probablemente solo usarán un par de veces al configurar sus canales.

Todos estos comandos solo pueden ser utilizados por el personal del servidor (personas con permisos de administración de canales y roles de administración).

* [alias](/commands/alias) - Establece un alias para el nombre de un juego.
* [aliases](/commands/aliases) - Lista todos los alias de nombres de juegos que has establecido.
* [asip](/commands/asip) - Asume que los usuarios sin conexión/sin estado están jugando el mismo juego.
* [create](/commands/create) - Crea un nuevo canal principal.
* [dcnf](/commands/dcnf) - Desactiva los errores de "comando no encontrado".
* [defaultlimit](/commands/defaultlimit) - Establece el límite de usuario predeterminado para los canales secundarios de un determinado canal principal.
* [disable](/commands/disable) - Deshabilita el Bot.
* [ecnf](/commands/ecnf) - Habilita los errores de "comando no encontrado"
* [enable](/commands/enable) - Habilita el bot (habilitado de forma predeterminada).
* [general](/commands/general)💳 - Establece la palabra que se utilizará en lugar de "General" en los nombres de los canales.
* [inheritpermissions](/commands/inheritpermissions) - Establece de dónde obtienen los permisos los canales secundarios (predeterminado de su principal).
* [listroles](/commands/listroles) - Lista todos los roles en su servidor y sus ID.
* [logging](/commands/logging)💳 - Configura el registro de actividad del canal.
* [prefix](/commands/prefix) - Establece el prefix del Bot en su servidor (`vc/` es el predeterminado).
* [removealias](/commands/removealias) - Elimina un alias del  nombre de un juego.
* [restrict](/commands/restrict)💳 - Evita que los usuarios sin un rol específico utilicen determinados comandos.
* [restrictions](/commands/restrictions)💳 - Lista las restricciones de comando que ha establecido.
* [servercheck](/commands/servercheck) - Muestra información sobre su servidor y los canales que conoce el Bot.
* [showtextchannelsto](/commands/showtextchannelsto)💳 - Establece un rol para el que los canales de texto creados por el Bot también serán visibles.
* [template](/commands/template) - Establece la plantilla de nombre para los canales secundarios.
* [textchannelname](/commands/textchannelname)💳 - Establece el nombre de los canales de texto creados por el Bot.
* [textchannels](/commands/textchannels)💳 - Dígale al bot que cree un canal de texto privado para cada canal de voz secundario.
* [toggleposition](/commands/toggleposition) - Permite alternar si los canales secundarios se crean por encima o por debajo de los principales.
* [uniquenames](/commands/uniquenames)💳 - Fuerza que los nombres establecidos con [vc/name](/commands/name) sean únicos.

## Comandos de uso

Comandos que puede usar regularmente para controlar y modificar los canales en los que se encuentra.

La mayoría de estos comandos pueden ser utilizados por todos en su servidor. Utilice el comando [restrict](/commands/restrict) para evitar esto si no lo desea.

Los comandos que modifican un canal de voz generalmente requieren que usted sea el creador del canal o un administrador.

* [allyourbase](/commands/allyourbase) - (solo administrador) Asume la propiedad del canal en el que estás.
* [bitrate](/commands/bitrate)💳 - Establece una velocidad de bits personalizada para usted.
* [channelinfo](/commands/channelinfo) - Un comando de depuración para mostrar información de juego/bitrate sobre los usuarios de su canal.
* [help](/commands/help) - Muestra información/ayuda sobre cómo usar el Bot.
* [invite](/commands/invite) - Te da un enlace para invitar al Bot a un nuevo servidor.
* [kick](/commands/kick) - Inicia una votación para expulsar a alguien de su canal.
* [limit](/commands/limit)/[lock](/commands/limit) - Establece el límite de usuario de su canal.
* [name](/commands/name)💳 - Cambie el nombre de su canal de voz (admite todas las opciones de plantilla).
* [nick](/commands/nick)💳 - Cambia cómo se muestra tu nombre en el nombre del canal.
* [patreon](/commands/patreon) - Le da un enlace a la página de patreon de los desarrolladores de Bots.
* [ping](/commands/ping) - Prueba el tiempo de respuesta del Bot.
* [private](/commands/private) - Evita que los usuarios puedan unirse a usted directamente.
* [public](/commands/public) - Vuelve a hacer público su canal después de ser privado.
* [rename](/commands/rename)💳 - (solo administrador) Como [vc/name](/commands/name), pero puedes renombrar el canal de otra persona.
* [source](/commands/source) - Obtenga un enlace al código fuente del Bot.
* [transfer](/commands/transfer) - Transfiere la propiedad de su canal a otra persona.
* [unlimit](/commands/unlimit)/[unlock](/commands/unlimit) - Elimina el límite de usuarios de su canal.
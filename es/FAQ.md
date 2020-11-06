---
title: FAQ (Preguntas frecuentes)
description: Preguntas que estamos cansados de responder mil veces :)
published: true
date: 2020-11-06T18:27:35.804Z
tags: 
editor: markdown
---

# ¿Por qué los bots públicos gratuitos son inestables/lentos/se desconectan a veces?

Los bots públicos gratuitos simplemente están luchando por ganar popularidad. Hay tanta gente que los usa que se quedan atascados y tardan mucho en hacer cualquier cosa, como crear canales o responder a comandos.

A veces tardan tanto en hacer algo que en realidad simplemente se rinden y nunca lo hacen.

También pueden atascarse en un ciclo infinito de creación de canales para usted e inundar su servidor con canales corruptos, aunque esto es menos común.

Las únicas soluciones actuales para esta inestabilidad son:

1. [Hostee su propio bot](https://github.com/gregzaal/Auto-Voice-Channels). Puede hacer esto en su propio ordenador de forma gratuita, pero se recomienda un VPS con una conexión decente que esté encendida las 24 horas, los 7 días de la semana. Por lo general, estos comienzan desde $5/m.
2. [Apóyenos en Patreon](https://www.patreon.com/pixaal) ($3/m) y use nuestro Bot Gold estable, o permítanos alojar un bot privado solo para usted ($7/m).


# ¿Por qué mi canal no cambia de nombre?

Discord tiene un rate-limit estricto que evita que el Bot cambie el nombre de los canales con demasiada frecuencia. Si constantemente alcanzamos estos límites, el Bot sería baneado. Para evitar esto, los canales solo se comprueban para cambiar el nombre una vez cada 10 minutos. [Más información aquí](/how-it-works#cambio-del-nombre-del-canal)


# ¿Cuál es la diferencia entre los Bots *Alpha*, *Beta* y *Asia*?

*Alpha* y *Beta* son lo mismo, son 2 copias del mismo Bot en un intento de distribuir la carga y mejorar el rendimiento.

*Asia* también es lo mismo, solo alojado en Singapur para un mejor tiempo de respuesta a los servidores de Discord asiáticos.

Alpha es el Bot original de "Auto Voice Channels" y simplemente se lo denomina "Alpha" en nuestro servidor de soporte.


# ¿Por qué no funciona el comando [toggleposition](/commands/toggleposition)?

El posicionamiento del canal en Discord es extremadamente impredecible. Hacemos nuestros mejores y más intrincados métodos para que sea lo más cocorrecto posible, pero no siempre es suficiente.

Si un nuevo canal va a ser el canal de voz más bajo en su servidor, se colocará en segundo lugar desde abajo. Para solucionar esto, simplemente cree un canal AFK, o un canal de voz invisible en la parte inferior de su servidor.


# ¿Por qué a veces el orden de los canales es incorrecto?

El posicionamiento del canal en Discord es extremadamente impredecible. Hacemos nuestros mejores y más intrincados métodos para que sea lo más correcto posible, pero no siempre es suficiente.

Puede intentar mover manualmente los canales o eliminarlos para forzar la actualización de la caché del bot, lo que puede mejorar las cosas para usted. De lo contrario, no hay nada que nadie pueda hacer porque el Bot ya cree que las cosas están correctas, Discord esta simplemente dándole información falsa.


# ¿Puedo hacer canales [privados](/comannds/private) por defecto?

No. Los canales privados son muy utilizan muchla la API y a menudo alcanzan el rate-limit de Discord tal como está, en su implementación actual. Hacer canales privados por defecto haría que los Bots públicos fueran baneados.

Sin embargo, esta es una función muy solicitada, por lo que es muy probable que tengamos una solución para ella en el futuro, pero puede estar limitada solo a los usuarios con una versión de pago o self-hosting.


# ¿Por qué el bot no responde a mi comando?

Por lo general, esto se debe a que el Bot no tiene permiso para ver (o responder) el canal donde escribió el comando. Verifique los permisos del Bot en estas tres ubicaciones: el servidor, la categoría en la que se encuentra el canal y el canal en sí.

Debería ver el Bot en la lista de usuarios de la derecha, aunque es posible que aún no tenga permiso para enviar mensajes allí. La causa más común de esto es que estás ocultando ese canal al rol `@everyone`, que incluye al Bot.

Si no es eso, entonces también es posible que usted/alguien haya cambiado el prefijo. Simplemente @mencione el Bot para probar esto ("`@Auto Voice Channels` ping"), y si responde, luego configure su prefijo de nuevo a lo que espera que sea (predeterminado`vc/`) con "`@Auto Voice Channels` prefix vc/".


# ¿Por qué no puedo ver el bot en la lista de usuarios?

Esto suele deberse a que el Bot no tiene permiso para ver el canal que estás viendo. Verifique los permisos del Bot en estas tres ubicaciones: el servidor, la categoría en la que se encuentra el canal y el canal en sí.


# No pasa nada cuando me uno al canal "+ New Session"

Esto generalmente se debe a que el Bot no tiene permiso para crear un nuevo canal en esa categoría. Asegúrese de agregar la función del Bot a los permisos de esa categoría y habilite lo siguiente:
- Leer canales de texto y ver canales de voz
- Administrar canal
- Enviar mensajes
- Mover miembros
- Conectar


# Estoy hosteando el Bot y envía spam de mensajes "Ready" cada pocos minutos

Esto generalmente se debe a que el Bot se aloja en una conexión a Internet deficiente, como la red doméstica. Cada mensaje de "Ready" indica que el bot perdió la conexión y luego se reconectó.

Recomendamos utilizar un VPS económico, ya que normalmente se encuentran en un centro de datos con una conexión a Internet estable, pero también puede configurar `"disable_ready_message": true` en su [archivo de configuración](/self-hosting/optional-config) .
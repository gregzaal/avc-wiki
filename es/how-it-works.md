---
title: Cómo funciona
description: Explicación de varios conceptos.
published: true
date: 2020-11-06T17:46:18.812Z
tags: 
editor: markdown
---

# Lo básico

Este Bot está destinado a resolver el problema de tener un número impredecible o variable de canales de voz necesarios según la actividad en su servidor.

A veces, nadie juega y tienes una lista enorme de canales vacíos. Entonces, tal vez un juego se ponga de moda y de repente todos tus  amigos vuelvan para jugar y no tengas suficientes canales de voz para cada equipo.

Este Bot permite a sus usuarios crear canales de voz sobre la marcha, lo que significa que puede tener una lista de canales limpia cuando no hay nadie conectado y cientos de canales cuando haya actividad en el servidor.


## Canales principales y secundarios

Para lograr esto, crea canales "principales", que actúan como una especie de botón para crear nuevos canales para sus usuarios. Cuando alguien hace clic en el canal principal para unirse a él, el Bot creará un nuevo canal "secundario" para ellos y los moverá a él.

Los canales secundarios se nombran dinámicamente en función de una serie de factores, como el juego que juegan los miembros del canal, el nombre de los creadores, etc. [Una lista completa de estas opciones está disponible aquí](/commands/template).

También puede tener tantos canales principales como desee, cada uno con su propia plantilla de nombre, permisos, límites, tasa de bits predeterminada, etc., y cada canal principal se puede utilizar para crear tantos canales secundarios como desee, que se eliminarán automáticamente cuando ya no se utilizan.

Use [vc/create](/commands/create) para crear un nuevo canal primario y [vc / template](/commands/template) para configurar la plantilla de nombre para los canales secundarios en los que sus usuarios generan.

Una vez que todos abandonen un canal secundario, el Bot lo eliminará.


# El creador

Cuando se crea un nuevo canal secundario, el usuario que lo creó se asigna como el "creador" de ese canal.

Hay ciertos comandos como [vc/private](/commands/private) que solo el creador puede usar.

Si el creador original alguna vez abandona su canal, la persona que está en la parte superior del canal (en orden alfabético primero) se asigna como el nuevo creador, obteniendo acceso a esos comandos restringidos.


# Cómo funcionan los canales secundarios


## Creación de canales

La forma principal en que se crean los canales es cuando el Bot detecta que alguien se une a un canal principal.

Sin embargo, hay varias formas en que las personas pueden abusar del Bot mediante canales de creación de spam, lo que podría provocar que Discord banee el Bot por abusar de su API.

Para contrarrestar esto, existe un sistema de detección de abuso que evita que los usuarios creen canales demasiado rápido:

1. El Bot bloquea durante unos segundos al usuario para que sea ignorado si realmente hace spam de clic en los canales principales.
2. Si el usuario crea exitosamente varios canales en una sucesión corta de tiempo, bloqueará al usuario un periodo de tiempo mayor, le enviará un mensaje de advertencia y registrará el evento si [registro](/commands/logging) está habilitado.

También hay un bucle de fondo que comprueba si hay ocupantes de cualquier canal principal que haya estado allí durante unos segundos al menos, y creará un canal si no hay ningún bloqueo.

> Discord tiene un límite interno de 50 canales por categoría, esto no tiene nada que ver con el Bot. Si necesita más de 50 canales, simplemente use varios canales principales en diferentes categorías.
{.is-info}


## Cambio del nombre del canal

El cambio del nombre del canal funciona a partir de un bucle de fondo continuo que comprueba cada pocos minutos* si es necesario cambiar el nombre de un canal.

En cada iteración de bucle, calcula cuál debería ser el nombre del canal actualmente de acuerdo con su [plantilla](/commands/template) y los diversos datos sobre los miembros del canal. Si este nombre calculado difiere del nombre actual, cambia el nombre del canal.

> *Nota: El rate-limiting de Discord evita que el Bot cambie el nombre de un canal más de dos veces cada 10 minutos. Para estar seguros mientras implementamos un sistema de cambio de nombre más inmediato basado en eventos, actualmente solo cambiará el nombre de los canales una vez cada 5 minutos.
{.is-info}

> Si el Bot es self-hosting y modifica el código para aumentar el intervalo de cambio de nombre, corre el riesgo de empeorar aún más su rendimiento y que Discord banee su bot.
{.is-warning}


## Eliminación de canales

Cuando el último usuario de un canal secundario se desconecta de él, el bot eliminará el canal.

Si el canal se creó muy recientemente, no se eliminará de inmediato, sino que se eliminará uno o dos minutos más tarde una vez que el bot se dé cuenta de que aún no está en uso.

También puede eliminar manualmente los canales secundarios de forma segura, sin embargo, esto puede alterar temporalmente la numeración y la posición de otros canales secundarios. El bot tardará unos minutos en darse cuenta de que el canal ya no existe y eliminarlo de su memoria.
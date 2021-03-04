---
title: Optionale Konfiguration
description: 
published: true
date: 2021-03-04T00:59:12.642Z
tags: 
editor: markdown
---

Die `config.json` Datei lässt sich durch eine Reihe von optionalen Einträgen anpassen, um deine Erfahrung als Administrator nochmals zu verbessern:

* `"disable_ready_message"`: (*bool*, default `false`) - Setze diesen Eintrag auf `true`, um den Bot daran zu hindern, dich jedes Mal mit "Ready" zu benachrichtigen, wenn er die Verbindung wiederhergestellt hat. Dies kann wahlweise öfter passieren, wenn deine Internetverbindung sehr instabil ist.
* `"admin_channel"`: (*int*, channel ID) - Definiere einen Channel für Admin Benachrichtigungen (wie z.B. die "Ready" Benachrichtung oder Fehlernachrichten), anstatt private Nachrichten vom Bot zu erhalten. Aber Vorsicht! Jeder Benutzer, der die Berechtigung hat, in diesen Channel zu schreiben, kann alle [Admin Befehle](https://github.com/gregzaal/Auto-Voice-Channels/blob/master/commands/admin_commands.py) nutzen, wie z.B. den Bot herunterfahren, deaktivieren, den Status verändern oder potenziell sensible Benutzerdaten abgreifen/verändern.
* `"disable_creation_loop"`: (*bool*, standardmäßig `false`) - Für sehr große Server. Setze diesen Wert auf `true`, wenn dein Bot anfängt mehrere Channel für eine Person zu erstellen, obwohl die Person nur einen Channel benötigt. Dieser Eintrag wird den "loop" (Endlosschleife) deaktivieren, welcher die primären Channel überwacht. Ein neuer Channel wird also nur erstellt, wenn das Ereignis, dass der Benutzer einem primären Channel beitritt, aufgefangen wird.
* `"heartbeat_timeout"`: (*int*, standardmäßig 60) - Für *sehr* sehr große Server. Ändere diesen Eintrag, wenn dein Bot Probleme mit dem Verbinden auf den Server hat und/oder wiederholt einen Timeout bekommt, bevor die Abarbeitung aller Mitglieder abgeschlossen werden konnte. In diesem Fall erhöhe den Wert der Zahl.
* `"b2_key_id"`, `"b2_key"`, and `"b2_destination"`: (*string*) - Erstellt automatische Back-Ups vom Bot (einschließlich Konfigurationsdatei und guild Einstellungen auf der [Backblaze B2](https://www.backblaze.com/b2/cloud-storage.html) Cloud. Im Falle eines katastrophalen Server oder Festplatten Versagens sind deine Daten gesichert. Solltest du dieses Feature nutzen, kannst du den gesamten `b2_destination` Ordner auf einen neuen Server laden und den Bot sofort wieder zum Laufen bringen. Die Kosten für die Nutzung von B2 in dieser Art, für einen einzelnen Bot, belaufen sich wahrscheinlich auf unter 0.10$ pro Monat. `b2_destination` sollte ungefähr dieser Form entsprechen: `b2://bucketname/subfolder`. Der Bot selbst führt keine Backups aus. Aber `backup.py` verwendet diese Informationen - die du separat ausführen musst - (um vorzugsweise einen Cronjob, ähnlich dem in` backup_cron.txt` für automatisierte reguläre Backups gezeigten Format, einzurichten).
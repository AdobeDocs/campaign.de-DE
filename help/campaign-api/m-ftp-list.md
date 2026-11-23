---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 15%
---
# auflisten

Gibt die Liste der Dateien auf dem Server in einem angegebenen Verzeichnis zurück.

```text
list (URL, pattern [, max ])
```

## Parameter

**URL** Adresse des FTP-Servers als URL.

**pattern** Datei und Maske der Liste der abzurufenden Dateien.

**max** Maximale Anzahl an zurückzugebenden Dateien Wenn dieser Parameter fehlt, gibt die Methode die vollständige Liste der Dateien zurück.

## Rückgabewert

Eine Tabelle mit den Dateinamen, die dem angegebenen Pfad und der angegebenen Maske entsprechen.

## Bemerkungen

Wenn der FTP-Befehl fehlschlägt und eine Ausnahme ausgelöst wird. Beispiel:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
```

## Funktionen

**Methode der Klasse:** [FTP](c-ftp.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

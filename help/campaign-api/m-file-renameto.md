---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 40%
---
# Umbenennen in

Benennt eine Datei um.

```text
renameTo (fileName)
```

## Parameter

**fileName** Neuer Dateiname (muss ein vollständiger Pfad sein).

## Rückgabewert

Keine.

## Bemerkungen

Beispiele:

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
```

## Funktionen

**Methode der Klasse:** [File](c-file.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

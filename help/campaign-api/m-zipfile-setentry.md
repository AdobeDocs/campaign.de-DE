---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 23%
---
# setEntry

Fügt eine Datei im Archiv hinzu oder aktualisiert sie.

```text
setEntry (filename, buffer)
```

## Parameter

**filename** Name der Quelldatei.

**buffer** MemoryBuffer, der die Datei enthält.

## Rückgabewert

Keine.

## Bemerkungen

Das Archiv wird erst dann effektiv auf der Festplatte geändert, wenn die Methode [save()](m-zipfile-save.md) aufgerufen wird.

## Funktionen

**Methode der Klasse:** [ZipFile](c-zipfile.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

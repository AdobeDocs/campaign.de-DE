---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 18%
---
# öffnen

Lädt ein vorhandenes Archiv.

```text
open ()
```

## Parameter

Keine.

## Rückgabewert

Keine.

## Bemerkungen

Im Falle eines vorhandenen Archivs müssen Sie zunächst die Methode ⌐[fileCount](p-zipfile-filecount.md) aufrufen, um die Anzahl der Dateien abzurufen, oder [getEntry()](m-zipfile-getentry.md), um eine Datei zu extrahieren. Die Methode löst eine Ausnahme aus, wenn die Datei nicht vorhanden ist oder wenn die Datei kein gültiges Archiv ist.

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

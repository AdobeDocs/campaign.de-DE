---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 21%
---
# fileGetTempName

Erzeugt einen temporären Dateinamen.

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## Parameter

**directory** Verzeichnis der temporären Datei. Wenn leer, verwenden Sie das vom System definierte temporäre Verzeichnis.

**prefix** Präfix mit maximal 4 Zeichen. Wenn es leer ist, wird das tmp-Präfix verwendet.

**extension** Dateierweiterung.

## Rückgabewert

Vollständiger Name der Datei.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

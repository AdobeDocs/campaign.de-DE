---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 18%
---
# loadXmlFile

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Diese Funktion ist veraltet. Verwenden Sie [DOMDocument.load()](m-domdocument-load.md). Lädt eine Datei in Form eines XML-Dokumentobjekts

```text
loadXmlFile (filename [, noErr ])
```

## Parameter

**filename** Der vollständige Name der zu ladenden Datei.

**noErr** Wenn „true“, wird kein Fehler ausgegeben, wenn die Datei leer ist (default=false).

## Rückgabewert

Ein XML-Dokument.

## Bemerkungen

Diese Funktion unterstützt die Erkennung der Codepage der Datei dank der Erkennung von BOM und des XML-Prologs.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Versandnachricht
* Typologieregel
* Import
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

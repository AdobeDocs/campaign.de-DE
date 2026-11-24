---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 27%
---
# loadFile

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Gibt den Inhalt einer Textdatei aus

```text
loadFile (filename [, codePage ])
```

## Parameter

**filename** Der vollständige Name der zu ladenden Datei.

**codePage** Mit diesem optionalen Parameter können Sie die Zeichencodierung angeben. Beispiel:

* ISO-8859-1
* UTF-8
* UTF-16
* US-ASCII
* Shift-JIS
* EUC-KR

## Rückgabewert

Ein String, der dem Inhalt der Textdatei entspricht.

## Bemerkungen

Wenn die Zeichenkodierung nicht angegeben ist, wird der Server-Standard verwendet.

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

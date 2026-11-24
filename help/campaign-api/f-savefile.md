---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 26%
---
# saveFile

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Speichert einen String in eine Datei.

```text
saveFile (text, filename [, codePage ])
```

## Parameter

**text** Die zu speichernde Textzeichenfolge.

**filename** Der vollständige Name der zu speichernden Datei.

**codePage** Mit diesem optionalen Parameter können Sie die Zeichencodierung angeben. Beispiel:

* ISO-8859-1
* UTF-8
* UTF-16
* US-ASCII
* Shift-JIS
* EUC-KR

## Rückgabewert

Keine.

## Bemerkungen

Wenn die Zeichenkodierung nicht angegeben ist, wird der Server-Standard verwendet.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

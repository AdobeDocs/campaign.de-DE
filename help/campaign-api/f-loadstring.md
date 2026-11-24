---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 29%
---
# loadString

Dieser Befehl ist veraltet. Verwenden Sie ⌐[loadFile()](f-loadfile.md). Gibt den Inhalt einer Textdatei aus

```text
loadString (filename [, codePage ])
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

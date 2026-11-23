---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 20%
---
# saveXmlFile

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Speichert einen String entsprechend einem XML-Dokument in einer Datei.

```text
saveXmlFile (text, filename [, codePage ])
```

## Parameter

**text** Das XML-Dokument in Form einer Zeichenfolge, die gespeichert werden soll.

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

Diese Funktion fügt bei Bedarf ein XML-Prolog in die Datei ein und gibt die Dokumentcodierung an. Wenn die Zeichenkodierung nicht angegeben ist, wird der Server-Standard verwendet.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 18%
---
# belasten

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Erstellt ein neues Dokument aus einer XML-Datei.

```text
load (filename [, allowEmpty ])
```

## Parameter

**filename** Name der zu ladenden Datei.

**allowEmpty** Wenn „true“, wird keine Ausnahme ausgelöst, wenn die Datei leer ist (default=false).

## Rückgabewert

Keine.

## Bemerkungen

Eine Ausnahme wird ausgelöst, wenn die Datei nicht geladen werden kann oder wenn der Dateiinhalt kein gültiges XML-Dokument ist. Diese Funktion gilt für die DOMDocument-Klasse. Beispiel:

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## Funktionen

**Methode der Klasse:** [DOMDocument](c-domdocument.md)

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

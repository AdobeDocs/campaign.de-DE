---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 28%
---
# fromXMLString

Erstellt ein neues Dokument aus einer XML-Zeichenfolge.

```text
fromXMLString (string)
```

## Parameter

**Zeichenfolge** Zeichenfolge von XML-Zeichen.

## Rückgabewert

Keine.

## Bemerkungen

Es wird eine Ausnahme ausgelöst, wenn das Argument kein gültiges XML-Dokument ist. Diese Funktion gilt für die DOMDocument-Klasse. Beispiel:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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

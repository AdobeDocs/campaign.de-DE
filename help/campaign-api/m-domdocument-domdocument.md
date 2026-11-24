---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 46%
---
# DOMDocument

Erstellt ein neues Dokument.

```text
DOMDocument (name [, namespaceURI ])
```

## Parameter

**name** Dokumentname.

**namespaceURI** Dokument-Namespace-URI.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
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

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 20%
---
# fromJSON

Erstellt ein neues Dokument aus einem JSON-Objekt.

```text
fromJXON (obj)
```

## Parameter

**obj** Ein JXON-Objekt, das das zu erstellende XML-Dokument darstellt.

## Rückgabewert

Keine.

## Bemerkungen

Funktionen, die ein DOMDocument oder ein DOMElement als Parameter übergeben, akzeptieren auch direkt ein JSON-Objekt. Das Erstellen eines Zwischenobjekts mit dieser Funktion ist nicht erforderlich. Es wird eine Ausnahme ausgelöst, wenn das -Objekt kein gültiges JSON-Objekt ist. Diese Funktion gilt für die DOMDocument-Klasse. Beispiel:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
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

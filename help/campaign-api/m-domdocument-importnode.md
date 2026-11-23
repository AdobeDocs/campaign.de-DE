---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 34%
---
# importNode

Erstellt eine Knotenkopie aus einem anderen Dokument.

```text
importNode (importedNode, deep)
```

## Parameter

**importedNode** Source.

**Deep** true, wenn der vollständige Knoten kopiert werden muss, andernfalls false.

## Rückgabewert

Kopie des Knotens.

## Bemerkungen

Beispiel:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
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

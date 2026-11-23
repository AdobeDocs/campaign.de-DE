---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 25%
---
# renameNode

Ändert den Namen eines Elements oder Attributs.

```text
renameNode (node, namespaceURI, qualifiedName)
```

## Parameter

**node** Knoten vom Typ Element/Attribut .

**namespaceURI:** Namespace-URI.

**qualifiedName** Neuer qualifizierter Name.

## Rückgabewert

Umbenannter Knoten. Dies kann der angegebene Knoten sein oder ein Knoten, der den alten ersetzt.

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

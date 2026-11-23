---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 17%
---
# isEqualNode

Vergleicht zwei Knoten.

```text
isEqualNode (arg)
```

## Parameter

**arg** Der zweite Knoten.

## Rückgabewert

true, wenn die beiden Knoten gleich sind, andernfalls false.

## Bemerkungen

Zwei Knoten sind gleich, wenn die folgenden Bedingungen überprüft werden:

* Die beiden Knoten sind vom Typ .
* Die Eigenschaften nodeName, localName, namespaceURI, prefix und nodeValue müssen identisch sein.
* Die beiden Knoten sind vom Typ .
* Attribute müssen gleich sein.
* Knoten müssen gleich sein.

Da die Normalisierung die Gleichheit beeinträchtigen kann, empfehlen wir, sie vor dem Vergleich zu normalisieren.

## Funktionen

**Methode der Klasse:** [DOMNode](c-domnode.md)

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

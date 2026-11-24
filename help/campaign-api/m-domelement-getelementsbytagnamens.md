---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 20%
---
# getElementsByTagNameNS

Gibt die Liste aller untergeordneten Elemente mit dem angegebenen Namen zurück.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parameter

**namespaceURI** Der URI des Namespace der nach Elementen gesuchten Elemente.

**localName** Name der Elemente, nach denen gesucht wird.

## Rückgabewert

Tabelle, die die Liste der Elemente enthält

## Bemerkungen

Diese Methode erstellt für jeden Aufruf eine neue Tabelle. Daher ist es besser, die Tabelle in einer lokalen Variablen zu speichern, anstatt mehrere Aufrufe durchzuführen.

## Funktionen

**Methode der Klasse:** [DOMElement](c-domelement.md)

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

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 20%
---
# getElementsByTagNameNS

Gibt die Liste aller Dokumentelemente mit dem angegebenen Namen und Namespace zurück.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parameter

**namespaceURI** Namespace-URI.

**localName** Name der Elemente, nach denen gesucht wird.

## Rückgabewert

Tabelle, die die Liste der Elemente enthält

## Bemerkungen

Diese Methode erstellt für jeden Aufruf eine neue Tabelle. Daher ist es besser, die Tabelle in einer lokalen Variablen zu speichern, anstatt mehrere Aufrufe durchzuführen.

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

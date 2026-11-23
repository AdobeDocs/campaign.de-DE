---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 19%
---
# getElements

Gibt die Liste der untergeordneten Elemente mit dem angegebenen Namen zurück, die zu diesem Element gehören.

```text
getElements ( [tagName ])
```

## Parameter

**tagName** Name der durchsuchten Elemente. Wenn dieser Parameter übersprungen wird, gibt die Funktion alle untergeordneten Elemente zurück.

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

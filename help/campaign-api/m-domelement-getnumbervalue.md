---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 22%
---
# getNumberValue

Gibt den digitalen Knotenwert zurück, der durch den angegebenen XPath referenziert wird.

```text
getNumberValue (xpath)
```

## Parameter

**xpath** Pfad.

## Rückgabewert

Der digitale Wert entspricht dem referenzierten Knoten.

## Bemerkungen

Die Syntax für den XPath akzeptiert nur eine XPath-Sprachuntergruppe. Eine Ausnahme wird ausgelöst, wenn der Pfad fehlerhaft ist oder wenn der Wert keine gültige Zahl ist.

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

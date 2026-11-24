---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 20%
---
# getDateValue

Gibt den Wert vom Typ Datum+Stunde des Knotenverweises durch den angegebenen XPath zurück.

```text
getDateValue (xpath)
```

## Parameter

**xpath** Pfad.

## Rückgabewert

Ein Objekt vom Typ Datum , das dem Wert des referenzierten Knotens entspricht.

## Bemerkungen

Die Syntax für den XPath akzeptiert nur eine XPath-Sprachuntergruppe. Eine Ausnahme wird ausgelöst, wenn der Pfad fehlerhaft ist oder wenn der Wert kein gültiges Datum ist.

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

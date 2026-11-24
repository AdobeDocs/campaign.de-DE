---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 17%
---
# getBooleanValue

Gibt den booleschen Knotenwert zurück, der durch den angegebenen XPath referenziert wird.

```text
getBooleanValue (xpath)
```

## Parameter

**xpath** Pfad.

## Rückgabewert

true, wenn der Textwert des referenzierten Knotens „true“ oder „1“ ist, false ist der Wert „false“ oder „0“.

## Bemerkungen

Die Syntax für den XPath akzeptiert nur eine XPath-Sprachuntergruppe. Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. Es wird eine Ausnahme ausgelöst, wenn der Pfad fehlerhaft ist oder wenn der Wert kein gültiger boolescher Wert ist.

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

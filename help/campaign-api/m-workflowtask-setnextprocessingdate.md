---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 6%
---
# setNextProcessingDate

Zieht das nächste Verarbeitungsdatum durch die Aufgabe vor.

```text
setNextProcessingDate (timestamp)
```

## Parameter

**Zeitstempel** Nächstes Verarbeitungsdatum. Wenn es leer ist, erfolgt die nächste Verarbeitung sofort.

## Rückgabewert

Keine.

## Bemerkungen

* Mit dieser Methode wird das nächste Verarbeitungsdatum überschrieben, wenn es vom Planer angegeben wird.
* Die nächste Verarbeitung wird immer mit der Funktion \*\_recall() durchgeführt.

## Funktionen

**Methode der Klasse:** [WorkflowTask](c-workflowtask.md)

**Verfügbar in:**

* Workflow

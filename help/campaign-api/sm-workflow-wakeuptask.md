---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%
---
# Aufgabe wecken

Zieht die Ausführung einer ausstehenden oder mehrerer ausstehender Aufgaben vor.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**taskIdentifier** Die Kennung der Aufgabe (@taskIdentifier Feld) oder eine leere Zeichenfolge, um die frühzeitige Verarbeitung aller ausstehenden Aufgaben zu erzwingen, die einer bestimmten Aktivität zugeordnet sind.

**activityName** Der Name der Aktivität, für die die vorzeitige Verarbeitung aller zugehörigen Aufgaben erzwungen werden soll, oder eine leere Zeichenfolge.

## Rückgabewert(e)

Keine.

## Bemerkungen

Wenn weder taskIdentifier noch activityName angegeben sind, werden alle ausstehenden Aufgaben berücksichtigt.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

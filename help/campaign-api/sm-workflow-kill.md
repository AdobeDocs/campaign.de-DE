---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 5%
---
# töten

Stoppt einen Workflow bedingungslos.

```text
Kill ( String workflowId )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

## Rückgabewert(e)

Keine.

## Bemerkungen

Diese Methode ist nützlich, wenn ein Workflow nicht normal angehalten werden kann. Dies kann vorkommen, wenn der Workflow oder eine Aufgabe eine bestimmte Affinität aufweisen und wenn das diese Affinität verwaltende Wfserver-Modul nicht mehr läuft. In diesem Fall bleibt der Workflow mit „Wartet auf Stopp“ gekennzeichnet und kann nur durch den Befehl Kill angehalten werden.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

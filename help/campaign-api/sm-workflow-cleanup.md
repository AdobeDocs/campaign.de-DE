---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 7%
---
# Bereinigung

Löscht den Verlauf eines Workflows.

```text
Cleanup ( String workflowId )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

## Rückgabewert(e)

Keine.

## Bemerkungen

Löscht alle verarbeiteten Ereignisse, abgeschlossene Aufgaben, fehlgeschlagene Aufgaben und Protokollmeldungen. Löscht auch den Fortschritt aus dem Diagramm, wenn der Workflow abgeschlossen ist. Diese Methode löscht nur die Daten, die nicht mehr von der Workflow-Engine verwendet werden, und hat keinen Einfluss auf das Verhalten des Workflows.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# Ausführen

Führt den Workflow sofort aus und wartet auf seinen Abschluss.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**simulationMode** Ausführungssimulation.

**keepResult** Zwischenergebnis festhalten

**logSQL** Ist es notwendig, eine Spur von SQL-Bestellungen zu speichern?

## Rückgabewert(e)

**workflow** Das Ausführungsergebnis.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

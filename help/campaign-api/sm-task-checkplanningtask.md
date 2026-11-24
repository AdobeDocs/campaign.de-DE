---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# Planungsaufgabe prüfen

Interne Funktion zur Überprüfung von Überlastungen innerhalb der Zeitpläne der Aufgabenbenutzer (gibt bei Überlastung „true“ aus). Diese Funktion überprüft auch die Konsistenz der zugehörigen Aufgabenpläne und aktualisiert sie bei Bedarf.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## Parameter

**taskId** Aufgabenkennung.

## Rückgabewert(e)

**workloadAlert** Ressourcenüberlastungswarnung

## Funktionen

**Schema:** [nms:task](s-nms-task.md)

**static:**

Ja

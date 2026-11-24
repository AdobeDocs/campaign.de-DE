---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 6%
---
# Antwort

Antwortet auf eine laufende Aufgabe vom Typ Validierung.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**taskIdentifier** Die Kennung der Aufgabe vom Typ Genehmigung (@taskIdentifier).

**response** Der Kommentar, der mit der Antwort verknüpft ist.

**choice** Die Auswahl der Antwort. Diese Auswahl muss dem Namen der zu aktivierenden Transition entsprechen.

## Rückgabewert(e)

Keine.

## Bemerkungen

Der aktuelle Benutzer muss in der Gruppe sein, der die Aufgabe zugewiesen wurde.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

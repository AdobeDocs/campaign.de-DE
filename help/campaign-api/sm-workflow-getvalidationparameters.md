---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 3%
---
# GetValidationParameters

Gibt die Parameter einer laufenden Workflow-Aufgabe aus

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**taskIdentifier** Die Kennung der Aufgabe vom Typ Genehmigung (@taskIdentifier).

## Rückgabewert(e)

**content** Das die Parameter enthaltende XML-Dokument.

## Bemerkungen

Das zurückgesendete Dokument enthält alle Informationen zur Validierung, wer geantwortet hat und wer noch antworten darf.

* Die Attribute title, creationDate, processingDate, timeout, status, abortReason und completionDate entsprechen den Attributen in der Validierungsaufgabe.
* isAssignee: Der aktuelle Benutzer befindet sich in der Gruppe, die dieser Aufgabe zugewiesen ist.
* hasResponded: Der aktuelle Benutzer hat bereits geantwortet.
* canReply: Der aktuelle Benutzer kann antworten (entweder hat noch niemand geantwortet, oder es sind mehrere Antworten zulässig).

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

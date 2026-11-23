---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 5%
---
# SetLogin

Ändert das Ausführungskonto.

```text
SetLogin ( String workflowId, String login )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**login** Benutzerlogin oder Leer-String, wenn diesem Workflow kein Benutzer zugeordnet ist.

## Rückgabewert(e)

Keine.

## Bemerkungen

Das einem Workflow zugeordnete Ausführungskonto ermöglicht es, anstelle der Ausführungsrechte des Benutzers, der den Workflow gestartet hat, die Ausführungsrechte eines bestimmten Benutzers zu erzwingen. Das Ausführungskonto wird beim Duplizieren eines Workflows nicht weitergegeben.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

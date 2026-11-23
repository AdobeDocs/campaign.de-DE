---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%
---
# GetLogin

Gibt die Informationen des Ausführungskontos aus.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

## Rückgabewert(e)

**id** Kennung des Benutzers oder 0, wenn diesem Workflow kein Benutzer zugeordnet ist.

**login** Benutzerlogin oder Leer-String, wenn diesem Workflow kein Benutzer zugeordnet ist.

**cs** String mit der Beschreibung des Benutzers oder Leerstring, wenn diesem Workflow kein Benutzer zugeordnet ist.

## Bemerkungen

Das einem Workflow zugeordnete Ausführungskonto ermöglicht es, anstelle der Ausführungsrechte des Benutzers, der den Workflow gestartet hat, die Ausführungsrechte eines bestimmten Benutzers zu erzwingen. Das Ausführungskonto wird beim Duplizieren eines Workflows nicht weitergegeben.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

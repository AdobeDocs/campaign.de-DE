---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

Gibt das letzte Ereignis zurück, das einer bestimmten Transition unterzogen werden soll.

```text
getEventFromTransition (transitionName)
```

## Parameter

**transitionName** Der interne Name der Transition.

## Rückgabewert

Das letzte Ereignis, das einer bestimmten Transition oder Null unterzogen wurde. Das Objekt entspricht einer Entität im Schema „xtk:workflowEvent.

## Funktionen

**Verfügbar in:**

* Workflow

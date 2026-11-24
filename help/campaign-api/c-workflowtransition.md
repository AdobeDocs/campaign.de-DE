---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition (Klasse)

Stellt eine Workflow-Transition dar.

Eine Transition ist ein opakes Objekt, das mithilfe von Methoden wie oder wiederhergestellt wird und zum Aktivieren der Aufgabenübergabe verwendet wird.

Beispiel:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## Funktionen

**Verfügbar in:**

* Workflow

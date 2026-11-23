---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 2%
---
# PostEvent

Erzeugt ein Ereignis basierend auf einer beliebigen Aktivität.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**activity** Der Name der Aktivität, von der das Ereignis ausgeht

**transition** Der Name der zu aktivierenden Transition. Wenn dieser Name leer ist, wird das Ereignis bei der ersten gültigen Transition ausgegeben (Ablauf-Ereignisse werden ignoriert).

**parameters** Die Parameter des Ereignisses in Form eines XML-Elements Der Name des Elements muss Variablen sein. Wenn Sie keine Variable übergeben möchten, können Sie ein leeres Element &lt;variables/> oder eine leere Zeichenfolge &quot;&quot; verwenden.

**abgeschlossen** Alle ausstehenden Aufgaben der angegebenen Aktivität sind abgeschlossen.

## Rückgabewert(e)

Keine.

## Bemerkungen

* Der Befehl wird asynchron ausgeführt und hat keine sofortige Auswirkung nach der Rückgabe der Methode.
* Der Ziel-Workflow muss gestartet werden, wenn diese Methode aufgerufen wird. Wenn er nicht gestartet wird, wird ein Fehler in die entsprechende Protokolldatei geschrieben.
* Wenn der Ziel-Workflow beim Aufruf der Methode ausgesetzt wird, bleibt der Befehl in der Warteschlange, bis der Workflow fortgesetzt wird.
* Die Aktivität unterliegt keinen Einschränkungen. Es ist nicht erforderlich, dass für sie eine Aufgabe in Bearbeitung oder sogar abgeschlossen ist.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

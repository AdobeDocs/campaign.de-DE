---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%
---
# Warten

Wartet auf ein Signal.

```text
wait (timeout)
```

## Parameter

**timeout** Wartezeit in Millisekunden.

## Rückgabewert

Ein boolescher Wert auf „true“, wenn ein Signal vor Ablauf der Wartezeit empfangen wird.

## Bemerkungen

Das Signal wird von den SOAP-Methoden [Wakeup](sm-workflow-wakeup.md) und [WakeupTask](sm-workflow-wakeuptask.md) ausgegeben. Das verwendete Protokoll (UDP) garantiert keinen Nachrichtenempfang. Dieses Signal ist nur für die schnellere Ausführung eines Vorgangs nützlich. Warnung: Dieses Signal wird in einem Unter-Workflow niemals empfangen. Beispiel: Hier ist ein typisches Anwendungsbeispiel: Eine Schleife verarbeitet Vorgänge aus einer Warteschlange (poll()) und wartet dann zwischen den einzelnen Vorgängen eine bestimmte Zeit. Eine zusätzliche Verzögerung wird hinzugefügt, um die Workflow-Passivierung zu erzwingen.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## Funktionen

**Methode der Klasse:** [WorkflowTask](c-workflowtask.md)

**Verfügbar in:**

* Workflow

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 26%
---
# ExecCommand

Führt einen Befehl in Bezug auf den Versand aus

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## Parameter

**deliveryId** Versandkennung

**Befehl** Befehlsname (&#39;play&#39;, &#39;pause&#39; oder &#39;stop&#39;)

## Rückgabewert(e)

**newState** Versandstatus nach Ausführung des Befehls

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

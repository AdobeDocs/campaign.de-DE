---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

Transaktionsnachricht auf Ausführungsinstanzen veröffentlichen. Gibt bei erfolgreicher Veröffentlichung „true“ und andernfalls „false“ zurück.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## Parameter

**deliveryId** ID des bereitzustellenden Versands

**localPublish** Nur auf der Kontrollinstanz veröffentlichen?

## Rückgabewert(e)

**isSuccess** Veröffentlichung abgeschlossen

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

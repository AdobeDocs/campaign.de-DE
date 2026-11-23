---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# Versand übermitteln

Erstellung und Unterbreitung eines Versands von einer Vorlage ausgehend (durch den internen Namen bezeichnet)

```text
Number deliveryId = SubmitDelivery ( String scenarioName, XML content )
```

## Parameter

**scenarioName** Interner Name der Versandvorlage

**content** XML-Inhalt, der der Vorlage hinzugefügt werden soll

## Rückgabewert(e)

**deliveryId** Kennung des neuen Versands (wird auch dann zurückgegeben, wenn die Analyse fehlschlägt)

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

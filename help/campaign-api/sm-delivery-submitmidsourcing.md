---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

Unterbreitet einen Versand im Mid-Sourcing-Modus

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## Parameter

**delivery** Dokument, das den Versand darstellt.

**routingMatch** Wird nicht mehr verwendet

**folderName** Vollständiger Ordnername (in der Absenderdatenbank).

## Rückgabewert(e)

**remoteId** Kennung des Versands in der Empfängerdatenbank.

**remoteMatchId** wird nicht mehr verwendet

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

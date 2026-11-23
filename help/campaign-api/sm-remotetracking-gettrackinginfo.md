---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

Ermöglicht einem Remote-Trackingserver Versandinformationen herunterzuladen

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## Parameter

**instance** Instanzname

**dbId** Datenbankkennung des Kunden, der einen Versand durchführt

**deliveryId** Versand-ID

## Rückgabewert(e)

**Dokument** Dokument, das die Tracking-Informationen für diesen Versand enthält

## Funktionen

**Schema:** [nms:remoteTracking](s-nms-remotetracking.md)

**static:**

Ja

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 28%
---
# RegisterTrackingInstance

Validiert eine Trackinginstanz auf einem  Weiterleitungsserver (durch Festlegung der Datenbankkennung)

```text
RegisterTrackingInstance ( String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword )
```

## Parameter

**serverUrl** Externe URL des Trackingservers

**secureServerUrl** Externe sichere URL des Trackingservers

**serverUrlList** Interne URLs der Tracking-Server

**instanceName** Name der zu validierenden Instanz

**cryptedPassword** Verschlüsseltes Kennwort

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:trackingUrl](s-nms-trackingurl.md)

**static:**

Ja

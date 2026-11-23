---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

Ruft die letzten Protokolllogs und den Versandstatus ab.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## Parameter

**deliveryId** Versandkennung

**lastLogId** Kennung des letzten Journaleintrags, der im vorherigen Aufruf zurückgegeben wurde

## Rückgabewert(e)

**deliveryState** Versandstatus

**returnLogs** Protokollmeldungen

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

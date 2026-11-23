---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadlogs

Ruft die zuletzt aktualisierten Versandlogs in Bezug auf Mid-Sourcing-Sendungen ab.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## Parameter

**startDate** Ruft die seit diesem Datum geänderten Protokolle ab (auf dem Mid-Sourcing-Server).

**logCount** Maximale Anzahl an abzurufenden Protokollen, sofern diese nicht innerhalb derselben Sekunde aktualisiert wurden.

**emitterDate** Referenzdatum des sendenden Servers Dient zur Anpassung der Versandlog-Daten.

## Rückgabewert(e)

**Ergebnis** Ausgabedokument, Liste der Versandlogs.

**nextDate** Datum des ersten abgerufenen Logs (größer als startDate).

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliverys

Ruft den Status der zuletzt im Mid-Sourcing-Modus aktualisierten Sendungen ab.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## Parameter

**startDate** Ruft die Änderungen seit diesem Datum ab (auf dem Mid-Sourcing-Server).

**maxCount** Maximale Anzahl an abzurufenden Sendungen, sofern diese nicht in derselben Sekunde aktualisiert wurden.

**emitterDate** Referenzdatum des sendenden Servers Wird zum Anpassen der Versanddaten verwendet.

## Rückgabewert(e)

**Ergebnis** Ausgabedokument, Liste der aktualisierten Sendungen

**nextDate** Startdatum für den nächsten Aufruf.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

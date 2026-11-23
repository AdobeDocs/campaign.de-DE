---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 27%
---
# Versandvalidierung

Validiert einen Versand innerhalb einer Kampagne.

```text
DeliveryValidation ( Number deliveryId, Number type, Boolean refused, String comment )
```

## Parameter

**deliveryId** Versandkennung

**Typ** Validierungstyp (Zielgruppenbestimmung=0, Inhalt=1, Budget=2, Extraktion=3)

**abgelehnt** Ablehnen

**Kommentar** Kommentar

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:operation](s-nms-operation.md)

**static:**

Ja

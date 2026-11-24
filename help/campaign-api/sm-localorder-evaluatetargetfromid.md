---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%
---
# EvaluateTargetFromId

Wertet die Zielgruppe für jeden Versand im Rahmen einer Kampagnenbestellung aus. Diese Auswertung wird bei der Bestellung unter Verwendung der Benutzerrechte durchgeführt, bevor die lokale Kampagne erstellt wird.

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## Parameter

**orderId** Auftrags-ID.

## Rückgabewert(e)

**result** Ergebnis der Zählungen für jeden Kampagnenversand.

## Funktionen

**Schema:** [nms:localOrder](s-nms-localorder.md)

**static:**

Ja

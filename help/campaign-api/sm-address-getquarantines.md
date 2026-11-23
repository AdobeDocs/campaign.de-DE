---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# Quarantänen abrufen

Ruft die letzten Quarantäne-Neuzugänge und -Abgänge ab.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## Parameter

**startDate** Ruft die seit diesem Datum geänderten Quarantänen ab. Wenn es leer ist, wird der Zeigerwert verwendet.

**pointerName** Ruft die seit diesem Zeiger geänderten Quarantänen ab (optional).

**quarantineCount** Maximale Anzahl von abzurufenden Quarantänen, sofern diese nicht in derselben Sekunde aktualisiert wurden.

**callerDate** Referenzdatum des Aufrufers. Ermöglicht die Änderung des Referenzdatums für die Quarantäne (optional).

## Rückgabewert(e)

**Ergebnis** Ausgabedokument, Quarantäneliste.

**nextDate** Datum der ersten nicht abgerufenen Quarantäne (streng größer als startDate).

**hasMore** Wenn ja, gibt es immer noch abzurufende Quarantänen.

## Funktionen

**Schema:** [nms:address](s-nms-address.md)

**static:**

Ja

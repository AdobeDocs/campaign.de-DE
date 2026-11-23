---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# buildUpdateSchemaDiff

Erzeugt ein Dokument, das die Unterschiede zwischen der physischen Datenbank und ihrer logischen Beschreibung aufzeigt.

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## Parameter

**parameter** Aktualisierungsparameter

**useNamingConventions** Verwenden Sie SQL-Benennungskonventionen zur Berechnung der Pfade neuer Felder.

## Rückgabewert(e)

**sqlSchemaDiff** generiertes Schema

## Funktionen

**Schema:** [xtk:builder](s-xtk-builder.md)

**static:**

Ja

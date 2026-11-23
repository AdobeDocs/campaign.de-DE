---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# buildUpdateOneSchemaDiff

Erzeugt ein Dokument, das die Unterschiede zwischen einer Tabelle der physischen Datenbank und der logischen Beschreibung dieser Tabelle aufzeigt.

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## Parameter

**schemaId** Schemakennung

**useNamingConventions** Verwenden Sie SQL-Benennungskonventionen zur Berechnung der Pfade neuer Felder.

## Rückgabewert(e)

**sqlSchemaDiff** generiertes Schema

## Funktionen

**Schema:** [xtk:builder](s-xtk-builder.md)

**static:**

Ja

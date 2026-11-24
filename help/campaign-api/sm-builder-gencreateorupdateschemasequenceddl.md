---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

Erzeugt das SQL-Script, mit dem die autopk-Schemasequenz erstellt oder aktualisiert wird

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## Parameter

**schemaId** Schemakennung

**newSequence** Neue Sequenz

**oldSequence** Alte Sequenz

## Rückgabewert(e)

**sqlDDL** SQL-Script

## Funktionen

**Schema:** [xtk:builder](s-xtk-builder.md)

**static:**

Ja

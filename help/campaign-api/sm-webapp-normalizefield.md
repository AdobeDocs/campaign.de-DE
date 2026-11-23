---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 4%
---
# Feld normalisieren

```text
NormalizeField ( XML selectedWebApp, XML archivedField, String newSQLName, String tableName, String schemaId, Boolean rename )
```

## Parameter

**selectedWebApp** Liste der Umfragen, die das zu normalisierende Feld enthalten können.

**archivedField** Informationen zum Feld, das normalisiert werden soll.

**newSQLName** Neuer SQL-Name dieses Felds.

**tableName** Name der Tabelle, die das neue SQL-Feld enthalten wird.

**schemaId** Schemakennung (Ansicht), unter der ein Verweis zum neuen Feld hinzugefügt werden soll (optional).

**umbenennen** Auch zuvor standardisierte Felder umbenennen.

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:webApp](s-nms-webapp.md)

**static:**

Ja

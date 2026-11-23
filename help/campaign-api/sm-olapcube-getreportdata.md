---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## Parameter

**cubeId** Cube-Kennung. Kann auf 0 gesetzt werden, wenn der Cube als Parameter übergeben wird.

**queryDef** Im Bericht definierte QueryDef

**selectAll** Alle auswählen

**useAggregates** Aktivieren der Verwendung von Aggregaten

**cube** XML, die den Cube beschreibt.

## Rückgabewert(e)

**result** Result

## Funktionen

**Schema:** [xtk:olapCube](s-xtk-olapcube.md)

**static:**

Ja

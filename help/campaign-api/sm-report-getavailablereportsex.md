---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

Ausgabe der Berichtsliste ohne Verlaufsdaten unter Berücksichtigung der Sortierbedingungen und des Seitenlayouts

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## Parameter

**activeContext** Aktiver Kontext (Auswahl, global)

**schema** beteiligtes Schema

**selection** IDs der ausgewählten Entitäten, getrennt durch &quot;,“

**where** „where“-Knoten filtern

**orderBy** Sortierung des Knotens „orderBy“

**editionMode** Während der Bearbeitung sind auch nicht veröffentlichte Berichte sichtbar

**lineCount** Anzahl an zu erfassenden Berichten

**startLine** Versatz zur Anwendung auf die Seitennummerierung

**locationName**

## Rückgabewert(e)

**Berichte** Liste der infrage kommenden Berichte

## Funktionen

**Schema:** [xtk:report](s-xtk-report.md)

**static:**

Ja

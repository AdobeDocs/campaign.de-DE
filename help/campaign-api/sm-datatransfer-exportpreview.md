---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# Vorschau exportieren

Erstellt eine Vorschau der Spalten der Ausgabedatei für die ersten Zeilen der Abfrage

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## Parameter

**dataTransferStep** Übertragungsschritt, bei dem das berechnete Feld definiert wird.

**lineCount** Anzahl an zurückzugebenden Zeilen

**countMode** Zeilenzählungsmodus

**calcFieldName** Name des beobachteten berechneten Feldes. Wenn leer, handelt es sich um eine globale Vorschau der Ausgabedatei.

## Rückgabewert(e)

**resultColumns** Gibt die Werte der Exportdateispalten zurück (line/col/val, line/col/errors).

**resultXML** Gibt das XML-Ausgabedokument der Abfrage zurück.

**resultSQLRequest** Gibt die ausgeführte SQL-Abfrage zurück.

## Funktionen

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**static:**

Ja

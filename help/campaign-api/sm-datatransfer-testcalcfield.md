---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# testCalcField

Testet das berechnete Feld für Beispielzeilen

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## Parameter

**dataTransferStep** Datenübertragungsschritt, bei dem das berechnete Feld definiert wird

**calcFieldName** Berechnetes Feld zum Testen

## Rückgabewert(e)

**calcFieldValues** Gibt die Liste der Werte für jede Beispielzeile (calcFieldValues/line) und den Feldnamen (calcFieldValues/@name) zurück.

## Funktionen

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**static:**

Ja

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# Exportieren

Erzeugung und Export eines Berichts

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## Parameter

**reportName** Interner Berichtsname

**context** Ausführungskontext.

**exportFormat** Mögliche Werte sind: XLS, OOXML\_SS, ODF\_SS, PDF

XLS generiert ein Excel 94-2003-Dokument\
 OOXML\_SS generiert ein Excel 2007-Dokument\
 ODF\_SS generiert ein Open-Dokument

**fileName** Name der Ausgabedatei

**isAdHoc** Gibt an, ob der Export einen Ad-hoc-Bericht betrifft

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [xtk:report](s-xtk-report.md)

**static:**

Ja

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

Unterbreitet einen Auftrag von einer Vorlage ausgehend

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## Parameter

**schema** Schema der Bearbeitungsvorlage

**where** Ausdruck für die Vorlagenauswahl

**methodName** Name der aufzurufenden Methode

**diff** XML-Inhalt, der der Vorlage hinzugefügt werden soll

**asynchron** Asynchrone Auftragsübermittlung durchführen

## Rückgabewert(e)

**jobId** Kennung des gerade erstellten Vorgangs

## Funktionen

**Schema:** [xtk:job](s-xtk-job.md)

**static:**

Ja

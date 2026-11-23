---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# Ausführen

Führt einen Auftrag synchron aus (in diesem Modus sind keine Informationen über den Fortschritt verfügbar und der Abbruch ist nicht möglich).

```text
String id = job.Execute ( String methodName ) const
```

## Parameter

**methodName** Name der Methode, die für die Entität aufgerufen wird

## Rückgabewert(e)

**id** Kennung des erstellten Vorgangs (wird auch dann zurückgegeben, wenn der Vorgang fehlgeschlagen ist, wenn er in der Datenbank erstellt wurde)

## Funktionen

**Schema:** [xtk:job](s-xtk-job.md)

**static:**

Nein

**const:**

Ja

**Nur Schlüssel:**

Nein

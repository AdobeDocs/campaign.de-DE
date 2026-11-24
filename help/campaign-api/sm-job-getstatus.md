---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

Abrufen von Informationen zum Verarbeitungsfortschritt. Warnung: Diese API garantiert nicht, dass eine Liste eindeutiger Protokolleinträge zurückgegeben wird (der Aufrufer muss sie mithilfe seiner ID deduplizieren).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## Parameter

**id** Auftragskennung

**lastLogId** Kennung des letzten Protokolleintrags, der im vorherigen Aufruf zurückgegeben wurde

**maxLogCount** Maximale Anzahl an zu sendenden Protokolleinträgen

## Rückgabewert(e)

**status** Auftragsstatus

**returnLogs** Protokollmeldungen

**Eigenschaften** Eigenschaften (Fortschritt usw.)

## Funktionen

**Schema:** [xtk:job](s-xtk-job.md)

**static:**

Ja

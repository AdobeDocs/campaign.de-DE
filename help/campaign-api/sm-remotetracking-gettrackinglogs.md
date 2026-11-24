---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# GetTrackingLogs

Emöglicht den Abruf der vom Weiterleitungs- und Webtrackingdienst erzeugten Trackinglogs.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs ( String instance, String dbId, Number version, String pointer, Number logCount )
```

## Parameter

**instance** Short Identifier

**dbId** Datenbankkennung des Kunden, der einen Versand durchführt

**version** Trackinglog-Version

**pointer** Kennung (serialisiert int64) des Logs, aus dem die Logs abgerufen werden sollen.

**logCount** Anzahl der Protokolle, die für die Anfrage abgerufen werden sollen (0 bedeutet Standardwert), Anzahl der von der Antwort zurückgegebenen Protokolle.

## Rückgabewert(e)

**pointer** Kennung (serialisiert int64) des Logs, aus dem die Logs abgerufen werden sollen.

**logCount** Anzahl der Protokolle, die für die Anfrage abgerufen werden sollen (0 bedeutet Standardwert), Anzahl der von der Antwort zurückgegebenen Protokolle.

**logs** Protokolle abgerufen

**srvDate** GMT-Zeit des Servers zum Zeitpunkt des Log-Abrufs

## Funktionen

**Schema:** [nms:remoteTracking](s-nms-remotetracking.md)

**static:**

Ja

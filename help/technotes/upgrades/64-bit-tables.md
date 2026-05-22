---
title: 64-Bit-Schemata
description: Erfahren Sie mehr über 64-Bit-Schemata in Adobe Campaign v8 für migrierte Campaign Standard-Kunden
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
source-git-commit: 25ce962e7c8b6a62fc2c1edb08a78afa839d264e
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 18%

---

# 64-Bit-Schemata {#sixty-four-bit-tables}

Um den Übergang von Campaign Standard zu Campaign v8 zu erleichtern, wurden mehrere Tabellen von 32 auf 64 Bit geändert. Campaign Standard unterstützt 64-Bit-PK in mehreren vordefinierten Schemata, während Campaign v8 in den meisten Schemata 32-Bit-PK unterstützt.

## Einschränkungen

* Diese technische Änderung gilt nur für Kunden, die von Campaign Standard migrieren.
* Schema- und Broadlog-Erweiterung werden in 64 Bit nicht unterstützt. Es bleibt in 32 Bit.
* Protokolle zu Sendungen an technische Benutzende sind in Campaign v8 nicht verfügbar.
* Es wird nur PostgreSQL unterstützt.

## Geänderte Schemata

Im Folgenden finden Sie die Liste der Schemata, die auf 64 Bit geändert wurden, und ihrer geänderten Attribute.

| Schemaname | Name des Attributs |
|--- |--- |
| nms:broadLogRcp | ID |
| nms:trackingLogRcp | ID |
| nms:excludeLogRcp | ID |
| nms:broadLogVisitor | ID |
| nms:trackingLogVisitor | ID |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | ID |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | ID |
| nms:trackingLogAppSubRcp | ID |
| nms:excludeLogAppSubRcp | ID |
| nms:webEvent | broadLogSrc-id, broadLogRemote-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |

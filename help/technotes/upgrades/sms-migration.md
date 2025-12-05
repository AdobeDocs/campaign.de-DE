---
title: Wechsel zum neuen SMS-Connector v2
description: Erfahren Sie, wie Sie zum neuen SMS-Connector v2 wechseln.
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Wechsel zum neuen SMS-Connector v2

Adobe Campaign v8 führt einen neuen **dedizierten SMS-Prozess-Connector** (v2) ein, der im Vergleich zum alten MTA-basierten SMS-Connector eine verbesserte Leistung und Zuverlässigkeit bietet.

## Warum zum V2-Connector wechseln?

Der dedizierte SMS-Prozess führt die Unterstützung für den SMPP-Transceiver-Modus ein, reduziert die Verbindungsanzahl und verbessert die Ressourceneffizienz, unterstützt jedoch bei Bedarf weiterhin Sender-/Empfängereinstellungen. Sie bietet deutlich mehr Stabilität, schnellere Wiederherstellung nach Fehlern, persistenten Verbindungen und keine Abhängigkeit von lokalen Dateien oder prozessübergreifender Kommunikation. Die Leistung wird ebenfalls verbessert, mit geringerer Latenz, höherem Durchsatz und intelligentem Microbatching, um Geschwindigkeit und Zuverlässigkeit auszugleichen. Darüber hinaus vereinfacht die Isolierung des SMS-Prozesses die Fehlerbehebung und minimiert Cross-Channel-Auswirkungen. Diese Verbesserungen machen den dedizierten Connector zu einer robusteren und skalierbareren Lösung für den SMS-Versand.

## Konfiguration

Bei Adobe Campaign Managed Cloud Services werden die Serverkonfiguration und die SMS-Connector-Migration von Adobe verwaltet. Dieses technische Verfahren erfordert direkten Zugriff auf die Konfigurationsdateien des Servers und Datenbankvorgänge.

Wenn Sie zum neuen SMS-Connector v2 migrieren müssen, wenden Sie sich an Ihren Adobe-Support-Mitarbeiter oder die Adobe-Kundenunterstützung. Sie planen und führen die erforderlichen Aktualisierungen für Ihre Instanz durch.

Weitere Informationen zum SMS-Kanal in Campaign v8 finden Sie in der [SMS-](../../v8/send/sms/sms.md).

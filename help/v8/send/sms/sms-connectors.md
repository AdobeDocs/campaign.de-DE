---
title: SMS-Connectoren
description: Erfahren Sie mehr über SMS-Connectoren in Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# Über SMS-Connector-Typen {#sms-connectors}

Adobe Campaign unterstützt zwei SMS-Connectoren für den Versand von SMS-Nachrichten an Ihre Kunden:

* **Legacy SMS-Connector**: Erste Version des in Campaign v7 verwendeten Connectors und frühere Versionen von Campaign v8. [Weitere Informationen](#legacy-sms-connector)
* **SMS-Connector v2**: Dieser dedizierte SMS-Connector von v2 wurde ab Campaign v8.9.1 allgemein verfügbar und wurde modernisiert, um eine verbesserte Leistung und Zuverlässigkeit zu bieten. [Weitere Informationen](#sms-connector-v2)

## Legacy SMS-Connector {#legacy-sms-connector}

Der alte SMS-Connector ist der MTA-basierte SMS-Connector, der in früheren Versionen von Adobe Campaign verwendet wurde. Dieser Connector wird weiterhin für bestehende Implementierungen unterstützt, aber Adobe empfiehlt dringend, auf Version 8.9.1 oder höher zu aktualisieren, um von der verbesserten Leistung und Zuverlässigkeit des v2-Connectors zu profitieren.

Informationen zu den Vorteilen des v2-Connectors finden Sie im Abschnitt [Aktivierung](#activation).

Detaillierte Informationen zur Konfiguration und Verwendung des alten SMS-Connectors finden Sie in der [Dokumentation zu Campaign Classic](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## SMS-Connector v2 {#sms-connector-v2}

Der v2-Connector ist in GA ab Version 8.9.1 verfügbar und ermöglicht SMPP-Verbindungen im Transceiver-Modus sowie persistente SMPP-Verbindungen und sorgt für eine bessere Kompatibilität. Ein dediziertes externes SMS-Konto ist für alle SMS-Implementierungen mit dem v2-Connector verfügbar.

Der v2-Connector ist bei Neuinstallationen standardmäßig aktiviert. Wenn Sie von einer früheren Version mit dem alten Connector ein Upgrade durchgeführt haben, müssen Sie sich an den Adobe-Support wenden, um zum V2-Connector zu wechseln. Siehe Abschnitt [Aktivierung](#activation).

Informationen zur Verwendung des SMS-Connectors v2 in Campaign v8 finden Sie in der [SMS-](sms.md).

>[!NOTE]
>
>Der v2-Connector ist mit einigen Einschränkungen auch in den folgenden Builds verfügbar:
>* 8.8.1: Version für alle Campaign FDA-Umgebungen. Nicht verfügbar für Campaign FFDA-Bereitstellungen.
>* 8.8.2: Version für alle Bereitstellungstypen, einschließlich FFDA. In begrenzter Verfügbarkeit (LA) veröffentlicht.

## Aktivierung {#activation}

### Warum zum V2-Connector wechseln? {#why-switch-v2}

Der dedizierte SMS-Prozess führt die Unterstützung für den SMPP-Transceiver-Modus ein, reduziert die Verbindungsanzahl und verbessert die Ressourceneffizienz, unterstützt jedoch bei Bedarf weiterhin Sender-/Empfängereinstellungen. Sie bietet deutlich mehr Stabilität, schnellere Wiederherstellung nach Fehlern, persistenten Verbindungen und keine Abhängigkeit von lokalen Dateien oder prozessübergreifender Kommunikation. Die Leistung wird ebenfalls verbessert, mit geringerer Latenz, höherem Durchsatz und intelligentem Microbatching, um Geschwindigkeit und Zuverlässigkeit auszugleichen. Darüber hinaus vereinfacht die Isolierung des SMS-Prozesses die Fehlerbehebung und minimiert Cross-Channel-Auswirkungen. Diese Verbesserungen machen den dedizierten Connector zu einer robusteren und skalierbareren Lösung für den SMS-Versand.

### Konfiguration {#configuration}

Bei Adobe Campaign Managed Cloud Services werden die Serverkonfiguration und die SMS-Connector-Migration von Adobe verwaltet. Dieses technische Verfahren erfordert direkten Zugriff auf die Konfigurationsdateien des Servers und Datenbankvorgänge.

Um den SMS-Connector v2 zu aktivieren und zu verwenden, müssen Sie zunächst ein Upgrade auf v8.9.1 oder höher durchführen. Wenden Sie sich an den Adobe-Support oder die Adobe-Kundenunterstützung. Sie planen und führen die erforderlichen Aktualisierungen für Ihre Instanz durch.
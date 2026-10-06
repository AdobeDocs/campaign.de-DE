---
title: SMS-Connectoren
description: Erfahren Sie mehr über SMS-Connectoren in Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
exl-id: 5ec3f172-22dc-458b-8688-9974009c985e
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%
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

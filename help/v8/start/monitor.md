---
title: Übersicht über die Überwachung von Kampagnen
description: Informationen zum Überwachen von Sendungen, Workflows und Ihrer Campaign-Instanz
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 4%

---

# Übersicht über die Überwachung von Kampagnen {#monitor-campaign}

Adobe Campaign bietet umfassende Funktionen zur Überwachung Ihrer Prozesse, Sendungen und Umgebungen, um eine optimale Leistung sicherzustellen und Probleme proaktiv zu beheben.

>[!NOTE]
>
>Als Campaign-Admin können Sie auch das [Campaign Control Panel](#control-panel) verwenden, um Ihre Instanzen zu überwachen, die Leistung zu verwalten und Einstellungen mit Self-Service-Funktionen zu konfigurieren.

## Sendungen überwachen {#monitor-deliveries}

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Nach dem Versand eines Versands können Sie dessen Status überwachen und Schlüsselmetriken im Versand-Dashboard verfolgen. Das Dashboard bietet Zugriff auf Versandlogs, Ausschlusslogs, Trackinglogs und andere Überwachungsfunktionen, mit denen Sie die Versandleistung kanalübergreifend analysieren können.

**E-Mail-**: Überwachen Sie den Status des E-Mail-Versands, verfolgen Sie Schlüsselmetriken und greifen Sie auf detaillierte Protokolle zu. Erfahren Sie mehr über [Überwachen von Sendungen in der Campaign](../send/delivery-dashboard.md)-Benutzeroberfläche, [Versandstatus](../send/delivery-statuses.md) und [Überwachen von E-Mail-Sendungen](../send/send.md#email-monitoring).

**SMS-Sendungen** - Verfolgen Sie den Status des SMS-Versands und überwachen Sie Schlüsselmetriken im Dashboard des SMS-Versands. Weitere Informationen zu [SMS-Überwachung](../send/sms/sms-monitor.md).

**Push-Benachrichtigungen** - Überwachen Sie den Versand von Push-Benachrichtigungen, um sicherzustellen, dass sie die Benutzer Ihrer Mobile App effektiv erreichen. Weitere Informationen zur [Überwachung von Push-](../send/push.md#push-test)&quot;

**Transaktionsnachrichten** - Überwachen Sie für Nachrichten, die durch Ereignisse ausgelöst werden, den Status der Ereignisverarbeitung, die Ausführung von Nachrichten und den Versandstatus. Weitere Informationen über [Überwachung von Transaktionsnachrichten](../send/delivery-execution.md#monitor-messages).

**Versandfehler** - Um eine saubere Datenbank zu verwalten und gute Zustellbarkeitsraten zu gewährleisten, ist es von entscheidender Bedeutung, die Gründe für fehlgeschlagene Sendungen zu verstehen. Versandfehler werden in Hardbounces, Softbounces und ignorierte Nachrichten klassifiziert. Weitere Informationen zu [fehlgeschlagenen Sendungen und Quarantänen](../send/delivery-failures.md).

## Überwachen der Zustellbarkeit {#monitor-deliverability}

Die Zustellbarkeits-Überwachung hilft Ihnen sicherzustellen, dass Ihre Nachrichten die Posteingänge Ihrer Empfänger erreichen und Spam-Filter vermeiden. Adobe Campaign bietet mehrere integrierte Tools zur Überwachung und Verbesserung der Zustellbarkeit, einschließlich Versandberichte, Inbox Rendering, SpamAssassin-Tests und Broadcast-Statistiken. Die Befolgung von Best Practices für die Zustellbarkeit, wie die Pflege einer sauberen E-Mail-Liste, die Überwachung der Reputation des Absenders und die Authentifizierung von Versand-Domains, ist wichtig, um gute Zustellbarkeitsraten aufrechtzuerhalten.

Erfahren Sie mehr über [Tools zur Zustellbarkeitsüberwachung](../send/monitoring-deliverability.md) und [Best Practices zur Zustellbarkeit](../send/about-deliverability.md).

## Überwachen von Workflows {#monitor-workflows}

Workflows sind zur Automatisierung Ihrer Marketing-Kampagnen und Datenverarbeitung unerlässlich. Die Überwachung der Workflow-Ausführung hilft Ihnen bei Folgendem:

* Sicherstellen, dass Workflows erfolgreich abgeschlossen werden
* Fehler identifizieren und beheben
* Optimieren der Workflow-Leistung

### Workflow-Überwachungsfunktionen {#workflow-monitoring}

**Überwachen Sie die folgenden Workflow-Elemente:**

**Workflow-Ausführungsstatus** - Verfolgen Sie, ob Workflows ausgeführt werden, angehalten, fehlgeschlagen oder abgeschlossen sind. [Erfahren Sie mehr über die Ausführung von Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

**Protokolle zur Aktivitätsausführung** - Greifen Sie auf detaillierte Protokolle für jede Workflow-Aktivität zu, um Probleme zu beheben und die Leistung zu optimieren.

**Workflow-Heatmap** - Visualisieren Sie Ausführungsmuster von Workflows, identifizieren Sie Engpässe und überwachen Sie gleichzeitige Workflows. Die Workflow-Heatmap steht Campaign-Administratoren zur Verfügung. [Erfahren Sie mehr über Workflow-Heatmap](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=de){target="_blank"}

**Workflow-Verlauf** - Verfolgen Sie alle Workflow-Ausführungen und -Änderungen im Laufe der Zeit, um das Verhalten und die Leistung von Workflows zu verstehen.

## Überwachen einer Instanz {#monitor-instance}

Mit der Instanzüberwachung können Sie den Zustand und die Leistung Ihrer Adobe Campaign-Umgebung sicherstellen.

### Audit-Protokoll {#audit-trail}

Über die Self-Service-Benutzeroberfläche des Audit-Protokolls können Sie Änderungen überwachen, die in Ihrer Adobe Campaign-Instanz vorgenommen wurden. Das Audit-Protokoll erfasst in Echtzeit eine umfassende Liste von Aktionen und Ereignissen, die in Ihrer Instanz auftreten.

**Audit-Protokoll verwenden für:**

* **Komponentenänderungen verfolgen** Überwachen Sie, was mit Ihren Workflows, Schemata, Optionen und anderen Komponenten passiert ist
* **Ermitteln, wer Änderungen vorgenommen hat**: Ermitteln Sie, wer ein bestimmtes Element zuletzt aktualisiert hat und wann
* **Benutzeraktionen verstehen**: Überprüfen Sie, was Benutzer in der Instanz getan haben, um Fehler zu beheben oder Prüfungen durchzuführen
* **Einhaltung gewährleisten**: Verfolgen Sie alle Konfigurationsänderungen zu Compliance- und Sicherheitszwecken

Das Audit-Protokoll ist über die Campaign-Client-Konsole aufrufbar und enthält detaillierte Informationen zu den von den Benutzern durchgeführten Aktionen.

Weitere Informationen zu [Audit-Protokoll](../reporting/audit-trail.md)

### Überwachen der Performance {#performance-monitoring}

Campaign v8 bietet verschiedene Überwachungsfunktionen, um die Leistung Ihrer Instanz zu verfolgen und einen optimalen Betrieb sicherzustellen:

**Datenbanküberwachung** - Überwachen Sie die Datenbanknutzung und -kapazität über das Control Panel, um eine optimale Leistung und Speicherverwaltung sicherzustellen. [Erfahren Sie mehr über die Datenbanküberwachung](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html?lang=de){target="_blank"}

**Überwachen aktiver Profile** - Verfolgen Sie die aktive Profilnutzung anhand Ihrer vertraglichen Beschränkungen, um die Compliance aufrechtzuerhalten und die Ressourcenzuweisung zu optimieren. [Erfahren Sie mehr über aktive Profile](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=de){target="_blank"}

**Workflow-Überwachung** - Überwachen Sie den Ausführungsstatus des Workflows, um langwierige Workflows zu identifizieren und sicherzustellen, dass alle technischen Workflows ordnungsgemäß ausgeführt werden. [Erfahren Sie mehr über technische Workflows](#technical-workflows)

**Versanddurchsatz und Latenz** - Verfolgen Sie den Versanddurchsatz (Nachrichten pro Stunde) und die Latenz für die Transaktionskommunikation über das Control Panel. [Erfahren Sie mehr über die Überwachung des Durchsatzes](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=de){target="_blank"}

>[!NOTE]
>
>Bei Campaign v8 Managed Cloud Services wird die Serverinfrastruktur (CPU, Arbeitsspeicher, Festplatte) von Adobe überwacht und verwaltet.

### Technische Workflows {#technical-workflows}

Technische Workflows sind wichtige Prozesse, die im Hintergrund ausgeführt werden, um Ihre Campaign-Instanz zu verwalten.

**Überwachen Sie, dass technische Workflows Folgendes sind:**

* Planmäßig ausführen
* Erfolgreich und fehlerfrei abschließen
* Richtige Verarbeitung der Daten

**Wichtige zu überwachende technische Workflows:**

| Workflow | Zweck |
|----------|---------|
| **Tracking** | Verarbeitet Tracking-Daten von E-Mail-Sendungen |
| **Bereinigung** | Entfernt alte Daten und Protokolle, um die Datenbankleistung aufrechtzuerhalten |
| **Zustellbarkeitsaktualisierung** | Aktualisiert Zustellbarkeitsregeln und Spam-Filtermuster |
| **Datenbankbereinigung** | Löscht alte Versand- und Trackinglogs |

Weitere Informationen zu [technischen Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=de){target="_blank"}

### Campaign Control Panel {#control-panel}

Das Campaign Control Panel bietet Administratoren Self-Service-Funktionen zur Überwachung und Verwaltung von Campaign-Instanzen.

| Überwachungstyp | Funktionen |
|-----------------|--------------|
| **Leistung** | Tracking der aktiven Profilnutzung, Überwachung der Datenbanknutzung und -kapazität, Anzeige des Ausführungsstatus des Workflows, Überwachung des Versanddurchsatzes und der Latenz |
| **Infrastruktur** | Überwachen der SFTP-Speicherkapazität, Verfolgen der Subdomain-Konfiguration, Überwachen des SSL-Zertifikatablaufs, Verwalten der IP-Zulassungsauflistung |
| **instance** | Anzeigen von Build-Version und installierten Paketen, Überwachen der Systemkonfiguration, Verwalten autorisierter externer Domains |

Erfahren Sie mehr über [Control Panel](../config/self-service.md) und [Leistungsüberwachung des Control Panels](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=de){target="_blank"}

>[!NOTE]
>
>Für Campaign v8 Managed Cloud Services überwacht und verwaltet Adobe die Server-Infrastruktur, das Betriebssystem und die Anwendungsebene. Sie können die auf dieser Seite und im Control Panel beschriebenen Überwachungsfunktionen verwenden, um die Leistung, Workflows und Sendungen Ihrer Instanz zu überwachen.

## Tracking und Reporting {#tracking-reporting}

### Nachrichten-Tracking {#message-tracking}

Verfolgen Sie das Empfängerverhalten und messen Sie die Effektivität Ihrer Kampagnen:

* **Öffnungen**: Verfolgen Sie, wann Empfänger Ihre E-Mails öffnen
* **Klicks**: Überwachen Sie, auf welche Links die Empfänger klicken
* **Abmeldungen**: Verfolgen von Abmeldeanfragen
* **Mirrorseitenansichten**: Anzeigen, wie viele Empfänger Ihre E-Mail in einem Browser anzeigen

Weitere Informationen über [Nachrichten-Tracking](../send/tracking.md)

### Versandberichte {#delivery-reports}

Adobe Campaign bietet einen umfassenden Berichtssatz zur Analyse der Versandleistung:

* **Versandzusammenfassung**: Übersicht über Sendungen, Sendungen und Fehler
* **Tracking-Indikatoren**: Öffnungen, Klicks und Klickraten
* **URLs und Clickstreams**: Die beliebtesten Links in Ihren Sendungen
* **Klicks**: Visuelle Darstellung des Ortes, an dem Empfänger auf Ihre E-Mail geklickt haben

Weitere Informationen zu [Versandberichten](../reporting/delivery-reports.md)

### Allgemeine Berichte {#global-reports}

Zugriff auf globale Berichte zur Leistungsanalyse über alle Kampagnen und Sendungen hinweg:

* **Versanddurchsatz**: Nachrichten, die im Zeitverlauf gesendet werden
* **Fehler und Bounces**: Analyse fehlgeschlagener Sendungen
* **Benutzeraktivitäten**: Öffnungen, Klicks und Abmeldungen in allen Kampagnen

Weitere Informationen zu [globalen Berichten](../reporting/global-reports.md)

## Verwandte Themen {#related-topics}

* [Best Practices beim Versand](delivery-best-practices.md)
* [Quarantäneverwaltung](../send/quarantines.md)
* [Sendungen konfigurieren und durchführen](../send/configure-and-send.md)
* [Erste Schritte mit Berichten](../reporting/gs-reporting.md)


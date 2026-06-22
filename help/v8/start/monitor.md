---
title: Übersicht über die Überwachung von Kampagnen
description: Informationen zum Überwachen von Sendungen, Workflows und Ihrer Campaign-Instanz
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 6%

---

# Übersicht über die Überwachung von Kampagnen {#monitor-campaign}

Adobe Campaign bietet Ihnen Einblicke auf jeder Ebene - angefangen bei der Frage, ob eine einzelne Nachricht zugestellt wurde, über die Gründe für das Fehlschlagen eines Workflows bis hin zur verbleibenden Datenbankkapazität Ihrer Instanz. Auf dieser Seite werden alle Überwachungsfunktionen zugeordnet, sodass Sie wissen, wo Sie suchen müssen, wenn etwas Aufmerksamkeit erfordert.

>[!NOTE]
>
>Als Campaign-Admin können Sie auch das [Campaign Control Panel](#control-panel) verwenden, um Ihre Instanzen zu überwachen, die Leistung zu verwalten und Einstellungen mit Self-Service-Funktionen zu konfigurieren.

>[!TIP]
>
>**Sie sind sich nicht sicher, wo Sie anfangen sollen?**
>
>- Marketer-Überprüfung einer Kampagne → [Überwachen Ihrer Sendungen](#monitor-deliveries)
>- Fehlerbehebung bei einem Workflow → [Überwachen von Workflows](#monitor-workflows)
>- Admin überprüft den Zustand der Instanz → [Instanz überwachen](#monitor-instance)

## Überwachen von Sendungen {#monitor-deliveries}

Das Monitoring Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Nach dem Versand eines Versands können Sie dessen Status überwachen und Schlüsselmetriken im Versand-Dashboard verfolgen. Das Dashboard bietet Zugriff auf Versandlogs, Ausschlusslogs, Trackinglogs und andere Überwachungsfunktionen, mit denen Sie die Versandleistung kanalübergreifend analysieren können.

>[!NOTE]
>
>**Neu bei Campaign?** Das Versand-Dashboard ist Ihr Hauptbildschirm im Alltag. Öffnen Sie einen gesendeten Versand, klicken Sie auf die Registerkarte **Protokolle** und Sie sehen, welche Empfänger die Nachricht erhalten haben, welche ausgeschlossen wurden und warum, und wer geklickt oder geöffnet hat.

**E-Mail-**: Überwachen Sie den Status des E-Mail-Versands, verfolgen Sie Schlüsselmetriken und greifen Sie auf detaillierte Protokolle zu. Erfahren Sie mehr über [Überwachen von Sendungen in der Campaign](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/send/monitor/delivery-dashboard)-Benutzeroberfläche, [Versandstatus](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/send/monitor/delivery-statuses) und [Überwachen von E-Mail-Sendungen](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/emails/send#email-monitoring).

**SMS-Sendungen** - Verfolgen Sie den Status des SMS-Versands und überwachen Sie Schlüsselmetriken im Dashboard des SMS-Versands. Weitere Informationen zu [SMS-Überwachung](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/sms/sms-monitor).

**Push-Benachrichtigungen** - Überwachen Sie den Versand von Push-Benachrichtigungen, um sicherzustellen, dass sie die Benutzer Ihrer Mobile App effektiv erreichen. Weitere Informationen zur [Überwachung von Push-](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/push/push#push-test)&quot;

**Transaktionsnachrichten** - Überwachen Sie für Nachrichten, die durch Ereignisse ausgelöst werden, den Status der Ereignisverarbeitung, die Ausführung von Nachrichten und den Versandstatus. Weitere Informationen über [Überwachung von Transaktionsnachrichten](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages).

**Versandfehler** - Um eine saubere Datenbank zu verwalten und gute Zustellbarkeitsraten zu gewährleisten, ist es von entscheidender Bedeutung, die Gründe für fehlgeschlagene Sendungen zu verstehen. Fehlgeschlagene Sendungen werden in drei Typen unterteilt: Wenn Sie den Unterschied verstehen, können Sie entscheiden, welche Aktion Sie durchführen möchten:

| Fehlertyp | Was dies bedeutet | Funktionsweise von Campaign |
| --- | --- | --- |
| **Hardbounce** | Die Adresse ist dauerhaft ungültig (existiert nicht, Domain unbekannt) | Kontakt wird automatisch unter Quarantäne gestellt, sodass er in zukünftigen Sendungen nicht mehr als Zielgruppe dient |
| **Softbounce** | Ein temporäres Problem (vollständiges Postfach, Server vorübergehend nicht verfügbar) | Campaign versucht es für einen konfigurierten Zeitraum automatisch erneut |
| **Ignoriert** | Die Adresse wurde vor dem Versand bereits unter Quarantäne gestellt oder befindet sich auf einer Blockierungsliste | Es wird kein Versuch unternommen. Er wird getrennt von den Bounces gezählt |

Weitere Informationen zu [fehlgeschlagenen Sendungen und Quarantänen](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/send/monitor/delivery-failures).

## Überwachen der Zustellbarkeit {#monitor-deliverability}

>[!NOTE]
>
>Eine Nachricht, die als „zugestellt“ gezählt wird, bedeutet, dass sie vom empfangenden Server akzeptiert wurde - sie garantiert nicht die Platzierung im Posteingang. Die Zustellbarkeitsüberwachung gibt Aufschluss darüber, ob die Authentifizierung der sendenden Domain, die IP-Reputation und der E-Mail-Inhalt den Standards des Posteingangsanbieters entsprechen.

Die Zustellbarkeits-Überwachung hilft Ihnen sicherzustellen, dass Ihre Nachrichten die Posteingänge Ihrer Empfänger erreichen und Spam-Filter vermeiden. Adobe Campaign bietet mehrere integrierte Tools zur Überwachung und Verbesserung der Zustellbarkeit, einschließlich Versandberichte, Inbox Rendering, SpamAssassin-Tests und Broadcast-Statistiken. Die Befolgung von Best Practices für die Zustellbarkeit, wie die Pflege einer sauberen E-Mail-Liste, die Überwachung der Reputation des Absenders und die Authentifizierung von Versand-Domains, ist wichtig, um gute Zustellbarkeitsraten aufrechtzuerhalten.

Erfahren Sie mehr über [Tools zur Zustellbarkeitsüberwachung](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) und [Best Practices zur Zustellbarkeit](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability).

## Überwachen von Workflows {#monitor-workflows}

Workflows sind zur Automatisierung Ihrer Marketing-Kampagnen und Datenverarbeitung unerlässlich. Die Überwachung der Workflow-Ausführung hilft Ihnen bei Folgendem:

- Sicherstellen, dass Workflows erfolgreich abgeschlossen werden
- Fehler identifizieren und beheben
- Optimieren der Workflow-Leistung

>[!TIP]
>
>Wenn ein Workflow den Status **Fehlgeschlagen** aufweist, öffnen Sie ihn, klicken Sie mit der rechten Maustaste auf die rote Aktivität und wählen Sie **Protokolle anzeigen**. Die Fehlermeldung gibt genau an, was schiefgelaufen ist und auf welchem Datensatz.

### Workflow-Überwachungsfunktionen {#workflow-monitoring}

**Überwachen Sie die folgenden Workflow-Elemente:**

**Workflow-Ausführungsstatus** - Verfolgen Sie, ob Workflows ausgeführt werden, angehalten, fehlgeschlagen oder abgeschlossen sind. [Erfahren Sie mehr über die Ausführung von Workflows](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**Protokolle zur Aktivitätsausführung** - Greifen Sie auf detaillierte Protokolle für jede Workflow-Aktivität zu, um Probleme zu beheben und die Leistung zu optimieren.

**Workflow-Heatmap** - Ein visueller Überblick über alle Workflows, die gleichzeitig in Ihrer Instanz ausgeführt werden. Ermitteln Sie Spitzenlastzeiten, erkennen Sie Workflows, die unverhältnismäßige Ressourcen verbrauchen, und planen Sie die Planung, um Ausführungskonflikte zu vermeiden. Nur für Campaign-Administratoren verfügbar. [Erfahren Sie mehr über Workflow-Heatmap](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**Workflow-Verlauf** - Verfolgen Sie alle Workflow-Ausführungen und -Änderungen im Laufe der Zeit, um das Verhalten und die Leistung von Workflows zu verstehen.

## Überwachen einer Instanz {#monitor-instance}

Mit der Instanzüberwachung können Sie den Zustand und die Leistung Ihrer Adobe Campaign-Umgebung sicherstellen. Für Campaign v8 Managed Cloud Services überwacht und verwaltet Adobe auch die Infrastruktur in Ihrem Namen. Weitere Informationen zum [Adobe-verwalteten Monitoring](#adobe-cloud-monitoring).

### Audit-Protokoll {#audit-trail}

Über die Self-Service-Benutzeroberfläche des Audit-Protokolls können Sie Änderungen überwachen, die in Ihrer Adobe Campaign-Instanz vorgenommen wurden. Das Audit-Protokoll erfasst in Echtzeit eine umfassende Liste von Aktionen und Ereignissen, die in Ihrer Instanz auftreten.

**Audit-Protokoll verwenden für:**

- **Komponentenänderungen verfolgen** Überwachen Sie, was mit Ihren Workflows, Schemata, Optionen und anderen Komponenten passiert ist
- **Ermitteln, wer Änderungen vorgenommen hat**: Ermitteln Sie, wer ein bestimmtes Element zuletzt aktualisiert hat und wann
- **Benutzeraktionen verstehen**: Überprüfen Sie, was Benutzer in der Instanz getan haben, um Fehler zu beheben oder Prüfungen durchzuführen
- **Einhaltung gewährleisten**: Verfolgen Sie alle Konfigurationsänderungen zu Compliance- und Sicherheitszwecken

Das Audit-Protokoll ist über die Campaign-Client-Konsole aufrufbar und enthält detaillierte Informationen zu den von den Benutzern durchgeführten Aktionen.

Weitere Informationen zu [Audit-Protokoll](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/audit-trail)

### Überwachen der Performance {#performance-monitoring}

Campaign v8 bietet verschiedene Überwachungsfunktionen, um die Leistung Ihrer Instanz zu verfolgen und einen optimalen Betrieb sicherzustellen:

**Datenbanküberwachung** - Überwachen Sie die Datenbanknutzung und -kapazität über das Control Panel, um eine optimale Leistung und Speicherverwaltung sicherzustellen. [Erfahren Sie mehr über die Datenbanküberwachung](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**Überwachen aktiver Profile** - Verfolgen Sie die aktive Profilnutzung anhand Ihrer vertraglichen Beschränkungen, um die Compliance aufrechtzuerhalten und die Ressourcenzuweisung zu optimieren. [Erfahren Sie mehr über aktive Profile](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**Workflow-Überwachung** - Überwachen Sie den Ausführungsstatus des Workflows, um langwierige Workflows zu identifizieren und sicherzustellen, dass alle technischen Workflows ordnungsgemäß ausgeführt werden. [Erfahren Sie mehr über technische Workflows](#technical-workflows)

**Versanddurchsatz und Latenz** - Verfolgen Sie den Versanddurchsatz (Nachrichten pro Stunde) und die Latenz für die Transaktionskommunikation über das Control Panel. [Erfahren Sie mehr über die Überwachung des Durchsatzes](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>Bei Campaign v8 Managed Cloud Services wird die Serverinfrastruktur (CPU, Arbeitsspeicher, Festplatte) von Adobe überwacht und verwaltet. Weitere Informationen zum [Adobe-verwalteten Monitoring](#adobe-cloud-monitoring).

### Adobe-verwaltetes Monitoring {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services bietet durch eine flexible Cloud-Infrastruktur geschäftskritischen Support für die Bereitstellung anspruchsvoller Kundenerlebnisse. Auf diese Weise können Unternehmen Kundenerlebnisse starten, überwachen und optimieren, ohne die Campaign-Infrastruktur selbst verwalten oder betreiben zu müssen.

Adobe überwacht Ihre Campaign Cloud Services-Umgebungen, um verschiedene Probleme zu verwalten und Unterbrechungen zu minimieren, indem technische Probleme erkannt und kontinuierliches Feedback zur Leistung und zu laufenden Projekten gegeben wird.

**Wie Adobe reagiert**

Adobe überwacht rund um die Uhr alle wichtigen Netzwerkgeräte im Campaign-Netzwerk und erhält Benachrichtigungen von Überwachungssystemen, wenn Fehlerbehebungen oder Eskalationen erforderlich sind. Wenn ein Problem erkannt wird, verwendet das System Mechanismen für den automatischen Neustart und den automatischen Start, um eine Behebung zu versuchen. Wenn das System keine Selbstkorrektur durchführt, greift das Adobe On-Call-Engineering ein, um eine Fehlerbehebung auf der Grundlage vordefinierter Warnhinweis-Runbooks durchzuführen.

>[!NOTE]
>
>Einige von Adobe durchgeführte Überwachungsaktionen werden in den Kampagnenprotokollen unter dem Benutzer **campaign-loginMonitor** angezeigt.

Zusätzlich zur internen Überwachung von Adobe können Sie direkt über die Campaign-Client-Konsole oder das [Campaign Control Panel“ auf ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service) Überwachungsfunktionen zugreifen. Mit dem Control Panel können Sie Echtzeitwarnungen zu Ihren Instanzen abonnieren und empfohlene Schritte zur Behebung identifizierter Vorfälle erhalten (z. B. SSL-Zertifikate, die bald ablaufen).

**Überwachen der Taxonomie**

Adobe überwacht Ihre Umgebung auf drei Ebenen:

| Stufe | Gruppe | Mögliche geschäftliche Auswirkungen |
| --- | --- | --- |
| **Ebene 1: Infrastruktur** | Erschöpfung des Datenbankspeicherplatzes | Leistungsprobleme, einschließlich der Unfähigkeit, sich anzumelden, Batch-Sendungen auszuführen oder Abfragen auszuführen |
| **Ebene 1: Infrastruktur** | Datenbankverfügbarkeit | Benutzer und Dienste können das System möglicherweise nicht verwenden |
| **Ebene 1: Infrastruktur** | Datenbanküberlastung (Burst-Balance) | Leistungsprobleme, einschließlich der Unfähigkeit, sich anzumelden, Batch-Sendungen auszuführen oder Abfragen auszuführen |
| **Ebene 1: Infrastruktur** | Datenbanksequenz und Erschöpfung der Transaktions-ID | Es können keine neuen Workflows, Sendungen oder Batch-E-Mails erstellt werden |
| **Ebene 1: Infrastruktur** | SFTP-Speicher | Daten auf SFTP-Servern können nicht aktualisiert oder abgerufen werden |
| **Ebene 2: Plattform und Web** | Login | Benutzer können sich möglicherweise nicht anmelden. Geplante Aktivitäten und Workflows werden möglicherweise nicht ausgeführt |
| **Ebene 2: Plattform und Web** | API-Sperre | Benutzer oder Dienste können sich möglicherweise nicht authentifizieren oder Vorgänge ausführen |
| **Ebene 2: Plattform und Web** | Web | Es können keine neuen Verbindungen mit Campaign hergestellt werden |
| **Ebene 2: Plattform und Web** | Rechenzentrumsnetzwerk | Leistungsprobleme oder vollständige Nichtverfügbarkeit für Benutzer im Rechenzentrum |
| **Stufe 3: Software** | Versandverfolgung | Die Verarbeitung von Trackinglogs ist nicht verfügbar |
| **Stufe 3: Software** | inMail | Kein Feedback zu Fehlern und Bounces bei E-Mail-Sendungen |
| **Stufe 3: Software** | Message-Center-Status | Es können keine Transaktionsnachrichten gesendet werden |
| **Stufe 3: Software** | MTA | Geplante und Ad-hoc-E-Mail-Sendungen können nicht gesendet werden |
| **Stufe 3: Software** | Workflow-Server-Status | Workflows können nicht ausgeführt werden |
| **Stufe 3: Software** | Verfügbarkeit der Web-API | HTTP-Anfragen können nicht verarbeitet oder API-Aufrufe nicht ausgeführt werden |
| **Stufe 3: Software** | Eingehende Interaktionen | Eingehende Interaktionen können nicht verarbeitet werden |

>[!NOTE]
>
>Adobe Campaign Cloud Services basiert auf einer Multi-Cloud-Strategie und bietet Bereitstellungen auf AWS und Azure. Aufgrund von Anbieterunterschieden unterscheiden sich die Überwachungsfunktionen zwischen AWS, Azure und anderen Rechenzentrumsbereitstellungen. Die obige Tabelle gilt, sofern nicht anders angegeben, für Campaign Cloud Services-Kunden, die auf AWS gehostet werden. Beachten Sie außerdem, dass Adobe Campaign derzeit nicht alle vom On-Call-Engineering verwendeten Überwachungsdaten für Kunden verfügbar macht.

### Technische Workflows {#technical-workflows}

Technische Workflows sind wichtige Prozesse, die im Hintergrund ausgeführt werden, um Ihre Campaign-Instanz zu verwalten.

**Überwachen Sie, dass technische Workflows Folgendes sind:**

- Planmäßig ausführen
- Erfolgreich und fehlerfrei abschließen
- Richtige Verarbeitung der Daten

**Wichtige zu überwachende technische Workflows:**

| Workflow | Zweck | Wenn er fehlschlägt |
| --- | --- | --- |
| **Tracking** | Verarbeitet Tracking-Daten von E-Mail-Sendungen | Klicken und öffnen Sie Metriken, die nicht mehr in Berichten aktualisiert werden |
| **Bereinigung** | Entfernt alte Daten und Protokolle, um die Datenbankleistung aufrechtzuerhalten | Datenbank wächst ungeprüft, was die Abfrage- und Versandleistung beeinträchtigt |
| **Zustellbarkeitsaktualisierung** | Aktualisiert Zustellbarkeitsregeln und Spam-Filtermuster | Regeln werden veraltet; die Filtergenauigkeit kann sich verschlechtern |
| **Datenbankbereinigung** | Löscht alte Versand- und Trackinglogs | Die Protokollakkumulation verlangsamt Abfragen und Berichte im Zeitverlauf |

Weitere Informationen zu [technischen Workflows](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Campaign Control Panel {#control-panel}

Das Campaign Control Panel bietet Administratoren Self-Service-Funktionen zur Überwachung und Verwaltung von Campaign-Instanzen.

| Überwachungstyp | Funktionen |
| --- | --- |
| **Leistung** | Tracking der aktiven Profilnutzung, Überwachung der Datenbanknutzung und -kapazität, Anzeige des Ausführungsstatus des Workflows, Überwachung des Versanddurchsatzes und der Latenz |
| **Infrastruktur** | Überwachen der SFTP-Speicherkapazität, Verfolgen der Subdomain-Konfiguration, Überwachen des SSL-Zertifikatablaufs, Verwalten der IP-Zulassungsauflistung |
| **instance** | Anzeigen von Build-Version und installierten Paketen, Überwachen der Systemkonfiguration, Verwalten autorisierter externer Domains |

Erfahren Sie mehr über [Control Panel](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service) und [Leistungsüberwachung des Control Panels](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>Für Campaign v8 Managed Cloud Services überwacht und verwaltet Adobe die Server-Infrastruktur, das Betriebssystem und die Anwendungsebene. Weitere Informationen zum [Adobe-verwalteten Monitoring](#adobe-cloud-monitoring). Sie können die auf dieser Seite und im Control Panel beschriebenen Überwachungsfunktionen verwenden, um die Leistung, Workflows und Sendungen Ihrer Instanz zu überwachen.

## Tracking und Reporting {#tracking-reporting}

### Nachrichten-Tracking {#message-tracking}

Verfolgen Sie das Empfängerverhalten und messen Sie die Effektivität Ihrer Kampagnen:

- **Öffnungen**: Verfolgen Sie, wann Empfänger Ihre E-Mails öffnen
- **Klicks**: Überwachen Sie, auf welche Links die Empfänger klicken
- **Abmeldungen**: Verfolgen von Abmeldeanfragen
- **Mirrorseitenansichten**: Anzeigen, wie viele Empfänger Ihre E-Mail in einem Browser anzeigen

Weitere Informationen über [Nachrichten-Tracking](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/analytics/tracking/tracking)

### Versandberichte {#delivery-reports}

Adobe Campaign bietet einen umfassenden Berichtssatz zur Analyse der Versandleistung:

- **Versandzusammenfassung**: Übersicht über Sendungen, Sendungen und Fehler
- **Tracking-Indikatoren**: Öffnungen, Klicks und Klickraten
- **URLs und Clickstreams**: Die beliebtesten Links in Ihren Sendungen
- **Klicks**: Visuelle Darstellung des Ortes, an dem Empfänger auf Ihre E-Mail geklickt haben

Weitere Informationen zu [Versandberichten](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### Allgemeine Berichte {#global-reports}

Zugriff auf globale Berichte zur Leistungsanalyse über alle Kampagnen und Sendungen hinweg:

- **Versanddurchsatz**: Nachrichten, die im Zeitverlauf gesendet werden
- **Fehler und Bounces**: Analyse fehlgeschlagener Sendungen
- **Benutzeraktivitäten**: Öffnungen, Klicks und Abmeldungen in allen Kampagnen

Weitere Informationen zu [globalen Berichten](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## Verwandte Themen {#related-topics}

- [Best Practices für den Versand](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/send/delivery-best-practices)
- [Quarantäneverwaltung](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/send/monitor/quarantines)
- [Sendungen konfigurieren und durchführen](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [Erste Schritte mit Reporting](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/analytics/reports/gs-reporting)

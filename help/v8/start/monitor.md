---
title: Übersicht über die Überwachung von Kampagnen
description: Informationen zum Überwachen von Sendungen, Workflows und Ihrer Campaign-Instanz
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: e8438b85eec144e83b2660f9d66444c1a01863ab
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 5%

---

# Übersicht über die Überwachung von Kampagnen {#monitor-campaign}

Adobe Campaign bietet Ihnen Einblicke auf jeder Ebene - angefangen bei der Frage, ob eine einzelne Nachricht zugestellt wurde, über die Gründe für das Fehlschlagen eines Workflows bis hin zur verbleibenden Datenbankkapazität Ihrer Instanz. Auf dieser Seite werden alle Überwachungsfunktionen zugeordnet, sodass Sie wissen, wo Sie suchen müssen, wenn etwas Aufmerksamkeit erfordert. Als Campaign-Admin können Sie auch das [Campaign Control Panel](#control-panel) verwenden, um Ihre Instanzen zu überwachen, die Leistung zu verwalten und Einstellungen mit Self-Service-Funktionen zu konfigurieren.

>[!TIP]
>
>**Sie sind sich nicht sicher, wo Sie anfangen sollen?**
>
>- Marketer-Überprüfung einer Kampagne → [Überwachen Ihrer Sendungen](#monitor-deliveries)
>- Fehlerbehebung bei einem Workflow → [Überwachen von Workflows](#monitor-workflows)
>- Admin überprüft den Zustand der Instanz → [Instanz überwachen](#monitor-instance)

## Überwachen von Sendungen {#monitor-deliveries}

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kundschaft erreichen. Nach dem Versand eines Versands können Sie dessen Fortschritt verfolgen und Probleme über das Versand-Dashboard diagnostizieren. Das Dashboard bietet Zugriff auf Versandlogs, Ausschlusslogs, Trackinglogs und andere Daten für jeden Kanal, den Sie verwenden.

>[!NOTE]
>
>**Neu bei Campaign?** Das Versand-Dashboard ist Ihr Hauptbildschirm im Alltag. Öffnen Sie einen gesendeten Versand, klicken Sie auf die Registerkarte **Protokolle** und Sie sehen, welche Empfänger die Nachricht erhalten haben, welche ausgeschlossen wurden und warum, und wer geklickt oder geöffnet hat.

**E-Mail-**: Überwachen Sie den Status des E-Mail-Versands, verfolgen Sie Schlüsselmetriken und greifen Sie auf detaillierte Protokolle zu. Erfahren Sie mehr über [Überwachen von Sendungen in der Campaign](../send/delivery-dashboard.md)-Benutzeroberfläche, [Versandstatus](../send/delivery-statuses.md) und [Überwachen von E-Mail-Sendungen](../send/send.md#email-monitoring).

**SMS-Sendungen** - Verfolgen Sie den Status des SMS-Versands und überwachen Sie Schlüsselmetriken im Dashboard des SMS-Versands. Weitere Informationen zu [SMS-Überwachung](../send/sms/sms-monitor.md).

**Push-Benachrichtigungen** - Überwachen Sie den Versand von Push-Benachrichtigungen, um sicherzustellen, dass sie die Benutzer Ihrer Mobile App effektiv erreichen. Weitere Informationen zur [Überwachung von Push-](../send/push.md#push-test)&quot;

**Transaktionsnachrichten** - Für Nachrichten, die durch Ereignisse ausgelöst werden, überwachen Sie den Status der Ereignisverarbeitung, die Warteschlangentiefe und die Ausführungsergebnisse. Weitere Informationen über [Überwachung von Transaktionsnachrichten](../send/delivery-execution.md#monitor-messages).

**Versandfehler** - Um eine saubere Datenbank zu verwalten und gute Zustellbarkeitsraten zu gewährleisten, ist es von entscheidender Bedeutung, zu verstehen, warum ein Versand fehlgeschlagen ist. Fehlgeschlagene Sendungen werden in drei Typen unterteilt: Wenn Sie den Unterschied verstehen, können Sie entscheiden, welche Aktion Sie durchführen möchten:

| Fehlertyp | Was dies bedeutet | Funktionsweise von Campaign |
| --- | --- | --- |
| **Hardbounce** | Die Adresse ist dauerhaft ungültig (existiert nicht, Domain unbekannt) | Kontakt wird automatisch unter Quarantäne gestellt, sodass er in zukünftigen Sendungen nicht mehr als Zielgruppe dient |
| **Softbounce** | Ein temporäres Problem (vollständiges Postfach, Server vorübergehend nicht verfügbar) | Campaign versucht es für einen konfigurierten Zeitraum automatisch erneut |
| **Ignoriert** | Die Adresse wurde vor dem Versand bereits unter Quarantäne gestellt oder befindet sich auf einer Blockierungsliste | Es wird kein Versuch unternommen. Er wird getrennt von den Bounces gezählt |

Weitere Informationen zu [fehlgeschlagenen Sendungen und Quarantänen](../send/delivery-failures.md).

## Überwachen der Zustellbarkeit {#monitor-deliverability}

Die Zustellbarkeit ist der Maßstab dafür, wie erfolgreich Ihre Nachrichten die Posteingänge der Empfänger erreichen - und nicht nach Spam gefiltert oder abgelehnt werden. Adobe Campaign bietet mehrere integrierte Tools, mit denen Sie Ihre Platzierungsraten im Posteingang verstehen und verbessern können.

>[!NOTE]
>
>Eine Nachricht, die als „zugestellt“ gezählt wird, bedeutet, dass sie vom empfangenden Server akzeptiert wurde - sie garantiert nicht die Platzierung im Posteingang. Die Zustellbarkeitsüberwachung gibt Aufschluss darüber, ob die Authentifizierung der sendenden Domain, die IP-Reputation und der E-Mail-Inhalt den Standards des Posteingangsanbieters entsprechen.

Adobe Campaign bietet die folgenden integrierten Zustellbarkeits-Tools:

- **Versandberichte** - Integrierte Berichte mit Sendevolumen, Bounce-Raten und Abmeldungen im Zeitverlauf.
- **Inbox Rendering** - Vorschau der Darstellung Ihrer E-Mail auf wichtigen Clients (Gmail, Outlook, Apple Mail) vor oder nach dem Versand.
- **SpamAssassin-Test** - Bewerten Sie Ihren E-Mail-Inhalt anhand gängiger Spam-Filterregeln, um Probleme vor dem Versand zu erkennen.
- **Versandstatistiken**: Aggregieren Sie Versanddaten über Ihre Versandvolumen und IP-Reputation.

Die Befolgung von Best Practices zur Zustellbarkeit - wie die Pflege einer sauberen E-Mail-Liste, die Überwachung der Reputation des Absenders und die Authentifizierung von Versand-Domains - ist wichtig, um gute Zustellbarkeitsraten beizubehalten.

Erfahren Sie mehr über [Tools zur Zustellbarkeitsüberwachung](../send/monitoring-deliverability.md) und [Best Practices zur Zustellbarkeit](../send/about-deliverability.md).

## Überwachen von Workflows {#monitor-workflows}

Workflows sind der Motor für Marketing-Automatisierungen und Datenverarbeitung. Ihre Überwachung stellt sicher, dass geplante Aktivitäten erwartungsgemäß abgeschlossen werden und Fehler erkannt werden, bevor sie den Versand oder die Datenqualität beeinträchtigen.

>[!TIP]
>
>Wenn ein Workflow den Status **Fehlgeschlagen** aufweist, öffnen Sie ihn, klicken Sie mit der rechten Maustaste auf die rote Aktivität und wählen Sie **Protokolle anzeigen**. Die Fehlermeldung gibt genau an, was schiefgelaufen ist und auf welchem Datensatz.

### Workflow-Überwachungsfunktionen {#workflow-monitoring}

**Überwachen Sie die folgenden Workflow-Elemente:**

**Workflow-Ausführungsstatus** - Verfolgen Sie, ob Workflows ausgeführt werden, angehalten, fehlgeschlagen oder abgeschlossen sind. Spot-Stick oder langwierige Workflows auf einen Blick. [Erfahren Sie mehr über die Ausführung von Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

**Protokolle zur Aktivitätsausführung** - Aufschlüsselung der Protokolle pro Aktivität, um zu verstehen, was bei jedem Schritt passiert ist. Nützlich für die Fehlerbehebung bei fehlgeschlagenen Transitionen oder unerwarteten Datenausgaben.

**Workflow-Heatmap** - Ein visueller Überblick über alle Workflows, die gleichzeitig in Ihrer Instanz ausgeführt werden. Ermitteln Sie Spitzenlastzeiten, erkennen Sie Workflows, die unverhältnismäßige Ressourcen verbrauchen, und planen Sie die Planung, um Ausführungskonflikte zu vermeiden. Nur für Campaign-Administratoren verfügbar. [Erfahren Sie mehr über Workflow-Heatmap](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=de){target="_blank"}

**Workflow-Verlauf** - Verfolgen Sie alle Workflow-Ausführungen und -Änderungen im Laufe der Zeit, um das Workflow-Verhalten und die Leistungsmuster zu verstehen.

## Überwachen einer Instanz {#monitor-instance}

Die Instanzüberwachung deckt den Zustand Ihrer Campaign-Umgebung ab - Datenbankkapazität, Profilnutzung, Durchsatz und Infrastruktur. Für Campaign v8 Managed Cloud Services überwacht und verwaltet Adobe die zugrunde liegende Infrastruktur in Ihrem Namen, Sie behalten jedoch die volle Sichtbarkeit über die Client-Konsole und das Control Panel bei. Weitere Informationen zum [Adobe-verwalteten Monitoring](#adobe-cloud-monitoring).

### Audit-Protokoll {#audit-trail}

Über die Selbstbedienungsoberfläche des Audit-Protokolls können Sie alle wichtigen Änderungen überwachen, die in Ihrer Adobe Campaign-Instanz vorgenommen wurden. Das Audit-Protokoll erfasst in Echtzeit eine umfassende Liste von Aktionen und Ereignissen, die in Ihrer Instanz auftreten.

**Audit-Protokoll verwenden für:**

- **Komponentenänderungen verfolgen** - Überwachen Sie, was mit Ihren Workflows, Schemata, Optionen und anderen Komponenten passiert ist
- **Identifizieren, wer eine Änderung vorgenommen hat** - Ermitteln Sie, welcher Benutzer ein Element zuletzt geändert hat und zu welchem Zeitpunkt
- **Fehlerbehebung bei unerwartetem Verhalten** — Verfolgen Sie Benutzeraktionen, um herauszufinden, wann und wie ein Problem aufgetreten ist
- **Support Compliance and Audits** - Führen Sie eine vollständige, manipulationssichere Aufzeichnung aller Konfigurationsänderungen

Das Audit-Protokoll ist über die Campaign-Client-Konsole aufrufbar und enthält detaillierte Informationen zu den von den Benutzern durchgeführten Aktionen.

Weitere Informationen zu [Audit-Protokoll](../reporting/audit-trail.md)

### Überwachen der Performance {#performance-monitoring}

Campaign v8 bietet verschiedene Überwachungsfunktionen, um die Leistung Ihrer Instanz zu verfolgen und einen optimalen Betrieb sicherzustellen:

**Datenbanküberwachung** - Überwachen Sie die Datenbanknutzung und -kapazität über das Control Panel, um eine optimale Leistung und Speicherverwaltung sicherzustellen. [Erfahren Sie mehr über die Datenbanküberwachung](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Überwachen aktiver Profile** - Verfolgen Sie die aktive Profilnutzung anhand Ihrer vertraglichen Beschränkungen, um die Compliance aufrechtzuerhalten und die Ressourcenzuweisung zu optimieren. [Erfahren Sie mehr über aktive Profile](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=de){target="_blank"}

**Workflow-Überwachung** - Überwachen Sie den Ausführungsstatus des Workflows, um langwierige Workflows zu identifizieren und sicherzustellen, dass alle technischen Workflows ordnungsgemäß ausgeführt werden. [Erfahren Sie mehr über technische Workflows](#technical-workflows)

**Versanddurchsatz und Latenz** - Verfolgen Sie den Versanddurchsatz (Nachrichten pro Stunde) und die Latenz für die Transaktionskommunikation über das Control Panel. [Erfahren Sie mehr über die Überwachung des Durchsatzes](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=de){target="_blank"}

>[!NOTE]
>
>Bei Campaign v8 Managed Cloud Services wird die Serverinfrastruktur (CPU, Arbeitsspeicher, Festplatte) von Adobe überwacht und verwaltet. Die auf dieser Seite und im Control Panel beschriebenen Überwachungsfunktionen ergänzen sich. Sie bieten Ihnen Einblick in Ihre Daten und Konfigurationen, ohne dass ein Zugriff auf die Infrastruktur erforderlich ist. Einige von Adobe durchgeführte Aktionen werden in Ihren Kampagnenprotokollen unter dem Benutzer **campaign-loginMonitor** angezeigt. Weitere Informationen zum [Adobe-verwalteten Monitoring](#adobe-cloud-monitoring).

### Adobe-verwaltetes Monitoring {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services bietet durch eine flexible Cloud-Infrastruktur geschäftskritischen Support für die Bereitstellung anspruchsvoller Kundenerlebnisse. Auf diese Weise können Unternehmen Kundenerlebnisse starten, überwachen und optimieren, ohne die Campaign-Infrastruktur selbst verwalten oder betreiben zu müssen.

Adobe überwacht Ihre Campaign Cloud Services-Umgebungen rund um die Uhr, um technische Probleme zu erkennen und Unterbrechungen zu minimieren. Wenn ein Problem erkannt wird, verwendet das System Mechanismen für den automatischen Neustart und den automatischen Start, um eine Behebung zu versuchen. Wenn das System keine Selbstreparatur vornimmt, greift das Adobe On-Call-Engineering auf der Grundlage vordefinierter Warnhinweis-Runbooks ein.

>[!TIP]
>
>Sie können Warnhinweise zu Echtzeit-Instanzen über das [Campaign Control Panel](#control-panel) abonnieren und empfohlene Schritte zur Behebung erkannter Probleme erhalten - beispielsweise SSL-Zertifikate, die bald ablaufen.

**Überwachen von Ebenen**

Adobe überwacht Ihre Umgebung über drei Ebenen. Tier-1-Probleme haben die größte Wirkung und erhalten die schnellste Reaktion:

| Stufe | Gruppe | Was Sie möglicherweise erleben |
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
>Adobe Campaign Cloud Services basiert auf einer Multi-Cloud-Strategie mit Bereitstellungen auf AWS und Azure. Die Überwachungsfunktionen von AWS, Azure und anderen Rechenzentrumsbereitstellungen sind unterschiedlich. Die obige Tabelle gilt, sofern nicht anders angegeben, für Campaign Cloud Services-Kunden, die auf AWS gehostet werden. Adobe Campaign stellt derzeit nicht alle vom On-Call-Engineering verwendeten Überwachungsdaten für Kunden bereit.

### Technische Workflows {#technical-workflows}

Technische Workflows werden im Hintergrund leise ausgeführt, um Ihre Campaign-Instanz zu verwalten. Sie werden nicht von Benutzenden erstellt, sondern zusammen mit dem Produkt bereitgestellt. Schlägt ein technischer Workflow fehl, kann dies direkte Auswirkungen auf die Sendungen und die Datenqualität haben.

Stellen Sie sicher, dass jeder technische Workflow planmäßig ausgeführt wird, fehlerfrei abgeschlossen wird und die Daten korrekt verarbeitet werden.

| Workflow | Zweck | Wenn er fehlschlägt |
| --- | --- | --- |
| **Tracking** | Verarbeitet Tracking-Daten von E-Mail-Sendungen | Klicken und öffnen Sie Metriken, die nicht mehr in Berichten aktualisiert werden |
| **Bereinigung** | Entfernt alte Daten und Protokolle, um die Datenbankleistung aufrechtzuerhalten | Datenbank wächst ungeprüft, was die Abfrage- und Versandleistung beeinträchtigt |
| **Zustellbarkeitsaktualisierung** | Aktualisiert Zustellbarkeitsregeln und Spam-Filtermuster | Regeln werden veraltet; die Filtergenauigkeit kann sich verschlechtern |
| **Datenbankbereinigung** | Löscht alte Versand- und Trackinglogs | Die Protokollakkumulation verlangsamt Abfragen und Berichte im Zeitverlauf |

Weitere Informationen zu [technischen Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=de){target="_blank"}

### Campaign Control Panel {#control-panel}

Das Campaign Control Panel bietet Administratoren Self-Service-Funktionen zur Überwachung und Verwaltung von Campaign-Instanzen, ohne dass ein Support-Ticket erforderlich ist.

| Überwachungstyp | Funktionen |
| --- | --- |
| **Leistung** | Aktive Profilnutzung vs. Vertragsbeschränkung, Datenbanknutzung und -kapazität, Workflow-Ausführungsstatus, Versanddurchsatz und Latenz |
| **Infrastruktur** | SFTP-Speicherkapazität, Subdomain-Konfiguration, SSL-Zertifikat-Ablaufwarnungen, IP-Zulassungsauflistung |
| **instance** | Build-Version und installierte Pakete, Übersicht über die Systemkonfiguration, autorisierte externe Domains |

Erfahren Sie mehr über [Control Panel](../config/self-service.md) und [Leistungsüberwachung des Control Panels](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=de){target="_blank"}

>[!NOTE]
>
>Für Campaign v8 Managed Cloud Services überwacht und verwaltet Adobe die Server-Infrastruktur, das Betriebssystem und die Anwendungsebene. Die auf dieser Seite und im Control Panel beschriebenen Überwachungsfunktionen ergänzen sich. Sie bieten Ihnen Einblick in Ihre Daten und Konfigurationen, ohne dass ein Zugriff auf die Infrastruktur erforderlich ist.

## Tracking und Reporting {#tracking-reporting}

### Nachrichten-Tracking {#message-tracking}

Tracking zeichnet auf, wie Empfänger nach dem Versand mit Ihren Nachrichten interagieren. Alle verfolgten Ereignisse werden in Trackinglogs gespeichert und in Versandberichten angezeigt.

- **Öffnungen** - Wird aufgezeichnet, wenn das Tracking-Pixel geladen wird (nur E-Mail)
- **Klicks** - Wird für jeden verfolgten Link in der Nachricht aufgezeichnet
- **Abmeldungen** — Opt-out-Anfragen über den Abmelde-Link
- **Mirrorseitenansichten** - Empfänger, die die E-Mail in einem Browser angesehen haben

Weitere Informationen über [Nachrichten-Tracking](../send/tracking.md)

### Versandberichte {#delivery-reports}

Adobe Campaign bietet einen umfassenden Berichtssatz zur Analyse der Versandleistung:

- **Versandzusammenfassung** - Übersicht über Sendungen, Sendungen und Fehler für einen einzelnen Versand
- **Tracking-Indikatoren** - Öffnungen, Klicks und Clickthrough-Raten mit Trends im Zeitverlauf
- **URLs und Clickstreams** - Rangfolge der am häufigsten angeklickten Links mit Zahlen und Prozentsätzen
- **Klicks** - Visuelle Überlagerung, die anzeigt, wo Empfänger im E-Mail-Textkörper geklickt haben

Weitere Informationen zu [Versandberichten](../reporting/delivery-reports.md)

### Allgemeine Berichte {#global-reports}

Zugriff auf globale Berichte zur Leistungsanalyse über alle Kampagnen und Sendungen hinweg:

- **Versanddurchsatz** - Nachrichten, die über einen bestimmten Zeitraum hinweg pro Stunde über alle Sendungen hinweg gesendet werden
- **Fehler und Bounces** — Aufschlüsselung der fehlgeschlagenen Sendungen nach Fehlertyp und -ursache
- **Benutzeraktivitäten** - Öffnungen, Klicks und Abmeldungen in allen Kampagnen aggregiert

Weitere Informationen zu [globalen Berichten](../reporting/global-reports.md)

## Verwandte Themen {#related-topics}

- [Best Practices für den Versand](delivery-best-practices.md)
- [Quarantäneverwaltung](../send/quarantines.md)
- [Sendungen konfigurieren und durchführen](../send/configure-and-send.md)
- [Erste Schritte mit Berichten](../reporting/gs-reporting.md)

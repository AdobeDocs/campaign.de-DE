---
product: campaign
title: Überwachen der Zustellbarkeit in Adobe Campaign
description: Erfahren Sie mehr über Tools und Richtlinien zum Überwachen der Zustellbarkeit in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 56%

---

# Überwachen der Zustellbarkeit{#monitoring-deliverability}

Im Folgenden finden Sie Details zu den verschiedenen Monitoring-Tools, die Adobe Campaign zur Verfügung stellt, sowie einige zusätzliche Richtlinien zur Nutzung der von Adobe Campaign angebotenen Funktionen zur Überwachung der Zustellbarkeit Ihrer Plattform.

## Monitoring-Tools {#monitoring-tools}

Adobe Campaign bietet Ihnen Zugriff auf die unten aufgeführten Zustellbarkeits-Tools.

### Rendern des Posteingangs {#inbox-rendering-tool}

Der [Inbox Rendering-Bericht](inbox-rendering.md) ermöglicht die Vorschau Ihrer Nachrichten auf wichtigen E-Mail-Clients, um Inhalte zu überprüfen und die Reputation zu verbessern.

### Versanddurchsatz {#throughput-reports}

Der **[!UICONTROL Versanddurchsatz]**-Bericht bietet einen Überblick über den Durchsatz der gesamten Plattform für einen bestimmten Zeitraum. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](../reporting/global-reports.md#delivery-throughput).

### Broadcast-Statistiken {#broadcast-statistics}

Bei jedem Versand wird ein Bericht mit Versandstatistiken für die verschiedenen Internet-Dienstanbieter (ISPs) erstellt. Es werden verschiedene Datenqualitäts- und Reputationsmetriken angezeigt, die sich auf die Zustellbarkeit auswirken können, einschließlich der folgenden Zahlen:

**[!UICONTROL Hardbounces]** geben Auskunft über die Datenqualität. Diese Zahl sollte unter 2 % liegen.

**[!UICONTROL Softbounces]** geben Auskunft über die Reputation. Diese Zahl sollte bei keinem ISP über 10 % liegen.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Versand-Dashboard {#delivery-dashboard-monitoring}

Allgemein bietet Ihnen das [Versand-Dashboard](delivery-dashboard.md) Zugriff auf:

Die Versandzusammenfassung, die Details zum Versand und die Anzahl der erfolgreich zu sendenden, verarbeiteten und gesendeten Nachrichten anzeigt.

Die Versandlogs und der Versandverlauf, aus denen hervorgeht, welche Zielgruppe ausgeschlossen wurde und warum.

Die Trackinglogs, die Tracking-Informationen wie Öffnungen und Klicks anzeigen.

### SpamAssassin-Tests {#spam-testing}

Verwenden Sie [SpamAssassin](spamassassin.md), um Ihren E-Mail-Inhalt zu testen und eine Bewertung durchzuführen, um festzustellen, ob eine Nachricht von den Anti-Spam-Tools, die beim Empfang verwendet werden, möglicherweise als Spam eingestuft wird.

### Control Panel {#control-panel-monitoring}

>[!NOTE]
>
>Das Control Panel ist für Benutzende von Campaign v8 Managed Cloud Services verfügbar. Weitere Informationen über das [Control Panel](../config/self-service.md).

Das [Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de){target="_blank"} von Campaign bietet Überwachungsfunktionen für die Zustellbarkeit, einschließlich Subdomain- und Zertifikatverwaltung, Überwachung aktiver Profile sowie Metriken zu Versanddurchsatz und Latenz.

## Richtlinien für das Monitoring {#monitoring-guidelines}

Im Folgenden finden Sie einige zusätzliche Richtlinien zum Zustellbarkeits-Monitoring:

### Überwachung des Plattformdurchsatzes

Prüfen Sie regelmäßig den [Versanddurchsatz](../reporting/global-reports.md#delivery-throughput) für die gesamte Plattform, um festzustellen, ob er der ursprünglichen Einstellung entspricht.

### Konfiguration wiederholen

Achten Sie darauf, dass [weitere Zustellversuche](delivery-failures.md#retries) in den Versandvorlagen korrekt eingerichtet sind (30 Minuten für das Versuchsintervall und mehr als 20 weitere Versuche).

### Überprüfung des Bounce-Postfachs

Prüfen Sie regelmäßig, ob das [Bounce](delivery-failures.md#bounce-mail-qualification)-Postfach zugänglich ist, und sorgen Sie dafür, dass die Gültigkeit des Kontos nicht abläuft.

### Leistungsprüfungen beim Versand

Prüfen Sie, ob die einzelnen Versanddurchsätze (über das [ Versand-Dashboard](delivery-dashboard.md) abrufbar) der Gültigkeit des Versandinhalts entsprechen (&quot;Flash Sales&quot; zum Beispiel sollten innerhalb von Minuten, nicht von Tagen zugestellt werden).

### Validierung des zeitlichen Verlaufs einer Welle

Wenn der Versand in [Schüben](configure-and-send.md#sending-using-multiple-waves) erfolgt, stellen Sie sicher, dass genügend Zeit vorhanden ist, damit ein Schub fertiggestellt werden kann, bevor der nächste beginnt.

### Quarantäneüberwachung

Prüfen Sie, ob die Anzahl der Fehler und der neuen [Quarantänen](quarantines.md) der anderer Sendungen entspricht.

### Analyse des Versandlogs

Prüfen Sie in den [Versandlogs](delivery-dashboard.md#delivery-logs-and-history) sorgfältig die Art der hervorgehobenen Fehler (Blockierungsliste, DNS-Probleme, Anti-Spam-Regeln usw.).

## Verwandte Themen

[Adobe-Handbuch mit den Best Practices zur Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"} bietet umfassende Anleitungen zu Zustellbarkeitsstrategien, Definitionen, Metriken und Best Practices.

[Was ist Zustellbarkeit](about-deliverability.md) führt wichtige Konzepte zur Zustellbarkeit ein und zeigt, wie Sie Ihre Zustellbarkeitsrate in Campaign verbessern können.

[Versandfehler und Bounces](delivery-failures.md) beschreibt die verschiedenen Arten von Versandfehlern und erläutert, wie Campaign mit ihnen umgeht. Außerdem enthält er Anleitungen zur Fehlerbehebung bei häufigen Problemen.

[Quarantäneverwaltung](quarantines.md) erläutert, wie Campaign unter Quarantäne gestellte Adressen verwaltet, um Ihre Reputation als Versender zu schützen.

[Kontrollieren des Nachrichteninhalts](control-message-content.md) bietet Anleitungen, um sicherzustellen, dass Ihr Inhalt für die Zustellbarkeit optimiert ist.

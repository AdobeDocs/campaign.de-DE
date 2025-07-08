---
product: campaign
title: Überwachen der Zustellbarkeit in Adobe Campaign
description: Erfahren Sie mehr über Tools und Richtlinien zum Überwachen der Zustellbarkeit in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 67%

---

# Überwachen der Zustellbarkeit{#monitoring-deliverability}

Im Folgenden finden Sie Details zu den verschiedenen Monitoring-Tools, die Adobe Campaign zur Verfügung stellt, sowie einige zusätzliche Richtlinien zur Nutzung der von Adobe Campaign angebotenen Funktionen zur Überwachung der Zustellbarkeit Ihrer Plattform.

## Monitoring-Tools {#monitoring-tools}

Adobe Campaign bietet Ihnen Zugriff auf alle unten aufgeführten Zustellbarkeits-Tools.

* Der [Inbox Rendering-Bericht](inbox-rendering.md) ermöglicht die Vorschau Ihrer Nachrichten auf wichtigen E-Mail-Clients, um Inhalte zu überprüfen und die Reputation zu verbessern.

* Der **[!UICONTROL Versanddurchsatz]**-Bericht bietet einen Überblick über den Durchsatz der gesamten Plattform für einen bestimmten Zeitraum. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](../reporting/global-reports.md#delivery-throughput).
* Bei jedem Versand wird ein Bericht mit Versandstatistiken für die verschiedenen Internet-Dienstanbieter (ISPs) erstellt. Es werden verschiedene Datenqualitäts- und Reputationsmetriken angezeigt, die sich auf die Zustellbarkeit auswirken können, einschließlich der folgenden Zahlen:
   * **[!UICONTROL Hardbounces]** geben Auskunft über die Datenqualität. Diese Zahl sollte unter 2 % liegen.
   * **[!UICONTROL Softbounces]** geben Auskunft über die Reputation. Diese Zahl sollte bei keinem ISP über 10 % liegen.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* Allgemein bietet Ihnen das [Versand-Dashboard](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=de#sending-messages){target="_blank"} Zugriff auf:
   * die Versandzusammenfassung, die die Details des Versands und die Anzahl der zu sendenden, verarbeiteten und erfolgreich gesendeten Nachrichten anzeigt;
   * Versandlogs und -verlauf, aus denen hervorgeht, welche Zielgruppe aus welchem Grund ausgeschlossen wurde;
   * Die Trackinglogs, die Tracking-Informationen wie Öffnungen und Klicks anzeigen.

## Richtlinien für das Monitoring {#monitoring-guidelines}

Im Folgenden finden Sie einige zusätzliche Richtlinien zum Zustellbarkeits-Monitoring:

* Prüfen Sie regelmäßig den [Versanddurchsatz](../reporting/global-reports.md#delivery-throughput) für die gesamte Plattform, um festzustellen, ob er der ursprünglichen Einstellung entspricht.
* Achten Sie darauf, dass [weitere Zustellversuche](delivery-failures.md#retries) in den Versandvorlagen korrekt eingerichtet sind (30 Minuten für das Versuchsintervall und mehr als 20 weitere Versuche).
* Prüfen Sie regelmäßig, ob das [Bounce](delivery-failures.md#bounce-mail-qualification)-Postfach zugänglich ist, und sorgen Sie dafür, dass die Gültigkeit des Kontos nicht abläuft.
* Überprüfen Sie jeden Versanddurchsatz, auf den über das [Versand-Dashboard](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=de#sending-messages){target="_blank"} zugegriffen werden kann, um sicherzustellen, dass er mit der Gültigkeit des Versandinhalts übereinstimmt (z. B. sollten „Flash-Verkäufe“ in Minuten statt in Tagen bereitgestellt werden). ist ein wichtiges Tool, mit dem Sie Sendungen und potenzielle Probleme beim Nachrichtenversand überwachen können.
* Wenn der Versand in [Schüben](configure-and-send.md#sending-using-multiple-waves) erfolgt, stellen Sie sicher, dass genügend Zeit vorhanden ist, damit ein Schub fertiggestellt werden kann, bevor der nächste beginnt.
* Prüfen Sie, ob die Anzahl der Fehler und der neuen [Quarantänen](quarantines.md) der anderer Sendungen entspricht.
* Prüfen Sie in den [Versandlogs](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=de#delivery-logs-and-history){target="_blank"} sorgfältig die Art der hervorgehobenen Fehler (Blockierungsliste, DNS-Probleme, Anti-Spam-Regeln usw.).

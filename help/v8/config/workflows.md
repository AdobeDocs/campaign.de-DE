---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit der Automatisierung von Kampagnen
description: Erste Schritte mit der Automatisierung von Kampagnen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 2%

---

# Prozesse verwalten und automatisieren

Konfigurieren Sie die Kampagne, um leistungsstarke Automatisierungsfunktionen für Marketing-Kampagnen zu nutzen.

Sie können Folgendes einrichten:

* Workflows
* Wiederkehrende Kampagnen
* End-to-End-Validierungszyklus
* Warnhinweise
* Automatisches Senden von Berichten
* Ausgelöste Ereignis

## Entwerfen und Verwenden von Workflows{#gs-ac-wf}

Verwenden Sie Adobe Campaign Workflows, um die Geschwindigkeit und das Ausmaß Ihrer Marketing-Kampagnen zu verbessern, von der Erstellung von Segmenten über die Vorbereitung von Nachrichten bis hin zum Versand.

Weitere Informationen zu Workflows finden Sie in den folgenden Abschnitten:

* [Erste Schritte mit Worflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Workflow-Aktivitäten
   * [Targeting von Aktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html): Abfrage, Lesen von Liste, Anreicherung, Vereinigung und mehr
   * [Aktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) zur Flusssteuerung: Planung, Gabel, Alarm, externe Signale und mehr
   * [Aktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) der Aktion: Kanal-Versand, JavaScript-Code, CRM-Aktivitäten, Aggregat aktualisieren und mehr
   * [Ereignis-Aktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): Dateiübertragung, Web-Download und mehr
* [Lernen Sie die durchgängigen Anwendungsfälle kennen.](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [Erstellen einer Audience im Arbeitsablauf einer Marketing-Kampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [Best Practices bei Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [Integrierte technische Arbeitsabläufe](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## Einrichten wiederkehrender Kampagnen

Entwerfen Sie bei jeder Ausführung eine wiederkehrende Versand-Instanz und erstellen Sie sie. Wenn Ihr Workflow beispielsweise einmal pro Woche ausgeführt werden soll, würde dies nach einem Jahr zu 52 Versänden führen. Das bedeutet auch, dass die Protokolle durch jede Instanz des Versands getrennt werden.

:arrow_upper_right: Erfahren Sie, wie Sie eine wiederkehrende Kampagne in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns) erstellen.

## Konfigurieren des gesamten Überprüfungszyklus

Richten Sie den Genehmigungsprozess für jeden Schritt Ihrer Versand ein und sorgen Sie für eine vollständige Überwachung und Kontrolle der verschiedenen Prozesse Ihrer Marketing-Kampagnen: Targeting, Inhalt, Budget, Extraktion und Senden eines Testversands.

An die als Prüfer festgelegten Adobe Campaign-Operatoren werden Benachrichtigungen gesendet, um sie über eine Genehmigungsanfrage zu informieren.

:arrow_upper_right: Erfahren Sie, wie Sie den Genehmigungsprozess in [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html) einrichten und verwalten.


## Warnungen senden

Als Operator für Kampagne können Sie Warnungen erhalten, wenn ein Fehler auftritt.

Sie können einen Workflow erstellen, mit dem Sie den Status einer Reihe von Workflows überwachen und wiederkehrende Meldungen an die Aufsichtsbehörden senden können.

:arrow_upper_right: Erfahren Sie, wie Sie einen Arbeitsablauf zur Statusüberwachung anderer Workflows in [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow) erstellen.

Sie können auch eine Warnung erhalten, wenn ein Fehler auftritt

## Automatische Berichte senden

:arrow_upper_right: Erfahren Sie, wie Sie automatisch einen Bericht an eine Liste von Operatoren [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list) senden.


## Trigger-Ereignis nutzen

Verwenden Sie Kampagne Transactional Messaging, um Meldungen zu automatisieren, die aus Ereignissen generiert wurden, die aus Informationssystemen ausgelöst wurden. Diese Transaktionsnachrichten können z.B. in Rechnung, Auftragsbestätigung, Versandbestätigung, Passwortänderung, Produktersatzbenachrichtigung, Kontoauszug oder Website-Kontoerstellung bestehen. Diese Nachrichten können einzeln oder stapelweise per E-Mail, SMS oder Push-Benachrichtigung gesendet werden)ionen.

:arrow_upper_right: Weitere Informationen zu Transaktionsnachrichten finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging).


Verbinden Sie Adobe Campaign und Adobe Analytics, um Benutzeraktionen abzurufen und nahezu personalisierte Nachrichten in Echtzeit zu senden.

:arrow_upper_right: Erfahren Sie, wie Sie Kampagne mit Analytics-Triggern in [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud) integrieren.

:bulb: In [diesem Abschnitt ](../start/connect.md) erfahren Sie, wie Sie Kampagne in andere Lösungen integrieren.

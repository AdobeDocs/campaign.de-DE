---
product: Adobe Campaign
title: Verwalten und Automatisieren von Prozessen mit Adobe Campaign-Workflows
description: Erste Schritte mit Workflows
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Prozesse verwalten und automatisieren

Konfigurieren Sie Campaign, um leistungsstarke Automatisierungsfunktionen für Marketing-Kampagnen zu nutzen.

Sie können Folgendes einrichten:

* Workflows
* Wiederkehrende Kampagnen
* End-to-End-Validierungszyklus
* Warnhinweise
* Automatisches Senden von Berichten
* Erzeugte Ereignisse

## Entwerfen und Verwenden von Workflows{#gs-ac-wf}

Verwenden Sie Adobe Campaign-Workflows, um jeden Aspekt Ihrer Marketing-Kampagnen zu beschleunigen und zu skalieren – von der Erstellung von Segmenten über die Vorbereitung von Nachrichten bis hin zum Versand.

Erfahren Sie durch diese [End-to-End-Anwendungsfälle](#end-to-end-uc), wie Sie Workflows erstellen.

Weitere Informationen zur Benutzeroberfläche und Ausführung von Workflows finden Sie in der Dokumentation zu Campaign Classic v7:

[!DNL :arrow_upper_right:]  [Erste Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}
* Workflow-Aktivitäten:
   * [Zielgruppenbestimmungsaktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html?lang=de){target=&quot;_blank&quot;}: Abfrage, Liste lesen, Anreicherung, Vereinigung und mehr
   * [Steuerungsaktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html?lang=de){target=&quot;_blank&quot;}: Planung, Verzweigung, Warnhinweis, externes Signal und mehr
   * [Aktionsaktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html?lang=de){target=&quot;_blank&quot;}: Kanalübergreifende Sendungen, JavaScript-Code, CRM-Aktivitäten, Aggregat-Update und mehr
   * [Ereignisaktivitäten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target=&quot;_blank&quot;}: Dateiübertragung, HTTP-Übertragung und mehr
      [!DNL :arrow_upper_right:]  [Eine Audience im Workflow einer Marketing-Kampagne erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=de#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}
      [!DNL :arrow_upper_right:]  [Best Practices bei Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html?lang=de){target=&quot;_blank&quot;}
      [!DNL :arrow_upper_right:] [Native technische Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=de){target=&quot;_blank&quot;}
      [!DNL :arrow_upper_right:] [Ausführung von Workflows überwachen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=de){target=&quot;_blank&quot;}


## Einrichten wiederkehrender Kampagnen

Entwerfen Sie einen wiederkehrenden Workflow und erstellen Sie bei jeder Workflow-Ausführung eine neue Versandinstanz. Wenn der Workflow beispielsweise einmal pro Woche ausgeführt werden soll, führt dies nach einem Jahr zu 52 Sendungen. Das bedeutet auch, dass die Protokolle für jede Versandinstanz getrennt erstellt werden.

[!DNL :arrow_upper_right:] Wie Sie eine wiederkehrende Kampagne erstellen, erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=de#recurring-and-periodic-campaigns){target=&quot;_blank&quot;}.


## Erzeugte Ereignisse nutzen

Verwenden Sie Transaktionsnachrichten in Campaign, um Nachrichten zu automatisieren, die von durch Informationssysteme ausgelösten Ereignissen generiert werden. Diese Transaktionsnachrichten können z. B. Rechnungen, Auftragsbestätigungen, Versandbestätigungen, Passwortänderungen, Benachrichtigungen über die Nichtverfügbarkeit von Produkten, Kontoauszüge oder die Erstellung von Website-Konten sein. Diese Nachrichten können einzeln oder in Batches per E-Mail, SMS oder Push-Benachrichtigungen gesendet werden.

[!DNL :bulb:] Weitere Informationen zu den Funktionen von Transaktionsnachrichten finden Sie in [diesem Abschnitt](../send/transactional.md).

Verbinden Sie Adobe Campaign und Adobe Analytics, um Benutzeraktionen abzurufen und nahezu in Echtzeit personalisierte Nachrichten zu versenden.

[!DNL :bulb:] In [diesem Abschnitt](../start/connect.md) erfahren Sie, wie Sie Campaign mit anderen Lösungen integrieren.


## Anwendungsfälle von Workflows{#end-to-end-uc}

In diesem Abschnitt finden Sie verschiedene Anwendungsfälle, die Funktionen von Campaign-Workflows nutzen. Diese Anwendungsfälle wurden in Adobe Campaign Classic v7 erstellt und gelten für Adobe Campaign v8.

### Sendungen {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B-Tests](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=de){target=&quot;_blank&quot;}

   Hier erfahren Sie, wie Sie mithilfe eines Zielgruppen-Workflows zwei E-Mail-Versandinhalte vergleichen. Nachricht und Text sind bei beiden Sendungen identisch – nur das Layout ist unterschiedlich. Die Zielpopulation wird in drei Gruppen aufgeteilt: zwei Testgruppen und die restliche Population. An jede Testgruppe wird eine andere Version des Versands gesendet.

* [Senden einer Geburtstags-E-Mail](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=de){target=&quot;_blank&quot;}

   Im folgenden Anwendungsbeispiel wird aufgezeigt, wie sich der wiederkehrende Versand einer E-Mail an Empfänger zu deren Geburtstag planen lässt.

* [Laden des Versandinhalts](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html?lang=de){target=&quot;_blank&quot;}
Wenn Ihr Versandinhalt in einer auf einem Remote-Server gespeicherten HTML-Datei verfügbar ist, können Sie diesen Inhalt einfach in Adobe Campaign-Sendungen laden.

* [Workflow für einen kanalübergreifenden Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie einen Workflow für einen kanalübergreifenden Versand erstellen. Ziel ist es, eine Audience von den Empfängern in Ihrer Datenbank in verschiedene Gruppen zu unterteilen und der einen Gruppe eine E-Mail und der anderen eine SMS zu senden.

* [E-Mail-Anreicherung mit benutzerdefinierten Datumsfeldern](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie eine E-Mail mit benutzerdefinierten Datenfeldern an Profile senden, die in diesem Monat Geburtstag feiern. Die E-Mail enthält einen Gutschein, der eine Woche vor bis eine Woche nach dem Geburtstag gültig ist.

* [Automatisieren der Inhaltserstellung, -bearbeitung und -veröffentlichung](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie die Erstellung und den Versand eines Inhaltsbausteins mit dem Add-on Campaign Content Management automatisieren.


### Monitoring {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Senden eines Berichts an eine Liste](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=de){target=&quot;_blank&quot;}

   Hier erfahren Sie, wie Sie einen monatlichen integrierten Bericht zu Tracking-Indikatoren im PDF-Format generieren und an eine Liste von Campaign-Benutzern senden.

* [Überwachen Ihrer Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie einen Workflow erstellen, mit dem Sie den Status einer Reihe von Workflows überwachen können, die &quot;ausgesetzt&quot;, &quot;angehalten&quot; oder &quot;fehlerhaft&quot; sind.

* [Senden personalisierter Warnungen an Benutzer](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie einem Benutzer einen Hinweis senden, der den Namen der Profile enthält, die einen Newsletter geöffnet, aber nicht auf den darin enthaltenen Link geklickt haben.

### Daten-Management {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Koordinieren von Datenaktualisierungen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie überprüfen können, ob der Aktualisierungsprozess beendet wurde, bevor Sie einen weiteren Aktualisierungsvorgang ausführen. Zu diesem Zweck richten wir eine Instanzvariable ein und lassen den Workflow testen, ob die Instanz ausgeführt wird, um zu entscheiden, ob die Ausführung des Workflows fortgesetzt und die Aktualisierung durchgeführt werden soll.

* [Erstellen einer zusammenfassenden Liste](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie einen Workflow erstellen, mit dem Sie nach dem Erfassen von Dateien und mehreren Anreicherungen eine zusammenfassende Liste erstellen können. Das Beispiel basiert auf einer Liste von Kontakten, die in einem Geschäft Einkäufe getätigt haben.

* [Anreichern von Daten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie personalisierte Sendungen an Profile senden, die am letzten Wettbewerb teilgenommen haben, abhängig von der erzielten Punktzahl.

* [Verwenden von Aggregaten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie die letzten zur Datenbank hinzugefügten Empfänger identifizieren.

* [Vierteljährliches Listen-Update mithilfe einer inkrementellen Abfrage](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie über eine inkrementelle Abfrage automatisch eine Empfängerliste aktualisieren können.

* [Einrichten eines Workflows für den wiederkehrenden Import](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie ein Workflow für den wiederholten Import von Profilen aus einer CRM-Lösung in der Adobe Campaign-Datenbank erstellt wird.

### Zielgruppenbestimmung {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Empfängertabelle abfragen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie die Namen und E-Mails der Empfänger abrufen können, deren E-Mail-Domain &quot;orange.co.uk&quot; lautet und die nicht in London leben.

* [Informationen zum Abfrageversand](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie Abfragen zu Versandinformationen definieren, um das Verhalten des Profils abzurufen.

* [Berechnen von Aggregaten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie die Anzahl der in London lebenden Profile nach Geschlecht zählen.

* [Abfrage mit einer n:n-Beziehung](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html?lang=de){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie Profile finden, die in den letzten sieben Tagen nicht kontaktiert wurden.

* [Aufrufen von Instanzvariablen in Abfragen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=de#example){target=&quot;_blank&quot;}

   Erfahren Sie, wie Sie den auf eine Population anzuwendenden Aufspaltungs-Prozentsatz mithilfe einer Instanzvariablen dynamisch berechnen können.


---
product: campaign
title: Sendungen für eine Marketing-Kampagne
description: Erfahren Sie mehr über Sendungen zur Marketing-Kampagne
feature: Campaigns, Resource Management, Cross Channel Orchestration
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1d9638cb-0fc9-4d04-a9c5-bcab8f4ebe95
TQID: https://experienceleague.adobe.com/2qo8UUeTbMxMJse13-8HOB0dJXoSk0AKpNJamGTaqxs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 755
ht-degree: 88%

---

# Sendungen für eine Marketing-Kampagne {#marketing-campaign-deliveries}

Orchestrieren Sie Ihre kanalübergreifenden Sendungen in Ihren Kampagnen: Optimieren Sie mit Adobe Campaign Ihre Kommunikation durch personalisierte E-Mails, SMS, Push-Benachrichtigungen und In-App-Nachrichten. Sie können Rich Media wie Videos, Emojis oder GIFs verwenden und direkt integrieren.

Sendungen können über das Dashboard einer Kampagne, einen Kampagnen-Workflow oder direkt über die Übersicht der Sendungen erstellt werden. Wenn Sendungen aus einer Kampagne erstellt werden, werden sie mit dieser Kampagne verknüpft und auf der Kampagnenebene konsolidiert.

## Erstellen von Sendungen {#create-deliveries}

Sie haben zwei Möglichkeiten, Sendungen zu Ihren Marketing-Kampagnen hinzuzufügen:

* Über den Link **[!UICONTROL Versand hinzufügen]** im Kampagnen-Dashboard.

  ![](assets/campaign_op_add_delivery.png)

  Nach der Speicherung wird der Versand zum Kampagnen-Dashboard hinzugefügt.

* Über einen Kampagnen-Workflow auf der Registerkarte **[!UICONTROL Zielgruppenbestimmungen und Workflows]** durch Hinzufügen des Versands.

  ![](assets/campaign-wf-delivery.png)

  Nach dem Start des Workflows wird der Versand zum Kampagnen-Dashboard hinzugefügt.

Informationen darüber, wie Sie die Versandvalidierung einrichten und ausführen, finden Sie [auf dieser Seite](marketing-campaign-approval.md).

## Starten eines Versands {#start-a-delivery}

Ein Versand kann durchgeführt werden, sobald alle Validierungen erteilt wurden. Der Ausführungsprozess des Versands hängt vom Kanal ab.

* Informationen zu Sendungen per E-Mail oder über einen mobilen Kanal finden Sie in [diesem Abschnitt](#start-an-online-delivery)

* Informationen zu Briefpost-Sendungen finden Sie in [diesem Abschnitt](#start-an-offline-delivery).

### Starten eines E-Mail- oder Mobile-Versands {#start-an-online-delivery}

Sobald alle Validierungsanfragen bestätigt wurden, erhält der Versand den Status **[!UICONTROL Bestätigung ausstehend]** und kann gestartet werden. Validierungsverantwortliche, die den Versand starten können, werden darüber informiert, dass ein Versand startbereit ist.

![](assets/confirm-delivery.png)

Die Informationen werden auch auf dem Kampagnen-Dashboard angezeigt. Der Link **[!UICONTROL Absendung bestätigen]** ermöglicht es, den Versand zu beginnen.

![](assets/confirm-delivery-from-dashboard.png)

Die Validierung des Versands ist auf Administratoren sowie auf Benutzende oder Benutzergruppen beschränkt, die in den Versand- oder Kampagneneigenschaften ausdrücklich genannt werden. Wenn keine Benutzenden erstellt wurden, können Administratoren und der Kampagnenverantwortliche die Validierung vornehmen.

![](assets/select-delivery-reviewers.png)

Sie können jedoch auch zulassen, dass der/die Kampagnenverantwortliche den Versand bestätigt, selbst wenn in den Versand- oder Kampagneneigenschaften spezifische Validierungsverantwortliche definiert wurden. Erstellen Sie dazu als Administrator die Option **NmsCampaign_Activate_OwnerConfirmation** und legen Sie sie auf **1** fest. Die Verwaltung der Optionen erfolgt über den Ordner **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]** im Campaign-Explorer.


### Starten eines Briefpostversands {#start-an-offline-delivery}

Sobald alle Validierungen erteilt wurden, ändert sich der Versandstatus in **[!UICONTROL Extraktion ausstehend]**. Die Extraktionsdateien werden über einen speziellen [technischen Workflow](../workflow/technical-workflows.md) erstellt, der in einer Standardkonfiguration automatisch gestartet wird, wenn bei einem Briefpostversand die Extraktion ausstehend ist. Wenn ein Prozess in Bearbeitung ist, wird er im Dashboard angezeigt und kann über seinen Link bearbeitet werden.

Wenn der Extraktions-Workflow korrekt ausgeführt wurde, muss die Extrationsdatei validiert werden (sofern die Validierung der Extraktionsdatei in der Versandkonfiguration aktiviert wurde). [Weitere Informationen](marketing-campaign-approval.md#approving-an-extraction-file).

Gehen Sie wie folgt vor, um den Inhalt zu validieren und die Datei an den Provider zu senden:

1. Nachdem die Extraktionsdatei validiert wurde, können Sie den Testversand der Benachrichtigungs-E-Mail für den Router generieren. Diese E-Mail-Nachricht basiert auf einer Versandvorlage. Sie muss genehmigt werden.

   Dieser Schritt ist nur verfügbar, wenn die Option **[!UICONTROL Testversandvalidierung aktivieren aktivieren (Briefpost)]** auf der Registerkarte **[!UICONTROL Genehmigungen]** der erweiterten Kampagnenparameter aktiviert wurde.

   ![](assets/enable-proof-validation.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Testversand]**, um Testsendungen zu erstellen.

   Zunächst muss die Zielgruppe der Testsendungen bestimmt werden.

   Sie können so viele Testsendungen wie nötig erstellen. Über den Link **[!UICONTROL Briefpost…]** der Versanddetails können Sie auf sie zugreifen.

1. Der Versandstatus ändert sich zu **[!UICONTROL Zu unterbreiten]**. Klicken Sie auf die Schaltfläche **[!UICONTROL Testsendungen unterbreiten]**, um den Validierungsprozess zu beginnen.

1. Der Versandstatus wird daraufhin zu **[!UICONTROL Testversand zu validieren]**. Über die entsprechende Schaltfläche kann die Validierung erfolgen.

   Im Validierungs-Pop-up können Sie die Validierung akzeptieren oder ablehnen oder zur Extraktionsetappe zurückkehren.

1. Sobald der Testversand validiert wurde, wird die Extraktionsdatei an den Router gesendet und der Versand ist abgeschlossen.

### Budget- und Kostenberechnung {#compute-costs-and-stocks}

Die Dateiextraktion startet zwei Prozesse: Budgetberechnung und Bestandsberechnung. Die Budgeteinträge werden aktualisiert.

* Die Registerkarte **[!UICONTROL Budget]** ermöglicht die Budgetverwaltung der Kampagne. Die Summe der Kosteneinträge wird im Feld **[!UICONTROL Berechnete Kosten]** der Hauptregisterkarte der Kampagne und des Programms, zu dem sie gehört, angezeigt. Die Beträge werden auch im Kampagnenbudget angezeigt.

  ![](assets/campaign-budget-tab.png)

  Die tatsächlichen Kosten werden letztendlich anhand der vom Router gelieferten Informationen berechnet. Nur tatsächlich gesendete Nachrichten werden fakturiert.

* Die Lagerbestände werden im Knoten **[!UICONTROL Administration > Kampagnenverwaltung > Lager]** des Baums definiert.

  ![](assets/campaign-stocks.png)

  Kostenstrukturen im Knoten **[!UICONTROL Administration > Kampagnenverwaltung > Dienstleister]**.

  ![](assets/campaign-service-providers.png)

  Lagerpositionen werden im Lagerteil angezeigt. Um den Anfangsbestand zu definieren, öffnen Sie eine Lagerposition. Der Bestand verringert sich mit jedem Versand. Sie können eine Warnstufe und Benachrichtigungen definieren.


  >[!NOTE]
  >
  >Weitere Informationen über Budgets finden Sie [in diesem Abschnitt](providers-stocks-and-budgets.md).

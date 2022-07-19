---
product: campaign
title: Sendungen für eine Marketing-Kampagne
description: Erfahren Sie mehr über Sendungen zur Marketing-Kampagne
feature: Campaigns, Resource Management, Cross Channel Orchestration
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 35%

---

# Sendungen für eine Marketing-Kampagne {#marketing-campaign-deliveries}

Organisieren Sie Ihre kanalübergreifenden Sendungen in Ihren Kampagnen: Optimierung der Kommunikation mit Adobe Campaign durch personalisierte E-Mails, SMS, Push-Benachrichtigungen und In-App-Nachrichten. Sie können Rich Media wie Videos, Emojis oder GIF verwenden und direkt integrieren.

Sendungen können über das Dashboard einer Kampagne, einen Kampagnen-Workflow oder direkt über die Übersicht der Sendungen erstellt werden. Wenn Sendungen aus einer Kampagne erstellt werden, werden sie mit dieser Kampagne verknüpft und auf der Kampagnenebene konsolidiert.

## Erstellen von Sendungen {#create-deliveries}

Sie haben zwei Möglichkeiten, Sendungen zu Ihren Marketing-Kampagnen hinzuzufügen:

* Aus dem **[!UICONTROL Versand hinzufügen]** im Kampagnen-Dashboard.

![](assets/campaign_op_add_delivery.png)

Nach der Speicherung wird der Versand zum Kampagnen-Dashboard hinzugefügt.

* Über einen Kampagnen-Workflow im **[!UICONTROL Zielbestimmungen und Workflows]** durch Hinzufügen des Versands.

   ![](assets/campaign-wf-delivery.png)

   Nach dem Start des Workflows wird der Versand zum Kampagnen-Dashboard hinzugefügt.

Erfahren Sie, wie Sie den Ablauf der Versandvalidierung einrichten und ausführen [auf dieser Seite](marketing-campaign-approval.md).

## Starten eines Versands {#start-a-delivery}

Ein Versand kann durchgeführt werden, sobald alle Validierungen erteilt wurden. Der Ausführungsprozess des Versands hängt vom Kanal ab.

* E-Mail- oder Mobile-Kanal-Sendungen, siehe [diesem Abschnitt](#start-an-online-delivery)

* Briefpost-Sendungen, siehe [diesem Abschnitt](#start-an-offline-delivery)

### E-Mail- oder Mobile-Versand starten {#start-an-online-delivery}

Sobald alle Validierungsanfragen akzeptiert wurden, erhält der Versandstatus folgende Fassung: **[!UICONTROL Ausstehende Bestätigung]** und gestartet werden. Validierungsverantwortliche, die den Versand starten können, werden darüber informiert, dass ein Versand startbereit ist.

![](assets/confirm-delivery.png)

Diese Information wird ebenfalls im Dashboard der Kampagne angezeigt. Über den Link **[!UICONTROL Versand bestätigen]** kann der Versand gestartet werden.

![](assets/confirm-delivery-from-dashboard.png)

Die Validierung des Versands ist auf Administratoren sowie auf Benutzer oder Benutzergruppen beschränkt, die in den Versand- oder Kampagneneigenschaften ausdrücklich erwähnt werden. Wenn kein Benutzer erstellt wurde, können Administratoren und der Kampagneninhaber die Validierung vornehmen.

![](assets/select-delivery-reviewers.png)

Sie können jedoch auch zulassen, dass der Kampagneninhaber den Versand bestätigt, selbst wenn in den Versand- oder Kampagneneigenschaften spezifische Validierungsverantwortliche definiert wurden. Erstellen Sie dazu als Administrator die **NmsCampaign_Activate_OwnerConfirmation** und legen Sie sie auf **1**. Die Verwaltung der Optionen erfolgt über die **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]** -Knoten im Adobe Campaign-Explorer.


### Briefpost-Versand starten {#start-an-offline-delivery}

Sobald alle Genehmigungen erteilt wurden, ändert sich der Versandstatus in **[!UICONTROL Ausstehende Extraktion]**. Die Extraktionsdateien werden über eine dedizierte [technischer Workflow](../workflow/technical-workflows.md) in einer Standardkonfiguration automatisch gestartet wird, wenn ein Briefpost-Versand auf Extraktion wartet. Wenn ein Prozess ausgeführt wird, wird er im Dashboard angezeigt und kann über seinen Link bearbeitet werden.

Wenn der Extraktions-Workflow korrekt ausgeführt wurde, muss die Extrationsdatei validiert werden (sofern die Validierung der Extraktionsdatei in der Versandkonfiguration aktiviert wurde). [Weitere Informationen](marketing-campaign-approval.md#approving-an-extraction-file).

Gehen Sie wie folgt vor, um den Inhalt zu validieren und die Datei an den Provider zu senden:

1. Nachdem die Extraktionsdatei validiert wurde, kann der Testversand der Benachrichtigungs-E-Mail an den Router erzeugt werden. Diese E-Mail wird auf der Grundlage einer Versandvorlage erstellt und muss validiert werden.

   Dieser Schritt ist nur verfügbar, wenn die Variable **[!UICONTROL Versand und Validierung von Testsendungen aktivieren (Briefpost)]** -Option aktiviert in **[!UICONTROL Genehmigungen]** der erweiterten Kampagnenparameter.

   ![](assets/enable-proof-validation.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Testversand]**, um Testsendungen zu erstellen.

   Zunächst muss die Zielgruppe der Testsendungen bestimmt werden.

   Sie können so viele Testsendungen erstellen wie nötig. Auf die durchgeführten Testsendungen besteht Zugriff über den Link **[!UICONTROL Briefpost...]** in den Versanddetails.

1. Der Versand erhält nun den Status **[!UICONTROL Zu unterbreiten]**. Klicken Sie auf die Schaltfläche **[!UICONTROL Testsendungen unterbreiten]** um den Validierungsprozess zu starten.

1. Der Versandstatus wird daraufhin zu **[!UICONTROL Testversand zu validieren]**. Über die entsprechende Schaltfläche kann die Validierung erfolgen.

   Im Validierungs-Pop-up können Sie die Validierung akzeptieren oder ablehnen oder zur Extraktionsetappe zurückkehren.

1. Sobald der Testversand validiert wurde, wird die Extraktionsdatei an den Router gesendet und der Versand ist abgeschlossen.

### Budget- und Kostenberechnung {#compute-costs-and-stocks}

Die Dateiextraktion startet zwei Prozesse: Budgetberechnung und Bestandsberechnung. Die Budgeteinträge werden aktualisiert.

* Die **[!UICONTROL Budget]** -Tab ermöglicht die Budgetverwaltung der Kampagne. Die Summe der Kosteneinträge wird im Abschnitt **[!UICONTROL Berechnete Kosten]** -Feld des Haupttabs der Kampagne und des Programms, zu dem sie gehört. Die Beträge werden auch im Kampagnenbudget angezeigt.

   ![](assets/campaign-budget-tab.png)

   Die tatsächlichen Kosten werden am Ende entsprechend der vom Router kommunizierten Informationen berechnet: Nur die tatsächlich versendeten Briefe werden fakturiert.

* Die Lagerbestände werden im Abschnitt **[!UICONTROL Administration > Kampagnenverwaltung > Lager]** Knoten des Baums.

   ![](assets/campaign-stocks.png)

   Kostenstrukturen in der **[!UICONTROL Administration > Kampagnenverwaltung > Dienstleister]** Knoten.

   ![](assets/campaign-service-providers.png)

   Lagerpositionen können auf Ebene der Lager angezeigt werden. Öffnen Sie eine Lagerposition, um den Anfangsbestand festzulegen. Der Bestand wird mit jedem Versand dekrementiert. Sie haben die Möglichkeit, einen Meldebestand mit Benachrichtigungen zu konfigurieren.


   >[!NOTE]
   >
   >Weitere Informationen zu Budgets [in diesem Abschnitt](providers--stocks-and-budgets.md).

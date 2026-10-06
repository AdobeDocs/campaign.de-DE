---
product: campaign
title: Laden des Versandinhalts
description: Laden des Versandinhalts
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 08febcbc-1703-4d36-89e1-32c903618084
TQID: 'https://experienceleague.adobe.com/iTopl-qZwqJdSMV-ZiJ3ymveNdCsAb8IR-SXQmt9VhI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 100%
---
# Laden des Versandinhalts{#loading-delivery-content}

Wenn Ihr Versandinhalt in einer auf einem Amazon-S3-, FTP- oder SFTP-Server gespeicherten HTML-Datei verfügbar ist, können Sie diesen Inhalt einfach in Adobe Campaign-Sendungen laden.

Gehen Sie dazu wie folgt vor:

1. Wenn Sie die Verbindung zwischen Adobe Campaign und dem (S)FTP-Server, auf dem sich die Inhaltsdateien befinden, noch nicht definiert haben, erstellen Sie ein neues S3-, FTP- oder externes SFTP-Konto in **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Externe Konten]**. Geben Sie in diesem externen Konto die Adresse und die Anmeldedaten für die Verbindungsherstellung zum S3- oder (S)FTP-Server an.

   Hier ist ein Beispiel eines externen S3-Kontos:

   ![](assets/delivery_loadcontent_filetransfertexamples3.png)

1. Erstellen Sie einen neuen Workflow, beispielsweise in **[!UICONTROL Profile und Zielgruppen]** > **[!UICONTROL Aufträge]** > **[!UICONTROL Zielgruppen-Workflow]**.
1. Fügen Sie Ihrem Workflow die Aktivität **[!UICONTROL Dateiübertragung]** hinzu und konfigurieren Sie sie durch folgende Angaben:

   * das zu verwendende externe Konto für die Verbindung mit dem S3- oder (S)FTP-Server.
   * den Pfad der Datei auf dem S3- oder (S)FTP-Server.

   ![](assets/delivery_loadcontent_filetransfertexample.png)

1. Fügen Sie eine Aktivität **[!UICONTROL Versand]** hinzu und verbinden Sie sie mit der ausgehenden Transition der Aktivität **[!UICONTROL Dateiübertragung]**. Konfigurieren Sie wie folgt:

   * Versand: nach Bedarf entweder ein bestimmter im System vorhandener Versand oder ein neuer Versand auf der Basis einer vorhandenen Vorlage.
   * Empfänger: In diesem Beispiel wurde die Zielgruppe im Versand selbst festgelegt.
   * Inhalt: Selbst wenn der Inhalt in der vorherigen Aktivität importiert wurde, wählen Sie **[!UICONTROL Im Versand angegeben]** aus. Da der Inhalt direkt aus einer auf einem Remote-Server gespeicherten Datei importiert wird, besitzt er keine Kennung, wenn er vom Workflow verarbeitet wird, und kann nicht als vom Eingangsereignis stammend identifiziert werden.
   * Auszuführende Aktion: Wählen Sie **[!UICONTROL Speichern]**, um den Versand zu speichern und darauf über **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Sendungen]** zugreifen zu können, wenn der Workflow ausgeführt wird.

   ![](assets/delivery_loadcontent_activityexample.png)

1. Fügen Sie in der Aktivität **[!UICONTROL Versand]** im Tab **[!UICONTROL Script]** den folgenden Befehl hinzu, um den Inhalt der importierten Datei in den Versand zu laden:

   ```
   delivery.content.html.source=loadFile(vars.filename)
   ```

   ![](assets/delivery_loadcontent_script.png)

1. Speichern und starten Sie den Workflow. Unter **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Sendungen]** wird ein neuer Versand mit dem geladenen Inhalt erstellt.


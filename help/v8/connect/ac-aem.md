---
title: Arbeiten mit Campaign und Adobe Experience Manager
description: Erfahren Sie, wie Sie Campaign und Adobe Experience Manager gemeinsam verwenden können
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 90%

---

# Arbeiten mit Campaign und Adobe Experience Manager {#ac-aem}

Die Integration von Adobe Campaign und Adobe Experience Manager ermöglicht es Ihnen, den Inhalt von E-Mail-Sendungen sowie von Formularen direkt in Adobe Experience Manager zu verwalten. Sie haben die Möglichkeit, entweder Ihre **Adobe Experience Manager**-Inhalte in Campaign zu importieren oder eine Verbindung mit Ihrem **Adobe Experience Manager as a Cloud Service**-Konto herzustellen, wodurch Sie Inhalte direkt in der Web-Oberfläche bearbeiten können.

[Erfahren Sie, wie Sie in der Campaign-Weboberfläche Adobe Experience Manager als Cloud Service bearbeiten](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html){target="_blank"}.

[Weitere Informationen zu Adobe Experience Manager finden Sie in diesem Dokument .](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=de#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Als Benutzer von Managed Cloud Service [Adobe kontaktieren](../start/campaign-faq.md#support) zur Integration von Adobe Experience Manager in Campaign.

## Importieren von Inhalten aus Adobe Experience Manager {#integrating-with-aem}

Mit dieser Integration kann beispielsweise ein Newsletter in Adobe Experience Manager erstellt werden, der danach in Adobe Campaign als Teil einer E-Mail-Kampagne verwendet wird.

**In Adobe Experience Manager:**

1. Navigieren Sie zu Ihrer [!DNL Adobe Experience Manager]-Autoreninstanz und klicken Sie oben links auf der Seite auf „Adobe Experience“. Wählen Sie **[!UICONTROL Sites]** im Menü.

   ![](assets/aem_authoring_1.png)

1. Navigieren Sie zu **[!UICONTROL Kampagnen > Name Ihres Unternehmens (hier we.Shopping) > Hauptbereich > E-Mail]**.

1. Klicken Sie auf **[!UICONTROL Erstellen]** und wählen Sie **[!UICONTROL Seite]** im Dropdown-Menü aus.

   ![](assets/aem_authoring_2.png)

1. Wählen Sie die Vorlage **[!UICONTROL Adobe Campaign-E-Mail]** aus und benennen Sie Ihren Newsletter.

1. Öffnen Sie nach der Erstellung Ihrer Seite das Menü **[!UICONTROL Seiteninformationen]** und klicken Sie auf **[!UICONTROL Eigenschaften öffnen]**.

   ![](assets/aem_authoring_3.png)

1. Bearbeiten Sie den E-Mail-Inhalt, indem Sie Komponenten hinzufügen, z. B. Personalisierungsfelder aus Adobe Campaign. Weitere Informationen finden Sie unter [Adobe Experience Manager-Dokumentation](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html#editing-email-content){target="_blank"}.

1. Wenn Ihre E-Mail fertig ist, navigieren Sie zum Menü **[!UICONTROL Seiteninformationen]** und klicken Sie auf **[!UICONTROL Workflow starten]**.

   ![](assets/aem_authoring_4.png)

1. Wählen Sie in der ersten Dropdown-Liste als Workflow-Modell **[!UICONTROL Adobe Campaign genehmigen]** aus und klicken Sie auf **[!UICONTROL Workflow starten]**.

   ![](assets/aem_authoring_5.png)

1. Oben auf Ihrer Seite erscheint ein Haftungsausschluss mit folgendem Inhalt: `This page is subject to the workflow Approve for Adobe Campaign`. Klicken Sie neben dem Haftungsausschluss auf **[!UICONTROL Fertig]**, um die Überprüfung zu bestätigen, und klicken Sie dann auf **[!UICONTROL Ok]**.

1. Klicken Sie erneut auf **[!UICONTROL Fertig]** und wählen Sie danach **[!UICONTROL Newsletter-Genehmigung]** in der Dropdown-Liste **[!UICONTROL Nächster Schritt]**.

   ![](assets/aem_authoring_6.png)

Ihr Newsletter ist jetzt fertig und in Adobe Campaign synchronisiert.

**In Adobe Campaign:**

1. Wählen Sie im Tab **[!UICONTROL Kampagnen]** die Option **[!UICONTROL Sendungen]** und danach die Schaltfläche **[!UICONTROL Erstellen]** aus.

1. Wählen Sie die Vorlage **[!UICONTROL E-Mail-Versand mit AEM-Inhalt (mailAEMContent)]** aus dem Dropdown-Menü **[!UICONTROL Versandvorlagen]**.

   ![](assets/aem_authoring_7.png)

1. Fügen Sie zu Ihrem Versand einen **[!UICONTROL Titel]** hinzu und klicken Sie dann auf **[!UICONTROL Fortfahren]**.

1. Klicken Sie auf **[!UICONTROL Synchronisieren]**, um auf Ihre AEM-Sendungen zuzugreifen.

   Wenn die Schaltfläche in der Benutzeroberfläche nicht sichtbar ist, navigieren Sie zur Schaltfläche **[!UICONTROL Eigenschaften]** und greifen Sie darüber auf die Registerkarte **[!UICONTROL Erweitert]** zu. Stellen Sie sicher, dass das Feld **[!UICONTROL Inhaltsbearbeitungsmodus]** auf **[!UICONTROL AEM]** eingestellt ist, und geben Sie Ihre AEM-Instanzdetails in das Feld **[!UICONTROL AEM Konto]** ein.

   ![](assets/aem_authoring_8.png)

1. Wählen Sie den zuvor in [!DNL Adobe Experience Manager] erstellten Versand aus und bestätigen Sie durch Klicken auf **[!UICONTROL OK]**.

   ![](assets/aem_authoring_11.png)

1. Stellen Sie sicher, dass Sie immer dann auf die Schaltfläche **[!UICONTROL Inhalt aktualisieren]** klicken, wenn Änderungen an Ihrem AEM-Versand vorgenommen werden.

   ![](assets/aem_authoring_12.png)

1. Um die Verknüpfung zwischen Experience Manager und Campaign zu entfernen, klicken Sie auf **[!UICONTROL Synchronisierung aufheben]**.

Ihre E-Mail kann jetzt an Ihre Zielgruppe gesendet werden.

## Importieren von Assets aus der Adobe Experience Manager Assets-Bibliothek {#assets-library}

Sie können Assets auch direkt aus Ihrer [!DNL Adobe Experience Manager Assets Library] einfügen, während Sie eine E-Mail oder Landingpage in Adobe Campaign bearbeiten. Diese Funktion wird im Abschnitt [Adobe Experience Manager Assets-Dokumentation](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html){target="_blank"}.

**In Adobe Experience Manager:**

1. Navigieren Sie zu Ihrer [!DNL Adobe Experience Manager]-Autoreninstanz und klicken Sie oben links auf der Seite auf „Adobe Experience“. Wählen Sie im Menü **[!UICONTROL Assets]** `>` **[!UICONTROL Dateien]**.

   ![](assets/aem_assets_1.png)

1. Klicken Sie auf **Erstellen** und dann auf **Dateien**, um das Asset in Ihre **Adobe Experience Manager Assets-Bibliothek** zu importieren. Weitere Informationen finden Sie unter [Dokumentation zu Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html#uploading-assets){target="_blank"}.

   ![](assets/aem_assets_2.png)

1. Benennen Sie Ihr Asset bei Bedarf um und klicken Sie auf **Hochladen**.

Ihr Asset wurde jetzt in Ihre **Adobe Experience Manager Assets-Bibliothek** hochgeladen.

**In Adobe Campaign:**

1. Um einen neuen Versand zu erstellen, gehen Sie in Adobe Campaign zur Registerkarte **Kampagnen**, klicken Sie auf **Sendungen** und anschließend oberhalb der Liste der vorhandenen Sendungen auf die Schaltfläche **Erstellen**.

   ![](assets/aem_assets_3.png)

1. Wählen Sie eine **Versandvorlage** aus und benennen Sie Ihren Versand.

1. Definieren und personalisieren Sie den Nachrichteninhalt. [Weitere Informationen](../send/email.md)

1. Navigieren Sie zum Verwenden Ihrer **Adobe Experience Manager Assets-Bibliothek** zu den **[!UICONTROL Eigenschaften]** Ihres AEM-Versands und öffnen Sie die Registerkarte **[!UICONTROL Erweitert]**.

   Wählen Sie Ihr **AEM-Konto** und aktivieren Sie die Option **[!UICONTROL obige AEM-Instanz als freigegebene Asset-Bibliothek verwenden]**.

   ![](assets/aem_authoring_9.png)

1. Navigieren Sie über das **Bild**-Symbol zum Menü **[!UICONTROL Ein freigegebenes Asset auswählen]**.

   ![](assets/aem_assets_4.png)

1. Wählen Sie im Auswahlfenster ein Bild aus Ihrer **Adobe Experience Manager Assets-Bibliothek** und klicken Sie auf **Auswählen**.

   ![](assets/aem_assets_5.png)

Ihr Asset wird jetzt in Ihren E-Mail-Versand hochgeladen. Jetzt können Sie die Zielgruppe festlegen, den Versand bestätigen und mit dem Senden fortfahren.

---
title: Versenden von Push-Benachrichtigungen mit Adobe Campaign
description: Erste Schritte mit Push-Benachrichtigungen in Campaign
feature: Push
role: Data Engineer
level: Beginner
badge: label="Eingeschränkte Verfügbarkeit" type="Informativ"
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 49%

---

# Überarbeitete Konfiguration für Push-Benachrichtigungen {#push-notifications-config}

>[!AVAILABILITY]
>
> Diese Funktion steht nur neuen Kunden ab Version 8.5 zur Verfügung und wird schrittweise für ausgewählte Kunden eingeführt. Wenn Ihre Umgebung vor Juni 2023 bereitgestellt wurde, müssen Sie die detaillierten Verfahren befolgen [auf dieser Seite](push-settings.md).

Um Push-Benachrichtigungen in Adobe Campaign senden zu können, müssen Sie folgende Schritte befolgen:

1. [Erstellen einer App-Oberfläche in der Adobe Experience Platform-Datenerfassung](#create-app-surface)

1. [Anwendungseinstellungen in Adobe Campaign konfigurieren](#push-config-campaign)

1. [Erstellen und Konfigurieren einer mobilen Eigenschaft in der Adobe Experience Platform-Datenerfassung](#create-mobile-property)

1. [Hinzufügen der Adobe Adobe Experience Platform Assurance-Erweiterung](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}(empfohlen)

1. [Campaign Classic zur Mobile App hinzufügen](#campaign-mobile-ap)

1. [Erstellen Sie einen Versand sowohl für iOS als auch für Android](##push-create)

>[!NOTE]
>
> Legacy-FCM und APNS p12 werden von der Datenerfassung nicht unterstützt.

## Erstellen einer App-Oberfläche in der Adobe Experience Platform-Datenerfassung {#create-app-surface}

Sie müssen Ihre Push-Anmeldedaten für Mobile Apps in [!DNL Adobe Experience Platform Data Collection].

Die Registrierung der Push-Anmeldedaten für mobile Apps ist erforderlich, um der Adobe zu erlauben, Push-Benachrichtigungen in Ihrem Namen zu senden. Gehen Sie wie folgt vor:

1. Von [!DNL Adobe Experience Platform Data Collection], wählen Sie die **[!UICONTROL App-Oberflächen]** im linken Bereich.

1. Klicken **[!UICONTROL App-Oberfläche erstellen]** , um eine neue Konfiguration zu erstellen.

   ![](assets/push-config-1.png)

1. Geben Sie einen **[!UICONTROL Name]** für die Konfiguration.

1. Von **[!UICONTROL Konfiguration von Mobile Apps]** wählen Sie das Betriebssystem aus:

   * **Für iOS**

     ![](assets/push-config-2.png)

      1. Mobile App eingeben **Bundle-ID** im **[!UICONTROL App-ID (iOS Bundle ID)]** -Feld.

         Die App-Paket-ID finden Sie im **Allgemein** Registerkarte der primären Zielgruppe in **XCode** Ihres Apple-Entwicklerkontos.

      1. Einschalten **[!UICONTROL Push-Anmeldedaten]** , um Ihre Anmeldedaten hinzuzufügen.

      1. Ziehen Sie die Datei mit dem Authentifizierungsschlüssel für Push-Benachrichtigungen in Apple per Drag-and-Drop in den Arbeitsbereich.

         Dieser Schlüssel kann über die **Zertifikate**, **Kennungen** und **Profile** Seite Ihres Apple-Entwicklerkontos.

      1. Stellen Sie die **Schlüssel-ID**. Dies ist eine 10-stellige Zeichenfolge, die bei der Erstellung des p8-Authentifizierungsschlüssels zugewiesen wurde.

         Sie finden sie unter **Schlüssel** Registerkarte in **Zertifikate**, **Kennungen** und **Profile** Seite Ihres Apple-Entwicklerkontos.

      1. Stellen Sie die **Team-ID**. Dies ist ein string -Wert, der unter der **Mitgliedschaft** Registerkarte.

   * **Für Android**

     ![](assets/push-config-3.png)

      1. Stellen Sie die **[!UICONTROL App-ID (Android-Paketname)]**. Normalerweise ist der Paketname die App-ID in Ihrer `build.gradle` -Datei.

      1. Switch **[!UICONTROL Push-Anmeldedaten]** , um Ihre Anmeldedaten hinzuzufügen.

      1. Ziehen Sie die FCM-Push-Anmeldeinformationen per Drag-and-Drop in den Arbeitsbereich. Weitere Informationen zum Abrufen der Push-Anmeldeinformationen finden Sie unter [Dokumentation zu Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

1. Klicken **[!UICONTROL Speichern]** , um Ihre App-Konfiguration zu erstellen.

## Anwendungseinstellungen in Adobe Campaign konfigurieren{#push-config-campaign}

### Dienst erstellen {#create-service}

Bevor Sie Push-Benachrichtigungen senden, müssen Sie Ihre Einstellungen für iOS- und Android-Apps in Adobe Campaign definieren.

Push-Benachrichtigungen werden über einen dedizierten Dienst an die Benutzerinnen und Benutzer Ihrer App gesendet. Wenn Benutzerinnen und Benutzer Ihre Anwendung installieren, abonnieren sie diesen Dienst: Adobe Campaign greift auf diesen Dienst zurück, um nur die Abonnentinnen und Abonnenten Ihrer App anzusprechen. In diesem Dienst müssen Sie Ihre iOS- und Android-Apps hinzufügen, um etwas auf iOS- und Android-Geräten zu senden.

Gehen Sie wie folgt vor, um einen Dienst zum Senden von Push-Benachrichtigungen zu erstellen:

1. Navigieren Sie zu **[!UICONTROL Profile und Zielgruppen > Services und Abonnements]** und klicken Sie auf **[!UICONTROL Erstellen]**.

   ![](assets/push-config-4.png){width="800" align="left"}

1. Geben Sie einen **[!UICONTROL Titel]** und einen **[!UICONTROL internen Namen]** ein und wählen Sie den Typ **[!UICONTROL Mobile App]** aus.

   >[!NOTE]
   >
   >Das standardmäßig vorgeschlagene Zielgruppen-Mapping **[!UICONTROL Abonnierte Anwendungen (nms:appSubscriptionRcp)]** bezieht sich auf die Empfängertabelle. Wenn Sie ein anderes Zielgruppen-Mapping verwenden wollen, haben Sie die Möglichkeit, im Feld **[!UICONTROL Zielgruppen-Mapping]** des Service ein neues Zielgruppen-Mapping anzugeben. Weitere Informationen über Zielgruppen-Mapping finden Sie auf [dieser Seite](../audiences/target-mappings.md).

1. Klicken Sie dann auf das Symbol **[!UICONTROL Hinzufügen]** oben rechts, um die Mobile Apps zu definieren, die diesen Dienst verwenden.

   ![](assets/push-config-5.png)

### Mobile App erstellen {#create-sapp}

Nachdem Sie Ihren Dienst erstellt haben, müssen Sie jetzt die Mobile Apps definieren, die diesen Dienst verwenden werden.

>[!BEGINTABS]

>[!TAB iOS]

Gehen Sie wie folgt vor, um eine App für iOS-Geräte zu erstellen:

1. Klicken Sie in Ihrem Dienst auf **[!UICONTROL Hinzufügen]** und wählen Sie **[!UICONTROL Erstellen einer iOS-Anwendung]**. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/push-config-6.png)

1. Aus dem **[!UICONTROL Liste der App-Konfigurationen starten]** Wählen Sie die zuvor in diesem Abschnitt erstellte App-Oberfläche aus. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/push-config-7.png)

1. (Optional) Sie können den Inhalt einer Push-Nachricht mit einigen **[!UICONTROL Anwendungsvariablen]** anreichern. Diese sind vollständig anpassbar und Teil der an das mobile Gerät gesendeten Nachrichten-Payload.

   Im folgenden Beispiel wird die Variable **mediaURl** und **mediaExt** -Variablen hinzugefügt werden, um Rich-Push-Benachrichtigungen zu erstellen, und liefert dann der Anwendung das Bild, das in der Benachrichtigung angezeigt werden soll.

   ![](assets/push-config-8.png)

1. Auf der Registerkarte **[!UICONTROL Abonnementparameter]** können Sie das Mapping mit einer Erweiterung des Schemas **[!UICONTROL Abonnierte Anwendungen (nms:appsubscriptionRcp)]** definieren.

1. Navigieren Sie zur Registerkarte **[!UICONTROL Töne]**, um einen Ton festzulegen, der wiedergegeben werden soll. Klicken Sie auf **[!UICONTROL Hinzufügen]** und füllen Sie das Feld **[!UICONTROL Interner Name]** aus, das den Namen der in die Anwendung eingebetteten Datei oder den Namen des Systemtons enthalten muss.

1. Klicken Sie auf **[!UICONTROL Weiter]**, um mit dem Konfigurieren der Entwicklungsanwendung zu beginnen.

1. Die **[!UICONTROL Integrationsschlüssel]** ist für jede Anwendung spezifisch. Sie verknüpft die Mobile App mit Adobe Campaign und wird bei der Konfiguration der Campaign-Erweiterung verwendet.

   Stellen Sie sicher, dass in Adobe Campaign und im Anwendungs-Code über das SDK derselbe **[!UICONTROL Integrationsschlüssel]** definiert ist 

   Weitere Informationen finden Sie in der [Developer-Dokumentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > Der **[!UICONTROL Integrationsschlüssel]** kann mit einem Zeichenfolgenwert vollständig angepasst werden, muss jedoch mit dem im SDK angegebenen Schlüssel identisch sein.
   >
   > Sie können nicht dasselbe Zertifikat sowohl für die Entwicklungsversion (Sandbox) als auch für die Produktionsversion der Anwendung verwenden.

   ![](assets/push-config-9.png)

1. Wählen Sie im Feld **[!UICONTROL Anwendungssymbol]** das Symbol aus, um die Mobile App in Ihrem Dienst zu personalisieren.

1. Nun können Sie die Produktionsanwendung konfigurieren, indem Sie auf **[!UICONTROL Weiter]** klicken und nach dem gleichen Verfahren wie oben beschrieben vorgehen. Beachten Sie, dass Sie nicht dasselbe **[!UICONTROL Integrationsschlüssel]** für die Entwicklungsversion (Sandbox) und die Produktionsversion der Anwendung.

1. Klicken Sie auf **[!UICONTROL Beenden]**.

Ihre iOS-Anwendung kann jetzt in Campaign verwendet werden.

>[!TAB Android]

Gehen Sie wie folgt vor, um eine App für Android-Geräte zu erstellen:

1. Klicken Sie in Ihrem Dienst auf **[!UICONTROL Hinzufügen]** und wählen Sie **[!UICONTROL Android-Anwendung erstellen]**. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/push-config-10.png)

1. Aus dem **[!UICONTROL Liste der App-Konfigurationen starten]** Wählen Sie im Fenster die in diesem Abschnitt erstellte App-Oberfläche aus und klicken Sie auf **[!UICONTROL Nächste]**.

   ![](assets/push-config-11.png)

1. Der Integrationsschlüssel ist für jede Anwendung spezifisch. Sie verknüpft die Mobile App mit Adobe Campaign und wird bei der Konfiguration der Campaign-Erweiterung verwendet.

   Stellen Sie sicher, dass in Adobe Campaign und im Anwendungs-Code über das SDK derselbe **[!UICONTROL Integrationsschlüssel]** definiert ist 

   Weitere Informationen finden Sie in der [Developer-Dokumentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}

   >[!NOTE]
   >
   > Der **[!UICONTROL Integrationsschlüssel]** kann mit einem Zeichenfolgenwert vollständig angepasst werden, muss jedoch mit dem im SDK angegebenen Schlüssel identisch sein.

   ![](assets/push-config-12.png)

1. Wählen Sie im Feld **[!UICONTROL Anwendungssymbol]** das Symbol aus, um die Mobile App in Ihrem Dienst zu personalisieren.

1. Bei Bedarf können Sie die Inhalte von Push-Nachrichten mit bestimmten **[!UICONTROL Anwendungsvariablen]** anreichern. Diese sind vollständig anpassbar und Teil der an das mobile Gerät gesendeten Nachrichten-Payload.

1. Auf der Registerkarte **[!UICONTROL Abonnementparameter]** können Sie das Mapping mit einer Erweiterung des Schemas **[!UICONTROL Abonnierte Anwendungen (nms:appsubscriptionRcp)]** definieren.

1. Klicken Sie auf **[!UICONTROL Beenden]** und danach auf **[!UICONTROL Speichern]**.

Ihre Android-Anwendung kann jetzt in Campaign verwendet werden.

>[!ENDTABS]

Im Folgenden finden Sie die FCM-Payload-Namen, mit denen Sie Ihre Push-Benachrichtigung weiter personalisieren können:

| Nachrichtentyp | Konfigurierbares Nachrichtenelement (FCM-Payload-Name) | Konfigurierbare Optionen (Name der FCM-Payload) |
|:-:|:-:|:-:|
| Datennachricht | K. A. | validate_only |
| Benachrichtigungsinhalt | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |

## Konfigurieren einer mobilen Eigenschaft in der Adobe Experience Platform-Datenerfassung {#create-mobile-property}

1. Rufen Sie auf der Homepage Datenerfassung das Menü Tags auf.

1. Klicken **[!UICONTROL Neue Eigenschaft]**.

   ![](assets/push-config-13.png)

1. Geben Sie einen Namen für die Eigenschaft ein und wählen Sie **[!UICONTROL Mobile]** als Plattform.

   ![](assets/push-config-14.png)

1. Klicken **[!UICONTROL Speichern]** , um die Eigenschaft für Mobilgeräte zu erstellen.

1. Greifen Sie auf Ihre neu erstellte Eigenschaft für Mobilgeräte zu.

1. Rufen Sie über das Dashboard Ihrer mobilen Property das **[!UICONTROL Erweiterungen]** Menü und **[!UICONTROL Katalog]** Registerkarte.

   ![](assets/push-config-15.png)

1. Installieren Sie die **[!DNL Adobe Campaign Classic]** -Erweiterung. [Weitere Informationen zur Campaign-Erweiterung](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configure-campaign-classic-extension)

   ![](assets/push-config-16.png)

1. Füllen Sie Ihre Instanzdetails aus:

   * **[!UICONTROL Registrierungs-Endpunkt]** oder **[!UICONTROL Tracking-Endpunkt]** URLs finden Sie im Abschnitt **[!UICONTROL Instrumente]** > **[!UICONTROL Erweitert]** > **[!UICONTROL Implementierungsassistent]** in Campaign.
   * **[!UICONTROL Integrationsschlüssel]** finden Sie in der Mobile App, die in konfiguriert ist. [diesem Abschnitt](#create-app).

   ![](assets/push-config-17.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

1. Sie müssen die Konfiguration jetzt über die **[!UICONTROL Veröffentlichungsfluss]** Menü. [Weitere Informationen](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

Ihre Eigenschaft für Mobilgeräte wird jetzt automatisch mit der **[!UICONTROL Adobe Experience Platform-Datenerfassung]** technischer Arbeitsablauf. [Weitere Informationen](../../automation/workflow/technical-workflows.md#list-technical-workflows)

## Campaign Classic zur Mobile App hinzufügen {#campaign-mobile-app}

Mit dem Adobe Experience Platform Mobile SDK können Sie die Experience Cloud-Lösungen und -Dienste von Adobe in mobilen Apps nutzen. Die SDK-Konfiguration wird über die Datenerfassungs-Benutzeroberfläche verwaltet, um eine flexible Konfiguration und erweiterbare, regelbasierte Integrationen zu ermöglichen.

[Weitere Informationen finden Sie in der Adobe Developer-Dokumentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Push-Benachrichtigung erstellen{#push-create}

Nachdem Sie Ihre Mobile App in der Datenerfassung erfolgreich konfiguriert haben, können Sie jetzt Push-Benachrichtigungen in Adobe Campaign erstellen und senden.

Siehe [diese Seite](push.md#push-create) für die detaillierten Elemente zur Bereitstellung von iOS- und Android-Benachrichtigungen.

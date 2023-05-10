---
title: Integrieren von AEP SDK und Campaign
description: Erfahren Sie, wie Sie das mobile Adobe Experience Platform SDK in Ihre App integrieren.
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: 3bef6d2544a86bf1d5efa4868b82ec59c7e36484
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 2%

---


# AEP SDK + Campaign: Push-Benachrichtigungskanal konfigurieren {#push-notification-configuration}

Bevor Sie mit dem Versand von Push-Benachrichtigungen mit Adobe Campaign beginnen, müssen Sie sicherstellen, dass Konfigurationen und Integrationen in der App und für Tags in Adobe Experience Platform vorhanden sind.

Das Adobe Experience Platform Mobile SDK bietet Client-seitige Integrations-APIs für Ihre Mobiltelefone über Android- und iOS-kompatible SDKs.

Gehen Sie wie folgt vor, um Ihre App mit Adobe Experience Platform Mobile SDKs einzurichten:

1. Überprüfen [Voraussetzungen](#before-starting).
1. Richten Sie eine [mobile Tag-Eigenschaft](#launch-property) in der Adobe Experience Platform-Datenerfassung.
1. Abrufen des Adobe Experience Platform Mobile SDK im Detail [auf dieser Seite](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (optional) Aktivieren Sie die Protokollierung und Lebenszyklusmetriken wie beschrieben. [auf dieser Seite](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (optional) Hinzufügen [Adobe Experience Platform Assurance für Ihre App](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Folgen [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} , um die Einrichtung mit Adobe Experience Platform Mobile SDKs in Ihrer App zu erhalten.
1. Installieren und Konfigurieren [Adobe Campaign-Erweiterung](#configure-extension) in Ihrer mobilen Eigenschaft.
1. Konfigurieren Sie Ihre iOS- und Android-Mobile-Dienste in Adobe Campaign wie beschrieben. [auf dieser Seite](../send/push.md#push-config).


## Voraussetzungen {#before-starting}

### Berechtigungen einrichten {#setup-permissions}

Bevor Sie eine Mobile App erstellen, müssen Sie zunächst sicherstellen, dass Sie in Adobe Experience Platform über die richtigen Benutzerberechtigungen für Tags verfügen oder diese zuweisen. Benutzerberechtigungen für Tags in Adobe Experience Platform werden Benutzern über Adobe Admin Console zugewiesen. Weitere Informationen finden Sie unter [Dokumentation zu Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>Die Push-Konfiguration muss von einem erfahrenen Benutzer durchgeführt werden. Abhängig von Ihrem Implementierungsmodell und den an dieser Implementierung beteiligten Rollen müssen Sie möglicherweise den gesamten Berechtigungssatz einem einzelnen Produktprofil zuweisen oder Berechtigungen zwischen dem App-Entwickler und dem **Adobe Campaign** Administrator.

Zuweisen **Eigenschaft** und **Firma** -Berechtigungen verwenden, führen Sie die folgenden Schritte aus:

1. Zugriff auf **[!DNL Admin Console]**.
1. Aus dem **[!UICONTROL Produkte]** auswählen, wählen Sie die **[!UICONTROL Adobe Experience Platform-Datenerfassung]** Karte.
1. Vorhandene wählen **[!UICONTROL Produktprofil]** oder erstellen Sie eine neue mit der **[!UICONTROL Neues Profil]** Schaltfläche. Erfahren Sie, wie Sie eine neue **[!UICONTROL Neues Profil]** im [Dokumentation zur Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. Aus dem **[!UICONTROL Berechtigungen]** Registerkarte, wählen Sie **[!UICONTROL Eigenschaftsrechte]**.
1. Klicken **[!UICONTROL Alle hinzufügen]**. Dadurch wird Ihrem Produktprofil die folgende Berechtigung hinzugefügt:
   * **[!UICONTROL Genehmigen]**
   * **[!UICONTROL Entwickeln]**
   * **[!UICONTROL Eigenschaft bearbeiten]**
   * **[!UICONTROL Verwalten von Umgebungen]**
   * **[!UICONTROL Verwalten von Erweiterungen]**
   * **[!UICONTROL Veröffentlichen]**

   Diese Berechtigungen sind erforderlich, um die Adobe Campaign-Erweiterung zu installieren und zu veröffentlichen und die App-Eigenschaft in **Adobe Experience Platform Mobile SDK**.

1. Wählen Sie anschließend **[!UICONTROL Unternehmensrechte]** im Menü links.
1. Fügen Sie die folgenden Berechtigungen hinzu:

   * **[!UICONTROL App-Konfigurationen verwalten]**
   * **[!UICONTROL Eigenschaften verwalten]**

   Diese Berechtigungen sind erforderlich, damit der Entwickler der mobilen App Push-Anmeldeinformationen in **Adobe Experience Platform-Datenerfassung**.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Zuweisen **[!UICONTROL Produktprofil]** für Benutzer die folgenden Schritte ausführen:

1. Zugriff auf **[!DNL Admin Console]**.
1. Aus dem **[!UICONTROL Produkte]** auswählen, wählen Sie die **[!UICONTROL Adobe Experience Platform-Datenerfassung]** Karte.
1. Wählen Sie die zuvor konfigurierte **[!UICONTROL Produktprofil]**.
1. Aus dem **[!UICONTROL Benutzer]** Registerkarte, klicken Sie auf **[!UICONTROL Benutzer hinzufügen]**.
1. Geben Sie den Namen oder die E-Mail-Adresse Ihres Benutzers ein und wählen Sie den Benutzer aus. Klicken Sie anschließend auf **[!UICONTROL Speichern]**.

   >[!NOTE]
   >
   >Wenn der Benutzer zuvor nicht in der Admin Console erstellt wurde, lesen Sie den Abschnitt [Dokumentation zu Benutzern hinzufügen](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### App konfigurieren {#configure-app}

Die technische Einrichtung umfasst eine enge Zusammenarbeit zwischen dem App-Entwickler und dem Business-Administrator. Bevor Sie mit dem Versand von Push-Benachrichtigungen beginnen [!DNL Adobe Campaign], müssen Sie Einstellungen in [!DNL Adobe Experience Platform Data Collection] und integrieren Sie Ihre Mobile App in Adobe Experience Platform Mobile SDKs.

Folgen Sie den Implementierungsschritten, die in den folgenden Links beschrieben werden:

* Für **Apple iOS**: Erfahren Sie, wie Sie Ihre App mit APNs in [Dokumentation zu Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Für **Google Android**: Erfahren Sie, wie Sie eine Firebase Cloud Messaging-Client-App unter Android einrichten in [Dokumentation zu Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Einrichten einer mobilen Tag-Eigenschaft in der Adobe Experience Platform-Datenerfassung {#launch-property}

Durch das Einrichten einer mobilen Eigenschaft können Entwickler oder Marketingexperten der mobilen App die mobilen SDKs konfigurieren. Normalerweise erstellen Sie für jede Mobile App, die Sie verwalten möchten, eine mobile Eigenschaft. Erfahren Sie, wie Sie eine mobile Eigenschaft in erstellen und konfigurieren [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

Um die SDKs zu erhalten, die für die Push-Benachrichtigung benötigt werden, benötigen Sie die folgenden SDK-Erweiterungen für Android und iOS:

* **[!UICONTROL Mobile Core]** (automatisch installiert)
* **[!UICONTROL Profil]** (automatisch installiert)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional, jedoch zum Debuggen der mobilen Implementierung empfohlen.

Weitere Informationen [!DNL Adobe Experience Platform Data Collection] Tags in [Adobe Experience Platform-Dokumentation](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Öffnen Sie nach der Erstellung die neue Tag-Eigenschaft und erstellen Sie eine Bibliothek. Gehen Sie dazu wie folgt vor:

1. Navigieren Sie zu **Veröffentlichungsfluss** in der linken Navigation und wählen Sie **Bibliothek hinzufügen**.
1. Geben Sie den Namen der Bibliothek ein und wählen Sie die Umgebung aus.
1. Auswählen **Alle geänderten Ressourcen hinzufügen** und **Speichern und in der Entwicklung erstellen**.
1. Legen Sie diese Bibliothek als Arbeitsbibliothek aus dem **Arbeitsbibliothek auswählen** Schaltfläche.


## Konfigurieren der Adobe Campaign-Erweiterung in Ihrer mobilen Eigenschaft {#configure-extension}

Die **Adobe Campaign Classic-Erweiterung** für Adobe Experience Platform Mobile SDKs ermöglicht Push-Benachrichtigungen für Ihre mobilen Apps, unterstützt Sie bei der Erfassung von Benutzer-Push-Token und verwaltet die Interaktionsmessung mit Adobe Experience Platform Services.

Diese Erweiterung ist in Ihrer Umgebung vorinstalliert und muss konfiguriert werden. Gehen Sie wie folgt vor, um die Erweiterung für Ihre mobile Tag-Eigenschaft zu konfigurieren:

1. Öffnen Sie die zuvor erstellte Tag-Eigenschaft.
1. Navigieren Sie in der linken Navigation zu **Erweiterungen** und öffnen Sie die **Katalog** Registerkarte. Verwenden Sie das Suchfeld, um die **Adobe Campaign Classic** -Erweiterung.
1. Klicken Sie auf der Karte Campaign Classic auf die **Installieren** Schaltfläche.
1. Geben Sie die Einstellungen wie unter [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Sie können Ihrer App jetzt Campaign hinzufügen, wie im Abschnitt  [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Mobile Services in Campaign konfigurieren{#push-service}

Nachdem Ihre App in eingerichtet wurde [!DNL Adobe Experience Platform Data Collection]müssen Sie zwei Dienste erstellen (einen für iOS-Geräte, einen für Android-Geräte), um Push-Benachrichtigungen von senden zu können. **[!DNL Adobe Campaign]**.

Erfahren Sie, wie Sie einen Dienst für Push-Benachrichtigungen in iOS und Android erstellen und konfigurieren in [diesem Abschnitt](../send/push.md#push-config).

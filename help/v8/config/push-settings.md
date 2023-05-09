---
title: Integrieren von AEP SDK und Campaign
description: Erfahren Sie, wie Sie das mobile Adobe Experience Platform SDK in Ihre App integrieren.
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e3ea361cc486096fe6c19ac469e8a71b636371ac
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 3%

---


# AEP SDK + Campaign: Push-Benachrichtigungskanal konfigurieren {#push-notification-configuration}

Bevor Sie mit dem Versand von Push-Benachrichtigungen mit Adobe Campaign beginnen, müssen Sie sicherstellen, dass in der App Konfigurationen und Integrationen vorhanden sind und dass Tags in Adobe Experience Platform verwendet werden.. .... ....


## Vor Beginn {#before-starting}

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

### Integrieren Ihrer mobilen App mit dem Adobe Experience Platform SDK {#integrate-mobile-app}

Das Adobe Experience Platform Mobile SDK bietet Client-seitige Integrations-APIs für Ihre Mobiltelefone über Android- und iOS-kompatible SDKs. Folgen [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} , um die Einrichtung mit Adobe Experience Platform Mobile SDKs in Ihrer App zu erhalten.

Am Ende hätten Sie auch eine Eigenschaft für Mobilgeräte in [!DNL Adobe Experience Platform Data Collection]. Normalerweise erstellen Sie für jede Mobile App, die Sie verwalten möchten, eine mobile Eigenschaft. Erfahren Sie, wie Sie eine mobile Eigenschaft in erstellen und konfigurieren [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.


## Schritt 1: App-Push-Anmeldedaten zur Adobe Experience Platform-Datenerfassung hinzufügen {#push-credentials}

Nachdem Sie die richtigen Benutzerberechtigungen erteilt haben, müssen Sie jetzt Ihre Push-Anmeldedaten für Mobile Apps zur Adobe Experience Platform-Datenerfassung hinzufügen.

Die Registrierung der Push-Anmeldedaten für mobile Apps ist erforderlich, um der Adobe zu erlauben, Push-Benachrichtigungen in Ihrem Namen zu senden. Gehen Sie wie folgt vor:

1. Von [!DNL Adobe Experience Platform Data Collection], navigieren Sie zu **[!UICONTROL App-Oberflächen]** in der linken Leiste.

1. Klicken **[!UICONTROL App-Oberfläche erstellen]** , um eine neue Konfiguration zu erstellen.

1. Geben Sie einen **[!UICONTROL Name]** für die Konfiguration.

1. Von **[!UICONTROL Konfiguration von Mobile Apps]** wählen Sie das Betriebssystem aus:

   * **Für iOS**

      1. Mobile App eingeben **Bundle-ID** im **[!UICONTROL App-ID (iOS Bundle ID)]** -Feld. Die App-Paket-ID finden Sie im **Allgemein** Registerkarte der primären Zielgruppe in **XCode**.

      1. Schalten Sie die **[!UICONTROL Push-Anmeldedaten]** -Schaltfläche, um Ihre Anmeldedaten hinzuzufügen.

      1. Ziehen Sie die Datei mit dem Authentifizierungsschlüssel für Push-Benachrichtigungen in Apple per Drag-and-Drop in den Arbeitsbereich. Dieser Schlüssel kann über die **Zertifikate**, **Kennungen** und **Profile** Seite.

      1. Stellen Sie die **Schlüssel-ID**. Dies ist eine 10-stellige Zeichenfolge, die bei der Erstellung des p8-Authentifizierungsschlüssels zugewiesen wurde. Sie finden sie unter **Schlüssel** Registerkarte in **Zertifikate**, **Kennungen** und **Profile** Seite.

      1. Stellen Sie die **Team-ID**. Dies ist ein string -Wert, der auf der Registerkarte Mitgliedschaft zu finden ist.
   * **Für Android**

      1. Stellen Sie die **[!UICONTROL App-ID (Android-Paketname)]**: gewöhnlich ist der Paketname die App-ID in Ihrer `build.gradle` -Datei.

      1. Schalten Sie die **[!UICONTROL Push-Anmeldedaten]** -Schaltfläche, um Ihre Anmeldedaten hinzuzufügen.

      1. Ziehen Sie die FCM-Push-Anmeldeinformationen per Drag-and-Drop in den Arbeitsbereich. Weitere Informationen zum Abrufen der Push-Anmeldeinformationen finden Sie unter [Dokumentation zu Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.



1. Klicken **[!UICONTROL Speichern]** , um Ihre App-Konfiguration zu erstellen.


## Schritt 2: Einrichten einer mobilen Tag-Eigenschaft in der Adobe Experience Platform-Datenerfassung {#launch-property}

Durch das Einrichten einer mobilen Eigenschaft kann der Entwickler der Mobile App oder Marketingexperte die Attribute der mobilen SDKs konfigurieren, wie z. B. Sitzungs-Timeouts, die [!DNL Adobe Experience Platform] Sandbox, die als Ziel ausgewählt werden soll, und **[!UICONTROL Adobe Experience Platform-Datensätze]** , das für das mobile SDK verwendet wird, um Daten an zu senden.

Weitere Einzelheiten und Verfahren zur Einrichtung einer **mobile property** , siehe die Schritte unter [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

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


## Schritt 3: Konfigurieren der Adobe Campaign-Erweiterung in Ihrer mobilen Eigenschaft {#configure-extension}

Die **Adobe Campaign Classic-Erweiterung** für Adobe Experience Platform Mobile SDKs ermöglicht Push-Benachrichtigungen für Ihre mobilen Apps, unterstützt Sie bei der Erfassung von Benutzer-Push-Token und verwaltet die Interaktionsmessung mit Adobe Experience Platform Services.

Diese Erweiterung ist in Ihrer Umgebung vorinstalliert und muss konfiguriert werden. Gehen Sie wie folgt vor, um die Erweiterung für Ihre mobile Tag-Eigenschaft zu konfigurieren:

1. Öffnen Sie die zuvor erstellte Tag-Eigenschaft.
1. Navigieren Sie in der linken Navigation zu **Erweiterungen** und öffnen Sie die **Katalog** Registerkarte. Verwenden Sie das Suchfeld, um die **Adobe Campaign Classic** -Erweiterung.
1. Klicken Sie auf der Karte Campaign Classic auf die **Installieren** Schaltfläche.
1. Geben Sie die Einstellungen wie unter [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Sie können Ihrer App jetzt Campaign hinzufügen, wie im Abschnitt  [Dokumentation zum Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Schritt 4: Mobile Services in Campaign konfigurieren{#push-service}

Nachdem Ihre App in eingerichtet wurde [!DNL Adobe Experience Platform Data Collection]müssen Sie zwei Dienste erstellen (einen für iOS-Geräte, einen für Android-Geräte), um Push-Benachrichtigungen von senden zu können. **[!DNL Adobe Campaign]**.

Erfahren Sie, wie Sie einen Dienst für Push-Benachrichtigungen in iOS und Android erstellen und konfigurieren in [diesem Abschnitt](../send/push.md#push-config).

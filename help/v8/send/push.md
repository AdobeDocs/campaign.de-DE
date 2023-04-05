---
title: Versenden von Push-Benachrichtigungen mit Adobe Campaign
description: Erste Schritte mit Push-Benachrichtigungen in Campaign
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 1bcb1b3d1e6062a8b5c0368725248edfc7e3d1b4
workflow-type: tm+mt
source-wordcount: '1937'
ht-degree: 63%

---

# Push-Benachrichtigungen erstellen und versenden{#push-notifications-create}

Mit Mobile-App-Sendungen können Sie Benachrichtigungen an iOS- und Android-Geräte senden.

Um Push-Benachrichtigungen in Adobe Campaign senden zu können, müssen Sie folgende Schritte befolgen:

1. Integrieren Sie das SDK in Ihre App. [Weitere Informationen](#push-sdk)
1. Erstellen Sie einen Informationsdienst vom Typ Mobile App für Ihre Mobile App und fügen Sie diesem Dienst die iOS- und Android-Versionen der App hinzu. [Weitere Informationen](#push-config)
1. Erstellen Sie einen Versand sowohl für iOS als auch für Android. [Weitere Informationen](#push-create)

## SDK integrieren {#push-sdk}

Sie können das Adobe Experience Platform Mobile SDK auch verwenden, indem Sie die Adobe Campaign-Erweiterung in der Benutzeroberfläche „Datenerfassung“ konfigurieren. Mit dem Adobe Experience Platform Mobile SDK können Sie die Experience Cloud-Lösungen und -Dienste von Adobe in Ihren mobilen Apps nutzen. Die SDK-Konfiguration wird über die Datenerfassungs-Benutzeroberfläche verwaltet, um eine flexible Konfiguration und erweiterbare, regelbasierte Integrationen zu ermöglichen. [Weitere Informationen finden Sie in der Adobe Developer-Dokumentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.

Sie können auch das Campaign SDK integrieren, um die Integration Ihrer App in die Adobe Campaign-Plattform zu erleichtern. Kompatible SDK-Versionen sind in der [Campaign-Kompatibilitätsmatrix](../start/compatibility-matrix.md#MobileSDK) aufgeführt.

Informationen zur Integration von Campaign Android- und iOS-SDKs in Ihre App finden Sie [auf dieser Seite](../config/push-config.md).

## Mobile-App-Einstellungen in Campaign konfigurieren{#push-config}

Bevor Sie Push-Benachrichtigungen senden, müssen Sie Ihre Einstellungen für iOS- und Android-Apps in Adobe Campaign definieren.

Push-Benachrichtigungen werden über einen dedizierten Dienst an Ihre App-Benutzer gesendet. Wenn Benutzer Ihre App installieren, abonnieren sie diesen Dienst: Adobe Campaign verlässt sich auf diesen Dienst, um nur die Abonnenten Ihrer App anzusprechen. In diesem Dienst müssen Sie Ihre iOS- und Android-Apps hinzufügen, um sie auf iOS- und Android-Geräten zu senden.

Gehen Sie wie folgt vor, um einen Dienst zum Senden von Push-Benachrichtigungen zu erstellen:

1. Navigieren Sie zu **[!UICONTROL Profile und Zielgruppen > Dienste und Abonnements]** und klicken Sie auf **[!UICONTROL Erstellen]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Geben Sie einen **[!UICONTROL Titel]** und **[!UICONTROL Interner Name]** und wählen Sie eine **[!UICONTROL Mobile App]** Typ.

   >[!NOTE]
   >
   >Das standardmäßig vorgeschlagene Zielgruppen-Mapping **[!UICONTROL Abonnierte Anwendungen (nms:appSubscriptionRcp)]** bezieht sich auf die Empfängertabelle. Wenn Sie ein anderes Zielgruppen-Mapping verwenden wollen, haben Sie die Möglichkeit, im Feld **[!UICONTROL Zielgruppen-Mapping]** des Service ein neues Zielgruppen-Mapping anzugeben. Weitere Informationen zu Zielgruppen-Mappings finden Sie unter [diese Seite](../audiences/target-mappings.md).

1. Verwenden Sie dann die **[!UICONTROL Hinzufügen]** rechts klicken, um die Mobile Apps zu definieren, die diesen Dienst verwenden.

>[!BEGINTABS]

>[!TAB iOS]

Gehen Sie wie folgt vor, um eine App für iOS-Geräte zu erstellen:

1. Auswählen **[!UICONTROL Erstellen einer iOS-Anwendung]** und klicken Sie auf **[!UICONTROL Nächste]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Geben Sie den Namen Ihrer App im **[!UICONTROL Titel]** -Feld.
1. (Optional) Sie können den Inhalt einer Push-Nachricht mit einigen **[!UICONTROL Anwendungsvariablen]**. Diese sind vollständig anpassbar; ein Teil der Payload der Nachricht wird an das Mobilgerät gesendet.

   Im folgenden Beispiel wird die **mediaURl** und **mediaExt** -Variablen hinzugefügt werden, um Rich-Push-Benachrichtigungen zu erstellen, und liefert dann der Anwendung das Bild, das in der Benachrichtigung angezeigt werden soll.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Navigieren Sie zum **[!UICONTROL Abonnementparameter]** -Registerkarte, um das Mapping mit einer Erweiterung des **[!UICONTROL Abonnierte Anwendungen (nms:appsubscriptionRcp)]** Schema.

1. Navigieren Sie zum **[!UICONTROL Sounds]** um einen abzuspielenden Ton zu definieren. Klicken Sie auf **[!UICONTROL Hinzufügen]** und füllen Sie das Feld **[!UICONTROL Interner Name]** aus, das den Namen der in die Anwendung eingebetteten Datei oder den Namen des Systemtons enthalten muss.

1. Klicken Sie auf **[!UICONTROL Weiter]**, um mit dem Konfigurieren der Entwicklungsanwendung zu beginnen.

1. Der Integrationsschlüssel ist für jede Anwendung spezifisch. Dadurch wird die Mobile App mit Adobe Campaign verknüpft.

   Stellen Sie sicher, dass dasselbe **[!UICONTROL Integrationsschlüssel]** wird in Adobe Campaign und im Anwendungscode über das SDK definiert.

   Wenn Sie das Campaign SDK verwenden, erfahren Sie mehr unter[diese Seite](../config/push-config.md).


   Wenn Sie das Adobe Experience Platform SDK (Datenerfassung) verwenden, erfahren Sie mehr unter [diese Seite](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > Der **[!UICONTROL Integrationsschlüssel]** kann mit einem Zeichenfolgenwert vollständig angepasst werden, muss jedoch mit dem im SDK angegebenen Schlüssel identisch sein.
   >
   > Sie können nicht dasselbe Zertifikat für die Entwicklungsversion (Sandbox) und die Produktionsversion der Anwendung verwenden.

1. Wählen Sie das Symbol aus dem **[!UICONTROL Anwendungssymbol]** -Feld, um die Mobile App in Ihrem Dienst zu personalisieren.

1. Wählen Sie den **[!UICONTROL Authentifizierungsmodus]** aus. Zwei Modi sind verfügbar:

   * (Empfohlen) **[!UICONTROL Token-basierte Authentifizierung]**: Füllen Sie die APNs-Verbindungseinstellungen aus. **[!UICONTROL Schlüsselkennung]**, **[!UICONTROL Team-ID]** und **[!UICONTROL Bundle-ID]** Wählen Sie dann Ihr p8-Zertifikat aus, indem Sie auf **[!UICONTROL Geben Sie den privaten Schlüssel ein...]**. Weitere Informationen zur **[!UICONTROL Token-basierten Authentifizierung]** finden Sie in der [Apple-Dokumentation](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Zertifikatbasierte Authentifizierung]**: Klicken Sie auf **[!UICONTROL Zertifikat angeben...]**. Wählen Sie dann Ihren p12-Schlüssel und geben Sie das vom Entwickler der Mobile App bereitgestellte Passwort ein.
   Sie können Ihren Authentifizierungsmodus später im **[!UICONTROL Zertifikat]** in Ihrer Mobile App.

1. Verwenden Sie die **[!UICONTROL Verbindung testen]** zur Validierung Ihrer Konfiguration.

1. Nun können Sie die Produktionsanwendung konfigurieren, indem Sie auf **[!UICONTROL Weiter]** klicken und nach dem gleichen Verfahren wie oben beschrieben vorgehen.

1. Klicken Sie auf **[!UICONTROL Beenden]**.

Ihre iOS-Anwendung kann jetzt in Campaign verwendet werden.

>[!TAB Android]

Gehen Sie wie folgt vor, um eine App für Android-Geräte zu erstellen:

1. Auswählen **[!UICONTROL Android-Anwendung erstellen]** und klicken Sie auf **[!UICONTROL Nächste]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Geben Sie den Namen Ihrer App im **[!UICONTROL Titel]** -Feld.
1. Der Integrationsschlüssel ist für jede Anwendung spezifisch. Dadurch wird die Mobile App mit Adobe Campaign verknüpft.

   Stellen Sie sicher, dass dasselbe **[!UICONTROL Integrationsschlüssel]** wird in Adobe Campaign und im Anwendungscode über das SDK definiert.

   Wenn Sie das Campaign SDK verwenden, erfahren Sie mehr unter [diese Seite](../config/push-config.md).

   Wenn Sie das Adobe Experience Platform SDK (Datenerfassung) verwenden, erfahren Sie mehr unter [diese Seite](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > Der **[!UICONTROL Integrationsschlüssel]** kann mit einem Zeichenfolgenwert vollständig angepasst werden, muss jedoch mit dem im SDK angegebenen Schlüssel identisch sein.

1. Wählen Sie das Symbol aus dem **[!UICONTROL Anwendungssymbol]** -Feld, um die Mobile App in Ihrem Dienst zu personalisieren.
1. Auswählen **HTTP v1** in  **[!UICONTROL API-Version]** Dropdown-Liste.
1. Klicken **[!UICONTROL Projekt-JSON-Datei laden , um Projektdetails zu extrahieren..]** -Link, um Ihre JSON-Schlüsseldatei zu laden. Weitere Informationen zum Extrahieren Ihrer JSON-Datei finden Sie unter [Dokumentation zu Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   Sie können auch die folgenden Details manuell eingeben:
   * **[!UICONTROL Projektkennung]**
   * **[!UICONTROL Privater Schlüssel]**
   * **[!UICONTROL Client-E-Mail]**

1. Verwenden Sie die **[!UICONTROL Verbindung testen]** zur Validierung Ihrer Konfiguration.

   >[!CAUTION]
   >
   >Die **[!UICONTROL Verbindung testen]** -Schaltfläche überprüft nicht, ob der MID-Server Zugriff auf den FCM-Server hat.

1. (Optional) Sie können den Inhalt einer Push-Nachricht mit einigen **[!UICONTROL Anwendungsvariablen]** bei Bedarf. Diese sind vollständig anpassbar; ein Teil der Payload der Nachricht wird an das Mobilgerät gesendet.

1. Klicken Sie auf **[!UICONTROL Beenden]** und danach auf **[!UICONTROL Speichern]**. Ihre Android-Anwendung kann jetzt in Campaign verwendet werden.

Im Folgenden finden Sie die FCM-Payload-Namen, mit denen Sie Ihre Push-Benachrichtigung weiter personalisieren können:

| Nachrichtentyp | Konfigurierbares Nachrichtenelement (FCM-Payload-Name) | Konfigurierbare Optionen (Name der FCM-Payload) |
|:-:|:-:|:-:|
| Datennachricht | K. A. | validate_only |
| Benachrichtigungsinhalt | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## Erstellen der ersten Push-Benachrichtigung{#push-create}

In diesem Abschnitt werden die Elemente beschrieben, die für den Versand von iOS- und Android-Benachrichtigungen erforderlich sind.

>[!CAUTION]
>
>Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) ist die Mobile-Registrierung jetzt **asynchron**. [Weitere Informationen](../architecture/staging.md)

Um einen neuen Versand zu erstellen, gehen Sie zur Registerkarte **[!UICONTROL Kampagnen]**, klicken Sie auf **[!UICONTROL Sendungen]** und anschließend auf die Schaltfläche **[!UICONTROL Erstellen]** oberhalb der Liste der vorhandenen Sendungen.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

Gehen Sie wie folgt vor, um Benachrichtigungen auf iOS-Geräten zu senden:

1. Wählen Sie die Versandvorlage **[!UICONTROL iOS-Versand]**.

   ![](assets/push_ios_1.png)

1. Klicken Sie zur Bestimmung der Zielgruppe der Benachrichtigung auf den Link **[!UICONTROL An]** und anschließend auf **[!UICONTROL Hinzufügen]**.

   ![](assets/push_ios_2.png)

1. Wählen Sie **[!UICONTROL Abonnenten einer iOS-Mobile-App (iPhone, iPad)]**, dann den Ihrer Mobile App entsprechenden Dienst und anschließend die iOS-Version der Mobile App.

   ![](assets/push_ios_3.png)

1. Wählen Sie Ihre **[!UICONTROL Art der Benachrichtigung]** aus **[!UICONTROL Allgemeine Benachrichtigung (Warnung, Ton, Badge)]** oder **[!UICONTROL Stille Benachrichtigung]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >Im Modus **Silent Push** kann eine &quot;stille&quot; Benachrichtigung an eine Mobile App gesendet werden. Dem Benutzer wird das Eintreffen der Benachrichtigung nicht mitgeteilt. Sie wird direkt an die Mobile App übertragen.

1. Geben Sie in das Feld **[!UICONTROL Titel]** die Bezeichnung ein, die in der Liste der im Benachrichtigungscenter verfügbaren Benachrichtigungen erscheinen soll.

   In diesem Feld können Sie den Wert des Parameters **title** der iOS-Benachrichtigungs-Payload definieren.

1. Sie können einen **[!UICONTROL Untertitel]** hinzufügen, den Wert des Parameters **subtitle** der iOS-Benachrichtigungs-Payload.

1. Geben Sie den Inhalt der Nachricht im Abschnitt **[!UICONTROL Nachrichteninhalt]** des Assistenten ein.

1. In der Registerkarte **[!UICONTROL Ton und Badge]** können Sie die folgenden Optionen bearbeiten:

   * **[!UICONTROL Badge entfernen]**: Aktivieren Sie diese Optionen, um den Badge-Wert zu aktualisieren.

   * **[!UICONTROL Wert]**: Legen Sie eine Zahl fest, mit der die Anzahl der neuen ungelesenen Informationen direkt auf dem Anwendungssymbol angezeigt wird.

   * **[!UICONTROL Kritischer Alarmmodus]**: Aktivieren Sie diese Option, um Ihrer Benachrichtigung einen Ton hinzuzufügen, selbst wenn das Handy des Benutzers im Fokusmodus eingestellt ist oder wenn das iPhone stummgeschaltet ist.

   * **[!UICONTROL Name]**: Wählen Sie den Ton aus, der beim Erhalt der Benachrichtigung vom Mobilgerät abgespielt werden soll.

   * **[!UICONTROL Lautstärke]**: Lautstärke Ihres Tons auf einer Skala von 0 bis 100.

      >[!NOTE]
      > 
      >Töne müssen in die App integriert und zum Zeitpunkt der Erstellung des entsprechenden Service konfiguriert werden.
   ![](assets/push_ios_5.png)

1. Ihre **[!UICONTROL Anwendungsvariablen]** werden automatisch von der Registerkarte **[!UICONTROL Anwendungsvariablen]** hinzugefügt. Damit können Sie beispielsweise das Benachrichtigungsverhalten definieren. So können Sie einen speziellen Anwendungsbildschirm konfigurieren, der angezeigt wird, wenn der Benutzer die Benachrichtigung aktiviert.

1. Auf der Registerkarte **[!UICONTROL Erweitert]** können Sie die folgenden allgemeinen Optionen bearbeiten:

   * **[!UICONTROL Veränderlicher Inhalt]**: Aktivieren Sie diese Option, damit die Mobile App Medieninhalte herunterladen kann.

   * **[!UICONTROL Thread-ID]**: Kennung, die verwendet wird, um verknüpfte Benachrichtigungen zu gruppieren.

   * **[!UICONTROL Kategorie]**: Name Ihrer Kategorie-ID, über die Aktionsschaltflächen angezeigt werden. Mit diesen Benachrichtigungen können Benutzer rascher unterschiedliche Aufgaben ausführen, ohne die Anwendung öffnen oder darin navigieren zu müssen.

   ![](assets/push_ios_6.png)

1. Für zeitabhängige Benachrichtigungen können Sie die folgenden Optionen spezifizieren:

   * **[!UICONTROL ID des Zielinhalts]**: Kennung, die angibt, welches Anwendungsfenster beim Öffnen der Benachrichtigung in den Vordergrund gebracht werden soll.

   * **[!UICONTROL Startbild]**: Name der anzuzeigenden Startbilddatei. Wenn der Benutzer Ihre Anwendung starten möchte, wird das ausgewählte Bild anstelle des Startbildschirms Ihrer Anwendung angezeigt.

   * **[!UICONTROL Unterbrechungsgrad]**:

      * **[!UICONTROL Aktiv]**: Ist dies als Standardeinstellung festgelegt, wird die Benachrichtigung sofort angezeigt, der Bildschirm wird beleuchtet und eventuell wird ein Ton abgespielt. Benachrichtigungen umgehen nicht den Fokusmodus.

      * **[!UICONTROL Passiv]**: Die Benachrichtigung wird zur Benachrichtigungsliste hinzugefügt, ohne dass der Bildschirm beleuchtet oder ein Ton abgespielt wird. Benachrichtigungen umgehen nicht den Fokusmodus.

      * **[!UICONTROL Zeitabhängig]**: Die Benachrichtigung wird sofort angezeigt, der Bildschirm wird beleuchtet, eventuell wird ein Ton abgespielt und der Fokusmodus kann umgangen werden. Für diese Stufe ist keine spezielle Berechtigung von Apple erforderlich.

      * **[!UICONTROL Kritisch]**: Die Benachrichtigung wird sofort angezeigt, der Bildschirm wird beleuchtet und der Stummschaltungs- oder Fokusmodus wird umgangen. Beachten Sie, dass für diese Ebene eine spezielle Berechtigung von Apple erforderlich ist.
   * **[!UICONTROL Relevanzwert]**: Legen Sie einen Relevanzwert auf der Skala von 0 bis 100 fest. Das System verwendet diesen Wert, um die Benachrichtigungen in der Benachrichtigungszusammenfassung zu sortieren.

   ![](assets/push_ios_7.png)

1. Klicken Sie nach Angabe aller erforderlichen Benachrichtigungsparameter auf den Tab **[!UICONTROL Vorschau]**, um das Rendering der Benachrichtigung zu prüfen.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Gehen Sie wie folgt vor, um Benachrichtigungen auf Android-Geräten zu senden:

1. Wählen Sie die Versandvorlage **[!UICONTROL Android-Versand (Android)]**.

   ![](assets/push-template-android.png)

1. Klicken Sie zur Bestimmung der Zielgruppe der Benachrichtigung auf den Link **[!UICONTROL An]** und anschließend auf **[!UICONTROL Hinzufügen]**.

   ![](assets/push-android-select-target.png)

1. Wählen Sie **[!UICONTROL Abonnenten einer Android-Mobile-App]**, dann den Ihrer Mobile App entsprechenden Dienst (hier Neotrips) und schließlich die Android-Version der App.

   ![](assets/push-android-subscribers.png)

1. Erfassen Sie den Inhalt der Benachrichtigung.

   ![](assets/push-android-content.png)

1. Klicken Sie auf das Symbol **[!UICONTROL Emoticon einfügen]**, um Ihrer Push-Benachrichtigung Emoticons hinzuzufügen.

1. Geben Sie im Feld **[!UICONTROL Anwendungsvariablen]** den Wert der einzelnen Variablen ein. Sie können beispielsweise einen bestimmten Anwendungsbildschirm konfigurieren, der angezeigt wird, wenn der Benutzer die Benachrichtigung aktiviert.

1. Klicken Sie nach Angabe aller erforderlichen Benachrichtigungsparameter auf den Tab **[!UICONTROL Vorschau]**, um das Rendering der Benachrichtigung zu prüfen.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Push-Benachrichtigungen testen, senden und überwachen

Um einen Testversand durchzuführen und den endgültigen Versand durchzuführen, gehen Sie genauso vor wie bei anderen Sendungen.

Erfahren Sie, wie Sie einen Versand validieren in [diese Seite](preview-and-proof.md).

Erfahren Sie, wie Sie den Versand bestätigen und durchführen können in [diese Seite](send.md)

Nach dem Nachrichtenversand können Sie Ihre Sendungen überwachen und verfolgen. Weitere Informationen zu Ursachen für fehlgeschlagene Push-Benachrichtigungen finden Sie unter [diese Seite](delivery-failures.md#push-error-types).


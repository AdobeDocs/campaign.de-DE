---
product: campaign
title: Künftige Änderungen am Push-Benachrichtigungskanal
description: Künftige Änderungen am Push-Benachrichtigungskanal
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="Gilt auch für Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="Gilt für Campaign v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: a280e560a6e84f5afa214daaded9ac5331018d7c
workflow-type: tm+mt
source-wordcount: '1413'
ht-degree: 55%

---

# Änderungen am Push-Benachrichtigungskanal {#push-upgrade}

Sie können Campaign verwenden, um Push-Benachrichtigungen auf iOS- und Android-Geräten zu senden. Dazu nutzt Campaign Mobile-App-Abonnementdienste.

Einige wichtige Änderungen am Android Firebase Cloud Messaging (FCM)-Dienst werden 2024 veröffentlicht und können sich auf Ihre Adobe Campaign-Implementierung auswirken. Ihre Konfiguration der Anmeldedienste für Android-Push-Nachrichten muss möglicherweise aktualisiert werden, um diese Änderung zu unterstützen.

Darüber hinaus empfiehlt Adobe dringend, zur Token-basierten Verbindung zu APNs zu wechseln, anstatt zu einer bestimmten, sichereren und skalierbaren Verbindung zu wechseln.

## Google Android Firebase Cloud Messaging (FCM)-Dienst {#fcm-push-upgrade}

### Was hat sich geändert? {#fcm-changes}

Im Rahmen der kontinuierlichen Bemühungen von Google, seine Dienste zu verbessern, werden die veralteten FCM-APIs am **20. Juni 2024** eingestellt. Weitere Informationen zum HTTP-Protokoll von Firebase Cloud Messaging finden Sie in der [Google Firebase-Dokumentation](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 und Adobe Campaign v8 unterstützen bereits die neuesten APIs zum Senden von Push-Benachrichtigungen. Einige alte Implementierungen sind jedoch weiterhin auf die alten APIs angewiesen. Diese Implementierungen müssen aktualisiert werden.

### Sind Sie betroffen? {#fcm-impact}

Wenn Ihre aktuelle Implementierung Anmeldedienste unterstützt, die über die veralteten APIs eine Verbindung zu FCM herstellen, sind Sie betroffen. Der Übergang zu den neuesten APIs ist obligatorisch, um eine Dienstverzerrung zu vermeiden. In diesem Fall werden Adobe-Teams Kontakt mit Ihnen aufnehmen.

Um zu überprüfen, ob Sie betroffen sind, können Sie Ihre **Dienste und Abonnements** mit dem untenstehenden Filter filtern:

![](assets/filter-services-fcm.png)


* Wenn einer Ihrer aktiven Push-Benachrichtigungsdienste die **(veraltete) HTTP-API** verwendet, ist Ihr Setup direkt von dieser Änderung betroffen. Sie müssen Ihre aktuellen Konfigurationen überprüfen und zu den neueren APIs wechseln, wie unten beschrieben.

* Wenn Ihr Setup ausschließlich die **HTTP-v1**-API für Android-Push-Benachrichtigungen verwendet, sind Sie bereits konform und es sind keine weiteren Maßnahmen Ihrerseits erforderlich.

### Wie wird die Aktualisierung durchgeführt? {#fcm-transition-procedure}

#### Voraussetzungen {#fcm-transition-prerequisites}

* Für Campaign Classic v7 wurde die Unterstützung von HTTP v1 in Version 20.3.1 hinzugefügt. Wenn Ihre Umgebung auf einer älteren Version ausgeführt wird, besteht eine Voraussetzung für die Umstellung auf HTTP v1 darin, Ihre Umgebung auf die [neueste Campaign Classic-Build](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=de){target="_blank"}. Bei Campaign v8 wird HTTP v1 von allen Versionen unterstützt und es ist keine Aktualisierung erforderlich.

* Die JSON-Datei des Kontos des Firebase Admin SDK-Dienstes ist erforderlich, damit die Mobile App auf HTTP v1 verschoben wird. In der [Dokumentation zu Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"} erfahren Sie, wie Sie diese Datei erhalten.

* Bei Hybrid-, gehosteten und Managed Services-Bereitstellungen wenden Sie sich neben dem unten beschriebenen Übergangsverfahren an Adobe, um Ihren Echtzeit-Ausführungsserver (RT) zu aktualisieren. Der Mid-Sourcing-Server ist nicht betroffen.

* On-Premise-Benutzende von Campaign Classic v7 wie Sie müssen sowohl die Marketing- als auch die Echtzeit-Ausführungs-Server aktualisieren. Der Mid-Sourcing-Server ist nicht betroffen.

#### Übergangsverfahren {#fcm-transition-steps}

Gehen Sie wie folgt vor, um Ihre Umgebung auf HTTP v1 zu verschieben:

1. Navigieren Sie zu Ihrer Liste von **Diensten und Abonnements**.
1. Listen Sie alle Mobile Apps auf, die die **(veraltete) HTTP-API-Version** verwenden.
1. Legen Sie für jede dieser Mobile Apps die **API-Version** auf **HTTP v1** fest.
1. Klicken Sie auf den Link **[!UICONTROL Projekt-JSON-Datei zum Extrahieren der Projektdetails laden…]**, um Ihre JSON-Schlüsseldatei direkt zu laden.

   Sie können auch die folgenden Details manuell eingeben:

   * **[!UICONTROL Projektkennung]**
   * **[!UICONTROL Privater Schlüssel]**
   * **[!UICONTROL Client-E-Mail]**

   ![](assets/android-http-v1-config.png)

1. Klicken Sie auf **[!UICONTROL Verbindung testen]**, um zu prüfen, ob Ihre Konfiguration korrekt ist und ob der Marketing-Server Zugriff auf den FCM-Server hat. Beachten Sie bei Mid-Sourcing-Bereitstellungen, dass die Schaltfläche **[!UICONTROL Verbindung testen]** nicht überprüfen kann, ob der Server Zugriff auf den Android Firebase Cloud Messaging(FCM)-Dienst hat.
1. Bei Bedarf können Sie die Inhalte von Push-Nachrichten mit bestimmten **[!UICONTROL Anwendungsvariablen]** anreichern. Diese sind vollständig anpassbar; ein Teil der Payload der Nachricht wird an das Mobilgerät gesendet.
1. Klicken Sie auf **[!UICONTROL Beenden]** und danach auf **[!UICONTROL Speichern]**.

Im Folgenden finden Sie die FCM-Payload-Namen, mit denen Sie Ihre Push-Benachrichtigung weiter personalisieren können. Diese Optionen werden [hier](#fcm-apps) im Detail beschrieben.

| Nachrichtentyp | Konfigurierbares Nachrichtenelement (FCM-Payload-Name) | Konfigurierbare Optionen (Name der FCM-Payload) |
|:-:|:-:|:-:|
| Datennachricht | K. A. | validate_only |
| Benachrichtigungsinhalt | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Sobald diese Änderungen auf allen Ihren Servern vorgenommen wurden, verwenden alle neuen Sendungen von Push-Benachrichtigungen an Android-Geräte die HTTP v1 API. Für bestehende Push-Sendungen, die gerade erneut versucht werden, gestartet sind oder verwendet werden, wird weiterhin die (veraltete) HTTP-API verwendet.

### Wie wirkt sich dies auf meine Android-Apps aus? {#fcm-apps}

Es sind keine spezifischen Änderungen am Code der Android Mobile Apps erforderlich, und das Benachrichtigungsverhalten sollte sich nicht ändern.

Mit HTTP v1 können Sie jedoch Ihre Push-Benachrichtigung mit **[!UICONTROL zusätzlichen Optionen für HTTPV1]** weiter personalisieren.

![](assets/android-push-additional-options.png)

Sie haben folgende Möglichkeiten:

* Verwenden Sie das Feld **[!UICONTROL Ticker]**, um den Ticker-Text Ihrer Benachrichtigung festzulegen.
* Verwenden Sie das Feld **[!UICONTROL Bild]**, um die URL des Bildes festzulegen, das in Ihrer Benachrichtigung angezeigt werden soll.
* Verwenden Sie das Feld **[!UICONTROL Anzahl der Benachrichtigungen]**, um festzulegen, dass die Zahl der neuen, ungelesenen Informationen direkt auf dem App-Symbol angezeigt werden soll.
* Setzen Sie die Option **[!UICONTROL Sticky]** auf „false“, damit die Benachrichtigung automatisch verworfen wird, wenn die Benutzenden darauf klicken. Bei der Einstellung „true“ wird die Benachrichtigung weiter angezeigt, auch wenn die Benutzenden darauf klicken.
* Setzen Sie die **[!UICONTROL Benachrichtigungsprioritätsstufe]** Ihrer Benachrichtigung auf Standard, Minimum, niedrig oder hoch.
* Setzen Sie die **[!UICONTROL Sichtbarkeitsstufe]** Ihrer Benachrichtigung auf öffentlich, privat oder geheim.

Weitere Informationen zu den **[!UICONTROL zusätzlichen HTTP v1-Optionen]** und dazu, wie diese Felder auszufüllen sind, finden Sie in der [FCM-Dokumentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.




## Apple iOS Push Notification Service (APNs) {#apns-push-upgrade}

### Was hat sich geändert? {#ios-changes}

Wie von Apple empfohlen, sollten Sie Ihre Kommunikation mit dem Apple Push Notification Service (APNs) mithilfe von stateless-Authentifizierungstoken sichern.

Token-basierte Authentifizierung bietet eine stateless-Möglichkeit, mit APNs zu kommunizieren. Staatenlose Kommunikation ist schneller als zertifikatbasierte Kommunikation, da es keine APNs erfordert, das Zertifikat oder andere Informationen zu Ihrem Provider-Server nachzuschlagen. Die Verwendung der Token-basierten Authentifizierung bietet noch weitere Vorteile:

* Sie können dasselbe Token von mehreren Anbieterservern verwenden.

* Mit einem Token können Sie Benachrichtigungen für alle Apps Ihres Unternehmens verteilen.

Erfahren Sie mehr über Token-basierte Verbindungen zu APNS in [Dokumentation für Apple-Entwickler](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Classic v7 und Adobe Campaign v8 unterstützen sowohl Token-basierte als auch zertifikatbasierte Verbindungen. Wenn Ihre Implementierung auf einer zertifikatbasierten Verbindung basiert, empfiehlt Adobe dringend, sie auf eine Token-basierte Verbindung zu aktualisieren.

### Sind Sie betroffen? {#ios-impact}

Wenn Ihre aktuelle Implementierung für die Verbindung mit APNS auf zertifikatbasierten Anforderungen basiert, sind Sie betroffen. Der Übergang zu einer Token-basierten Verbindung wird empfohlen.

Um zu überprüfen, ob Sie betroffen sind, können Sie Ihre **Dienste und Abonnements** mit dem untenstehenden Filter filtern:

![](assets/filter-services-ios.png)


* Wenn einer Ihrer aktiven Push-Benachrichtigungsdienste die **Zertifikatbasierte Authentifizierung** -Modus (.p12), sollten Ihre aktuellen Implementierungen überprüft und in eine **Token-basierte Authentifizierung** mode (.p8) wie unten beschrieben.

* Wenn Ihr Setup ausschließlich die Funktion **Token-basierte Authentifizierung** -Modus für iOS-Push-Benachrichtigungen verwenden, ist Ihre Implementierung bereits auf dem neuesten Stand und Sie müssen keine weiteren Maßnahmen ergreifen.

### Wie wird die Aktualisierung durchgeführt? {#ios-transition-procedure}

#### Voraussetzungen {#ios-transition-prerequisites}

* Für Campaign Classic v7 die Unterstützung von **Token-basierte Authentifizierung** -Modus wurde in Version 20.2 hinzugefügt. Wenn Ihre Umgebung auf einer älteren Version ausgeführt wird, besteht eine Voraussetzung für diese Änderung darin, Ihre Umgebung auf die [neueste Campaign Classic-Build](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=de){target="_blank"}. Für Campaign v8: **Token-basierte Authentifizierung** -Modus wird von allen Versionen unterstützt und es ist keine Aktualisierung erforderlich.

* Sie benötigen einen Signaturschlüssel des APNs-Authentifizierungstokens, um die Token zu generieren, die Ihr Server verwendet. Sie fordern diesen Schlüssel wie unter [Dokumentation für Apple-Entwickler](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* Bei Hybrid-, gehosteten und Managed Services-Bereitstellungen wenden Sie sich neben dem unten beschriebenen Übergangsverfahren an Adobe, um Ihren Echtzeit-Ausführungsserver (RT) zu aktualisieren. Der Mid-Sourcing-Server ist nicht betroffen.

* On-Premise-Benutzende von Campaign Classic v7 wie Sie müssen sowohl die Marketing- als auch die Echtzeit-Ausführungs-Server aktualisieren. Der Mid-Sourcing-Server ist nicht betroffen.

#### Übergangsverfahren {#ios-transition-steps}

Gehen Sie wie folgt vor, um Ihre mobilen iOS-Anwendungen in den Token-basierten Authentifizierungsmodus zu versetzen:

1. Navigieren Sie zu Ihrer Liste von **Diensten und Abonnements**.
1. Auflisten aller Mobile Apps mit **Zertifikatbasierte Authentifizierung** mode (.p12).
1. Bearbeiten Sie jede dieser Mobile Apps und navigieren Sie zum **Zertifikat/privater Schlüssel** Registerkarte.
1. Aus dem **Authentifizierungsmodus** Dropdown-Liste auswählen **Token-basierte Authentifizierung** mode (.p8).
1. Füllen Sie die APNs-Verbindungseinstellungen aus. **[!UICONTROL Schlüssel-ID]**, **[!UICONTROL Team-ID]** und **[!UICONTROL Bundle-ID]** Wählen Sie dann Ihr p8-Zertifikat aus, indem Sie auf **[!UICONTROL Geben Sie den privaten Schlüssel ein...]**.

   ![](assets/token-based-certif.png)

1. Klicks **[!UICONTROL Verbindung testen]** , um zu überprüfen, ob Ihre Konfiguration korrekt ist und ob der Server Zugriff auf APNs hat. Beachten Sie bei Mid-Sourcing-Bereitstellungen, dass die Variable **[!UICONTROL Verbindung testen]** -Schaltfläche kann nicht überprüfen, ob der Server Zugriff auf APNS hat.
1. Nun können Sie die Produktionsanwendung konfigurieren, indem Sie auf **[!UICONTROL Weiter]** klicken und nach dem gleichen Verfahren wie oben beschrieben vorgehen.
1. Klicken Sie auf **[!UICONTROL Beenden]** und danach auf **[!UICONTROL Speichern]**.

Ihre iOS-Anwendung wird jetzt in den Token-basierten Authentifizierungsmodus versetzt.

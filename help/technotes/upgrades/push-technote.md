---
product: campaign
title: Künftige Änderungen am Push-Benachrichtigungskanal
description: Künftige Änderungen am Push-Benachrichtigungskanal
hide: true
hidefromtoc: true
source-git-commit: fc274e1266d37611c8781a007ccb6a293a683c21
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 24%

---

# Künftige Änderungen am Push-Benachrichtigungskanal {#push-upgrade}

Sie können Campaign verwenden, um Push-Benachrichtigungen auf Android-Geräten zu senden. Dazu benötigt Campaign bestimmte externe Android-Konten und Abonnementdienste. Einige wichtige Änderungen am Android Firebase Cloud Messaging (FCM)-Dienst werden 2024 veröffentlicht und können sich auf Ihre Adobe Campaign-Implementierung auswirken.

## Was hat sich geändert? {#fcm-changes}

Im Rahmen der kontinuierlichen Bemühungen von Google, seine Dienste zu verbessern, werden die veralteten FCM-APIs eingestellt auf **20. Juni 2024**. Weitere Informationen zum Firebase Cloud Messaging-HTTP-Protokoll finden Sie in [Google-Dokumentation](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 und Adobe Campaign v8 unterstützen bereits die neuesten APIs zum Senden von Push-Benachrichtigungen. Einige alte Implementierungen sind jedoch weiterhin auf die Legacy-APIs angewiesen. Diese Implementierungen müssen aktualisiert werden.

## Sind Sie betroffen? {#fcm-impact}

Wenn Ihre aktuelle Implementierung Abonnementdienste unterstützt, die über die veralteten APIs eine Verbindung zu FCM herstellen, sind Sie betroffen. Die Migration zu den neuesten APIs ist obligatorisch, um eine Dienstverzerrung zu vermeiden. In diesem Fall wenden sich Adobe-Teams an Sie.

Um zu überprüfen, ob Sie betroffen sind, können Sie Ihre **Dienste und Abonnements** wie unten beschrieben Filter:

![](assets/filter-services-fcm.png)


* Wenn eine Ihrer aktiven Push-Benachrichtigungskampagnen die Variable **HTTP (veraltet)** API verwenden, wird sich diese Änderung direkt auf Ihr Setup auswirken. Sie müssen Ihre aktuellen Konfigurationen überprüfen und zu den neueren APIs migrieren, wie unten beschrieben.

* Wenn Ihr Setup ausschließlich die Funktion **HTTP v1** API für Android-Push-Benachrichtigungen verwenden, sind Sie bereits konform und es sind keine weiteren Maßnahmen Ihrerseits erforderlich.

## Wie wird die Migration durchgeführt?{#fcm-migration-procedure}

### Voraussetzungen{#fcm-migration-prerequisites}

* Für Campaign Classic v7 wurde die Unterstützung von HTTP v1 in Version 20.3.1 hinzugefügt. Wenn Ihre Umgebung auf einer älteren Version ausgeführt wird, besteht eine Voraussetzung für die Migration auf HTTP v1 darin, Ihre Umgebung auf die [neueste Campaign Classic-Build](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=de){target="_blank"}. Für Campaign v8 wird HTTP v1 von allen Versionen unterstützt. Es ist kein Upgrade erforderlich.

* Um die Migration durchzuführen, ist die JSON-Kontodatei des Android Firebase Admin SDK-Dienstes erforderlich, damit die Mobile App auf HTTPv1 verschoben wird. Mehr dazu erfahren Sie auf [dieser Seite](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Wenden Sie sich bei Hybrid-, gehosteten und Managed Services-Bereitstellungen an Adobe, um Ihren Echtzeitausführungsserver (RT) zu aktualisieren.

### Migrationsverfahren {#fcm-migration-steps}

Um Ihre Umgebung auf HTTP v1 zu migrieren, führen Sie die folgenden Schritte auf Ihren Marketing- und Echtzeitausführungsservern aus:

1. Navigieren Sie zu Ihrer Liste von **Dienste und Abonnements**.
1. Suchen Sie alle Mobile Apps mithilfe der **HTTP (veraltet)** API-Version.
1. Legen Sie für jede dieser Mobile Apps die Variable **API-Version** nach **HTTP v1**.
1. Klicken Sie auf **[!UICONTROL Projekt-JSON-Datei laden , um Projektdetails zu extrahieren..]** -Link, um Ihre JSON-Schlüsseldatei direkt zu laden.

   Sie können auch die folgenden Details manuell eingeben:
   * **[!UICONTROL Projektkennung]**
   * **[!UICONTROL Privater Schlüssel]**
   * **[!UICONTROL Client-E-Mail]**

   ![](assets/android-http-v1-config.png)

1. Klicken Sie auf **[!UICONTROL Verbindung testen]**, um zu prüfen, ob Ihre Konfiguration korrekt ist und ob der Marketing-Server Zugriff auf den FCM-Server hat. Beachten Sie bei Mid-Sourcing-Bereitstellungen, dass die Variable **[!UICONTROL Verbindung testen]** kann nicht überprüfen, ob der Server Zugriff auf den Android Firebase Cloud Messaging (FCM)-Dienst hat.
1. Bei Bedarf können Sie die Inhalte von Push-Nachrichten mit bestimmten **[!UICONTROL Anwendungsvariablen]** anreichern. Diese sind vollständig anpassbar; ein Teil der Payload der Nachricht wird an das Mobilgerät gesendet.
1. Klicken Sie auf **[!UICONTROL Beenden]** und danach auf **[!UICONTROL Speichern]**.

Im Folgenden finden Sie die FCM-Payload-Namen, mit denen Sie Ihre Push-Benachrichtigung weiter personalisieren können. Diese Optionen werden im Detail beschrieben [here](#fcm-apps).

| Nachrichtentyp | Konfigurierbares Nachrichtenelement (FCM-Payload-Name) | Konfigurierbare Optionen (Name der FCM-Payload) |
|:-:|:-:|:-:|
| Datennachricht | K. A. | validate_only |
| Benachrichtigungsinhalt | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Sobald diese Änderungen auf all Ihren Server angewendet werden, verwenden alle neuen Push-Benachrichtigungen, die an Android-Geräte gesendet werden, die HTTP v1-API. Vorhandene Push-Sendungen, die wiederholt, in Bearbeitung und in Verwendung sind, verwenden weiterhin die HTTP-API (frühere Version).

### Wie wirkt sich dies auf meine Android-Apps aus? {#fcm-apps}

Es sind keine spezifischen Änderungen am Code der Android Mobile Apps erforderlich und das Benachrichtigungsverhalten sollte sich nicht ändern.

Mit HTTP v1 können Sie Ihre Push-Benachrichtigung jedoch mit **[!UICONTROL Zusätzliche Optionen für HTTPV1]**.

![](assets/android-push-additional-options.png)

Sie haben folgende Möglichkeiten:

* Verwenden Sie die **[!UICONTROL Ticker]** -Feld, um den Ticker-Text Ihrer Benachrichtigung festzulegen.
* Verwenden Sie die **[!UICONTROL Bild]** -Feld, um die URL des Bildes festzulegen, das in Ihrer Benachrichtigung angezeigt werden soll.
* Verwenden Sie die **[!UICONTROL Benachrichtigungsanzahl]** um die Anzahl der neuen ungelesenen Informationen festzulegen, die direkt auf dem Anwendungssymbol angezeigt werden.
* Legen Sie die **[!UICONTROL Sticky]** auf &quot;false&quot;, damit die Benachrichtigung automatisch verworfen wird, wenn der Benutzer darauf klickt. Bei der Einstellung &quot;Wahr&quot; wird die Benachrichtigung weiter angezeigt, wenn der Benutzer darauf klickt.
* Legen Sie die **[!UICONTROL Benachrichtigungspriorität]** Ebene Ihrer Benachrichtigung auf Standard, Minimum, Niedrig oder Hoch.
* Legen Sie die **[!UICONTROL Sichtbarkeit]** Ebene Ihrer Benachrichtigung an öffentlich, privat oder geheim.

Weitere Informationen zu den **[!UICONTROL zusätzlichen HTTP v1-Optionen]** und dazu, wie diese Felder auszufüllen sind, finden Sie in der [FCM-Dokumentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.


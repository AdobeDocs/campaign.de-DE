---
solution: Campaign v8
product: Adobe Campaign
title: Push-Benachrichtigung mit Adobe Campaign senden
description: Erste Schritte mit Push-Benachrichtigungen in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 22%

---

# Push-Benachrichtigungen erstellen und senden

Mit Mobile-App-Sendungen können Sie Benachrichtigungen an iOS- und Android-Systeme senden.

Um Push-Benachrichtigungen in Adobe Campaign senden zu können, müssen Sie folgende Schritte befolgen:

1. Campaign-Umgebung konfigurieren
1. Erstellen Sie einen Informationsdienst vom Typ Mobile App für Ihre Mobile App.
1. Fügen Sie diesem Dienst die iOS- und Android-Versionen der App hinzu.
1. Erstellen Sie je einen Versand für iOS und Android.

:[!DNL :arrow_upper_right:]: Erfahren Sie mehr über die ersten Schritte mit der mobilen App in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=de)

## Integrieren mit Adobe SDK

### Integrieren des Campaign SDK

Campaign SDK ermöglicht die Integration Ihrer Mobile App in die Adobe Campaign-Plattform.

:[!DNL :arrow_upper_right:]: Informationen zur Integration des Campaign SDK in Ihre App finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk) .

### Konfigurieren der Campaign-Erweiterung in Launch

Sie können das Adobe Experience Platform Launch-SDK mit Campaign integrieren, indem Sie die Campaign Classic-Erweiterung nutzen.

:[!DNL :arrow_upper_right:]: Weitere Informationen finden Sie in der [Adobe Mobile SDK-Dokumentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## App-Einstellungen in Campaign konfigurieren

Sie müssen Ihre iOS- und Android-App-Einstellungen in Adobe Campaign definieren.

:[!DNL :arrow_upper_right:]: Die Konfigurationsrichtlinien für iOS finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages) .

:[!DNL :arrow_upper_right:]: Die Konfigurationsrichtlinien für Android finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages) .

## Erste Push-Benachrichtigung erstellen

:[!DNL :arrow_upper_right:]: Erfahren Sie, wie Sie Ihre ersten Push-Benachrichtigungen in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios) erstellen.


>[!CAUTION]
>
>Mit Campaign v8 ist die mobile Registrierung jetzt **asynchron**. [Weitere Informationen](../dev/staging.md).

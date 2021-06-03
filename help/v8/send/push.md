---
product: Adobe Campaign
title: Versenden von Push-Benachrichtigungen mit Adobe Campaign
description: Erste Schritte mit Push-Benachrichtigungen in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 72%

---

# Push-Benachrichtigungen erstellen und versenden

Sie können mittels Mobile-App-Versand Benachrichtigungen an iOS- und Android-Systeme senden.

Um Push-Benachrichtigungen in Adobe Campaign senden zu können, müssen Sie folgende Schritte befolgen:

1. Campaign-Umgebung konfigurieren
1. Erstellen Sie einen Informations-Service vom Typ &quot;Mobile App&quot; für Ihre Mobile App.
1. Fügen Sie diesem Dienst die iOS- und Android-Versionen der App hinzu.
1. Erstellen Sie je einen Versand für iOS und Android.

[!DNL :arrow_upper_right:] Informationen zu den ersten Schritten mit der mobilen App finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=de)

## Mit Adobe SDK integrieren

### Campaign SDK integrieren

Über das Campaign SDK wird die Integration Ihrer Mobile App in die Adobe Campaign-Plattform umgesetzt.

[!DNL :arrow_upper_right:] Informationen zur Integration des Campaign SDK in Ihre App finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=de#loading-campaign-sdk)

### Campaign-Erweiterung in Launch konfigurieren

Die Integration des Adobe Experience Platform Launch SDK mit Campaign erfolgt über die Campaign Classic-Erweiterung.

[!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zum Mobile SDK für  [Adobe.](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Mobile-App-Einstellungen in Campaign konfigurieren

Sie müssen die Einstellungen Ihrer iOS- bzw. Android-basierten Mobile Apps in Adobe Campaign definieren.

[!DNL :arrow_upper_right:] Die Konfigurationsrichtlinien für iOS werden in der Dokumentation zu  [Campaign Classic v7 beschrieben.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=de#sending-messages)

[!DNL :arrow_upper_right:] Die Konfigurationsrichtlinien für Android werden in der Dokumentation zu  [Campaign Classic v7 beschrieben.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=de#sending-messages)

## Erste Push-Benachrichtigung erstellen

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Ihre ersten Push-Benachrichtigungen in der Dokumentation von  [Campaign Classic v7 erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=de#sending-notifications-on-ios)


>[!CAUTION]
>
>Mit Campaign v8 ist die mobile Registrierung jetzt **asynchron**. [Mehr dazu](../dev/staging.md)

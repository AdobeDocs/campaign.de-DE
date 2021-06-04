---
product: Adobe Campaign
title: Verwaltung von Abonnements und Abmeldungen in Campaign
description: Erfahren Sie, wie Sie Abonnements und Abmeldungen in Campaign v8 verwalten
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: f69d318b4ea767c44f8c19bf0cf45fb1b7001b11
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 37%

---

# Verwaltung von Abonnements und Abmeldungen{#optin-optout}

Mit Adobe Campaign können Sie Informations-Services wie Newsletter erstellen und überwachen und die Abonnements/Abmeldungen für diese verwalten. Dabei können mehrere Services parallel definiert werden, z. B. spezialisierte Newsletter für bestimmte Kategorien, Themen oder Bereiche einer Website, Abonnements zu verschiedenen Arten von Warnmeldungen und Echtzeitbenachrichtigungen. Weiterführende Informationen finden Sie im Abschnitt &quot;Abonnements verwalten&quot;.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie einen Informationsdienst erstellen, Newsletter senden und Opt-in- und Opt-out-Verfahren in der Dokumentation zu  [Campaign Classic v7 verwalten.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=de#sending-messages)

Folgende Optionen stehen zur Anmeldung (Opt-in) für ein Profil für einen Dienst zur Verfügung:

* Fügen Sie den Dienst manuell zum Empfängerprofil hinzu: Klicken Sie dazu im Tab **[!UICONTROL Abonnements]** ihres Profils auf **[!UICONTROL Hinzufügen]** und wählen Sie den entsprechenden Informationsdienst aus.

   ![](assets/subscribe-to-a-service.png)

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)

* automatisch eine Gruppe von Empfängern für den Dienst anmelden. Die Empfängerliste kann aus einem Filtervorgang, einer Gruppe, einem Ordner, einem Import oder einer direkten manuellen Auswahl stammen. Um diese Empfänger anzumelden, wählen Sie die Profile aus und klicken Sie mit der rechten Maustaste darauf. Wählen Sie **[!UICONTROL Aktionen > Auswahl für einen Dienst anmelden...]**, wählen Sie den betreffenden Dienst aus und starten Sie den Vorgang.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)


* Empfänger im Zuge eines Imports für einen Dienst anmelden. Geben Sie im letzten Schritt des Import-Assistenten den gewünschten Dienst an.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients)

* Empfänger melden sich persönlich über ein Webformular an.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in)


* Erstellen Sie einen Zielgruppen-Workflow und verwenden Sie die Aktivität **[!UICONTROL Abonnement-Dienst]** .

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter)


Folgende Optionen stehen zur Abmeldung (Opt-out) eines Profils von einem Dienst zur Verfügung:

**Manuelle Abmeldung**

* Personalisierter Abmelde-Link oder Webformular
* Manuelles Löschen eines Informationsdienstes
* Manuelles Löschen von Empfängern von einem bestimmten Abonnement-Dienst

**Automatische Abmeldung**

* Legen Sie eine maximale Dauer für den Informationsdienst fest: -Empfänger werden automatisch abgemeldet, wenn die Gültigkeitsdauer abgelaufen ist. Dieser Zeitraum wird im Tab Bearbeiten der Diensteigenschaften angegeben. Sie wird in Tagen ausgedrückt.
* Einrichten eines Abmelde-Workflows für eine Population

[!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service)


>[!CAUTION]
>
>Abonnement und Abmeldungen sind **asynchrone** Prozesse. Opt-in und Opt-out-Anfragen werden stündlich verarbeitet. [Mehr dazu](../dev/new-apis.md#sub-apis)

Sie können es Ihren Versandempfängern auch ermöglichen, Nachrichten an Freunde weiterzuleiten. Fügen Sie dazu die entsprechenden Links in Ihren Versand ein. Sie können diesen Freigabeprozess sowie die Anzahl der Besuche auf den betroffenen Seiten tracken.

[!DNL :arrow_upper_right:] Weitere Informationen zu dieser Funktion finden Sie in der  [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend).
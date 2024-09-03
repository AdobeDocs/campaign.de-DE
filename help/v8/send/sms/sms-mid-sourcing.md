---
title: SMS in einer Mid-Sourcing-Infrastruktur
description: Erfahren Sie, wie Sie einen SMS-Versand in einer Mid-Sourcing-Infrastruktur konfigurieren.
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 11%

---


# SMS in einer Mid-Sourcing-Infrastruktur {#sms-mid}

>[!IMPORTANT]
>
>Diese Dokumentation gilt für Adobe Campaign v8.7.2 und höher.
>
>Für ältere Versionen lesen Sie bitte die [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

Für den SMS-Versand mit einer Mid-Sourcing-Infrastruktur ist Folgendes erforderlich:

1. Ein SMS-Operator auf dem Mid-Server. [Erfahren Sie hier, wie Sie ihn erstellen](#sms-operator-mid)
1. Ein externes SMS-Konto auf dem Marketing-Server, das den zuvor erstellten Benutzer verwendet. [Erfahren Sie hier, wie Sie ihn erstellen](#sms-external-account)
1. Ein externes SMPP-Konto auf dem Mid-Server, das den Bereitstellungsmodus für Kanal und Mid-Sourcing angibt. [Erfahren Sie hier, wie Sie ihn erstellen](#smpp-external-account-mid)
1. Eine Versandvorlage, die auf das externe Konto verweist, um den Versandprozess zu optimieren. [Erfahren Sie hier, wie Sie ihn erstellen](#sms-delivery-template)

## SMS-Operator auf dem Mid-Server erstellen {#sms-operator-mid}

Erstellen Sie zunächst einen SMS-Operator auf dem Mid-Server, der vom externen SMS-Konto auf dem Marketing-Server verwendet wird.

Gehen Sie wie folgt vor, um einen SMS-Benutzer zu erstellen:

1. Klicken Sie in &quot;**[!UICONTROL Administration]**&quot;> &quot;**[!UICONTROL Zugriffsverwaltung]**&quot;> &quot;**[!UICONTROL Benutzer]**&quot; auf &quot;**[!UICONTROL Neu]**&quot; und füllen Sie das Formular im neu geöffneten Fenster aus.

   * **[!UICONTROL Name (Login)]** und **[!UICONTROL Titel]** sind obligatorisch.
   * Das Kennwort ist nicht obligatorisch, wird aber für die Sicherheit dringend empfohlen.

   Beachten Sie, dass der Name (Login) später verwendet werden soll, um Ihr externes SMPP-Konto im Mid-Server zu benennen.

   ![](assets/smsoperator_mid.png){zoomable="yes"}

1. Klicken Sie im Teil **[!UICONTROL Gruppen und spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** .
Wählen Sie im geöffneten neuen Fenster **[!UICONTROL Spezifische Berechtigungen]** in der Liste **[!UICONTROL Ordner]** und dann **[!UICONTROL ADMINISTRATION]** in der rechten Liste.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL OK]** .

   ![](assets/smsoperator_rights.png){zoomable="yes"}

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]** , um die Erstellung Ihres SMS-Operators abzuschließen.

   ![](assets/smsoperator_save.png){zoomable="yes"}

Sie können sie jetzt in der Benutzerliste sehen.

![](assets/smsoperator_list.png){zoomable="yes"}

## Erstellen eines externen SMS-Kontos auf dem Marketing-Server {#sms-external-account}

In einer Mid-Infrastruktur müssen Sie wie unten gezeigt ein externes SMS-Konto auf dem Marketing-Server erstellen

>[!IMPORTANT]
>
>Die Verwendung desselben Kontos und Kennworts für mehrere externe SMS-Konten kann zu Konflikten und Überschneidungen zwischen den Konten führen. Weitere Informationen finden Sie auf der Seite [SMS-Fehlerbehebung](smpp-connection.md#sms-troubleshooting).

1. Klicken Sie in **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Externe Konten]** auf das Symbol **[!UICONTROL Neu]** .

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. Richten Sie den **[!UICONTROL Titel]** und den **[!UICONTROL internen Namen]** Ihres externen Kontos ein. Definieren Sie den Kontotyp als &quot;**[!UICONTROL Routing]**&quot;, aktivieren Sie das Feld &quot;**[!UICONTROL Aktiviert]**&quot;, wählen Sie &quot;**[!UICONTROL Mobiltelefon (SMS)]**&quot; für den Kanal und &quot;**[!UICONTROL Mid-Sourcing]**&quot;für den Versandmodus.

   ![](assets/mid_smsextaccount.png){zoomable="yes"}

1. Füllen Sie im Tab **[!UICONTROL Mid-Sourcing]** das Formular mit der Mid-Sourcing-Server-URL und dem zuvor auf dem Mid-Sourcing-Server erstellten SMS-Operator aus.

   Bestätigen Sie die Verbindung, indem Sie auf **[!UICONTROL Verbindung testen]** klicken.

   ![](assets/midtab_smsextaccount.png){zoomable="yes"}

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Erstellen eines externen SMPP-Kontos auf dem Mid-Server {#smpp-external-account-mid}

>[!IMPORTANT]
>
>Die Verwendung desselben Kontos und Kennworts für mehrere externe SMS-Konten kann zu Konflikten und Überschneidungen zwischen den Konten führen. Siehe die [Seite zur SMS-Fehlerbehebung](smpp-connection.md#sms-troubleshooting).

Das Ziel besteht nun darin, Ihr externes SMPP-Konto auf dem Mid-Server einzurichten.

Gehen Sie dazu wie folgt vor:

1. Klicken Sie in **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Externe Konten]** des Mid-Servers auf das Symbol **[!UICONTROL Neu]** .

1. Richten Sie den **[!UICONTROL Titel]** und den **[!UICONTROL internen Namen]** Ihres externen Kontos ein.

   >[!WARNING]
   >
   >Achten Sie bei der Zuweisung eines internen Namens auf die angegebene Namenskonvention: `SMS Operator Name_Internal Name of the Marketing SMS external account`.
   >

   Definieren Sie den Kontotyp als &quot;**[!UICONTROL Routing]**&quot;, aktivieren Sie das Feld &quot;**[!UICONTROL Aktiviert]**&quot;, wählen Sie &quot;**[!UICONTROL Mobiltelefon (SMS)]**&quot; für den Kanal und &quot;**[!UICONTROL Gebündelter Versand]**&quot; für den Versandmodus.
   ![](assets/mid_extaccount.png){zoomable="yes"}

1. Behalten Sie auf der Registerkarte **[!UICONTROL Mobil]** den Eintrag **[!UICONTROL Erweitertes allgemeines SMPP]** in der Dropdownliste **[!UICONTROL Connector]** bei.

   Das Kontrollkästchen **[!UICONTROL Nachrichten über einen dedizierten Prozess senden]** ist standardmäßig aktiviert.

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   Um die Verbindung einzurichten, müssen Sie die Registerkarten dieses Formulars ausfüllen. Weitere Informationen finden Sie unter [ mehr über das externe SMPP-Konto](smpp-external-account.md#smpp-connection-settings).

## Versandvorlage konfigurieren {#sms-delivery-template}

Um die Erstellung Ihres SMS-Versands zu erleichtern, erstellen Sie eine SMS-Versandvorlage, in der alle Ihre Einstellungen referenziert sind.

Klicken Sie unter **[!UICONTROL Ressourcen]** > **[!UICONTROL Vorlagen]** > **[!UICONTROL Versandvorlagen]** auf dem Marketing-Server mit der rechten Maustaste auf die vorhandene Mobile-Versandvorlage und wählen Sie **[!UICONTROL Duplizieren]** aus.

![](assets/sms_template_duplicate.png){zoomable="yes"}

Ändern Sie die **[!UICONTROL Beschriftung]** und den **[!UICONTROL internen Namen]** Ihrer Vorlage, um sie leicht zu erkennen, und klicken Sie auf die Schaltfläche **[!UICONTROL Eigenschaften]** .

![](assets/sms_template_name.png){zoomable="yes"}

Wählen Sie auf der Registerkarte **[!UICONTROL Allgemein]** in **[!UICONTROL Routing]** Ihr externes SMPP-Konto aus.

![](assets/mid_template.png){zoomable="yes"}

Auf der Registerkarte **[!UICONTROL SMS]** können Sie optionale Parameter zu Ihrer Vorlage hinzufügen.

![](assets/sms_template_properties.png){zoomable="yes"}

[Erfahren Sie mehr über diese Konfiguration der Registerkarte &quot;SMS&quot;](sms-delivery-settings.md).
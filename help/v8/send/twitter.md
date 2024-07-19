---
title: Posten von Nachrichten auf X (Twitter) mit Adobe Campaign
description: Erfahren Sie, wie Sie mit dem Social-Media-Marketing-Modul von Adobe Campaign Nachrichten auf X (ehemals Twitter) posten und Direktnachrichten an Ihre Follower senden können.
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 100%

---


# Posten von Nachrichten auf X (Twitter) mit Adobe Campaign {#post-tw-messages}

Adobe Campaign enthält das Modul **Social-Media-Marketing**, mit dem Sie über X (ehemals Twitter) mit Ihrer Kundschaft sowie interessierten Personen interagieren können.

Nach der Konfiguration der Integration haben Sie folgende Möglichkeiten:

* Senden von Direktnachrichten an Ihre Follower
* Posten auf Ihrem X-Konto
* Sammeln Sie neue Kontakte, indem Sie die Profildaten abrufen, um auf der Basis dieser Daten Zielgruppen-Kampagnen durchzuführen und Cross-Channel-Strategien anzuwenden. Diese Aktion erfordert die Benutzerzustimmung.


Die Konfigurationsschritte zur Integration Ihres X-Kontos mit Adobe Campaign werden auf [dieser Seite](../connect/ac-tw.md) beschrieben.

## Erstellen und Veröffentlichen eines X-Beitrags {#publish-on-tw}

Gehen Sie wie folgt vor, um eine Nachricht auf Ihrem X-Konto zu posten:

1. Erstellen eines X-Versands

   Erstellen Sie einen neuen Versand anhand der Versandvorlage **[!UICONTROL Tweet (Twitter)]**.

   ![](assets/tw-new-delivery.png)

1. Wählen Sie die Hauptzielgruppe aus.      

   Wählen Sie die Konten aus, an die Sie Beiträge senden möchten.

   ![](assets/tw-define-target.png)

   1. Wählen Sie den Link **[!UICONTROL An]** aus.
   1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**.
   1. Wählen Sie **[!UICONTROL Twitter-Konto]** aus.
   1. Wählen Sie im Feld **[!UICONTROL Ordner]** den Dienstordner aus, der das X-Konto enthält. Wählen Sie dann das X-Konto aus, an das Sie Ihren Tweet senden möchten.

1. Auswählen der Zielgruppe für den Testversand

   Über die Registerkarte **[!UICONTROL Testversand-Zielgruppe]** können Sie das Twitter-Konto festlegen, das Sie für Testsendungen vor dem endgültigen Versand verwenden möchten.

   Wie in den [Konfigurationsschritten](../connect/ac-tw.md#tw-test-account) beschrieben, müssen Sie ein privates X-Testkonto für den Testversand erstellen.

   >[!NOTE]
   >
   >Wenn Sie dasselbe X-Testkonto für alle Sendungen verwenden, können Sie die Testversand-Zielgruppe in der Versandvorlage **[!UICONTROL Tweet]** speichern, auf die über den Knoten **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** zugegriffen werden kann. Die Testversand-Zielgruppe wird dann standardmäßig bei jedem neuen Versand eingegeben.

1. Definieren des Inhalts Ihres Tweets

   Geben Sie den Inhalt Ihres Tweets auf der Registerkarte **[!UICONTROL Inhalt]** ein.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Beim Posten auf X gelten die folgenden Einschränkungen:
   >
   >* Die Nachricht darf nicht länger als 140 Zeichen sein.
   >* Das HTML-Format wird nicht unterstützt.
   >

1. Vorschau des Tweets

   Durchsuchen Sie die Registerkarte **[!UICONTROL Vorschau]**, um das Rendering Ihres Tweets zu überprüfen.

   ![](assets/tw-delivery-preview.png)

   1. Klicken Sie auf die Registerkarte **[!UICONTROL Vorschau]**.
   1. Klicken Sie auf das Dropdown-Menü **[!UICONTROL Personalisierung testen]** und wählen Sie **[!UICONTROL Dienst]** aus.
   1. Wählen Sie im Feld **[!UICONTROL Ordner]** den Dienstordner aus, der Ihr X-Konto enthält.

1. Durchführen eines Testversands

   Bevor Sie Ihren Tweet posten, überprüfen Sie ihn anhand eines Testversands. Sie erhalten dann ein exaktes Rendering des veröffentlichten Tweets auf einer privaten X-Testseite.

1. Posten der Nachricht

   1. Nachdem der Inhalt validiert wurde, klicken Sie auf die Schaltfläche **[!UICONTROL Senden]**.
   1. Wählen Sie **[!UICONTROL Sendungen schnellstmöglich abschicken]** aus und klicken Sie auf die Schaltfläche **[!UICONTROL Analysieren]**.
   1. Überprüfen Sie nach Abschluss der Analyse das Ergebnis.
   1. Klicken Sie auf **[!UICONTROL Absendung bestätigen]** und dann auf **[!UICONTROL Ja]**.

## Senden von Direktnachrichten an Follower {#direct-tw-messages}

Der technische Workflow **[!UICONTROL Twitter-Konten synchronisieren]** erfasst die Liste der X-Follower, sodass Sie ihnen Direktnachrichten senden können. [Weitere Informationen](../connect/ac-tw.md#synchro-tw-accounts)

Gehen Sie wie folgt vor, um Direktnachrichten an Ihre Follower zu senden:

1. Erstellen Sie einen X-Versand unter Verwendung der integrierten Versandvorlage **[!UICONTROL Twittern (Direktnachricht)]**.

1. Wählen Sie die Hauptzielgruppe aus.

   ![](assets/tw-dm-define-target.png)

   1. Klicken Sie auf den Link **[!UICONTROL An]** und anschließend auf den Button **[!UICONTROL Hinzufügen]**.

   1. Wählen Sie den Typ der Zielgruppenbestimmung

      * Wählen Sie **[!UICONTROL Twitter-Abonnenten]** aus, um eine Direktnachricht an alle Ihre Follower zu senden.

      * Wählen Sie **[!UICONTROL Filterbedingungen]** aus, um eine Abfrage zu definieren und deren Ergebnis anzuzeigen. Erfahren Sie in [diesem Abschnitt](../audiences/create-filters.md#advanced-filters), wie Sie einen Filter erstellen können.

1. Wählen Sie auf der Registerkarte **[!UICONTROL Testversand-Zielgruppe]** die Zielgruppe für den Testversand aus: Dieses Konto wird den Testversand Ihrer Direktnachricht erhalten.

   Wie in den [Konfigurationsschritten](../connect/ac-tw.md#tw-test-account) beschrieben, müssen Sie ein privates X-Testkonto für den Testversand erstellen.


   >[!NOTE]
   >
   >Wenn Sie alle Ihre Testsendungen für Direktnachrichten an dasselbe X-Konto senden möchten, können Sie die Testversand-Zielgruppe in der Versandvorlage **[!UICONTROL Twittern (Direktnachricht)]** speichern, auf die Sie über den Knoten **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** zugreifen können.

1. Geben Sie in der Registerkarte **[!UICONTROL Inhalt]** den Inhalt der Nachricht ein.

   ![](assets/tw-dm-content.png)

   Personalisierungsfelder können auf dieselbe Weise wie für E-Mail-Sendungen verwendet werden, um beispielsweise den Namen des Followers im Nachrichtentext hinzuzufügen. Weiterführende Informationen finden Sie in [diesem Abschnitt](../send/personalize.md).

1. Sehen Sie sich Ihre Nachricht in der Vorschau an.

   Durchsuchen Sie die Registerkarte **[!UICONTROL Vorschau]**, um das Rendering Ihres Tweets zu überprüfen.

   ![](assets/tw-dm-preview.png)

   1. Klicken Sie auf die Registerkarte **[!UICONTROL Vorschau]**.
   1. Klicken Sie auf das Dropdown-Menü **[!UICONTROL Personalisierung testen]** und wählen Sie **[!UICONTROL Besucherabonnement]**.
   1. Wählen Sie das X-Konto aus, mit dem Sie die Vorschau testen möchten.

1. Durchführen eines Testversands

   Validieren Sie Ihre Nachricht vor dem Versand durch einen [Testversand an ein Testkonto](../send/preview-and-proof.md). Sie erhalten dann ein exaktes Rendering der Nachricht in einem privaten X-Konto und können Inhalt und Personalisierung überprüfen.

1. Senden Sie die Direktnachricht.

   1. Nachdem der Inhalt validiert wurde, klicken Sie auf die Schaltfläche **[!UICONTROL Senden]**.
   1. Wählen Sie **[!UICONTROL Sendungen schnellstmöglich abschicken]** aus und klicken Sie auf die Schaltfläche **[!UICONTROL Analysieren]**.
   1. Überprüfen Sie nach Abschluss der Analyse das Ergebnis.
   1. Klicken Sie auf **[!UICONTROL Absendung bestätigen]** und dann auf **[!UICONTROL Ja]**.

>[!CAUTION]
>
>Sie können pro Tag maximal 250 Direktnachrichten senden. Um eine Überschreitung dieses Grenzwerts zu vermeiden, können Sie in mehreren Schüben senden. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#sending-using-multiple-waves){target="_blank"}.


## Zugriff auf Tracking-Daten {#tw-tracking}

In der integrierten Versandvorlage **[!UICONTROL Tweet]** ist Tracking standardmäßig aktiviert.

Tracking kann in den Versandberichten und in der Registerkarte **[!UICONTROL Bearbeiten > Tracking]** des Versands und des Services eingesehen werden.

Die Tracking-Konfiguration ist dieselbe wie bei einem E-Mail-Versand. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de){target="_blank"}.


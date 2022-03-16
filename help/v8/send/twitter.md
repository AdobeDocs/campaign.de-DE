---
title: Posten von Nachrichten in Twitter mit Adobe Campaign
description: Erfahren Sie, wie Sie mit dem Adobe Campaign Social Marketing-Modul Nachrichten in Twitter posten und Kontaktdaten erfassen können.
role: Data Engineer
level: Beginner
hidefromtoc: true
hide: true
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: da6e585a789749ae0302f048940d104a36e2b477
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 52%

---


# Posten von Nachrichten in Twitter mit Adobe Campaign {#post-tw-messages}

Adobe Campaign enthält eine **Social Marketing** -Modul, mit dem Sie über Twitter mit Ihren Kunden und Interessenten interagieren können.

Nach der Konfiguration der Integration haben Sie folgende Möglichkeiten:

* Nachrichten auf Twitter senden: Mit Adobe Campaign können Sie Nachrichten direkt an Ihr twitter-Konto posten. Sie können auch Direktnachrichten an all Ihre Follower senden.
* Neue Kontakte sammeln: Adobe Campaign kann die Profildaten automatisch abrufen, sodass Sie Zielgruppenbestimmungskampagnen durchführen und nach Möglichkeit kanalübergreifende Strategien implementieren können. Diese Aktion erfordert die Zustimmung des Benutzers.


Die Konfigurationsschritte zur Integration Ihres Twitter-Kontos mit Adobe Campaign werden im Abschnitt [diese Seite](../connect/ac-tw.md).

## Erstellen und Veröffentlichen eines Twitter-Beitrags {#publish-on-tw}

Gehen Sie wie folgt vor, um eine Nachricht auf Ihrem Twitter-Konto zu posten:

1. Erstellen eines Twitter-Versands

   Erstellen Sie einen neuen Versand anhand der Versandvorlage **[!UICONTROL Tweet (Twitter)]**.

1. Auswählen der Hauptzielgruppe      

   Wählen Sie die Konten aus, an die Sie Tweets senden möchten.

   1. Wählen Sie den Link **[!UICONTROL An]** aus.
   1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**.
   1. Wählen Sie **[!UICONTROL Twitter-Konto]** aus.
   1. Wählen Sie im Feld **[!UICONTROL Ordner]** den Dienstordner aus, der das Twitter-Konto enthält. Wählen Sie dann das Twitter-Konto aus, an das Sie Ihren Tweet senden möchten.

1. Auswählen der Zielgruppe für den Testversand

   Über den Tab **[!UICONTROL Testversand-Zielgruppe]** können Sie das Twitter-Konto festlegen, das Sie vor dem endgültigen Versand für Testsendungen verwenden möchten.

   Wie im Abschnitt [Konfigurationsschritte](../connect/ac-tw.md#tw-test-account)müssen Sie ein privates Twitter-Konto für den Testversand erstellen.

   >[!NOTE]
   >
   >Wenn Sie dasselbe Twitter-Konto für alle Sendungen verwenden, können Sie die Testversand-Zielgruppe in der Versandvorlage **[!UICONTROL Tweet]** speichern, auf die über den Knoten **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** zugegriffen werden kann. Die Testversand-Zielgruppe wird dann standardmäßig bei jedem neuen Versand eingegeben.

1. Definieren des Inhalts Ihres Beitrags

   Geben Sie den Inhalt Ihres Beitrags im **[!UICONTROL Inhalt]** Registerkarte.

   >[!CAUTION]
   >
   >Beim Posten in Twitter gelten die folgenden Einschränkungen:
   >
   >* Die Nachricht darf nicht länger als 140 Zeichen sein.
   >* Das HTML-Format wird nicht unterstützt.


1. Beitragsvorschau

   Durchsuchen Sie die **[!UICONTROL Vorschau]** , um das Rendering Ihres Beitrags zu überprüfen.

   1. Klicken Sie auf den **[!UICONTROL Vorschau]**-Tab.
   1. Klicken Sie auf das Dropdown-Menü **[!UICONTROL Personalisierung testen]** und wählen Sie **[!UICONTROL Dienst]** aus.
   1. Wählen Sie im Feld **[!UICONTROL Ordner]** den Dienstordner aus, der Ihr Twitter-Konto enthält.
   1. Wählen Sie das Twitter-Konto aus, mit dem Sie die Vorschau testen möchten.

1. Durchführen eines Testversands

   Bevor Sie Ihren Tweet posten, überprüfen Sie ihn anhand eines Testversands Ihrer Veröffentlichung: Sie können dann ein genaues Rendering der Veröffentlichung auf einer privaten Twitter-Testseite erhalten.

   Die Erstellung einer privaten Twitter-Testseite wird in [diesem Abschnitt](../connect/ac-tw.md#tw-test-account) beschrieben.

   ![](../assets/do-not-localize/book.png) [Wichtige Schritte zur Validierung eines Versands](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=de){target=&quot;_blank&quot;}

1. Nachricht posten

   1. Nachdem der Inhalt validiert wurde, klicken Sie auf die Schaltfläche **[!UICONTROL Senden]**.
   1. Wählen Sie **[!UICONTROL Sendungen schnellstmöglich abschicken]** aus und klicken Sie auf die Schaltfläche **[!UICONTROL Analysieren]**.
   1. Überprüfen Sie nach Abschluss der Analyse das Ergebnis.
   1. Klicken Sie auf **[!UICONTROL Absendung bestätigen]** und dann auf **[!UICONTROL Ja]**.


## Direktnachrichten an Follower senden {#direct-tw-messages}

Die **[!UICONTROL Twitter-Konten synchronisieren]** Der technische Workflow stellt die Liste der Twitter-Follower wieder her, damit Sie ihnen Direktnachrichten senden können. [Weitere Informationen](../connect/ac-tw.md#synchro-tw-accounts)

Gehen Sie wie folgt vor, um Direktnachrichten an Ihre Follower zu senden:

1. Erstellen eines Twitter-Versands basierend auf dem **[!UICONTROL Tweet (Direktnachricht)]** integrierte Versandvorlage.

1. Auswählen der Hauptzielgruppe      

1. Wählen Sie die **[!UICONTROL nach]** und **[!UICONTROL Hinzufügen]** Schaltfläche.

1. Wählen Sie einen Typ der Zielgruppenbestimmung aus

   * Auswählen **[!UICONTROL Twitter-Abonnenten]** um eine Direktnachricht an alle Ihre Follower zu senden.

   * Wählen Sie **[!UICONTROL Filterbedingungen]** aus, um eine Abfrage zu definieren und deren Ergebnis anzuzeigen. Diese Option ist dieselbe wie bei E-Mail-Sendungen. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/creating-queries/defining-filter-conditions.html){target=&quot;_blank&quot;}.

1. Aus dem **[!UICONTROL Testversand-Zielgruppe]** den Follower auswählen, der den Testversand Ihrer Direktnachricht erhalten soll.

   >[!NOTE]
   >
   >Wenn Sie alle Ihre Testsendungen für Direktnachrichten an denselben Twitter-Follower senden möchten, können Sie die Testversand-Zielgruppe in der Versandvorlage für **[!UICONTROL Twittern (Direct Message)]** speichern, die über den Knoten **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** aufgerufen wird.

1. Geben Sie den Inhalt der Nachricht im **[!UICONTROL Inhalt]** Registerkarte.

   Personalisierungsfelder können auf dieselbe Weise wie für E-Mail-Sendungen verwendet werden, um beispielsweise den Namen des Followers im Nachrichtentext hinzuzufügen. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/about-personalization.html?lang=de){target=&quot;_blank&quot;}.

1. Sehen Sie sich Ihre Nachricht in der Vorschau an

   Durchsuchen Sie die **[!UICONTROL Vorschau]** , um das Rendering Ihres Beitrags zu überprüfen.

   1. Klicken Sie auf den **[!UICONTROL Vorschau]**-Tab.
   1. Klicken Sie auf das Dropdown-Menü **[!UICONTROL Personalisierung testen]** und wählen Sie **[!UICONTROL Dienst]** aus.
   1. Wählen Sie im Feld **[!UICONTROL Ordner]** den Dienstordner aus, der Ihr Twitter-Konto enthält.
   1. Wählen Sie das Twitter-Konto aus, mit dem Sie die Vorschau testen möchten.

1. Durchführen eines Testversands

   Vergewissern Sie sich vor dem Versand Ihrer Nachricht, dass Sie sie durch einen Testversand an ein Testkonto validieren: Sie können dann ein genaues Rendering der Nachricht in einem privaten Twitter-Konto abrufen und Inhalt und Personalisierung überprüfen.

   Die Erstellung einer privaten Twitter-Testseite wird in [diesem Abschnitt](../connect/ac-tw.md#tw-test-account) beschrieben.

   ![](../assets/do-not-localize/book.png) [Wichtige Schritte zur Validierung eines Versands](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}

1. Direktnachricht senden

   1. Nachdem der Inhalt validiert wurde, klicken Sie auf die Schaltfläche **[!UICONTROL Senden]**.
   1. Wählen Sie **[!UICONTROL Sendungen schnellstmöglich abschicken]** aus und klicken Sie auf die Schaltfläche **[!UICONTROL Analysieren]**.
   1. Überprüfen Sie nach Abschluss der Analyse das Ergebnis.
   1. Klicken Sie auf **[!UICONTROL Absendung bestätigen]** und dann auf **[!UICONTROL Ja]**.

>[!CAUTION]
>
>Sie können nicht mehr als 250 Direktnachrichten pro Tag senden. Um zu vermeiden, dass Sie diesen Schwellenwert überschreiten, können Sie Sendungen in Schüben durchführen. Mehr dazu finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#sending-using-multiple-wave){target=&quot;_blank&quot;}.


## Auf Tracking-Daten zugreifen {#tw-tracking}

Im integrierten **[!UICONTROL Tweet]** Versandvorlage, ist Tracking standardmäßig aktiviert.

Tracking-Daten können in den Versandberichten und im **[!UICONTROL Bearbeiten > Tracking]** des Versands und des Dienstes.

Die Tracking-Konfiguration ist dieselbe wie bei einem E-Mail-Versand. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de){target=&quot;_blank&quot;}.


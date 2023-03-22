---
title: Erstellen einer E-Mail-Vorschau und Testen einer E-Mail
description: Erfahren Sie, wie Sie Ihren Versand vor dem Versand validieren
feature: Personalization
role: User
level: Beginner
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 10%

---

# Erstellen einer E-Mail-Vorschau und Testen einer E-Mail {#preview-test}

Sobald der Nachrichteninhalt definiert wurde, können Sie mithilfe von Testprofilen die Vorschau anzeigen und testen. Wenn Sie [personalisierter Inhalt](personalize.md)können Sie mithilfe von Testprofildaten überprüfen, wie dieser Inhalt in der Nachricht angezeigt wird. Zusätzlich können Sie Testsendungen an Testprofile durchführen, um mögliche Fehler im Nachrichteninhalt oder in den Personalisierungseinstellungen zu erkennen. Bei jeder Änderung sollte ein Testversand durchgeführt werden, um den aktuellen Inhalt zu validieren.

## Inhaltsvorschau{#preview-content}

Bevor Sie Testsendungen durchführen, sollten Sie den Nachrichteninhalt im Vorschaubereich des Versandfensters überprüfen.

Gehen Sie wie folgt vor, um eine Vorschau des Nachrichteninhalts anzuzeigen:

1. Navigieren Sie zum **Vorschau** des Versands.
1. Klicken Sie auf **[!UICONTROL Personalisierung testen]** -Schaltfläche, um ein Profil zum Ausfüllen der Personalisierungsdaten auszuwählen. Sie können einen bestimmten Empfänger in der Datenbank oder eine Testadresse auswählen oder ein Profil aus der Zielpopulation auswählen, sofern es bereits definiert wurde. Sie können den Inhalt auch ohne Personalisierung überprüfen.

   ![](assets/test-personalization.png)

1. Die Vorschau wird erzeugt, damit Sie das Nachrichtenrendering überprüfen können. In der Nachrichtenvorschau werden personalisierte Elemente durch die ausgewählten Testprofildaten ersetzt.

   ![](assets/test-personalization-with-a-recipient.png)

1. Wählen Sie weitere Testprofile aus, um das E-Mail-Rendering für jede Variante Ihrer Nachricht in der Vorschau anzuzeigen.

## Durchführen eines Testversands {#send-proofs}

Mit Testsendungen können Sie den Abmelde-Link, die Mirrorseite und andere Links testen, die Nachricht validieren, die Anzeige von Bildern überprüfen, mögliche Fehler erkennen etc. Außerdem können Sie Ihr Design und die Darstellung auf verschiedenen Geräten testen.

Ein Testversand ist eine spezifische Nachricht, mit der Sie eine Nachricht testen können, bevor Sie sie an die Hauptzielgruppe senden. Die Empfänger des Testversands sind für die Validierung der Nachricht verantwortlich: Rendering, Inhalt, Personalisierungseinstellungen, Konfiguration.

### Testversand-Empfänger {#proofs-recipients}

Die Testversand-Zielgruppe kann in der Versandvorlage oder versandspezifisch definiert werden. In beiden Fällen können Sie über das Menü **[!UICONTROL nach]** und wählen Sie die **[!UICONTROL Testversand-Zielgruppe]** Registerkarte.

![](assets/target-of-proofs.png)

Der Typ der Testversand-Zielgruppe wird aus dem **[!UICONTROL Targeting-Modus]** Dropdown-Liste.

* Verwenden Sie die **[!UICONTROL Bestimmung einer speziellen Testversand-Zielgruppe]** die Option Empfänger in der Datenbank als Testversand-Zielgruppe auswählen.
* Verwenden Sie die **[!UICONTROL Adressersetzung]** zur Eingabe der E-Mail-Adressen und zur Validierung des Inhalts mithilfe der Empfängerzieldaten. Die Ersatzadressen können manuell eingegeben oder aus der Dropdown-Liste ausgewählt werden. Die zugehörige Auflistung ist Ersatzadresse (rcpAddress).
Standardmäßig wird die Ersetzung nach dem Zufallsprinzip durchgeführt. Sie können jedoch einen bestimmten Empfänger aus der Hauptzielgruppe über die  **[!UICONTROL Detail]** Symbol.

   ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

   Wählen Sie die **[!UICONTROL Profil auswählen (muss in die Zielgruppe aufgenommen werden)]** und wählen Sie einen Empfänger aus.

   ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* Verwenden Sie die **[!UICONTROL Testadressen]**  Option zur Verwendung von Testadressen als Testversand-Zielgruppe. Diese Adressen können aus einer Datei importiert oder manuell eingegeben werden.

   >[!NOTE]
   >
   >Testadressen gehören nicht zur Standard-Empfängertabelle (nms:recipient), sondern werden in einer separaten Tabelle erstellt. Wenn Sie die Empfängertabelle um neue Daten erweitern, müssen Sie die Testadressen-Tabelle ebenfalls um die gleichen Daten erweitern.

   Erfahren Sie mehr über Testadressen in [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.htmll){target="_blank"}.

* Verwenden Sie die **[!UICONTROL Spezifische Ziel- und Testadressen]** Option zur Kombination von Testadressen und spezifischen E-Mail-Adressen. Die entsprechenden Konfigurationen werden dann in zwei separaten Unterregisterkarten definiert.

### Durchführen eines Testversands{#proofs-send}

Gehen Sie wie folgt vor, um Testsendungen von Nachrichten durchzuführen:

1. Klicken Sie im Bildschirm zur Nachrichtendefinition auf die Schaltfläche **[!UICONTROL Testversand durchführen]** Schaltfläche.
1. Aus dem **[!UICONTROL Testversand durchführen]** -Fenster die Testversand-Empfänger zu überprüfen.
1. Klicken **[!UICONTROL Analyse]** , um die Vorbereitung der Testversand-Nachricht zu starten.

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. Sobald die Versandvorbereitung abgeschlossen ist, verwenden Sie die **[!UICONTROL Versand bestätigen]** , um mit dem Versand von Testversandnachrichten zu beginnen.

Navigieren Sie zum **[!UICONTROL Prüfung]** des Versands, um den Versand der Testsendungen zu überprüfen.

Es wird empfohlen, nach jeder Änderung am Nachrichteninhalt Testsendungen durchzuführen.

>[!NOTE]
>
>Im gesendeten Testversand ist der Link zur Mirrorseite nicht aktiv. Er wird nur in den endgültigen Nachrichten aktiviert.

### Eigenschaften des Testversands{#proofs-properties}

Die Eigenschaften des Testversands werden im Abschnitt **[!UICONTROL Erweitert]** im Fenster der Versandeigenschaften. Navigieren Sie zum **[!UICONTROL Eigenschaften von Testsendungen...]** -Link, um die Parameter und den Titel der Testsendungen zu definieren. Sie können Folgendes beibehalten:

* Doppelte Adressen im Testversand
* Auf die Blockierungsliste gesetzt Adressen im Testversand
* Im Testversand enthaltene Adressen

Standardmäßig werden Testversandnachrichten durch die Variable `Proof #N` im Betreff, wenn `N` die Nummer des Testversands. Diese Zahl wird bei jeder Testversand-Analyse erhöht. Sie können die `proof` bei Bedarf.

![](assets/proof-parameters.png){width="800" align="left"}


## Anleitungsvideo {#video-proof}

Hier erfahren Sie, wie Sie einen E-Mail-Testversand durchführen und validieren.

>[!VIDEO](https://video.tv.adobe.com/v/333404)

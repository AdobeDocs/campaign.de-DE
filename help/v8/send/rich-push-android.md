---
audience: end-user
title: Erstellen eines Rich-Push-Benachrichtigungsversands
description: Erfahren Sie, wie Sie einen Rich-Push-Benachrichtigungs-Versand mit Adobe Campaign Web erstellen.
feature: Push
role: User
level: Beginner
exl-id: 42e3623b-b401-4fcc-80a7-ea38347fddc6
source-git-commit: 4e52e596d4eb2a8e1a1799fcd7104dcd894b6c2d
workflow-type: tm+mt
source-wordcount: '2311'
ht-degree: 100%

---

# Erstellen eines Rich-Push-Versands in Android {#rich-push}

>[!IMPORTANT]
>
>Bevor Sie eine Rich-Push-Benachrichtigung entwerfen, müssen Sie zunächst Ihren V2-Connector konfigurieren. Eine detaillierte Vorgehensweise dazu finden Sie auf [dieser Seite](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android#configuring-external-account-android).

Bei Firebase Cloud Messaging stehen Ihnen zwei Nachrichtentypen zur Auswahl:

* Die **[!UICONTROL Datenmeldung]** wird von der Client-App verarbeitet. Diese Meldungen werden direkt an die App gesendet, die auf dem Gerät eine Android-Benachrichtigung generiert und anzeigt. Datennachrichten enthalten nur die von Ihnen definierten Anwendungsvariablen.

* Die **[!UICONTROL Benachrichtigungsmeldung]** wird automatisch vom FCM SDK verarbeitet. FCM übernimmt für die Client-App automatisch das Anzeigen der Nachricht auf den Geräten Ihrer Benutzenden. Benachrichtigungsmeldungen enthalten einen vordefinierten Satz von Parametern und Optionen, können aber mit benutzerspezifischen Anwendungsvariablen weiter personalisiert werden.

Wenn die Bildlaufleiste auf Ihrer Benutzeroberfläche deaktiviert ist, greifen Sie auf **[!UICONTROL Administration]** `>` **[!UICONTROL Plattform]** `>` **[!UICONTROL Optionen]** zu und setzen Sie die Option **[!UICONTROL XtkUseScrollBar]** auf „1“.

## Festlegen des Inhalts einer Android-Benachrichtigung {#push-message}

Sobald Ihr Push-Versand erstellt ist, können Sie seinen Inhalt mit einer der folgenden Vorlagen definieren:

* **Standard** ermöglicht es Ihnen, Benachrichtigungen mit einem einfachen Symbol und einem zugehörigen Bild zu senden.

* **Einfach** ermöglicht es Ihnen, Text, Bilder und Schaltflächen in Ihre Benachrichtigungen einzufügen.

* **Karussell** ermöglicht es Ihnen, Benachrichtigungen mit Text und mehreren Bildern zu senden, zwischen denen die Benutzenden hin und her wischen können.

* **Symbolschaltflächen** ermöglichen es Ihnen, Benachrichtigungen mit einem einfachen Symbol und einem zugehörigen Bild zu versenden.

* **Eingabefeld** erfasst Benutzereingaben und Feedback direkt über die Benachrichtigung.

* **Produktkatalog** zeigt eine Vielzahl von Produktbildern an.

* **Produktbewertung** ermöglicht Benutzenden die Rückmeldung von Feedback und Bewertung von Produkten.

* **Timer** fügt einen Live-Countdown-Timer in Ihre Benachrichtigungen ein.

* **Rahmenlos** verwendet die gesamte Hintergrundfläche für ein Bild mit nahtlos überlagertem Text.

Navigieren Sie durch die folgenden Registerkarten, um mehr über die Personalisierung dieser Vorlagen zu erfahren.

>[!BEGINTABS]

>[!TAB Standard]

1. Wählen Sie **[!UICONTROL Standard]** aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]**.

   ![](assets/rich_push_default.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]** und **[!UICONTROL Nachricht]** ein.

   ![](assets/rich_push_default_2.png)

1. Verwenden Sie dynamische Personalisierungsfelder, um Inhalte zu definieren, Daten zu personalisieren und dynamische Inhalte hinzuzufügen. [Weitere Informationen](../send/personalize.md)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_default_3.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Einfach]

1. Wählen Sie **[!UICONTROL Einfach]** aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]**.

   ![](assets/rich_push_basic.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_basic_2.png)

1. Verwenden Sie dynamische Personalisierungsfelder, um Inhalte zu definieren, Daten zu personalisieren und dynamische Inhalte hinzuzufügen. [Weitere Informationen](../send/personalize.md)

1. Geben Sie unter dem Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, Ihre **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Fügen Sie bei Bedarf eine **[!UICONTROL Schaltfläche „Später erinnern“]** hinzu. Geben Sie den **[!UICONTROL Text für die Erinnerung]** und das **Datum** in die entsprechenden Felder ein.

   Das Feld **[!UICONTROL Erinnerungsdatum]** benötigt einen Wert, der eine Zeitspanne in Sekunden darstellt.

1. Klicken Sie auf **[!UICONTROL Schaltfläche hinzufügen]** und füllen Sie folgende Felder aus:

   * **[!UICONTROL Titel]**: Text, der auf der Schaltfläche angezeigt wird.
   * **[!UICONTROL Link-URI]**: Geben Sie den URI an, der beim Klicken auf die Schaltfläche ausgeführt werden soll.

   Sie haben die Möglichkeit, bis zu drei Schaltflächen in Ihre Push-Benachrichtigung einzubauen. Wenn Sie sich für die **[!UICONTROL Schaltfläche „Später erinnern“]** entscheiden, können Sie maximal zwei Schaltflächen einfügen.

1. Wählen Sie den **[!UICONTROL Link-Typ]** für die verlinkte URL Ihrer Schaltfläche:

   * **[!UICONTROL Web-URL]**: Web-URLs leiten Benutzende zu Online-Inhalten weiter. Beim Anklicken öffnen sie den Standard-Webbrowser des Geräts und navigieren zu der angegebenen URL.

   * **[!UICONTROL Deeplink]**: Deeplinks sind URLs, die Benutzende zu bestimmten Abschnitten in einer App führen, selbst wenn die App geschlossen ist. Beim Anklicken kann ein Dialogfeld angezeigt werden, in dem Benutzende aus verschiedenen Apps wählen können, die den Link verarbeiten können.

   * **[!UICONTROL Open App]**: Open App-URLs ermöglichen es Ihnen, sich direkt mit Inhalten innerhalb einer Anwendung zu verbinden. Diese Art von URL ermöglicht es Ihrer Anwendung, sich als Standard-Handler für einen bestimmten Link-Typ zu etablieren und so das Dialogfeld zur Disambiguierung zu umgehen.

   Weitere Informationen über die Handhabung von Android-App-Links finden Sie in der [Entwicklerdokumentation zu Android](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Karussell]

1. Wählen Sie **[!UICONTROL Karussell]** aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]**.

   ![](assets/rich_push_carousel.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_carousel_1.png)

1. Verwenden Sie den Ausdruckseditor, um Inhalte zu definieren, Daten zu personalisieren und dynamische Inhalte hinzuzufügen. [Weitere Informationen](../send/personalize.md)

1. Geben Sie unter dem Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, Ihre **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Wählen Sie, wie das **[!UICONTROL Karussell]** bedient werden soll:

   * **[!UICONTROL Automatisch]**: Die Bilder werden automatisch in vordefinierten Intervallen als Folien wiedergegeben.
   * **[!UICONTROL Manuell]**: Benutzende können manuell zwischen den Folien streichen, um durch die Bilder zu navigieren.

1. Aktivieren Sie die Option **[!UICONTROL Filmstreifen]** aus der Dropdown-Liste **[!UICONTROL Layout]**, um die Vorschau der vorherigen und der nächsten Bilder neben der Hauptfolie einzuschließen.

1. Klicken Sie auf **[!UICONTROL Bild hinzufügen]** und geben Sie Ihre Bild-URL, Ihren Text und Ihre Aktions-URL ein.

   Stellen Sie sicher, dass Sie mindestens drei und maximal fünf Bilder einfügen.

   ![](assets/rich_push_carousel_2.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Symbolschaltflächen]

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Symbolschaltflächen]** aus.

   ![](assets/rich_push_icon.png)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Hintergrund]** ein.

   ![](assets/rich_push_icon_2.png)

1. Geben Sie die URL für das **[!UICONTROL Bild der Schaltfläche „Abbrechen“]** an.

1. Klicken Sie unter den **[!UICONTROL Symbolbildschaltflächen]** auf **[!UICONTROL Bild hinzufügen]**. Geben Sie dann die **Bild-URL**, den **Link-Typ** und den **Link-URI** ein.

   Stellen Sie sicher, dass Sie mindestens drei Bilder und maximal fünf Schaltflächen einfügen.

   ![](assets/rich_push_icon_3.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_icon_5.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Eingabefeld]

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Eingabefeld]** aus.

   ![](assets/rich_push_input.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_input_2.png)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für den **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Geben Sie im Menü **[!UICONTROL Eingabefeldoptionen]** die folgende Option ein:

   * **[!UICONTROL Namen der Empfängerin bzw. des Empfängers eingeben]**: Geben Sie den Namen oder die Kennung für die Empfängerin bzw. den Empfänger der Eingabe ein.
   * **[!UICONTROL Eingabetext]**: Geben Sie den Text für das **Eingabefeld** ein.
   * **[!UICONTROL Feedback-Text]**: Geben Sie den Text ein, der nach einer Antwort angezeigt werden soll.
   * **[!UICONTROL Feedback-Bild]**: Fügen Sie die URL für das Bild hinzu, das nach einer Antwort angezeigt wird.

   ![](assets/rich_push_input_3.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_input_4.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten einsetzen, um die Nachricht in einer Vorschau anzuzeigen und zu testen.

>[!TAB Produktkatalog]

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Produktkatalog]** aus.

   ![](assets/rich_push_catalog.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_catalog_2.png)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Geben Sie im Menü **[!UICONTROL Produktkatalogoptionen]** die folgenden Optionen ein:

   * **[!UICONTROL Text der Aktionsschaltfläche]**: Text, der auf der Schaltfläche angezeigt wird.
   * **[!UICONTROL Textfarbe der Aktionsschaltfläche]**: Farbe des Textes der Aktionsschaltfläche.
   * **[!UICONTROL Farbe der Aktionsschaltfläche]**: Farbe der Aktionsschaltfläche.
   * **[!UICONTROL Aktionsschaltflächen-URI]**: Geben Sie den URI an, der beim Klicken auf die Schaltfläche ausgeführt werden soll.
   * **[!UICONTROL Anzeigetyp]**: Wählen Sie zwischen vertikaler oder horizontaler Anzeige.

   ![](assets/rich_push_catalog_3.png)

1. Klicken Sie im Menü **[!UICONTROL Produktkatalogelemente]** auf **[!UICONTROL Hinzufügen]** und geben Sie die folgenden Details für jedes Element ein:

   * **[!UICONTROL Title]**
   * **[!UICONTROL Beschreibung]**
   * **[!UICONTROL Bild-URL]**
   * **[!UICONTROL Preis]**
   * **[!UICONTROL URI]**

   Stellen Sie sicher, dass Sie maximal drei Elemente einfügen.

   ![](assets/rich_push_catalog_4.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten einsetzen, um die Nachricht in einer Vorschau anzuzeigen und zu testen.

>[!TAB Produktbewertung]

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Produktbewertung]** aus.

   ![](assets/rich_push_rating.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_rating_2.png)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Geben Sie im Menü **[!UICONTROL Produktbewertungsoptionen]** die URLs für das **[!UICONTROL Bewertungssymbol im nicht ausgewählten Zustand]** und das **[!UICONTROL Bewertungssymbol im ausgewählten Zustand]** ein.

   ![](assets/rich_push_rating_3.png)

1. Klicken Sie im Menü **[!UICONTROL Produktbewertungselemente]** auf **[!UICONTROL Hinzufügen]**, geben Sie Ihre **[!UICONTROL Link-URL]** ein und wählen Sie Ihren **[!UICONTROL Link-Typ]** aus.

   * **[!UICONTROL Web-URL]**: Web-URLs leiten Benutzende zu Online-Inhalten weiter. Beim Anklicken öffnen sie den Standard-Webbrowser des Geräts und navigieren zu der angegebenen URL.

   * **[!UICONTROL Deeplink]**: Deeplinks sind URLs, die Benutzende zu bestimmten Abschnitten in einer App führen, selbst wenn die App geschlossen ist. Beim Anklicken kann ein Dialogfeld angezeigt werden, in dem Benutzende aus verschiedenen Apps wählen können, die den Link verarbeiten können.

   * **[!UICONTROL Open App]**: Open App-URLs ermöglichen es Ihnen, sich direkt mit Inhalten innerhalb einer Anwendung zu verbinden. Diese Art von URL ermöglicht es Ihrer Anwendung, sich als Standard-Handler für einen bestimmten Link-Typ zu etablieren und so das Dialogfeld zur Disambiguierung zu umgehen.

   * **[!UICONTROL Verwerfen]**: Der Schaltfläche ist keine URL zugeordnet. Durch Klicken wird das Dialogfeld oder die Benutzeroberfläche einfach geschlossen.

   Stellen Sie sicher, dass Sie mindestens drei und maximal fünf Werte einfügen.

   ![](assets/rich_push_rating_4.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Timer]

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Timer]** aus.

   ![](assets/rich_push_timer.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_timer_2.png)

1. Geben Sie den Text, der nach Ablauf des Timers angezeigt werden soll, in die Felder **[!UICONTROL Alternativer Titel]**, **[!UICONTROL Alternative Nachricht]** und **[!UICONTROL Alternative erweiterte Nachricht]** ein.

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]**, den **[!UICONTROL Hintergrund]** und den **[!UICONTROL Timer]** ein.

   ![](assets/rich_push_timer_3.png)

1. Legen Sie die **[!UICONTROL Dauer des Timers]** in Sekunden oder den **[!UICONTROL Zeitstempel für Timer-Ende]** auf einen bestimmten Epoch-Zeitstempel fest und fügen Sie die URL für **[!UICONTROL Alternatives Bild]** ein, das nach Ablauf des Timers angezeigt wird.

   ![](assets/rich_push_timer_4.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten einsetzen, um die Nachricht in einer Vorschau anzuzeigen und zu testen.

>[!TAB Rahmenlos]

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Rahmenlos]** aus.

   ![](assets/rich_push_bezel.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_zero_2.png)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Fügen Sie im Menü **[!UICONTROL Optionen für rahmenlose Displays]** Ihre Bild-URL im Feld **[!UICONTROL Ausgeblendeter Benachrichtigungsstil]** hinzu.

   ![](assets/rich_push_zero_3.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und die **[!UICONTROL zusätzlichen HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!ENDTABS]

## Erweiterte Einstellungen für Push-Benachrichtigungen {#push-advanced}

### Benachrichtigungsoptionen {#notification-options}

| Parameter | Beschreibung |
|---------|---------|
| **[!UICONTROL Kanal-ID]** | Legen Sie die Kanal-ID Ihrer Benachrichtigung fest. Die App muss einen Kanal mit dieser Kanal-ID erstellen, bevor eine Benachrichtigung mit dieser Kanal-ID empfangen werden kann. |
| **[!UICONTROL Symbol]** | Legt das Symbol fest, das für die Benachrichtigung auf den Geräten Ihrer Profile angezeigt werden soll. |
| **[!UICONTROL Ton]** | Legt den Ton fest, der abgespielt werden soll, wenn das Gerät Ihre Benachrichtigung erhält. |
| **[!UICONTROL Tag]** | Legt eine Kennung fest, die zum Ersetzen bestehender Benachrichtigungen in der Benachrichtigungsablage verwendet wird. Dadurch wird verhindert, dass sich mehrere Benachrichtigungen ansammeln, und sichergestellt, dass nur die jeweils letzte relevante Benachrichtigung angezeigt wird. |
| **[!UICONTROL Farbe]** | Legt die Farbe des Symbols Ihrer Benachrichtigung mit einem hexadezimalen Farb-Code fest. |
| **[!UICONTROL Klick-Aktion]** | Legt die Aktion fest, die für das Klicken der Benutzenden auf Ihre Benachrichtigung zugewiesen ist. |
| **[!UICONTROL Hintergrundfarbe der Benachrichtigungen]** | Legt die Farbe des Benachrichtigungshintergrunds mit den gewünschten Hexadezimal-Farb-Codes fest. |
| **[!UICONTROL Link-Typ]** | <ul><li>Web-URL: Web-URLs leiten Benutzende zu Online-Inhalten weiter. Beim Anklicken öffnen sie den Standard-Webbrowser des Geräts und navigieren zu der angegebenen URL.</li><li>Deeplink: Deeplinks sind URLs, die Benutzende zu bestimmten Abschnitten in einer App führen, selbst wenn die App geschlossen ist. Beim Anklicken kann ein Dialogfeld angezeigt werden, in dem Benutzende aus verschiedenen Apps wählen können, die den Link verarbeiten können.</li><li> Open App: Open App-URLs ermöglichen es Ihnen, sich direkt mit Inhalten innerhalb einer Anwendung zu verbinden. Diese Art von URL ermöglicht es Ihrer Anwendung, sich als Standard-Handler für einen bestimmten Link-Typ zu etablieren und so das Dialogfeld zur Disambiguierung zu umgehen.</li></ul> |

### Zusätzliche Optionen für HTTPv1 {#additional-options}

| Parameter | Beschreibung |
|---------|---------|
| **[!UICONTROL Ticker]** | Legt den Ticker-Text Ihrer Benachrichtigung fest. Nur verfügbar bei Geräten mit Android 5.0 Lollipop. |
| **[!UICONTROL Sticky]** | Wenn diese Option aktiviert ist, bleibt die Benachrichtigung auch dann sichtbar, wenn darauf geklickt wird. <br>Wenn sie deaktiviert ist, wird die Benachrichtigung automatisch verworfen, sobald damit interagiert wird. Durch das Sticky-Verhalten können wichtige Benachrichtigungen über längere Zeiträume auf dem Bildschirm beibehalten werden. |
| **[!UICONTROL Bild]** | Legt die URL des Bilds fest, das in Ihrer Benachrichtigung angezeigt werden soll. |
| **[!UICONTROL Benachrichtigungspriorität]** | Legen Sie die Prioritätsstufe Ihrer Benachrichtigung fest. Dies kann „Standard“, „Minimum“, „Niedrig“ oder „Hoch“ sein. Die Prioritätsstufe bestimmt die Wichtigkeit und Dringlichkeit der Benachrichtigung und beeinflusst deren Anzeige sowie die Frage, ob sie bestimmte Systemeinstellungen umgehen kann. Weitere Informationen hierzu finden Sie in der [FCM-Dokumentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Anzahl der Benachrichtigungen]** | Legt die Zahl der neuen ungelesenen Informationen fest, die direkt auf dem Symbol der App angezeigt werden. Dadurch können die Benutzenden schnell die Anzahl der ausstehenden Benachrichtigungen sehen. |
| **[!UICONTROL Sichtbarkeit]** | Legen Sie die Sichtbarkeitsstufe Ihrer Benachrichtigung fest. Dies kann öffentlich, privat oder geheim sein. Die Sichtbarkeitsstufe bestimmt, wie viel des Benachrichtigungsinhalts auf dem Sperrbildschirm und anderen sensiblen Bereichen angezeigt wird. Weitere Informationen finden Sie in der [FCM-Dokumentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Anwendungsvariablen]** | Damit können Sie das Verhalten von Benachrichtigungen definieren. Diese Variablen sind vollständig anpassbar und Teil der an das Mobilgerät gesendeten Nachrichten-Payload. |

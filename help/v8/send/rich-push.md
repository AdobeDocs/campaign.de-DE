---
audience: end-user
title: Rich-Push-Benachrichtigungsversand erstellen
description: Erfahren Sie, wie Sie mit Adobe Campaign Web einen Rich-Push-Benachrichtigungsversand für Android erstellen
feature: Push
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 771473620ea9b6d71be72871255d22b816c51b91
workflow-type: tm+mt
source-wordcount: '1234'
ht-degree: 32%

---

# Erstellen eines Rich-Push-Versands für Android {#rich-push}

Bei Firebase Cloud Messaging stehen Ihnen zwei Nachrichtentypen zur Auswahl:

* Die **[!UICONTROL Datenmeldung]** wird von der Client-App verarbeitet. Diese Meldungen werden direkt an die App gesendet, die auf dem Gerät eine Android-Benachrichtigung generiert und anzeigt. Datennachrichten enthalten nur die von Ihnen definierten Anwendungsvariablen.

* Die **[!UICONTROL Benachrichtigungsmeldung]** wird automatisch vom FCM SDK verarbeitet. FCM übernimmt für die Client-App automatisch das Anzeigen der Nachricht auf den Geräten Ihrer Benutzenden. Benachrichtigungsmeldungen enthalten einen vordefinierten Satz von Parametern und Optionen, können aber mit benutzerspezifischen Anwendungsvariablen weiter personalisiert werden.

## Festlegen des Inhalts der Benachrichtigung {#push-message}

Sobald Ihr Push-Versand erstellt ist, können Sie seinen Inhalt festlegen. Drei Vorlagen stehen zur Verfügung:

* **Standardvorlage** ermöglicht den Versand von Benachrichtigungen mit einem einfachen Symbol und einem zugehörigen Bild.

* **Grundlegende Vorlage** Sie können Text, Bilder und Schaltflächen in Ihre Benachrichtigungen einfügen.

* **Karussellvorlage** ermöglicht es Ihnen, Benachrichtigungen mit Text und mehreren Bildern zu senden, durch die Benutzer wischen können.

Auf den folgenden Registerkarten erfahren Sie, wie Sie Ihre Nachricht für jede Vorlage erstellen.

>[!BEGINTABS]

>[!TAB Standardvorlage]

1. Aus dem **[!UICONTROL Benachrichtigungstyp]** Dropdown-Liste auswählen **[!UICONTROL Standard]**.

   ![](assets/rich_push_default.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in das Feld **[!UICONTROL Titel]** und **[!UICONTROL Nachricht]** -Felder.

   ![](assets/rich_push_default_2.png)

1. Verwenden Sie dynamische Personalisierungsfelder, um Inhalte zu definieren, Daten zu personalisieren und dynamischen Inhalt hinzuzufügen. [Weitere Informationen](../send/personalize.md)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und **[!UICONTROL Zusätzliche HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_default_3.png)

Nachdem Sie den Nachrichteninhalt definiert haben, können Sie Testabonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Grundlegende Vorlage]

1. Aus dem **[!UICONTROL Benachrichtigungstyp]** Dropdown-Liste auswählen **[!UICONTROL Allgemein]**.

   ![](assets/rich_push_basic.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in das Feld **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** -Felder.

   Die **[!UICONTROL Nachricht]** Text wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** wird angezeigt, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_basic_2.png)

1. Verwenden Sie dynamische Personalisierungsfelder, um Inhalte zu definieren, Daten zu personalisieren und dynamischen Inhalt hinzuzufügen. [Weitere Informationen](../send/personalize.md)

1. Unter dem **[!UICONTROL Farboptionen]** Geben Sie die hexadezimalen Farbcodes für Ihre **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Hintergrund]**.

1. Hinzufügen einer **[!UICONTROL Schaltfläche &quot;Später erinnern&quot;]** bei Bedarf. Geben Sie Ihre **[!UICONTROL Erinnerungstext]** und **Datum** in die entsprechenden Felder ein.

   Die **[!UICONTROL Erinnerungsdatum]** -Feld erwartet einen Wert, der eine Epoche in Sekunden darstellt.

1. Klicks **[!UICONTROL Schaltfläche hinzufügen]** und füllen Sie folgende Felder aus:

   * **[!UICONTROL Titel]**: Auf der Schaltfläche angezeigter Text.
   * **[!UICONTROL Link-URI]**: Geben Sie den URI an, der beim Klicken auf die Schaltfläche ausgeführt werden soll.

   Sie haben die Möglichkeit, bis zu drei Schaltflächen in Ihre Push-Benachrichtigung einzuschließen. Wenn Sie sich für die **[!UICONTROL Schaltfläche &quot;Später erinnern&quot;]** können Sie nur maximal zwei Schaltflächen einfügen.

1. Wählen Sie die **[!UICONTROL Link-Typ]** der verknüpften URL Ihrer Schaltfläche:

   * **[!UICONTROL Web-URL]**: Web-URLs leiten Benutzer zu Online-Inhalten weiter. Nach dem Klicken wird der Standard-Webbrowser des Geräts aufgefordert, zu öffnen und zur angegebenen URL zu navigieren.

   * **[!UICONTROL Deeplink]**: Deep-Links sind URLs, die Benutzer zu bestimmten Abschnitten in einer App führen, selbst wenn die App geschlossen ist. Beim Klicken kann ein Dialogfeld angezeigt werden, in dem Benutzer aus verschiedenen Apps wählen können, die den Link verarbeiten können.

   * **[!UICONTROL App öffnen]**: Öffnen Sie App-URLs , um innerhalb einer Anwendung eine direkte Verbindung zu Inhalten herzustellen. Dadurch kann Ihre Anwendung sich selbst als Standard-Handler für einen bestimmten Link einrichten, wobei das Dialogfeld zur Unterscheidung umgangen wird.

   Weitere Informationen zum Umgang mit Android-App-Links finden Sie unter [Dokumentation für Android-Entwickler](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und **[!UICONTROL Zusätzliche HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Nachdem Sie den Nachrichteninhalt definiert haben, können Sie Testabonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!TAB Karussellvorlage]

1. Aus dem **[!UICONTROL Benachrichtigungstyp]** Dropdown-Liste auswählen **[!UICONTROL Karussell]**.

   ![](assets/rich_push_carousel.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in das Feld **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** -Felder.

   Die **[!UICONTROL Nachricht]** Text wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** wird angezeigt, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_carousel_1.png)

1. Verwenden Sie den Ausdruckseditor, um Inhalte zu definieren, Daten zu personalisieren und dynamischen Inhalt hinzuzufügen. [Weitere Informationen](../send/personalize.md)

1. Unter dem **[!UICONTROL Farboptionen]** Geben Sie die hexadezimalen Farbcodes für Ihre **[!UICONTROL Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Hintergrund]**.

1. Wählen Sie aus, wie **[!UICONTROL Karussell]** betrieben wird:

   * **[!UICONTROL Auto]**: durchläuft Bilder automatisch als Folien, wobei die Bilder in vordefinierten Intervallen durchlaufen werden.
   * **[!UICONTROL Manuell]**: ermöglicht Benutzern das manuelle Wischen zwischen Folien, um durch die Bilder zu navigieren.

1. Aus dem **[!UICONTROL Layout]** Dropdown-Liste auswählen **[!UICONTROL Filmstreifen]** -Option, um die Vorschau der vorherigen und der nächsten Bilder neben der Hauptfolie einzuschließen.

1. Klicks **[!UICONTROL Bild hinzufügen]** und geben Sie Ihre Bild-URL, Text- und AktionsURL ein.

   Stellen Sie sicher, dass Sie mindestens drei Bilder und maximal fünf Bilder einfügen.

   ![](assets/rich_push_carousel_2.png)

1. Um Ihre Push-Benachrichtigung weiter zu personalisieren, konfigurieren Sie die **[!UICONTROL Benachrichtigungsoptionen]** und **[!UICONTROL Zusätzliche HTTPv1-Optionen]** Ihrer Push-Benachrichtigung. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Nachdem Sie den Nachrichteninhalt definiert haben, können Sie Testabonnenten verwenden, um die Nachricht in der Vorschau anzuzeigen und zu testen.

>[!ENDTABS]

## Erweiterte Einstellungen für Push-Benachrichtigungen {#push-advanced}

### Benachrichtigungsoptionen {#notification-options}

| Parameter | Beschreibung |
|---------|---------|
| **[!UICONTROL Kanal-ID]** | Legen Sie die Kanal-ID Ihrer Benachrichtigung fest. Die Mobile App muss einen Kanal mit dieser Kanal-ID erstellen, bevor eine Benachrichtigung mit dieser Kanal-ID empfangen werden kann. |
| **[!UICONTROL Symbol]** | Legen Sie das Symbol der Benachrichtigung fest, das auf den Geräten Ihrer Profile angezeigt werden soll. |
| **[!UICONTROL Ton]** | Legt den Ton fest, der abgespielt werden soll, wenn das Gerät Ihre Benachrichtigung erhält. |
| **[!UICONTROL Tag]** | Legt eine Kennung fest, die zum Ersetzen bestehender Benachrichtigungen in der Benachrichtigungsablage verwendet wird. Dadurch wird verhindert, dass sich mehrere Benachrichtigungen ansammeln, und sichergestellt, dass nur die jeweils letzte relevante Benachrichtigung angezeigt wird. |
| **[!UICONTROL Farbe]** | Legen Sie die Symbolfarbe Ihrer Benachrichtigung mit hexadezimalem Farbcode fest. |
| **[!UICONTROL Klick-Aktion]** | Legen Sie die Aktion fest, die einem Benutzer zugeordnet ist, der auf Ihre Benachrichtigung klickt. |
| **[!UICONTROL Hintergrundfarbe für Benachrichtigungen]** | Legen Sie die Farbe Ihres Benachrichtigungshintergrunds mit Ihren Hexadezimalfarbcodes fest. |
| **[!UICONTROL Link-Typ]** | <ul><li>Web-URL: Web-URLs leiten Benutzer zu Online-Inhalten weiter. Nach dem Klicken wird der Standard-Webbrowser des Geräts aufgefordert, zu öffnen und zur angegebenen URL zu navigieren.</li><li>Deeplink: Deep-Links sind URLs, die Benutzer zu bestimmten Abschnitten in einer App führen, selbst wenn die App geschlossen ist. Beim Klicken kann ein Dialogfeld angezeigt werden, in dem Benutzer aus verschiedenen Apps wählen können, die den Link verarbeiten können.</li><li> App öffnen: Öffnen Sie App-URLs , um eine direkte Verbindung zu Inhalten innerhalb einer Anwendung herzustellen. Dadurch kann Ihre Anwendung sich selbst als Standard-Handler für einen bestimmten Link einrichten, wobei das Dialogfeld zur Unterscheidung umgangen wird.</li></ul> |

### Zusätzliche Optionen für HTTPv1 {#additional-options}

| Parameter | Beschreibung |
|---------|---------|
| **[!UICONTROL Ticker]** | Legen Sie den Ticker-Text Ihrer Benachrichtigung fest. Nur verfügbar bei Geräten mit Android 5.0 Lollipop. |
| **[!UICONTROL Sticky]** | Wenn diese Option aktiviert ist, bleibt die Benachrichtigung auch dann sichtbar, wenn darauf geklickt wird. <br>Wenn sie deaktiviert ist, wird die Benachrichtigung automatisch verworfen, sobald damit interagiert wird. Durch das Sticky-Verhalten können wichtige Benachrichtigungen über längere Zeiträume auf dem Bildschirm beibehalten werden. |
| **[!UICONTROL Bild]** | Legen Sie die URL des Bildes fest, das in Ihrer Benachrichtigung angezeigt werden soll. |
| **[!UICONTROL Benachrichtigungspriorität]** | Legen Sie die Prioritätsstufe Ihrer Benachrichtigung fest. Dies kann „Standard“, „Minimum“, „Niedrig“ oder „Hoch“ sein. Die Prioritätsstufe bestimmt die Wichtigkeit und Dringlichkeit der Benachrichtigung und beeinflusst deren Anzeige sowie die Frage, ob sie bestimmte Systemeinstellungen umgehen kann. Weitere Informationen hierzu finden Sie in der [FCM-Dokumentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Anzahl der Benachrichtigungen]** | Legt die Zahl der neuen ungelesenen Informationen fest, die direkt auf dem Symbol der App angezeigt werden. Dadurch können die Benutzenden schnell die Anzahl der ausstehenden Benachrichtigungen sehen. |
| **[!UICONTROL Sichtbarkeit]** | Legen Sie die Sichtbarkeitsstufe Ihrer Benachrichtigung fest. Dies kann öffentlich, privat oder geheim sein. Die Sichtbarkeitsstufe bestimmt, wie viel des Benachrichtigungsinhalts auf dem Sperrbildschirm und anderen sensiblen Bereichen angezeigt wird. Weitere Informationen finden Sie in der [FCM-Dokumentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Anwendungsvariablen]** | Damit können Sie das Verhalten von Benachrichtigungen definieren. Diese Variablen sind vollständig anpassbar und Teil der an das Mobilgerät gesendeten Nachrichten-Payload. |

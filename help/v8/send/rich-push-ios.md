---
audience: end-user
title: Erstellen eines Rich-Push-Benachrichtigungsversands
description: Erfahren Sie, wie Sie einen Rich-Push-Benachrichtigungsversand in iOS mit Adobe Campaign Web erstellen.
feature: Push
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 75a57ddb-558e-4dd2-a684-e63e51545554
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 100%

---

# Erstellen eines Rich-Push-Versands für iOS {#rich-push}

>[!IMPORTANT]
>
>Bevor Sie eine Rich-Push-Benachrichtigung entwerfen, müssen Sie zunächst Ihren V2-Connector konfigurieren. Eine detaillierte Vorgehensweise dazu finden Sie auf [dieser Seite](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application).

## Festlegen des Inhalts einer Benachrichtigung in iOS {#push-message}

Sobald Ihr Push-Versand erstellt ist, können Sie seinen Inhalt mit einer der folgenden Vorlagen definieren:

* **Standard** ermöglicht es Ihnen, Benachrichtigungen mit einem einfachen Symbol und einem zugehörigen Bild zu senden.

* **Einfach** ermöglicht es Ihnen, Text, Bilder und Schaltflächen in Ihre Benachrichtigungen einzufügen.

* **Karussell** ermöglicht es Ihnen, Benachrichtigungen mit Text und mehreren Bildern zu senden, zwischen denen die Benutzenden hin und her wischen können.

Navigieren Sie durch die folgenden Registerkarten, um mehr über die Personalisierung dieser Vorlagen zu erfahren.

>[!BEGINTABS]

>[!TAB Standard]

1. Wählen Sie **[!UICONTROL Allgemeine Benachrichtigung (Warnung, Ton, Badge)]** als Ihre **[!UICONTROL Art der Benachrichtigung]** aus.

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Standard]** aus.

   ![](assets/rich_push_ios_default_1.png)

1. Geben Sie in das Feld **[!UICONTROL Titel]** die Bezeichnung ein, die in der Liste der im Benachrichtigungscenter verfügbaren Benachrichtigungen erscheinen soll.

   In diesem Feld können Sie den Wert des Parameters **title** der iOS-Benachrichtigungs-Payload definieren.

1. Fügen Sie optional einen **[!UICONTROL Untertitel]** hinzu, der dem Parameter **subtitle** der iOS-Benachrichtigungs-Payload entspricht.

1. Geben Sie den Inhalt der Nachricht im Abschnitt **[!UICONTROL Nachrichteninhalt]** des Assistenten ein.

   ![](assets/rich_push_ios_default_2.png)

1. Navigieren Sie zur Registerkarte **[!UICONTROL Ton und Badge]**, um zusätzliche Einstellungen wie Ton- und Badge-Optionen für Ihre Benachrichtigungen anzupassen. [Weitere Informationen](#sound-badge)

   ![](assets/rich_push_ios_default_3.png)

1. Ihre **[!UICONTROL Anwendungsvariablen]** werden automatisch von der Registerkarte **[!UICONTROL Anwendungsvariablen]** hinzugefügt. Damit können Sie beispielsweise das Benachrichtigungsverhalten definieren. So können Sie einen speziellen Anwendungsbildschirm konfigurieren, der angezeigt wird, wenn der Benutzer die Benachrichtigung aktiviert.

1. Weitere Anpassungen finden Sie in den **[!UICONTROL erweiterten Optionen]**, die für Ihre Push-Benachrichtigungen zur Verfügung stehen. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_ios_default_4.png)

1. Sobald die Benachrichtigung konfiguriert ist, klicken Sie auf die Registerkarte **[!UICONTROL Vorschau]**, um eine Vorschau der Benachrichtigung anzuzeigen.

>[!TAB Einfach]

1. Wählen Sie **[!UICONTROL Allgemeine Benachrichtigung (Warnung, Ton, Badge)]** als Ihre **[!UICONTROL Art der Benachrichtigung]** aus.

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Einfach]** aus.

   ![](assets/rich_push_ios_basic_1.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Erweiterte Nachricht]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_ios_basic_2.png)

1. Fügen Sie optional einen **[!UICONTROL Untertitel]** hinzu, der dem Parameter **subtitle** der iOS-Benachrichtigungs-Payload entspricht.

1. Navigieren Sie zur Registerkarte **[!UICONTROL Ton und Badge]**, um zusätzliche Einstellungen wie Ton- und Badge-Optionen für Ihre Benachrichtigungen anzupassen. [Weitere Informationen](#sound-badge)

1. Ihre **[!UICONTROL Anwendungsvariablen]** werden automatisch von der Registerkarte **[!UICONTROL Anwendungsvariablen]** hinzugefügt. Damit können Sie beispielsweise das Benachrichtigungsverhalten definieren. So können Sie einen speziellen Anwendungsbildschirm konfigurieren, der angezeigt wird, wenn der Benutzer die Benachrichtigung aktiviert.

1. Weitere Anpassungen finden Sie in den **[!UICONTROL erweiterten Optionen]**, die für Ihre Push-Benachrichtigungen zur Verfügung stehen. [Weitere Informationen](#push-advanced)

   ![](assets/rich_push_ios_default_4.png)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

   ![](assets/rich_push_ios_basic_3.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten einsetzen, um die Nachricht in einer Vorschau anzuzeigen und zu testen.

>[!TAB Karussell]

1. Wählen Sie **[!UICONTROL Allgemeine Benachrichtigung (Warnung, Ton, Badge)]** als Ihre **[!UICONTROL Art der Benachrichtigung]** aus.

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Karussell]** aus.

   ![](assets/rich_push_ios_carousel_1.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Erweiterter Titel]** und **[!UICONTROL Nachricht]** ein.

   ![](assets/rich_push_ios_carousel_2.png)

1. Navigieren Sie zur Registerkarte **[!UICONTROL Ton und Badge]**, um zusätzliche Einstellungen wie Ton- und Badge-Optionen für Ihre Benachrichtigungen anzupassen. [Weitere Informationen](#sound-badge)

1. Ihre **[!UICONTROL Anwendungsvariablen]** werden automatisch von der Registerkarte **[!UICONTROL Anwendungsvariablen]** hinzugefügt. Damit können Sie beispielsweise das Benachrichtigungsverhalten definieren. So können Sie einen speziellen Anwendungsbildschirm konfigurieren, der angezeigt wird, wenn der Benutzer die Benachrichtigung aktiviert.

   ![](assets/rich_push_ios_carousel_4.png)

1. Weitere Anpassungen finden Sie in den **[!UICONTROL erweiterten Optionen]**, die für Ihre Push-Benachrichtigungen zur Verfügung stehen. [Weitere Informationen](#push-advanced)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

1. Wählen Sie auf der Registerkarte **[!UICONTROL Karusselloptionen]**, wie das **[!UICONTROL Karussell]** bedient werden soll:

   * **[!UICONTROL Automatisch]**: Die Bilder werden automatisch in vordefinierten Intervallen als Folien wiedergegeben.
   * **[!UICONTROL Manuell]**: Benutzende können manuell zwischen den Folien streichen, um durch die Bilder zu navigieren.

1. Klicken Sie auf **[!UICONTROL Bild hinzufügen]** und geben Sie Ihre **[!UICONTROL Bild-URL]**, den **[!UICONTROL Text]** und den **[!UICONTROL Aktions-URL]** ein.

   Stellen Sie sicher, dass Sie mindestens drei und maximal fünf Bilder einfügen.

   ![](assets/rich_push_ios_carousel_3.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten einsetzen, um die Nachricht in einer Vorschau anzuzeigen und zu testen.

>[!TAB Timer]

1. Wählen Sie **[!UICONTROL Allgemeine Benachrichtigung (Warnung, Ton, Badge)]** als Ihre **[!UICONTROL Art der Benachrichtigung]** aus.

1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Art der Benachrichtigung]** die Option **[!UICONTROL Timer]** aus.

   ![](assets/rich_push_ios_timer_1.png)

1. Um Ihre Nachricht zu erstellen, geben Sie Ihren Text in die Felder **[!UICONTROL Titel]**, **[!UICONTROL Erweiterter Titel]**, **[!UICONTROL Nachricht]** und **[!UICONTROL Erweiterte Nachricht]** ein.

   Der Text der **[!UICONTROL Nachricht]** wird in der ausgeblendeten Ansicht angezeigt, während die **[!UICONTROL Erweiterte Nachricht]** angezeigt wird, wenn die Benachrichtigung erweitert wird.

   ![](assets/rich_push_ios_timer_2.png)

1. Fügen Sie optional einen **[!UICONTROL Untertitel]** hinzu, der dem Parameter **subtitle** der iOS-Benachrichtigungs-Payload entspricht.

1. Navigieren Sie zur Registerkarte **[!UICONTROL Ton und Badge]**, um zusätzliche Einstellungen wie Ton- und Badge-Optionen für Ihre Benachrichtigungen anzupassen. [Weitere Informationen](#sound-badge)

1. Ihre **[!UICONTROL Anwendungsvariablen]** werden automatisch von der Registerkarte **[!UICONTROL Anwendungsvariablen]** hinzugefügt. Damit können Sie beispielsweise das Benachrichtigungsverhalten definieren. So können Sie einen speziellen Anwendungsbildschirm konfigurieren, der angezeigt wird, wenn der Benutzer die Benachrichtigung aktiviert.

1. Weitere Anpassungen finden Sie in den **[!UICONTROL erweiterten Optionen]**, die für Ihre Push-Benachrichtigungen zur Verfügung stehen. [Weitere Informationen](#push-advanced)

1. Geben Sie im Menü **[!UICONTROL Farboptionen]** die hexadezimalen Farb-Codes für Ihren **[!UICONTROL Titel]**, die **[!UICONTROL Nachricht]** und den **[!UICONTROL Hintergrund]** ein.

   ![](assets/rich_push_ios_timer_4.png)

1. Legen Sie auf der Registerkarte **[!UICONTROL Timer]** die **[!UICONTROL Dauer des Timers]** in Sekunden oder den **[!UICONTROL Zeitstempel für Timer-Ende]** auf einen bestimmten Epoch-Zeitstempel fest.

1. Geben Sie den Text und das Bild, die nach Ablauf des Timers angezeigt werden sollen, in die Felder **[!UICONTROL Alternativer Titel]**, **[!UICONTROL Alternative Nachricht]** und **[!UICONTROL Alternatives Bild]** ein.

   ![](assets/rich_push_ios_timer_3.png)

Sobald Sie den Inhalt Ihrer Nachricht definiert haben, können Sie Testabonnentinnen und -abonnenten einsetzen, um die Nachricht in einer Vorschau anzuzeigen und zu testen.

>[!ENDTABS]

## Erweiterte Einstellungen für Push-Benachrichtigungen {#push-advanced}

### Optionen für Ton und Badge {#sound-badge}

| Parameter | Beschreibung |
|---------|---------|
| **[!UICONTROL Badge entfernen]** | Aktivieren Sie diese Optionen, um den Badge-Wert zu aktualisieren. |
| **[!UICONTROL Wert]** | Legen Sie eine Zahl fest, die verwendet wird, um direkt auf dem Anwendungssymbol die Anzahl der neuen ungelesenen Informationen anzuzeigen. |
| **[!UICONTROL Kritischer Alarmmodus]** | Aktivieren Sie diese Option, um Ihrer Benachrichtigung einen Ton hinzuzufügen, selbst wenn das Telefon der Benutzerin oder des Benutzers auf den Fokusmodus festgelegt oder das iPhone stummgeschaltet ist. |
| **[!UICONTROL Name]** | Wählen Sie den Ton aus, der beim Erhalt der Benachrichtigung vom Mobilgerät abgespielt werden soll. |
| **[!UICONTROL Lautstärke]** | Legen Sie die Lautstärke Ihres Tons auf einer Skala von 0 bis 100 fest. Die Töne müssen in der App enthalten sein und bei der Erstellung des Dienstes definiert werden. |

### Erweiterte Optionen {#notification-options}

| Parameter | Beschreibung |
|---------|---------|
| **[!UICONTROL Veränderlicher Inhalt]** | Aktivieren Sie diese Option, damit die Mobile App Medieninhalte herunterladen kann. |
| **[!UICONTROL Thread-ID]** | Legen Sie die Kennung fest, die zur Gruppierung zusammengehöriger Meldungen verwendet wird. |
| **[!UICONTROL Kategorie]** | Legen Sie den Namen Ihrer Kategorie-ID fest, über die Aktionsschaltflächen angezeigt werden. Diese Benachrichtigungen ermöglichen es Benutzerinnen und Benutzern, verschiedene Aufgaben als Reaktion auf eine Benachrichtigung schneller auszuführen, ohne die App öffnen oder darin navigieren zu müssen. |
| **[!UICONTROL ID des Zielinhalts]** | Legen Sie eine Kennung fest, die angibt, welches App-Fenster beim Öffnen der Benachrichtigung im Vordergrund erscheinen soll. |
| **[!UICONTROL Startbild]** | Legen Sie den Dateinamen des anzuzeigenden Startbildes fest. Wenn die Benutzerinnen und Benutzer die App starten, wird anstelle des Startbildschirms der App das ausgewählte Bild angezeigt. |
| **[!UICONTROL Klick-Aktion]** | Legt die Aktion fest, die für das Klicken der Benutzenden auf Ihre Benachrichtigung zugewiesen ist. |
| **[!UICONTROL Unterbrechungsgrad]** | <ul><li>Aktiv: Standardmäßig eingestellt, zeigt das System die Benachrichtigung sofort an, der Bildschirm leuchtet auf und es kann ein Ton abgespielt werden. Benachrichtigungen umgehen nicht die Fokusmodi.</li><li>Passiv: Das System fügt die Benachrichtigung der Benachrichtigungsliste hinzu, ohne dass der Bildschirm aufleuchtet oder ein Ton abgespielt wird. Benachrichtigungen umgehen nicht die Fokusmodi.</li><li> Zeitkritisch: Das System zeigt die Benachrichtigung sofort an, der Bildschirm leuchtet auf, es kann ein Ton abgespielt werden und Fokusmodi werden umgangen. Für diese Stufe ist keine spezielle Berechtigung von Apple erforderlich.</li><li>Kritisch: Das System zeigt die Benachrichtigung sofort an, der Bildschirm leuchtet auf und der Stummschalter oder die Focus-Modi werden umgangen. Beachten Sie, dass für diese Stufe eine spezielle Berechtigung von Apple erforderlich ist.</li></ul> |
| **[!UICONTROL Relevanzwert]** | Legen Sie einen Relevanzwert auf der Skala von 0 bis 100 fest. Das System verwendet diesen Wert, um die Benachrichtigungen in der Benachrichtigungszusammenfassung zu sortieren. |

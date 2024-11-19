---
title: Definieren und Personalisieren des SMS-Inhalts
description: Erfahren Sie, wie Sie den Inhalt eines SMS-Versands definieren und personalisieren.
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
source-git-commit: 0ef082b49261d0d2de5a6891a4a7f0cf5aafa221
workflow-type: ht
source-wordcount: '261'
ht-degree: 100%

---

# Definieren des SMS-Inhalts {#sms-content}

So konfigurieren Sie den Inhalt Ihres SMS-Versands:

1. Geben Sie den Inhalt Ihrer Nachricht auf der Registerkarte **[!UICONTROL Textinhalt]** ein.

   ![](assets/sms_content.png){zoomable="yes"}

1. Sie können Ihre Nachricht personalisieren, indem Sie Personalisierungsfelder (z. B. den Vornamen) oder vordefinierte Personalisierungsblöcke (z. B. Grußformeln) einfügen. Klicken Sie auf die Schaltfläche „Personalisierung“, um diese hinzuzufügen:

   ![](assets/sms_perso.png){zoomable="yes"}

   Nachdem Sie beispielsweise auf **[!UICONTROL Empfänger]** > **[!UICONTROL Vorname]** geklickt haben, wird der SMS-Inhalt mit dem Feld „Personalisierung“ wie folgt personalisiert:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   Weitere Informationen zur Personalisierung in Adobe Campaign finden Sie in [diesem Abschnitt](../personalize.md).

1. Sie können eine Vorschau des Versandinhalts auf der Registerkarte **[!UICONTROL Vorschau]** anzeigen. Um Ihre Personalisierungseinstellungen zu überprüfen, klicken Sie auf die Dropdown-Liste **[!UICONTROL Personalisierung testen]** und wählen Sie eine Empfängerin oder einen Empfänger aus.

   ![](assets/sms_preview.png){zoomable="yes"}

   Anschließend können Sie die Vorschau Ihrer SMS mit der Personalisierung überprüfen:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* Bei Verwendung der Code-Seite „Latin-1 (ISO-8859-1)“ ist die Länge von SMS auf 160, bei Unicode auf 70 Zeichen begrenzt. Gewisse Sonderzeichen können sich auf die Länge der Nachricht auswirken. Weitere Informationen zur Nachrichtenlänge finden Sie im Abschnitt [Transliteration von SMS-Zeichen](smpp-external-account.md#smpp-channel-settings).
>
>* Wenn die Nachricht Personalisierungsfelder oder bedingte Inhalte enthält, kann die Länge von Empfänger zu Empfänger variieren. Daher sollte die Länge jeweils nach erfolgter Personalisierung ausgewertet werden.
>
>*Während der Analysephase wird die Nachrichtenlänge geprüft und im Falle eines Überschreitens ein Warnhinweis erzeugt.

Nachdem Sie den Inhalt Ihres Versands erstellt haben, können Sie [Ihre Zielgruppe auswählen](sms-audience.md).

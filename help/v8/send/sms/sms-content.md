---
title: SMS zur Inhaltsdefinition
description: Erfahren Sie, wie Sie den Inhalt eines SMS-Versands einrichten.
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 32%

---


# SMS-Inhalt {#sms-content}

So konfigurieren Sie den SMS-Inhalt:

1. Geben Sie den Inhalt Ihrer Nachricht im Assistenten **[!UICONTROL Textinhalt]** ein.

   ![](assets/sms_content.png){zoomable="yes"}

1. Sie können Ihre Nachricht personalisieren, indem Sie Personalisierungsfelder einfügen (z. B. den Vornamen) oder vordefinierte Gestaltungsbausteine einfügen (z. B. Grußformeln). Sie können auf die Personalisierungsschaltfläche klicken, um diese hinzuzufügen:

   ![](assets/sms_perso.png){zoomable="yes"}

   Nachdem Sie auf **[!UICONTROL Empfänger]** > **[!UICONTROL Vorname]** geklickt haben, wird die Personalisierung wie folgt aussehen:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. Sie können eine Vorschau Ihres Versands anzeigen, indem Sie im Tab **[!UICONTROL Vorschau]** auf die Dropdownliste **[!UICONTROL Personalisierung testen]** klicken und in der Tabelle **[!UICONTROL Empfänger]** einen Empfänger auswählen.

   ![](assets/sms_preview.png){zoomable="yes"}

   Sie erhalten die Vorschau Ihrer SMS mit der Personalisierung:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* Bei Verwendung der Codepage „Latin-1 (ISO-8859-1)“ ist die Länge von SMS auf 160, bei Unicode auf 70 Zeichen begrenzt. Gewisse Sonderzeichen können die Länge der Nachricht beeinflussen. Weiterführende Informationen zur Nachrichtenlänge finden Sie im Abschnitt [Transliteration von SMS-Zeichen](smpp-external-account.md#smpp-channel-settings) .
>
>* Wenn die Nachricht Personalisierungsfelder oder bedingte Inhalte enthält, kann die Länge von Empfänger zu Empfänger variieren. Daher sollte die Länge jeweils nach erfolgter Personalisierung ausgewertet werden.
>
>*Wenn Sie die Analyse starten, wird die Nachrichtenlänge geprüft und im Falle eines Überlaufs ein Warnhinweis angezeigt.

Nachdem Sie den Inhalt Ihres Versands erstellt haben, können Sie [Ihre Audience auswählen](sms-audience.md).
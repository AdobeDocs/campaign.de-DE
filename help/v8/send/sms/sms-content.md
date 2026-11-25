---
title: Definieren und Personalisieren des SMS-Inhalts
description: Erfahren Sie, wie Sie den Inhalt eines SMS-Versands definieren und personalisieren.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
TQID: 'https://experienceleague.adobe.com/N4C8Rkg-Kl-82FCZAvJ12KofuRObW170ySJaCHgW5wM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 63%
---
# SMS-Inhalt erstellen {#sms-content}

So konfigurieren Sie den Inhalt Ihres SMS-Versands:

1. Geben Sie den Inhalt Ihrer Nachricht auf der Registerkarte **[!UICONTROL Textinhalt]** ein.

   ![Registerkarte „Textinhalt“ des SMS-Versands mit eingegebenem Nachrichtentext](assets/sms_content.png){zoomable="yes"}

1. Sie können Ihre Nachricht personalisieren, indem Sie Personalisierungsfelder einfügen (z. B. den Vornamen hinzufügen) oder vordefinierte Personalisierungsblöcke einfügen (z. B. die Grußformeln hinzufügen). Klicken Sie auf die Schaltfläche „Personalisierung“, um diese hinzuzufügen:

   ![Personalization-Menü, das im Untermenü SMS-Textinhalt geöffnet ist und den Vornamen und andere Felder enthält](assets/sms_perso.png){zoomable="yes"}

   Nachdem Sie beispielsweise auf **[!UICONTROL Empfänger]** > **[!UICONTROL Vorname]** geklickt haben, wird der SMS-Inhalt mit dem Feld „Personalisierung“ wie folgt personalisiert:

   ![SMS-Textinhalt mit dem in die Nachricht eingefügten Personalisierungsfeld Vorname](assets/sms_perso_recipient.png){zoomable="yes"}

   Weitere Informationen zur Personalisierung in Adobe Campaign finden Sie unter [Erste Schritte mit der Personalisierung](../personalize.md).

1. Sie können eine Vorschau Ihres Versandinhalts über die Registerkarte **[!UICONTROL Vorschau]** anzeigen. Um Ihre Personalisierungseinstellungen zu überprüfen, klicken Sie auf die Dropdown-Liste **[!UICONTROL Personalisierung testen]** und wählen Sie eine Empfängerin oder einen Empfänger aus.

   ![Registerkarte „Vorschau“ der SMS mit geöffnetem Dropdown-Menü „Personalisierung testen“ zur Auswahl eines Empfängers](assets/sms_preview.png){zoomable="yes"}

   Anschließend können Sie die Vorschau Ihrer SMS mit der Personalisierung überprüfen:

   ![SMS-Vorschau mit dem Vornamen wird durch den Empfängerwert ersetzt, angezeigt als Text und in einem Telefon-Mock-up](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* SMS-Nachrichten sind auf eine Länge von 160 Zeichen beschränkt, wenn die Code-Seite Latin-1 (ISO-8859-1) verwendet wird. Wenn die Nachricht in Unicode geschrieben ist, darf sie 70 Zeichen nicht überschreiten. Bestimmte Sonderzeichen können sich auf die Nachrichtenlänge auswirken. Weitere Informationen zur Nachrichtenlänge finden Sie im Abschnitt [Transliteration von SMS-Zeichen](smpp-external-account.md#smpp-channel-settings).
>
>* Wenn die Nachricht Personalisierungsfelder oder Felder für bedingte Inhalte enthält, kann die Länge von einer empfangenden Person zur anderen variieren. Die Länge der Nachricht muss nach der Personalisierung ausgewertet werden.
>
>*Während der Analysephase wird die Nachrichtenlänge geprüft und im Falle eines Überschreitens ein Warnhinweis erzeugt.

Nachdem Sie den Inhalt Ihres Versands erstellt haben, können Sie [Ihre Zielgruppe auswählen](sms-audience.md).

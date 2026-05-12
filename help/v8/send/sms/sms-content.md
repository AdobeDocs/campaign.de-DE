---
title: Definieren und Personalisieren des SMS-Inhalts
description: Erfahren Sie, wie Sie den Inhalt eines SMS-Versands definieren und personalisieren.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
TQID: https://experienceleague.adobe.com/N4C8Rkg-Kl-82FCZAvJ12KofuRObW170ySJaCHgW5wM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 70%

---

# SMS-Inhalt erstellen {#sms-content}

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
>* SMS-Nachrichten sind auf eine Länge von 160 Zeichen beschränkt, wenn die Code-Seite Latin-1 (ISO-8859-1) verwendet wird. Wenn die Nachricht in Unicode geschrieben ist, darf sie 70 Zeichen nicht überschreiten. Bestimmte Sonderzeichen können sich auf die Nachrichtenlänge auswirken. Weitere Informationen zur Nachrichtenlänge finden Sie im Abschnitt [Transliteration von SMS-Zeichen](smpp-external-account.md#smpp-channel-settings).
>
>* Wenn Personalisierungsfelder oder bedingte Inhaltsfelder vorhanden sind, variiert die Größe der Nachricht von einem Empfänger zum anderen. Die Länge der Nachricht muss nach der Personalisierung ausgewertet werden.
>
>*Während der Analysephase wird die Nachrichtenlänge geprüft und im Falle eines Überschreitens ein Warnhinweis erzeugt.

Nachdem Sie den Inhalt Ihres Versands erstellt haben, können Sie [Ihre Zielgruppe auswählen](sms-audience.md).

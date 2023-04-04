---
title: Einstellungen für den E-Mail-Kanal in Campaign
description: Einstellungen für den E-Mail-Kanal in Campaign
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 100%

---

# Einstellungen für den E-Mail-Kanal in Campaign

## E-Mail-BCC {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Sie können Adobe Campaign so konfigurieren, dass von den von der Plattform gesendeten E-Mails eine Kopie beibehalten wird.

Adobe Campaign selbst ermöglicht keine Verwaltung von archivierten Dateien. Sie können aber die gewünschten Nachrichten an eine bestimmte BCC (Blind Carbon Copy)-E-Mail-Adresse senden, wo sie mithilfe eines externen Systems verarbeitet und archiviert werden. Die .eml-Dateien, die den gesendeten E-Mails entsprechen, können dann auf einen Remote-Server wie z. B. einen SMTP-E-Mail-Server übertragen werden.

>[!CAUTION]
>
>Aus Datenschutzgründen müssen BCC-E-Mails von einem Archivierungssystem bearbeitet werden, in dem personenbezogene Daten (PII, Personally Identifiable Information) sicher aufbewahrt werden.

Das Archivierungsziel ist die von Ihnen ausgewählte BCC-E-Mail-Adresse, die für die Versandempfänger unsichtbar bleibt.

![](../assets/do-not-localize/speech.png) Wenn Sie Managed Cloud Services verwenden, [wenden Sie sich an Adobe](../start/campaign-faq.md#support){target="_blank"}, um die für die Archivierung zu verwendende BCC-E-Mail-Adresse mitzuteilen.

Nachdem die BCC-E-Mail-Adresse definiert wurde, müssen Sie die entsprechende Option auf Versandebene aktivieren.

>[!CAUTION]
>
>Beim Erstellen eines neuen Versands oder einer neuen Versandvorlage ist **[!UICONTROL E-Mail-BCC]** nicht standardmäßig aktiviert. Sie müssen die Funktion auf der E-Mail-Versand- oder Versandvorlagenebene manuell aktivieren.


Gehen Sie dazu wie folgt vor:

1. Gehen Sie zu **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Sendungen]** oder **[!UICONTROL Ressourcen]** > **[!UICONTROL Vorlagen]** > **[!UICONTROL Versandvorlagen]**.
1. Wählen Sie den gewünschten Versand aus oder duplizieren Sie die Standardvorlage **[!UICONTROL E-Mail-Versand]**, und wählen Sie dann die duplizierte Vorlage aus.
1. Wählen Sie die **[!UICONTROL Eigenschaften]**-Schaltfläche aus.
1. Gehen Sie in den **[!UICONTROL Versand]**-Tab.
1. Aktivieren Sie die Option **[!UICONTROL E-Mail-BCC.]**

   ![](assets/email-bcc.png)

1. Klicken Sie auf **[!UICONTROL OK]**.

Eine Kopie aller gesendeten Nachrichten für jeden Versand, der auf dieser Vorlage basiert, wird an die dafür konfigurierte BCC-E-Mail-Adresse gesendet.

Beachten Sie die folgenden Besonderheiten und Empfehlungen:

* Sie können nur eine einzige BCC-E-Mail-Adresse verwenden.

* Stellen Sie sicher, dass die BCC-Adresse über genügend Aufnahmekapazität verfügt, um alle gesendeten E-Mails zu archivieren.

* E-Mail-BCC <!--with Enhanced MTA--> sendet die Nachrichten an die BCC-E-Mail-Adresse, bevor sie an die Empfänger gesendet werden. Dies kann dazu führen, dass BCC-Nachrichten gesendet werden, auch wenn die Original-Sendungen möglicherweise einen Bounce erzeugt haben. Weitere Informationen zu Bounces finden Sie unter [Fehlgeschlagene Sendungen](../send/delivery-failures.md).

* Wenn die an eine BCC-Adresse gesendeten E-Mails geöffnet und angeklickt werden, wird dies in der Versandanalyse in **[!UICONTROL Gesamtöffnungen]** und **[!UICONTROL Klicks]** berücksichtigt, was zu falschen Berechnungen führen könnte.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Weitere Informationen**

In diesen Abschnitten:

* [Verwenden von E-Mail-Versandvorlagen](../send/create-templates.md)

* [Ursachen für das Fehlschlagen von Sendungen](../send/delivery-failures.md)


Und in der Campaign Classic v7-Dokumentation:

* [Auswählen des E-Mail-Formats](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#selecting-message-formats){target="_blank"}

* [Auswählen der Zeichencodierung](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#character-encoding){target="_blank"}

* [Festlegen der Bounce-E-Mail-Adresse](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#managing-bounce-emails){target="_blank"}


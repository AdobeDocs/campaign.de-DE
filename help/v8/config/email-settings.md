---
title: Einstellungen für den E-Mail-Kanal in Campaign
description: Einstellungen für den E-Mail-Kanal in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 49%

---

# Einstellungen für den E-Mail-Kanal in Campaign

## E-Mail-BCC {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Sie können Adobe Campaign so konfigurieren, dass von den von der Plattform gesendeten E-Mails eine Kopie beibehalten wird.

Adobe Campaign selbst ermöglicht keine Verwaltung von archivierten Dateien. Sie können die gewünschten Nachrichten an eine dedizierte BCC-E-Mail-Adresse (Blind Carbon Copy) senden, von der aus sie mithilfe eines externen Systems verarbeitet und archiviert werden können. Die .eml-Dateien, die den gesendeten E-Mails entsprechen, können dann auf einen Remote-Server wie einen SMTP-E-Mail-Server übertragen werden.

>[!CAUTION]
>
>Aus Datenschutzgründen müssen BCC-E-Mails von einem Archivierungssystem bearbeitet werden, in dem personenbezogene Daten (PII, Personally Identifiable Information) sicher aufbewahrt werden.

Das Archivierungsziel ist die von Ihnen ausgewählte BCC-E-Mail-Adresse, die für die Versandempfänger unsichtbar bleibt.

![](../assets/do-not-localize/speech.png)  Als Benutzer von Managed Cloud Services [Adobe kontaktieren](../start/campaign-faq.md#support){target=&quot;_blank&quot;}, um die für die Archivierung zu verwendende BCC-E-Mail-Adresse mitzuteilen.

Nachdem die BCC-E-Mail-Adresse definiert wurde, müssen Sie die entsprechende Option auf Versandebene aktivieren.

>[!CAUTION]
>
>Bei der Erstellung eines neuen Versands oder einer neuen Versandvorlage **[!UICONTROL E-Mail-BCC]** ist standardmäßig nicht aktiviert. Sie müssen sie manuell in der E-Mail-Versand- oder Versandvorlage aktivieren.


Gehen Sie dazu wie folgt vor:

1. Navigieren Sie zu **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Sendungen]** oder **[!UICONTROL Ressourcen]** > **[!UICONTROL Vorlagen]** > **[!UICONTROL Versandvorlagen]**.
1. Wählen Sie den gewünschten Versand aus oder duplizieren Sie die Standardvorlage **[!UICONTROL E-Mail-Versand]**, und wählen Sie dann die duplizierte Vorlage aus.
1. Wählen Sie die **[!UICONTROL Eigenschaften]**-Schaltfläche aus.
1. Gehen Sie in den **[!UICONTROL Versand]**-Tab.
1. Aktivieren Sie die Option **[!UICONTROL E-Mail-BCC.]**

   ![](assets/email-bcc.png)

1. Auswählen **[!UICONTROL Ok]**.

Eine Kopie aller gesendeten Nachrichten für jeden auf dieser Vorlage basierenden Versand wird an die konfigurierte E-Mail-BCC-Adresse gesendet.

Beachten Sie die folgenden Besonderheiten und Empfehlungen:

* Sie können nur eine einzige BCC-E-Mail-Adresse verwenden.

* Stellen Sie sicher, dass die BCC-Adresse über genügend Aufnahmekapazität verfügt, um alle gesendeten E-Mails zu archivieren.

* E-Mail-BCC <!--with Enhanced MTA--> sendet an die BCC-E-Mail-Adresse, bevor die Nachrichten an die Empfänger gesendet werden. Dies kann dazu führen, dass BCC-Nachrichten gesendet werden, auch wenn die ursprünglichen Sendungen möglicherweise nicht durchgeführt wurden. Weitere Informationen zu Bounces finden Sie unter [Fehlgeschlagene Sendungen](../send/delivery-failures.md).

* Wenn die an eine BCC-Adresse gesendeten E-Mails geöffnet und angeklickt werden, wird dies in der Versandanalyse in **[!UICONTROL Gesamtöffnungen]** und **[!UICONTROL Klicks]** berücksichtigt, was zu falschen Berechnungen führen könnte.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7**

* [Mirror-Seite erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#generating-mirror-page){target=&quot;_blank&quot;}

* [E-Mail-Format auswählen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#selecting-message-formats){target=&quot;_blank&quot;}

* [Zeichencodierung auswählen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#character-encoding){target=&quot;_blank&quot;}

* [Bounce-E-Mail-Adresse festlegen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=de#managing-bounce-emails){target=&quot;_blank&quot;}

* [E-Mail-Versandvorlagen verwenden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=de){target=&quot;_blank&quot;}

* [Fehlgeschlagene Sendungen analysieren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html?lang=de){target=&quot;_blank&quot;} 

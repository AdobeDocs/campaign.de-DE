---
title: Senden einer Kopie Ihrer Nachrichten an eine BCC-Adresse
description: Erfahren Sie, wie Sie E-Mail-BCC in Adobe Campaign aktivieren
feature: Email
role: User
level: Beginner
source-git-commit: 87c971ac6cf4abb6b04d52ce60ac2036055e1e02
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 36%

---


# Senden einer Kopie Ihrer Nachrichten an eine BCC-Adresse {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## Über E-Mail-BCC {#gs-bcc}

Sie können Adobe Campaign so konfigurieren, dass eine Kopie der von Ihrer Plattform gesendeten E-Mails aufbewahrt wird. Diese Option ermöglicht den Versand von Nachrichten an eine BCC-E-Mail-Adresse (Blind Carbon Copy), von der aus sie mithilfe eines externen Systems verarbeitet und archiviert werden können.
Adobe Campaign selbst ermöglicht keine Verwaltung von archivierten Dateien. Die .eml-Dateien, die den gesendeten E-Mails entsprechen, können dann auf einen Remote-Server wie z. B. einen SMTP-E-Mail-Server übertragen werden.

Das Archivierungsziel ist die von Ihnen ausgewählte BCC-E-Mail-Adresse, die für die Versandempfänger unsichtbar bleibt. Nachdem die BCC-E-Mail-Adresse definiert wurde, müssen Sie die entsprechende Option im [Versandvorlage](create-templates.md) Ebene.

![](../assets/do-not-localize/speech.png) Wenn Sie Managed Cloud Services verwenden, [wenden Sie sich an Adobe](../start/campaign-faq.md#support){target="_blank"}, um die für die Archivierung zu verwendende BCC-E-Mail-Adresse mitzuteilen.

>[!CAUTION]
>
>Aus Datenschutzgründen müssen BCC-E-Mails von einem Archivierungssystem bearbeitet werden, in dem personenbezogene Daten (PII, Personally Identifiable Information) sicher aufbewahrt werden.


## E-Mail-BCC aktivieren {#enable-bcc}

So aktivieren Sie BCC für eine bestimmte [Versandvorlage](create-templates.md)führen Sie die folgenden Schritte aus:

1. Navigieren Sie im Campaign-Explorer zum Ordner Versandvorlagen . Standardmäßig werden Versandvorlagen im **[!UICONTROL Ressourcen]** > **[!UICONTROL Vorlagen]** > **[!UICONTROL Versandvorlagen]** Ordner.
1. Bearbeiten Sie die Versandvorlage, um sie mit BCC zu aktualisieren.
1. Wählen Sie die **[!UICONTROL Eigenschaften]**-Schaltfläche aus.
1. Aus dem **[!UICONTROL Versand]** Registerkarte, überprüfen Sie die **[!UICONTROL Email BCC]** -Option.

   ![](assets/email-bcc.png)

1. Klicks **[!UICONTROL Ok]** zur Bestätigung.

Eine Kopie aller gesendeten Nachrichten für jeden auf dieser Vorlage basierenden Versand wird an die E-Mail-BCC-Adresse gesendet, die für Ihre Plattform konfiguriert wurde.

## Schutzmechanismen und Empfehlungen {#recommendations-bcc}

Bei der Verwendung von E-Mail-BCC mit Adobe Campaign gelten die folgenden Limits und Empfehlungen:

* Sie können nur eine einzige BCC-E-Mail-Adresse verwenden.

* Stellen Sie sicher, dass die BCC-Adresse über genügend Aufnahmekapazität verfügt, um alle gesendeten E-Mails zu archivieren.

* E-Mail-BCC <!--with Enhanced MTA--> sendet die Nachrichten an die BCC-E-Mail-Adresse, bevor sie an die Empfänger gesendet werden. Dies kann dazu führen, dass BCC-Nachrichten gesendet werden, auch wenn die Original-Sendungen möglicherweise einen Bounce erzeugt haben. Weitere Informationen zu Bounces finden Sie unter [Fehlgeschlagene Sendungen](delivery-failures.md).

* E-Mails, die an die BCC-Adresse gesendet werden, sollten nicht geöffnet und angeklickt werden, da diese Aktivitäten im Abschnitt **[!UICONTROL Öffnungen insgesamt]** und **[!UICONTROL Klicks]** aus der Versandanalyse zu falschen Berechnungen führen.

<!--Only successfully sent emails are taken in account, bounces are not.-->

---
product: campaign
title: Veröffentlichen des Kampagnenkits
description: Veröffentlichen des Kampagnenkits
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 2cd1981d-f192-41dc-b2f2-4fcd60493079
TQID: https://experienceleague.adobe.com/cikc1fFIGeRzZ-mas4mqGqMsuMCSDOHhBT2g4tf8fZw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7e1c567dc2f70e2d9ada67c2ec46918c5821753e
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 100%
---
# Veröffentlichen des Kampagnenkits{#publishing-the-campaign-package}

Die Benutzenden der Zentralstelle veröffentlichen in der **[!UICONTROL Liste der Kampagnenkits]** die Kits, die den Lokalstellen zur Verfügung gestellt werden sollen.

Bevor sie in der Liste der Kampagnenkits veröffentlicht werden können, müssen die Kampagnenkits von der Zentralstelle genehmigt werden. Zu diesem Zweck können Sie Validierungsverantwortliche oder Gruppen von Validierungsverantwortlichen über den Link **[!UICONTROL Validierungsparameter]** im Kampagnenkit festlegen.

## Validierungsverantwortliche Person zuweisen {#assigning-a-reviewer}

Um den Validierer anzugeben, klicken Sie auf den Link **[!UICONTROL Validierungsparameter...]** des Kampagnenkits und wählen Sie den jeweiligen Benutzer in der Dropdown-Liste aus.

![](assets/s_advuser_mkg_dist_define_valid.png)

Um den Validierungsprozess zu starten, klicken Sie auf die Schaltfläche **[!UICONTROL Zur Validierung unterbreiten]**.

![](assets/s_advuser_mkg_dist_valid_process.png)

Die für die Validierung verantwortliche Person erhält daraufhin eine Benachrichtigung zur Bestätigung der Verfügbarkeit dieses Kampagnenkits. Die Nachricht enthält einen Link zum Akzeptieren oder Ablehnen der Validierung per Web-Zugriff.

![](assets/s_advuser_mkg_dist_valid_process1.png)

>[!NOTE]
>
>Auf Organisationseinheitsebene können Sie auch validierende Benutzer angeben, um Bestellungen zu validieren. Weitere Informationen hierzu finden Sie unter [Organisationseinheiten](about-distributed-marketing.md#organizational-entities).

## Hinzufügen weiterer validierungsverantwortlicher Personen {#adding-other-reviewers}

Über den Link **[!UICONTROL Bearbeiten...]** im Tab **[!UICONTROL Validierungsparameter...]** des Kampagnenkits können weitere validierungsverantwortliche Benutzer hinzugefügt werden.

![](assets/s_advuser_mkg_dist_select_op_valid.png)

## Validierungs-Timeline {#approval-periods}

Wenn nicht anders angegeben, muss die Validierung innerhalb von drei Tagen ab dem Unterbreitungsdatum erfolgen.

Im Fenster „Validierungsverantwortliche bearbeiten“ können Sie auch Erinnerungen einstellen, um eine oder mehrere Nachrichten zu senden, wenn ein Kampagnenkit nicht genehmigt wurde. Klicken Sie dazu zunächst auf den Link **[!UICONTROL Erinnerung hinzufügen]** und dann auf die Schaltfläche **[!UICONTROL Hinzufügen]**.

Erinnerungen können entweder an einem bestimmten Datum und/oder **x** Tage nach dem Übermittlungsdatum gesendet werden. Die Art der Erinnerung kann in der ersten Spalte der Tabelle mit den Erinnerungen konfiguriert werden. Im folgenden Beispiel erhalten die validierungsverantwortlichen Personen am 11.01.2023 eine Erinnerungsnachricht, also zwei Tage vor dem in der Variablen **[!UICONTROL Datum]** ausgewählten Datum. Sie erhalten eine zweite Erinnerung einen Tag vor Ablauf des Validierungszeitraums, d. h. zwei Tage nach dem Datum der Übermittlung zur Validierung.

![](assets/s_advuser_mkg_dist_reminder_planning.png)

Sobald diese Definition erfolgt ist und das Paket zur Validierung eingereicht wurde, wird der Ausführungsplan in der Registerkarte **[!UICONTROL Audit]** angezeigt. Er enthält die Bearbeitungsfrist, die basierend auf der vorherigen Konfiguration berechnet wurde, sowie die Termine aller konfigurierten Erinnerungen.

## Genehmigen über die Client-Konsole {#approving-via-the-adobe-campaign-console}

Wenn kein Validierungsverantwortlicher bestimmt wurde oder keiner der benachrichtigten Benutzer das Kit validiert hat, kann die Validierung direkt über die Schaltfläche **[!UICONTROL Kampagnenkit validieren]** des **[!UICONTROL Dashboards]** des Kampagnenkits oder über die Übersicht der Kits erfolgen.

![](assets/s_advuser_mkg_dist_valid_button.png)

Nach der Validierung wird die Kampagne veröffentlicht und der Liste hinzugefügt. Sobald das Verfügbarkeitsdatum erreicht ist, kann sie von Lokalstellen verwendet werden. Sofern bei der Kampagnenerstellung Lokalstellen angegeben wurden, werden die Benutzenden in der Benachrichtigungsliste über die Verfügbarkeit der Kampagne benachrichtigt. Wenn zuvor keine Entität angegeben wurde, ist die Kampagne standardmäßig für alle Lokalstellen verfügbar. Weitere Informationen hierzu finden Sie unter [Organisationseinheiten](about-distributed-marketing.md#organizational-entities).

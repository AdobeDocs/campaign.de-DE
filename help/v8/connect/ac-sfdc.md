---
title: Campaign und SFDC verwenden
description: Erfahren Sie, wie Sie mit Campaign und Salesforce.com arbeiten.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 495eff0f3b5926c8f91939bcb296bc36086cb8cd
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 31%

---

# Campaign und SFDC verwenden{#crm-sfdc}

Erfahren Sie, wie Sie den Campaign CRM-Connector konfigurieren, um Campaign v8 mit **Salesforce.com**.

Nach der Konfiguration erfolgt die Datensynchronisation zwischen Systemen über eine spezielle Workflow-Aktivität. [Weitere Informationen](crm-data-sync.md).

>[!NOTE]
>
>Die unterstützten SFDC-Versionen werden in Campaign beschrieben. [Kompatibilitätsmatrix](../start/compatibility-matrix.md).


Gehen Sie wie folgt vor, um ein dediziertes externes Konto zum Importieren und Exportieren von Salesforce-Daten in Adobe Campaign zu konfigurieren.

## Verbindung erstellen{#new-sfdc-external-account}

Zunächst müssen Sie das externe Salesforce -Konto erstellen.

1. Durchsuchen Sie die **[!UICONTROL Administration > Plattform > Externe Konten]** und erstellen Sie ein externes Konto.
1. Auswählen **[!UICONTROL Salesforce.com]** externes Konto im **Typ** Abschnitt.
1. Geben Sie Einstellungen zum Aktivieren der Verbindung ein.

   ![](assets/sfdc-external-account.png)

   Um dieses externe Konto für die gemeinsame Verwendung mit Adobe Campaign zu konfigurieren, müssen Sie die folgenden Informationen eingeben:

   * Geben Sie Ihre Salesforce-Anmeldung im **[!UICONTROL Konto]** -Feld.
   * Geben Sie Ihr Salesforce-Passwort ein.
   * Sie können die **[!UICONTROL Client-Kennung]** -Feld.
   * Salesforce kopieren/einfügen **[!UICONTROL Security-Token]**
   * Wählen Sie Ihre **[!UICONTROL API-Version]**. Die unterstützten SFDC API-Versionen sind in Campaign aufgeführt. [Kompatibilitätsmatrix](../start/compatibility-matrix.md).

1. Wählen Sie die **Aktivieren** aktivieren, um das Konto in Campaign zu aktivieren.

>[!NOTE]
>
>Zur Übernahme der Konfiguration müssen Sie sich von der Konsole ab- und wieder anmelden.

## Zu synchronisierende Tabellen auswählen{#sfdc-create-tables}

Sie können jetzt Tabellen zur Synchronisierung konfigurieren.

1. Klicken Sie auf **[!UICONTROL Konfigurationsassistent für Salesforce CRM ...]**.
1. Wählen Sie die zu synchronisierenden Tabellen aus und starten Sie den Prozess.
1. Prüfen Sie unter dem Knoten **[!UICONTROL Administration > Konfiguration > Datenschema]** das in Adobe Campaign erzeugte Schema.

   Beispiel einer **Salesforce** in Campaign importiertes Schema:

   ![](assets/sfdc-schemas.png)

## Synchronisation der Auflistungen,{#sfdc-enum-sync}

Sobald das Schema erstellt ist, können Sie Aufzählungen in Salesforce automatisch mit Adobe Campaign synchronisieren.

1. Öffnen Sie die Assistenzkraft über die  **[!UICONTROL Auflistungen synchronisieren...]** Link.
1. Wählen Sie die Adobe Campaign-Auflistung aus, die der Salesforce-Auflistung entspricht.
Sie können alle Werte einer Adobe-Campaign-Auflistung durch die des CRM-Systems ersetzen: Wählen Sie hierzu in der Spalte **[!UICONTROL Ersetzen]** die Option **[!UICONTROL Ja]**.

   ![](assets/sfdc-enum.png)

1. Klicken **[!UICONTROL Nächste]** und dann **[!UICONTROL Starten]** um mit dem Import der Auflistungen zu beginnen.

1. Durchsuchen Sie die **[!UICONTROL Administration > Plattform > Auflistungen]** Knoten zur Überprüfung der importierten Werte.


Adobe Campaign und Salesforce.com sind jetzt verbunden. Sie können eine Datensynchronisation zwischen den beiden Systemen einrichten.

Um Daten zwischen Adobe Campaign-Daten und SFDC zu synchronisieren, erstellen Sie einen Workflow und verwenden Sie die **[!UICONTROL CRM-Connector]** Aktivität.

Weitere Informationen zur Datensynchronisation finden Sie [auf dieser Seite](crm-data-sync.md).

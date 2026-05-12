---
title: Arbeiten mit Campaign und SFDC
description: Erfahren Sie, wie Sie mit Campaign und Salesforce.com arbeiten können
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
TQID: https://experienceleague.adobe.com/N50ecfMFC641fveGfyxx4W9XvZgWPgddrdpj9KrCHBY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 97%

---

# Arbeiten mit Campaign und SFDC{#crm-sfdc}

Erfahren Sie, wie Sie den Campaign CRM-Connector konfigurieren, um Campaign v8 mit **Salesforce.com** zu verbinden.

Sobald die Konfiguration abgeschlossen ist, wird die Datensynchronisation zwischen den Systemen über eine spezielle Workflow-Aktivität durchgeführt. [Weitere Informationen](crm-data-sync.md).

>[!NOTE]
>
>Unterstützte SFDC-Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign aufgeführt.

Gehen Sie wie folgt vor, um ein dediziertes externes Konto zu konfigurieren, um Salesforce-Daten in Adobe Campaign zu importieren und daraus zu exportieren.

## Erstellen der Verbindung{#new-sfdc-external-account}

Zunächst müssen Sie das externe Salesforce-Konto erstellen.

1. Durchsuchen Sie den Knoten **[!UICONTROL Administration > Plattform > Externe Konten]** im Campaign Explorer und erstellen Sie ein externes Konto.
1. Wählen Sie im Abschnitt **Typ** das externe Konto **[!UICONTROL Salesforce.com]** aus.
1. Geben Sie Einstellungen zum Aktivieren der Verbindung ein.

   ![](assets/sfdc-external-account.png)

   Um dieses externe Konto für die gemeinsame Verwendung mit Adobe Campaign zu konfigurieren, müssen Sie die folgenden Informationen eingeben:

   * Geben Sie im Feld **[!UICONTROL Konto]** Ihre Salesforce-Anmeldedaten ein.
   * Geben Sie Ihr Salesforce-Passwort ein.
   * Sie können das Feld **[!UICONTROL Client-Kennung]** ignorieren.
   * Kopien Sie Ihr Salesforce-**[!UICONTROL Security-Token]** und fügen Sie es ein.
   * Wählen Sie Ihre **[!UICONTROL API-Version]** aus. Die unterstützten SFDC API-Versionen sind in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign aufgeführt.

1. Wählen Sie die Option **Aktivieren** aus, um das Konto in Campaign zu aktivieren.

>[!NOTE]
>
>Zum Genehmigen des Setups müssen Sie sich von der Adobe Campaign-Client-Konsole ab- und wieder anmelden.

## Auswahl der zu synchronisierenden Tabellen{#sfdc-create-tables}

Sie können jetzt die Tabellen konfigurieren, die synchronisiert werden sollen.

1. Klicken Sie auf **[!UICONTROL Konfigurationsassistent für Salesforce CRM...]**.
1. Wählen Sie die zu synchronisierenden Tabellen aus und starten Sie den Prozess.
1. Prüfen Sie unter dem Knoten **[!UICONTROL Administration > Konfiguration > Datenschema]** das in Adobe Campaign erzeugte Schema.

   Beispiel eines in Campaign importierten **Salesforce**-Schemas:

   ![](assets/sfdc-schemas.png)

## Synchronisation der Aufzählungen{#sfdc-enum-sync}

Sobald das Schema erstellt ist, können Sie Aufzählungen in Salesforce automatisch mit Adobe Campaign synchronisieren.

1. Öffnen Sie den Assistenten über den Link **[!UICONTROL Aufzählungen synchronisieren...]**.
1. Wählen Sie die Adobe Campaign-Aufzählung aus, die der Salesforce-Aufzählung entspricht.
Sie können alle Werte einer Adobe Campaign-Aufzählung durch die des CRM-Systems ersetzen: Wählen Sie hierzu in der Spalte **[!UICONTROL Ersetzen]** die Option **[!UICONTROL Ja]**.

   ![](assets/sfdc-enum.png)

1. Klicken Sie abschließend auf **[!UICONTROL Weiter]** und dann auf **[!UICONTROL Starten]**, um mit dem Import der Aufzählungen zu beginnen.

1. Durchsuchen Sie den Knoten **[!UICONTROL Administration > Plattform > Aufzählungen]**, um die importierten Werte zu überprüfen. Weitere Informationen über Aufzählungen finden Sie auf [dieser Seite](../config/ui-settings.md#enumerations).

Adobe Campaign und Salesforce.com sind jetzt verbunden. Sie können eine Datensynchronisation zwischen den beiden Systemen einrichten.

Um Daten zwischen Adobe Campaign und SFDC zu synchronisieren, müssen Sie einen Workflow erstellen und die Aktivität **[!UICONTROL CRM-Connector]** verwenden.

Weitere Informationen zur Datensynchronisation finden Sie [auf dieser Seite](crm-data-sync.md).

Weitere Informationen zur Auflistungsverwaltung in Campaign [auf dieser Seite](../config/enumerations.md).

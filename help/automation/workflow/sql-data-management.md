---
product: campaign
title: SQL-Daten-Management
description: Erfahren Sie mehr über die Workflow-Aktivität "SQL-Daten-Management".
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
TQID: 'https://experienceleague.adobe.com/aQKYDkFnBDT-N-fFTRg8ggvxfjKOKBgE9dcuuh7L28k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 88%
---
# SQL-Daten-Management{#sql-data-management}

Die Aktivität **SQL-Daten-Management** ermöglicht Ihnen das Schreiben eigener SQL-Scripts zum Erstellen und Auffüllen von Arbeitstabellen.

## Voraussetzungen {#prerequisites}

Vor der Konfiguration der Aktivität müssen folgende Voraussetzungen gegeben sein:

* Die Aktivität ist nur für Remote-Datenquellen verfügbar.
* Das ausgehende Schema muss in der Datenbank vorhanden und mit einer FDA-Datenbank verknüpft sein.

## Wichtige Hinweise {#important-notes}

Ab 8.9.1 wurden die Workflow-Aktivitäten **[!UICONTROL SQL-Code]** und **[!UICONTROL SQL-Daten-Management]** verbessert, um PostgreSQL-Datenbanken besser zu schützen und dafür zu sorgen, dass Ihre Workflows reibungslos ausgeführt werden, wenn benutzerdefinierte SQL von Campaign aus ausgeführt wird.

Bei Fehlern stehen zwei Lösungen zur Verfügung:

* Lösung 1 — `XtkSecurity_FeatureFlag_SqlSensitive`
* Lösung 2 — `XtkSecurity_SqlSensitive_Methods`

Weitere Informationen [&#x200B; Best Practices finden &#x200B;](sql-code-and-javascript-code.md#important-notes) unter SQL-Code .

## SQL-Daten-Management-Aktivität konfigurieren {#configuring-the-sql-data-management-activity}

1. Spezifizieren Sie die Aktivität in **[!UICONTROL Titel]**.
1. Wählen Sie das zu verwendende **[!UICONTROL externe Konto]** aus und danach das mit diesem externen Konto verknüpfte **[!UICONTROL Outbound-Schema]**.

   >[!CAUTION]
   >
   >Das Outbound-Schema ist unveränderlich und kann nicht bearbeitet werden.

1. Fügen Sie das SQL-Script hinzu.

   >[!CAUTION]
   >
   >Die Person, die das SQL-Skript erstellt, ist dafür verantwortlich, dass das SQL-Skript funktioniert und seine Verweise (Feldnamen etc.) dem Outbound-Schema entsprechen.

   Wenn Sie einen vorhandenen SQL-Code laden möchten, wählen Sie die Option **[!UICONTROL Der SQL-Code ist in einer in der Datenbank gespeicherten Entität enthalten]** aus. SQL-Scripts müssen im Menü **[!UICONTROL Administration]** / **[!UICONTROL Konfiguration]** / **[!UICONTROL SQL-Scripts]** erstellt und gespeichert werden.

   Andernfalls können Sie Ihr SQL-Script auch in den dafür vorgesehenen Bereich kopieren.

   ![](assets/sql_datamanagement.png)

   Mithilfe der Aktivität können Sie die folgenden Variablen im Script verwenden:

   * **activity.tableName**: SQL-Name der ausgehenden Arbeitstabelle.
   * **task.incomingTransitionByName(&#39;name&#39;).tableName**: SQL-Name der Arbeitstabelle der zu verwendenden eingehenden Transition (die Transition wird durch den Namen identifiziert).

     >[!NOTE]
     >
     >Der Wert (&#39;name&#39;) entspricht dem Feld **[!UICONTROL Name]** in den Transition-Eigenschaften.

1. Wenn das SQL-Skript bereits Befehle zum Erstellen einer ausgehenden Arbeitstabelle enthält, deaktivieren Sie die Option **[!UICONTROL Arbeitstabelle automatisch erstellen]**. Anderenfalls wird automatisch eine Arbeitstabelle erstellt, sobald der Workflow ausgeführt wird.
1. Wählen Sie **[!UICONTROL Ok]** aus, um die Konfiguration der Aktivität zu bestätigen.

Der Aktivität ist jetzt konfiguriert. Sie ist zur Ausführung im Workflow bereit.

>[!CAUTION]
>
>Nachdem die Aktivität ausgeführt wurde, ist die Anzahl der Einträge in der ausgehenden Transition nur als Richtwert zu betrachten. Sie kann je nach Komplexität des SQL-Skripts variieren.
>  
>Wenn die Aktivität neu gestartet wird, wird das gesamte Script unabhängig vom Ausführungsstatus von vorn ausgeführt.

## Muster für SQL-Scripts {#sql-script-samples}

>[!NOTE]
>
>Die Script-Muster in diesem Abschnitt müssen unter PostgreSQL ausgeführt werden.

Mit diesem Script können Sie eine Arbeitstabelle erstellen und Daten darin einfügen.

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

Mit diesem Script können Sie eine CTAS-Operation ausführen (CREATE TABLE AS SELECT) und einen Arbeitstabellenindex erstellen:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

Mit diesem Skript können Sie zwei Arbeitstabellen zusammenführen:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```

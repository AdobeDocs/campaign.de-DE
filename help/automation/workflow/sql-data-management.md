---
product: campaign
title: SQL-Daten-Management
description: Erfahren Sie mehr über die Workflow-Aktivität "SQL-Daten-Management".
feature: Workflows
Role: User
Level: Experienced
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 94%

---

# SQL-Daten-Management{#sql-data-management}

Die Aktivität **SQL-Daten-Management** ermöglicht Ihnen das Schreiben eigener SQL-Scripts zum Erstellen und Auffüllen von Arbeitstabellen.

## Voraussetzungen {#prerequisites}

Vor der Konfiguration der Aktivität müssen folgende Voraussetzungen gegeben sein:

* Die Aktivität ist nur für Remote-Datenquellen verfügbar.
* Das ausgehende Schema muss in der Datenbank vorhanden und mit einer FDA-Datenbank verknüpft sein.


## SQL-Daten-Management-Aktivität konfigurieren {#configuring-the-sql-data-management-activity}

1. Spezifizieren Sie die Aktivität in **[!UICONTROL Titel]**.
1. Wählen Sie das zu verwendende **[!UICONTROL externe Konto]** aus und danach das mit diesem externen Konto verknüpfte **[!UICONTROL Outbound-Schema]**.

   >[!CAUTION]
   >
   >Das Outbound-Schema ist unveränderlich und kann nicht bearbeitet werden.

1. Fügen Sie das SQL-Script hinzu.

   >[!CAUTION]
   >
   >Der Codierer des SQL-Scripts ist dafür verantwortlich, dass das SQL-Script funktioniert und seine Referenzen (Feldnamen etc.) dem Outbound-Schema entsprechen.

   Wenn Sie einen vorhandenen SQL-Code laden möchten, wählen Sie die Option **[!UICONTROL Der SQL-Code ist in einer in der Datenbank gespeicherten Entität enthalten]** aus. SQL-Scripts müssen im Menü **[!UICONTROL Administration]** / **[!UICONTROL Konfiguration]** / **[!UICONTROL SQL-Scripts]** erstellt und gespeichert werden.

   Andernfalls können Sie Ihr SQL-Script auch in den dafür vorgesehenen Bereich kopieren.

   ![](assets/sql_datamanagement.png)

   Mithilfe der Aktivität können Sie die folgenden Variablen im Script verwenden:

   * **activity.tableName**: SQL-Name der ausgehenden Arbeitstabelle.
   * **task.incomingTransitionByName(&#39;name&#39;).tableName**: SQL-Name der Arbeitstabelle der zu verwendenden eingehenden Transition (die Transition wird durch ihren Namen identifiziert).

     >[!NOTE]
     >
     >Der Wert (&#39;name&#39;) entspricht dem Feld **[!UICONTROL Name]** in den Transition-Eigenschaften.

1. Wenn das SQL-Script bereits Befehle zum Erstellen einer ausgehenden Arbeitstabelle enthält, deselektieren Sie die Option **[!UICONTROL Arbeitstabelle automatisch erstellen]**. Andernfalls wird automatisch eine Arbeitstabelle erstellt, wenn der Workflow ausgeführt wird.
1. Wählen Sie **[!UICONTROL Ok]** aus, um die Konfiguration der Aktivität zu bestätigen.

Die Aktivität ist jetzt konfiguriert und kann im Workflow ausgeführt werden.

>[!CAUTION]
>
>Nachdem die Aktivität ausgeführt wurde, ist die Anzahl der gezählten Datensätze in der ausgehenden Transition nur als Richtwert zu erachten. Dieser kann je nach Komplexität des SQL-Scripts variieren.
>  
>Wenn die Aktivität erneut gestartet wird, wird das gesamte Script unabhängig vom Ausführungsstatus von vorn ausgeführt.

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

Mit diesem Script können Sie zwei Arbeitstabellen verbinden:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```

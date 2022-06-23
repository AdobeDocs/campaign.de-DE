---
title: Bekannte Probleme in Campaign v8
description: Bekannte Probleme in der neuesten Campaign-Version
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 5fe921e83f36675837b72ca282315692151dcf67
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 3%

---

# Bekannte Probleme{#known-issues}

Auf dieser Seite werden bekannte Probleme aufgelistet, die in der Variablen **neueste Version von Campaign v8**. Darüber hinaus werden Einschränkungen von Campaign v8 aufgelistet [auf dieser Seite](known-limitations.md).


>[!NOTE]
>
>Adobe veröffentlicht diese Liste bekannter Probleme nach eigenem Ermessen. Er basiert auf der Anzahl der Kundenberichte, der Schwere und der Verfügbarkeit der Problemumgehung. Wenn ein Problem, auf das Sie stoßen, nicht aufgelistet ist, entspricht es möglicherweise nicht den Kriterien für die Veröffentlichung auf dieser Seite.

<!--
## Change Data Source activity issue #1 {#issue-1}

### Description{#issue-1-desc}

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps{#issue-1-repro}

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Error message{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Workaround{#issue-1-workaround}

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference{#issue-1-ref}

Reference: NEO-45549 
-->


## Problem mit der Datenquelle-Aktivität ändern {#issue-2}

### Beschreibung{#issue-2-desc}

Beim Einfügen von Daten in eine Snowflake Cloud-Datenbank mit einer Campaign-Komponente **Abfrage** und **Datenquelle ändern** -Aktivität, schlägt der Prozess fehl, wenn in den Daten ein umgekehrter Schrägstrich vorhanden ist. Die Quellzeichenfolge wird nicht maskiert und die Daten werden auf dem Snowflake nicht korrekt verarbeitet.

Dieses Problem tritt nur auf, wenn sich der umgekehrte Schrägstrich am Ende der Zeichenfolge befindet, z. B.: `Barker\`.


### Reproduktionsschritte{#issue-2-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Hinzufügen einer **Abfrage** und konfigurieren Sie sie.
1. Wählen Sie Daten mit den oben beschriebenen Eigenschaften aus.
1. Hinzufügen einer **Datenquelle ändern** und konfigurieren Sie sie, um die Snowflake-Cloud-Datenbank auszuwählen.
1. Führen Sie den Workflow aus und überprüfen Sie die Workflow-Protokolle, um den Fehler anzuzeigen.


### Fehlernachricht{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Problemumgehung{#issue-2-workaround}

Problemumgehung besteht darin, Daten auszuschließen, die umgekehrte Schrägstriche am Ende der Zeichenfolge enthalten, oder sie aus der Quelldatei zu entfernen.

<!--
As a workaround, export the files with double quotes around the problematic values (like `Barker\`) and include a file format option `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.
-->

### Interner Verweis{#issue-2-ref}

Referenz: NEO-45549


## Die Aktivität Laden (Datei) konnte die Datei nicht auf den Server hochladen {#issue-3}

### Beschreibung{#issue-3-desc}

Beim Hochladen einer Datei auf den Campaign-Server mit einer **Laden (Datei)** -Aktivität, endet der Prozess bei 100 %, endet jedoch nie.

### Reproduktionsschritte{#issue-3-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Hinzufügen einer **Laden (Datei)** und konfigurieren Sie sie.
1. Wählen Sie die **Auf Server hochladen** -Option.
1. Wählen Sie die Datei auf Ihrem lokalen Computer aus.
1. Klicken **Hochladen**


### Fehlernachricht{#issue-3-error}

Der Prozess endet nie.

### Problemumgehung{#issue-3-workaround}

Die Lösung besteht darin, eine ältere Clientkonsole zu verwenden. Anschließend können Sie die Datei auf den Server hochladen.

Als Campaign-Administrator können Sie die Campaign v8.3.1-Clientkonsole in [Adobe Distribution Service](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Erfahren Sie, wie Sie auf den Adobe Distribution Service zugreifen können. [auf dieser Seite](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=de){target=&quot;_blank&quot;}.

Erfahren Sie, wie Sie Ihre Clientkonsole aktualisieren [auf dieser Seite](connect.md)

### Interner Verweis{#issue-3-ref}

Referenz: NEO-47269
---
title: Bekannte Probleme in Campaign v8
description: Bekannte Probleme in der neuesten Campaign-Version
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 96e9f5fe5f07ea0c476395d33efa4d6bcf10cf60
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 77%

---

# Bekannte Probleme{#known-issues}

Auf dieser Seite werden bekannte Probleme aufgelistet, die in der Variablen **Aktuelle Campaign v8-Versionen**. Zusätzlich werden [auf dieser Seite](ac-guardrails.md) Einschränkungen von Campaign v8 aufgeführt.


>[!NOTE]
>
>Adobe veröffentlicht diese Liste bekannter Probleme nach eigenem Ermessen. Sie basiert auf der Anzahl der Kundenberichte, dem Schweregrad und der Verfügbarkeit einer Problemumgehung. Wenn ein Problem, auf das Sie stoßen, nicht aufgelistet ist, entspricht es möglicherweise nicht den Kriterien für die Veröffentlichung auf dieser Seite.

## Campaign v8.3.8{#8.3-issues}

### Problem mit der Datenquelle-Aktivität ändern 1 {#issue-1}

#### Beschreibung{#issue-1-desc}

Die **Datenquelle ändern** -Aktivität schlägt beim Übertragen von Daten aus der lokalen Campaign-Datenbank in die Snowflake-Cloud-Datenbank fehl. Beim Wechsel der Richtung kann die Aktivität Probleme verursachen.

#### Reproduktionsschritte{#issue-1-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Hinzufügen einer **Abfrage** und eine **Datenquelle ändern** Aktivität.
1. Definieren Sie eine Abfrage im **email**, was eine Zeichenfolge ist.
1. Führen Sie den Workflow aus und klicken Sie mit der rechten Maustaste auf die Transition, um die Population anzuzeigen: die E-Mail-Datensätze werden ersetzt durch `****`.
1. Überprüfen Sie die Workflow-Protokolle: die **Datenquelle ändern** -Aktivität interpretiert diese Datensätze als numerische Werte.

#### Fehlernachricht{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

#### Problemumgehung{#issue-1-workaround}

Damit die Daten von der Snowflake Cloud-Datenbank in die Campaign-Datenbank und zurück in Snowflake übertragen werden, müssen Sie zwei verschiedene **Datenquelle ändern** Aktivitäten.

#### Interner Verweis{#issue-1-ref}

Referenz: NEO-45549



### Problem mit der Aktivität &quot;Datenquelle ändern&quot; {#issue-2}

#### Beschreibung{#issue-2-desc}

Beim Einfügen von Daten in eine Snowflake Cloud-Datenbank mit einer Campaign-**Abfrage** und der Aktivität **Datenquelle ändern** schlägt der Prozess fehl, wenn in den Daten ein umgekehrter Schrägstrich vorhanden ist. Die Quellzeichenfolge wird nicht mit Escape-Zeichen versehen, wodurch die Daten auf Snowflake nicht korrekt verarbeitet werden.

Dieses Problem tritt nur auf, wenn sich der umgekehrte Schrägstrich am Ende der Zeichenfolge befindet, z. B.: `Barker\`.


#### Reproduktionsschritte{#issue-2-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Fügen Sie eine **Abfrage**-Aktivität hinzu und konfigurieren Sie sie.
1. Wählen Sie Daten mit den oben beschriebenen Eigenschaften aus.
1. Fügen Sie die Aktivität **Datenquelle ändern** hinzu und konfigurieren Sie sie so, dass die Snowflake Cloud-Datenbank ausgewählt ist.
1. Führen Sie den Workflow aus und sehen Sie sich die Workflow-Protokolle an, um den Fehler zu finden.


#### Fehlernachricht{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Problemumgehung{#issue-2-workaround}

Die Problemumgehung besteht darin, Daten auszuschließen, die umgekehrte Schrägstriche am Ende der Zeichenfolge enthalten, oder sie aus der Quelldatei zu entfernen.


#### Interner Verweis{#issue-2-ref}

Referenz: NEO-45549


### Eine Datei konnte nicht mit der Aktivität &quot;Laden (Datei)&quot; auf den Server hochgeladen werden {#issue-3}

#### Beschreibung{#issue-3-desc}

Beim Hochladen einer Datei auf den Campaign-Server mit der Aktivität **Laden (Datei)** hört der Vorgang bei 100 % auf, endet jedoch nie.

#### Reproduktionsschritte{#issue-3-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Fügen Sie die Aktivität **Laden (Datei)** hinzu und konfigurieren Sie sie.
1. Wählen Sie die Option **Auf Server hochladen**.
1. Wählen Sie die Datei auf Ihrem lokalen Computer aus.
1. Klicken Sie auf **Hochladen**.


#### Fehlernachricht{#issue-3-error}

Der Prozess endet nie.

#### Problemumgehung{#issue-3-workaround}

Die Lösung besteht darin, eine ältere Client-Konsole zu verwenden. Damit können Sie die Datei auf den Server hochladen.

Als Campaign-Administrator können Sie die Client-Konsole für Campaign v8.3.1 in der [Adobe-Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;} herunterladen.

Auf [dieser Seite](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=de){target=&quot;_blank&quot;} erfahren Sie, wie Sie auf die Adobe-Software-Verteilung zugreifen können.

Auf [dieser Seite](connect.md) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

#### Interner Verweis{#issue-3-ref}

Referenz: NEO-47269
---
product: Adobe Campaign
title: Campaign-API-Staging-Mechanismus
description: Campaign-API-Staging-Mechanismus
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 4%

---

# Campaign-API-Staging-Mechanismus

In der Campaign Cloud-Datenbank werden gebündelte Einzelaufrufe aufgrund der Leistung (Latenz und gleichzeitige Nutzung) nicht empfohlen. Batch-Vorgänge werden immer bevorzugt. Um eine optimale Leistung der APIs zu gewährleisten, verarbeitet Campaign API-Aufrufe weiterhin auf lokaler Datenbankebene.

Der Campaign-Staging-Mechanismus ist für integrierte und benutzerdefinierte Tabellen verfügbar und bringt die folgenden Vorteile mit sich:

* Die Datenschemastruktur wird in der lokalen Staging-Tabelle repliziert
* Neue APIs zur Aufnahme fließen direkt in die Staging-Tabelle. [Mehr dazu](new-apis.md)
* Ein geplanter Workflow wird stündlich Trigger und die Daten werden wieder in die Cloud-Datenbank synchronisiert. [Weitere Informationen](../config/replication.md).

Einige integrierte Schemata werden standardmäßig als &quot;Staging&quot;festgelegt, z. B. nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Campaign Classic v7-APIs sind weiterhin verfügbar, können aber von diesem neuen Staging-Mechanismus nicht profitieren: API-Aufrufe werden direkt an die Cloud-Datenbank gesendet. Adobe empfiehlt, so weit wie möglich einen neuen Staging-Mechanismus zu verwenden, um den Gesamtdruck und die Latenz in der Campaign Cloud-Datenbank zu reduzieren.

>[!CAUTION]
>
>Mit diesem neuen Mechanismus ist die Datensynchronisation für Abonnements, Abmeldungen oder mobile Registrierungen jetzt **asynchron**.


## Implementierungsschritte{#implement-staging}

Gehen Sie wie folgt vor, um den Campaign-Staging-Mechanismus für eine bestimmte Tabelle zu implementieren:

1. Erstellen Sie ein benutzerdefiniertes Beispielschema in der Campaign Cloud-Datenbank. In diesem Schritt ist kein Staging aktiviert.

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   [!DNL :bulb:] Weitere Informationen zur Erstellung benutzerdefinierter Schemas finden Sie auf  [dieser Seite](create-schema.md).

1. Speichern und aktualisieren Sie die Datenbankstruktur.  [Mehr dazu](update-database-structure.md)

1. Aktivieren Sie den Staging-Mechanismus in der Schemadefinition, indem Sie den Parameter **autoStg=&quot;true&quot;** hinzufügen.

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. Speichern Sie die Änderung. Es ist ein neues Staging-Schema verfügbar, bei dem es sich um eine lokale Kopie des ursprünglichen Schemas handelt.

   ![](assets/staging-mechanism.png)

1. Datenbankstruktur aktualisieren. Die Staging-Tabelle wird in der lokalen Campaign-Datenbank erstellt.

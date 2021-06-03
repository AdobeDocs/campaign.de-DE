---
product: Adobe Campaign
title: Campaign-API-Staging-Mechanismus
description: Campaign-API-Staging-Mechanismus
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---

# Campaign-API-Staging-Mechanismus

In der Campaign Cloud-Datenbank wird die Weitergabe von Einzelaufrufen hinsichtlich der Leistung (Latenz und gleichzeitige Nutzung) nicht empfohlen. Der Stapelvorgang wird immer bevorzugt. Um die Leistung zu verbessern, werden Aufnahme-APIs an die lokale Datenbank weitergeleitet.

Die Staging-Funktion von Kampagnen ist in einigen integrierten Schemata standardmäßig aktiviert. Wir können sie auch für jedes benutzerdefinierte Schema aktivieren. Staging-Mechanismus in Kürze:

* Die Datenschemastruktur wird in die lokale Staging-Tabelle dupliziert.
* Neue APIs für die Datenerfassung werden direkt in die lokale Staging-Tabelle übertragen. [Mehr dazu](new-apis.md)
* Ein geplanter Workflow wird stündlich Trigger und die Daten werden wieder in die Cloud-Datenbank synchronisiert. [Mehr dazu](../config/replication.md)

Einige integrierte Schemata werden standardmäßig als &quot;Staging&quot;festgelegt, z. B. nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Campaign Classic v7-APIs sind weiterhin verfügbar, können aber von diesem neuen Staging-Mechanismus nicht profitieren: API-Aufrufe werden direkt an die Cloud-Datenbank gesendet. Adobe empfiehlt, so weit wie möglich einen neuen Staging-Mechanismus zu verwenden, um den Gesamtdruck und die Latenz in der Campaign Cloud-Datenbank zu reduzieren.

>[!CAUTION]
>
>* Mit diesem neuen Mechanismus ist die Datensynchronisation für die Abmeldung von Kanälen, Abonnements, Abmeldungen oder mobile Registrierung jetzt **asynchron**.
   >
   >
* Das Staging gilt nur für Schemas, die in der Cloud-Datenbank gespeichert sind. Aktivieren Sie keine Staging-Umgebung für replizierte Schemas. Aktivieren Sie keine Staging-Umgebung für lokale Schemas. Aktivieren Sie die Staging-Umgebung nicht für ein gestaffeltes Schema

>



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

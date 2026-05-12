---
title: Campaign-API-Staging-Mechanismus
description: Campaign-API-Staging-Mechanismus
feature: Configuration, API, FFDA
role: Developer
level: Intermediate
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
TQID: https://experienceleague.adobe.com/7lzQJvwlZtyuL-QAgSB1WGmiQhhQEZ66XRyiVFNqiZQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 100%

---

# Campaign-API-Staging-Mechanismus

Im Kontext einer [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md) ist es im Hinblick auf die Performance (Latenz und Gleichzeitigkeit) nicht empfehlenswert, einzelne Abfragen zu starten. Außer wenn Sie extrem geringe Menge senden, **muss** der Batch-Vorgang verwendet werden. Um die Performance zu verbessern, werden Aufnahme-APIs an die lokale Datenbank weitergeleitet.

Die Staging-Funktion von Campaign ist in einigen nativen Schemata standardmäßig aktiviert. Sie kann auch für jedes benutzerdefinierte Schema aktiviert werden. Staging-Verfahren in Kürze:

* Die Struktur des Datenschemas wird in die lokale Staging-Tabelle dupliziert.
* Neue APIs zur Datenaufnahme befüllen direkt die lokale Staging-Tabelle. [Weitere Informationen](new-apis.md)
* Ein geplanter Workflow wird stündlich ausgeführt und die Daten werden zurück in die Cloud-Datenbank synchronisiert. [Weitere Informationen](replication.md)

Einige integrierte Schemata werden standardmäßig beim Staging verwendet, etwa nmsSubscriptionRcp, nmsAppSubscriptionRcp und nmsRecipient.

Campaign Classic v7-APIs sind weiterhin verfügbar, profitieren jedoch nicht von dem neuen Staging-Mechanismus: API-Aufrufe fließen direkt in die Cloud-Datenbank. Adobe empfiehlt, wann immer möglich den neuen Staging-Mechanismus zu verwenden, um die Gesamtauslastung und die Latenz der Campaign Cloud-Datenbank zu reduzieren.

>[!CAUTION]
>
>* Mit diesem neuen Mechanismus ist die Datensynchronisation für Kanal-Opt-out, Abonnements, Abmeldungen oder mobile Registrierungen jetzt **asynchron**.
>
>* Staging gilt nur für Schemata, die in der Cloud-Datenbank gespeichert sind. Aktivieren Sie kein Staging für replizierte Schemata. Aktivieren Sie kein Staging für lokale Schemata. Aktivieren Sie kein Staging für ein bereitgestelltes Schema.
>

## Implementierungsschritte {#implement-staging}

Gehen Sie wie folgt vor, um den Campaign-Staging-Mechanismus für eine bestimmte Tabelle zu implementieren:

1. Erstellen Sie ein benutzerdefiniertes Beispielschema in der Campaign Cloud-Datenbank. Bei diesem Schritt ist kein Staging aktiviert.

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

   Weitere Informationen zur Erstellung benutzerdefinierter Schemata finden Sie auf [dieser Seite](../dev/create-schema.md).

1. Speichern und aktualisieren Sie die Datenbankstruktur.  [Weitere Informationen](../dev/update-database-structure.md)

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

1. Speichern Sie die Änderung. Ein neues Staging-Schema ist nun verfügbar, bei dem es sich um eine lokale Kopie des ursprünglichen Schemas handelt.

   ![](assets/staging-mechanism.png)

1. Datenbankstruktur aktualisieren. Die Staging-Tabelle wird in der lokalen Campaign-Datenbank erstellt.

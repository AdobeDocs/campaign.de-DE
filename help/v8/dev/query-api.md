---
title: Datenbank mit queryDef abfragen
description: Erfahren Sie, wie Sie queryDef- und NLWS-Methoden zum Abfragen der Campaign-Datenbank verwenden
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: ceab90331fab0725962a2a98f338ac3dc31a2588
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 2%

---

# Datenbank mit queryDef abfragen {#query-database-api}

[!DNL Adobe Campaign] bietet leistungsstarke JavaScript-Methoden für die Interaktion mit der Datenbank mithilfe von `queryDef` und dem `NLWS`. Mit diesen SOAP-basierten Methoden können Sie Daten mithilfe von JSON, XML oder SQL laden, erstellen, aktualisieren und abfragen.

>[!NOTE]
>
>Diese Dokumentation behandelt datenorientierte APIs für die programmgesteuerte Abfrage der Datenbank. Informationen zu REST-APIs finden Sie unter [Erste Schritte mit REST-APIs](api/get-started-apis.md). Informationen zur visuellen Abfrageerstellung finden Sie unter [Arbeiten mit dem Abfrage-Editor](../start/query-editor.md).

## Was ist NLWS? {#what-is-nlws}

`NLWS` (Neolane Web Services) ist das globale JavaScript-Objekt, das für den Zugriff auf die SOAP-basierten API-Methoden von [!DNL Adobe Campaign] verwendet wird. Schemata sind Eigenschaften des `NLWS`, mit denen Sie programmgesteuert mit Campaign-Entitäten interagieren können.

Gemäß der [Campaign JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=de){target="_blank"} sind „Schemata globale „NLWS“-Objekte.“ Die Syntax für den Zugriff auf Schemamethoden folgt diesem Muster:

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**Beispiele:**

* `NLWS.nmsRecipient` - Zugriffsmethoden für das Empfängerschema (`nms:recipient`)
* `NLWS.nmsDelivery` - Zugriffsmethoden für das Versandschema (`nms:delivery`)
* `NLWS.xtkQueryDef` - Zugriff auf queryDef-Methoden zum Abfragen der Datenbank

Zu den gängigen API-Methoden gehören:

* `load(id)` - Lädt eine Entität anhand ihrer ID. [Weitere Informationen](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html){target="_blank"}
* `create(data)` - Neue Entität erstellen
* `save()` - Änderungen an einer Entität speichern

**Beispiel aus der offiziellen Dokumentation:**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**Alternative Syntax:** Aus Gründen der Abwärtskompatibilität wird in einigen Dokumentationen (z. B. `nms.recipient.create()`, `xtk.queryDef.create()`) möglicherweise auch die Namespace-Syntax in Kleinbuchstaben angezeigt. Beide Syntaxen funktionieren, aber `NLWS` ist der Standard, der in der offiziellen Campaign-JSAPI-Referenz dokumentiert ist.

## Voraussetzungen {#prerequisites}

Vor der Verwendung der Methoden queryDef und NLWS sollten Sie mit Folgendem vertraut sein:

* JavaScript
* [!DNL Adobe Campaign] Datenmodell und Schemata
* XPath-Ausdrücke für die Navigation in Schemaelementen

**Grundlagen zum Campaign-Datenmodell:**

Adobe Campaign verfügt über ein vordefiniertes Datenmodell, das aus Tabellen besteht, die in einer Cloud-Datenbank miteinander verknüpft sind. Die Grundstruktur umfasst:

* **Empfängertabelle** (`nmsRecipient`) - Haupttabelle zum Speichern von Marketing-Profilen
* **Versandtabelle** (`nmsDelivery`) - Speichert Versandaktionen und Vorlagen mit Parametern zur Durchführung von Sendungen
* **Protokolltabellen** - Ausführungsprotokolle speichern:
   * `nmsBroadLogRcp` - Versandlogs für alle Nachrichten, die an Empfänger gesendet werden
   * `nmsTrackingLogRcp` - Trackinglogs für Empfängerreaktionen (Öffnungen, Klicks)
* **Technische Tabellen** - Speichern von Systemdaten wie Benutzern (`xtkGroup`), Sitzungen (`xtkSessionInfo`), Workflows (`xtkWorkflow`)

Um auf die Schemabeschreibungen in der Campaign-Benutzeroberfläche zuzugreifen, navigieren Sie zu **Administration > Konfiguration > Datenschemata** wählen Sie eine Ressource aus und klicken Sie auf die Registerkarte **Dokumentation**.

## Methoden des Entitätsschemas {#entity-schema-methods}

Jedes Schema in [!DNL Adobe Campaign] (z. B. `nms:recipient`, `nms:delivery`) verfügt über Methoden, auf die über das `NLWS`-Objekt zugegriffen werden kann. Diese Methoden bieten eine praktische Möglichkeit, mit Datenbankentitäten zu interagieren.

### Statische Methoden {#static-methods}

Auf statische SOAP-Methoden kann durch Aufrufen einer -Methode für das -Objekt zugegriffen werden, das das Schema darstellt. Beispielsweise ruft `NLWS.xtkWorkflow.PostEvent()` eine statische Methode auf.

### Nicht statische Methoden {#non-static-methods}

Um nicht statische SOAP-Methoden zu verwenden, müssen Sie zunächst eine Entität mit den `load`- oder `create`-Methoden für die entsprechenden Schemata abrufen. Weitere Informationen finden Sie in der [Campaign JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=de){target="_blank"}.

### Laden, Speichern und Erstellen von Entitäten {#load-save-create}

**Entität nach ID laden und aktualisieren:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**Empfänger mithilfe von JSON erstellen:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**Empfänger mithilfe von XML erstellen:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## QueryDef - Übersicht {#querydef-overview}

Das `xtk:queryDef` bietet Methoden zum Erstellen und Ausführen von Datenbankabfragen. Sie können `NLWS.xtkQueryDef.create()` verwenden, um Abfragen mit JSON- oder XML-Syntax zu erstellen.

**Verfügbare Vorgänge:**

* `select` - Abrufen mehrerer Datensätze
* `get` - Abrufen eines einzelnen Datensatzes (SQL-`LIMIT 1`)
* `getIfExists` : Ruft einen einzelnen Datensatz ab und gibt null zurück, wenn er nicht gefunden wurde.
* `count` - Anzahl der Datensätze, die den Kriterien entsprechen

Weitere Informationen zu queryDef-Methoden finden Sie in der [Campaign JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}.

## Abfrage mit JSON {#query-json}

Verwenden Sie `NLWS.xtkQueryDef.create()`, um Abfragen mit JSON-Syntax zu erstellen. Der `get` Vorgang ruft einen einzelnen Datensatz ab (SQL-`LIMIT 1`), während `select` mehrere Datensätze abruft.

**Einen einzelnen Empfänger abrufen:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Verwenden Sie `getIfExists`, um Ausnahmen zu vermeiden:**

Wenn der Datensatz möglicherweise nicht vorhanden ist, verwenden Sie `operation: "getIfExists"` anstelle von `get`, um Ausnahmen zu vermeiden:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Mehrere Datensätze auswählen {#select-multiple}

Verwenden Sie den `select` Vorgang, um mehrere Datensätze abzurufen. Sie können Bedingungen, eine bestimmte Reihenfolge und Einschränkungen hinzufügen.

**Abfrage-Workflows mit Filtern und Sortierung:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**Sendungen mit XML-Syntax abfragen:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**Ergebnisbeschränkungen:** Campaign begrenzt automatisch Abfrageergebnisse, um Speicherprobleme zu vermeiden:
>* Die Standardbegrenzung variiert je nach Kontext (normalerweise 200-10.000 Datensätze)
>* Verwenden Sie `lineCount` , um die maximale Anzahl von Ergebnissen explizit festzulegen
>* Verwenden Sie für große Datensätze (>1000 Datensätze) Workflows anstelle von queryDef. Workflows sind so konzipiert, dass sie Millionen von Zeilen effizient verarbeiten.

Weitere Informationen zu [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html?lang=de){target="_blank"} und [Best Practices für Abfragen](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}.

## Abfrage-Workflow-Übergangsdaten {#workflow-transition-data}

Beim Arbeiten mit JavaScript-Aktivitäten in Workflows können Sie Daten aus eingehenden Transitionen mithilfe von `vars.targetSchema` und `vars.tableName` abfragen.

**Empfängerdaten aus einer Workflow-Transition abfragen:**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Verwenden Sie immer parametrisierte Abfragen mit `$(sz)` für Zeichenfolgen und `$(l)` für Ganzzahlen, um SQL-Injection-Schwachstellen zu vermeiden. Weitere Informationen finden Sie in der [Campaign JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}.

## Zählen von Datensätzen {#count-records}

Verwenden Sie `Count(@id)` mit einem Alias, um Datensätze zu zählen.

**Anzahl der laufenden Hypothesen:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Anzahl mit mehreren Bedingungen:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Werteverteilung {#distribution-values}

Ermittelt die Verteilung der Werte für ein bestimmtes Feld, die für die Analyse von Datenmustern nützlich sind.

**Verteilung der Länder-Codes:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Abfragen von Auflistungen mit analyze {#analyze-enumerations}

Die Option `analyze` gibt benutzerfreundliche Namen für Auflistungswerte zurück. Anstelle nur numerischer Werte gibt Campaign auch den Zeichenfolgenwert und die Bezeichnung mit den Suffixen „Name“ und „Bezeichnung“ zurück.

**Abfrage der Versandzuordnung mit Auflistungsanalyse:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

Weitere Informationen zur Option [analysieren](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}.

## Paginierung {#pagination}

Verwenden Sie `lineCount` und `startLine`, um durch große Ergebnismengen zu paginieren.

**Abrufen von Datensätzen auf Seiten:**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**Paginierung erfordert orderBy:** Ohne eine `orderBy`-Klausel entsprechen die Abfrageergebnisse nicht garantiert einer konsistenten Reihenfolge. Nachfolgende Aufrufe geben möglicherweise unterschiedliche Seiten oder doppelte Datensätze zurück. Geben Sie bei Verwendung der Paginierung immer eine `orderBy` an.

Weitere Informationen über [Paginierung](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}.

## Dynamische Abfrageerstellung {#dynamic-queries}

Dynamisches Erstellen von Abfragen durch programmgesteuertes Anhängen von Bedingungen.

**Bedingungen an eine vorhandene Abfrage anhängen:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Erstellen und Auswählen, wo-Klauseln in Schleifen:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Erweiterte queryDef-Methoden {#advanced-methods}

Darüber hinaus bietet queryDef `ExecuteQuery()` mehrere spezialisierte Methoden für erweiterte Anwendungsfälle.

### BuildQuery - SQL ohne Ausführung generieren {#build-query}

Verwenden Sie `BuildQuery()`, um die SQL-Anweisung zu generieren, ohne sie auszuführen. Dies ist zum Debuggen, Protokollieren oder Übergeben von Abfragen an externe Systeme nützlich.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

Weitere Informationen zu &quot;[&#x200B; Query](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}.

### BuildQueryEx - SQL mit Formatzeichenfolge abrufen {#build-query-ex}

`BuildQueryEx()` gibt sowohl die SQL-Abfrage als auch eine mit der `sqlSelect()` Funktion kompatible Formatzeichenfolge zurück.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

Weitere Informationen zu [BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}.

### Alle auswählen - Alle auszuwählenden Felder hinzufügen {#select-all}

Die `SelectAll()`-Methode fügt automatisch alle Felder aus dem Schema zur select-Klausel hinzu, sodass Sie die einzelnen Felder nicht manuell auflisten müssen.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

Weitere Informationen zu [SelectAll](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}.

### Aktualisieren - Datensätze für die Massenaktualisierung {#mass-update}

Mit der `Update()` Methode können Sie umfangreiche Aktualisierungen für Datensätze durchführen, die Ihren Abfragekriterien entsprechen, ohne jeden Datensatz einzeln zu laden.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>Massenaktualisierungen wirken sich auf alle Datensätze aus, die der Where-Klausel entsprechen. Testen Sie immer, wo Ihre Bedingungen sind, indem Sie zuerst eine SELECT-Abfrage durchführen, um zu überprüfen, welche Datensätze betroffen sind.

Weitere Informationen zu [Aktualisieren](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}.

### GetInstanceFromModel - Instanzen der Abfragevorlage {#get-instance-from-model}

Verwenden Sie `GetInstanceFromModel()`, um Daten aus Instanzen abzurufen, die aus Vorlagen erstellt wurden.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

Weitere Informationen zu [GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}.

## Batch-Vorgänge {#batch-operations}

Mehrere Datensätze im Batch verarbeiten, um die Leistung zu verbessern.

**Batch-Update-Versandkennzeichnungen:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## SQL-Rohausführung {#raw-sql}

Bei komplexen Vorgängen können Sie Roh-SQL direkt ausführen.

**Ausführen von parametrisiertem SQL:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Abfrage mit sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>Bei Verwendung von Roh-SQL:
>
>* Benutzereingaben immer validieren und bereinigen
>* Verwenden parametrisierter Abfragen mit `$(sz)`, `$(l)`, `$(dt)` usw.
>* Achten Sie auf die Unterschiede zwischen der lokalen und der Cloud-Datenbank in [FFDA-Bereitstellungen](../architecture/enterprise-deployment.md)

## Best Practices {#best-practices}

Beim Arbeiten mit den Methoden queryDef und NLWS:

* **Verwenden von Workflows für große Datensätze** - QueryDef ist nicht für die Verarbeitung umfangreicher Daten konzipiert. Verwenden Sie für Datensätze mit mehr als 1.000 Datensätzen Workflows, die Millionen von Zeilen effizient verarbeiten können. Weitere Informationen finden Sie in der [&#x200B; zu Campaign SDK &#x200B;](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* **Parametrisierte Abfragen verwenden** - Gebundene Parameter (`$(sz)`, `$(l)`) immer mit `sqlExec` verwenden, um das Einschleusen von SQL zu verhindern
* **Explizite Limits festlegen** - Verwenden Sie `lineCount`, um die Ergebnisgröße zu steuern. Die Standardbeschränkungen von Campaign variieren je nach Kontext (200-10.000 Datensätze)
* **Verwenden von orderBy mit Paginierung** - Verwenden Sie bei der Verwendung von `orderBy` und `startLine` immer eine `lineCount`, um eine konsistente Paginierung sicherzustellen.
* **Use getIfExists** - Verwenden Sie `operation: "getIfExists"`, wenn möglicherweise keine Datensätze vorhanden sind, um Ausnahmen zu vermeiden.
* **Analyse für Auflistungen verwenden** - `analyze: true` zur Auswahl von Knoten hinzufügen, um benutzerfreundliche Auflistungsnamen und Beschriftungen zu erhalten
* **Abfragen optimieren** - Fügen Sie geeignete `where` hinzu, um Ergebnismengen zu begrenzen
* **Batch-Verarbeitung** - Verarbeitung mehrerer Datensätze in Batches, um Speicherprobleme und Zeitüberschreitungen zu vermeiden
* **FFDA-Erkennung** - Bei [Enterprise (FFDA)-](../architecture/enterprise-deployment.md) sollten Sie beachten, dass [!DNL Campaign] mit zwei Datenbanken funktioniert



## Praktische Anwendungsfälle {#use-cases}

### Debuggen und Protokollieren von Abfragen {#debug-queries}

`BuildQuery()` verwenden, um die generierte SQL vor der Ausführung zu überprüfen:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Duplizieren eines Datensatzes mit SelectAll {#duplicate-record}

Verwenden Sie `SelectAll()`, um beim Duplizieren von Datensätzen alle Felder zu kopieren:

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Vor einer Massenaktualisierung validieren {#validate-mass-update}

Betroffene Datensätze sollten vor Massenaktualisierungen immer in der Vorschau angezeigt werden:

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Syntaxreferenz für die Abfragedefinition {#querydef-reference}

Vollständige Struktur des `queryDef`:

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Verwandte Themen {#related-topics}

* [Erste Schritte mit Campaign-APIs](api.md)
* [Campaign JavaScript SDK - Abfrage-API](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [queryDef API-Referenz](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Campaign JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=de){target="_blank"}
* [Arbeiten mit Schemata](schemas.md)
* [Arbeiten mit dem Abfrage-Editor](../start/query-editor.md)


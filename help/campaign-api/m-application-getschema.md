---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 14%
---
# getSchema

Gibt eine Zuordnung zu einem Adobe Campaign-Schema zurück oder null, wenn das Schema nicht vorhanden ist.

```text
getSchema (name [, checkIfUpdated ])
```

## Parameter

**name** Vollständiger Schemaname.

**checkIfUpdated** Überprüfen Sie, ob das Schema im Cache aktualisiert wurde. Keine Auswirkung, wenn das Schema bereits im Skript instanziiert wurde.

## Rückgabewert

Eine Schemazuordnung (siehe [Schema](c-schema.md)-Objekt) oder die Methode startet eine Ausnahme, wenn kein Schema mit dem Namen übereinstimmt.

## Bemerkungen

Alle in einem Skript instanziierten Schemata bleiben bis zum Ende des Skripts im Speicher zugewiesen. Beispiel:

```javascript
      var schema = application.getSchema("nms:recipient")
```

## Funktionen

**Methode der Klasse:** [Application](c-application.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

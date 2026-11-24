---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 40%
---
# Felder

Gibt eine Tabelle zurück, die das Feld der Felder ([SchemaNode](c-schemanode.md)) des Schlüssels enthält.

```text
fields
```

## Bemerkungen

Beispiel:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
{
  logInfo("Key: " + key.name)
  for each(var field in key.fields)
    logInfo("\t" + field.name + "\t" + field.type)
}
    
```

## Funktionen

**Eigenschaft der Klasse:** [SchemaKey](c-schemakey.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

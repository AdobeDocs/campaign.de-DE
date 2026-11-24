---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 45%
---
# Schlüssel

Gibt eine Tabelle mit Definitionen der Schlüssel „SchemaKey[&#x200B; des aktuellen Knotens &#x200B;](c-schemakey.md).

```text
keys
```

## Bemerkungen

Beispiel:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
```

## Funktionen

**Eigenschaft der Klasse:** [SchemaNode](c-schemanode.md)

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

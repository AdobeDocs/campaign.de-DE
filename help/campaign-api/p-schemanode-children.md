---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 38%
---
# Children

Gibt ein -Objekt zurück, für das jede Eigenschaft ein untergeordneter Knoten ist, der anhand seines Namens indiziert wird.

```text
children
```

## Bemerkungen

Beispiel:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

logInfo(root.children["@firstName"].label)
logInfo(root.children.country.label)

// root.children is a map which :
//   each key is the name of the child
//   each value the corresponding SchemaNode instance
for each(var node in root.children)
{
  logInfo(node.label + " (" + node.type + ")")
}
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

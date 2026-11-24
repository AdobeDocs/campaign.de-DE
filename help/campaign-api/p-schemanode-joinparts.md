---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 21%
---
# joinParts

Gibt eine Tabelle von SchemaNode-Instanzen zurück, für die jedes Element eine Bedingung des Joins darstellt.

```text
joinParts
```

## Bemerkungen

Jedes Element in der Tabelle hat zwei Eigenschaften:

* source : Das -Element, das das Feld der Quelltabelle darstellt.
* destination - Das Element, das das Feld der Zieltabelle darstellt.

Beispiel:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
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

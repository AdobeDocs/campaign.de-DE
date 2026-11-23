---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 11%
---
# findNode

Gibt eine Instanz von [SchemaNode](c-schemanode.md) oder null zurück, wenn der Knoten nicht vorhanden ist und der Parameter „mustExist“ auf „false“ gesetzt ist.

```text
findNode (name [, strict ] [, mustExist ])
```

## Parameter

**name** XPath steht für den Namen des zu durchsuchenden Knotens

**rict** Boolescher Wert, der angibt, ob (strict bis false) oder nicht, wenn der Name des letzten Elements im Pfad nicht unverändert ist, sollte nach ihm als Attribut oder Element gesucht werden. Standardmäßig ist dies „true“.

**mustExist** Boolescher Wert, der angibt, ob eine Ausnahme ausgelöst werden muss, wenn der Knoten nicht vorhanden ist. Standardmäßig „true“.

## Rückgabewert

Gibt eine [SchemaNode](c-schemanode.md)-Instanz zurück, wenn der Knoten gefunden wird, oder null, wenn der Parameter „mustExist“ auf „false“ gesetzt ist.

## Bemerkungen

Beispiel:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

Ergebnis:

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## Funktionen

**Methode der Klasse:** [SchemaNode](c-schemanode.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

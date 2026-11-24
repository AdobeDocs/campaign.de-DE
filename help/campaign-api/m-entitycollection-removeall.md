---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 46%
---
# removeAll

Löscht alle Entitäten aus der Sammlung.

```text
removeAll ()
```

## Parameter

Keine.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## Funktionen

**Methode der Klasse:** [EntityCollection](c-entitycollection.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

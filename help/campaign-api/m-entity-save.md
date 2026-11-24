---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 46%
---
# speichern

Speichert eine Entität in der Datenbank

```text
save ()
```

## Parameter

Keine.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## Funktionen

**Methode der Klasse:** [Entity](c-entity.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

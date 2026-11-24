---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 34%
---
# entfernen

Löscht eine Entität aus der Sammlung.

```text
remove (index|object)
```

## Parameter

**index\|object** Index der zu löschenden Entität oder der Entität selbst.

## Rückgabewert

Keine.

## Bemerkungen

Beispiele:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
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

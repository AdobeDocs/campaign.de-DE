---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 18%
---
# EntityCollection (Klasse)

Stellt eine Auflistung einer Entität dar.

Ein solches Objekt kann nicht direkt instanziiert werden. Sie müssen die Methoden create(), get() oder load() verwenden.

Die Elemente einer Auflistung können mit `for` oder `for each` aufgezählt werden. Dieses Beispiel zeigt eine Auflistung von Dateien, die mit einer Versandaktion verknüpft sind.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [Hinzufügen](m-entitycollection-add.md) | Fügt der Sammlung eine neue Entität hinzu. |
| [Entfernen](m-entitycollection-remove.md) | Löscht eine Entität aus der Sammlung. |
| [removeAll](m-entitycollection-removeall.md) | Löscht alle Entitäten aus der Sammlung. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [length](p-entitycollection-length.md) | Gibt die Entitätsnummer der Sammlung zurück. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

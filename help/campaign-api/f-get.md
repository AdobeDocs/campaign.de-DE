---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 11%
---
# Abrufen

Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück.

```text
get ( [key or content ])
```

## Parameter

**key oder content** Eine Zeichenfolge, die dem Schlüssel der Entität des XML-Inhalts entspricht, um eine neue Entität zu erstellen oder zu initiieren.

## Rückgabewert

Gibt die Entität in Form eines JavaScript-Objekts zurück.

## Bemerkungen

GET ist keine globale Funktion, sondern eine Schemamethode. Um sie aufzurufen, müssen Sie ihr das gewünschte Schema voranstellen. Beispiel:

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

Die Eigenschaften und Untereigenschaften dieses Objekts können beliebig geändert werden. Das Dokument wird automatisch in der Datenbank gespeichert, wenn die Ausführung des Skripts abgeschlossen ist, falls es geändert wurde. Wenn es sich nicht um eine Erstellung handelt und sich die Entität noch nicht in der Datenbank befindet, wird ein Fehler ausgegeben und das Skript wird unterbrochen.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

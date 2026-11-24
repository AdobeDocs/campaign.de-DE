---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 11%
---
# belasten

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück.

```text
load (key)
```

## Parameter

**key** Eine Zeichenfolge, die dem Schlüssel der Entität entspricht.

## Rückgabewert

Gibt die Entität in Form eines JavaScript-Objekts zurück.

## Bemerkungen

LOAD ist keine globale Funktion, sondern eine Schemamethode. Um sie aufzurufen, müssen Sie ihr das gewünschte Schema voranstellen. Beispiel:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

Die Eigenschaften und Untereigenschaften dieses Objekts können beliebig geändert werden. Im Gegensatz zur [get()](f-get.md)-Methode wird das Dokument nicht automatisch in der Datenbank gespeichert, sondern Sie müssen die Methode [save()](m-entity-save.md) für das -Objekt aufrufen. Wenn die Entität nicht in der Datenbank gefunden wird, handelt es sich um einen Fehler, und das Skript wird unterbrochen.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 19%
---
# getNewIds

Gibt eine Liste der IDs der internen Datenbankschlüssel zurück.

```text
getNewIds (count [, sequence ])
```

## Parameter

**count** Anzahl der IDs, die die Methode zurückgeben muss.

**sequence** Name der zu verwendenden Sequenz.

## Rückgabewert

Eine Tabelle mit der Liste der IDs:

## Bemerkungen

Diese Methode entspricht den SOAP-Methoden NLWS.xtkSession.GetNewIds() und NLWS.xtkSession.GetNewIdsEx(), ist jedoch effizienter.

## Funktionen

**Methode der Klasse:** [Application](c-application.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

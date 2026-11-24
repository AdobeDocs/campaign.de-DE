---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 31%
---
# getImageUrl

Aktiviert die Erstellung der URL für den Zugriff auf öffentliche Ressourcen

```text
getImageUrl (ID|internal name)
```

## Parameter

**ID\|Interner Name** ID der öffentlichen Ressource oder interner Name der Ressource.

## Rückgabewert

Gibt die URL für den Zugriff auf öffentliche Ressourcen zurück.

## Bemerkungen

Ressourcen müssen auf Frontservern veröffentlicht werden. Beispiel:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
```

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Versandnachricht
* Typologieregel
* Import
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

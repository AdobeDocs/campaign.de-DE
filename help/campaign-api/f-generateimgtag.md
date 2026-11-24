---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 28%
---
# generateImgTag

Aktiviert die Erstellung eines HTML &lt;img>-Tags basierend auf einer öffentlichen Ressource.

```text
generateImgTag (ID)
```

## Parameter

**ID** ID der öffentlichen Ressource

## Rückgabewert

Gibt das HTML &lt;img>-Tag mit den Eigenschaften des Bildes aus, das in der Definition der öffentlichen Ressource enthalten ist.

## Bemerkungen

Ressourcen müssen auf Frontservern veröffentlicht werden. Beispiel:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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

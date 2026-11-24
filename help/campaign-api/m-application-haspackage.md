---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 35%
---
# hasPackage

Testet, ob ein Paket installiert ist.

```text
hasPackage (name)
```

## Parameter

**name** Vollständiger Name des Pakets.

## Rückgabewert

True, wenn das Paket installiert ist.

## Bemerkungen

Beispiel:

```javascript
var hasMRM = application.hasPackage("nms:mrm")
```

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

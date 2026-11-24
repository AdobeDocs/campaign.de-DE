---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 34%
---
# hasRight

Prüft, ob der Benutzer über eine spezifische spezifische spezifische spezifische spezifische Berechtigung verfügt.

```text
hasRight (name)
```

## Parameter

**name** Berechtigungsname.

## Rückgabewert

True, wenn der Benutzer über diese Berechtigung verfügt.

## Bemerkungen

Beispiel:

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## Funktionen

**Methode der Klasse:** [CurrentOperator](c-currentoperator.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 17%
---
# anmelden

Ändert den Ausführungskontext des Skripts in die aktuelle Anmeldung.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## Parameter

**sessionToken** Das zu verwendende Sitzungs-Token.

**login** Der zu verwendende Benutzerlogin.

**password** Das Benutzerkennwort. Das Kennwort kann eine leere Zeichenfolge sein, wenn die aktuelle Anmeldung über Administratorrechte verfügt.

**context** Ein Objekt, das eine Anmeldung darstellt, die von einem vorherigen Anmeldeaufruf zurückgegeben wurde.

## Rückgabewert

Gibt ein -Objekt zurück, das der vorherigen Anmeldung entspricht. Dies ermöglicht es, die vorherige Anmeldung wiederherzustellen, indem dieser Parameter an die Anmeldungsfunktion übergeben wird.

## Bemerkungen

Beispiel:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
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

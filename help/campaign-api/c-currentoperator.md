---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 12%
---
# CurrentOperator (Class)

Objekt, das Informationen zum aktuellen Operator enthält (Name, Bezeichner, Rechte usw.).

Diese Klasse verfügt über eine einzige Instanz, die Zugriff auf bestimmte Eigenschaften des Anwendungsservers bietet. Auf dieses Singleton kann über die Eigenschaft der globalen `application` zugegriffen werden.

Beispiel:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | Prüft, ob der Benutzer über eine spezifische spezifische spezifische spezifische spezifische Berechtigung verfügt. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [Anmeldung](p-currentoperator-login.md) | Gibt den Login des aktuellen Benutzers aus. |
| [id](p-currentoperator-id.md) | Gibt die interne Kennung des aktuellen Benutzers aus. |
| [computeString](p-currentoperator-computestring.md) | Gibt die aktuelle Zeichenfolge der Benutzerbeschreibung zurück. Standardmäßig ist dies der Name des Benutzers gefolgt von seiner Anmeldung. |
| [Gruppen](p-currentoperator-groups.md) | Gibt die Liste der Kennungen in den aktuellen Benutzergruppen aus. |
| [Rechte](p-currentoperator-rights.md) | Gibt die Liste der Berechtigungen des aktuellen Benutzers aus. |
| [Zeitzone](p-currentoperator-timezone.md) | Gibt den Namen der vom aktuellen Operator verwendeten Zeitzone zurück. |
| [Startseite](p-currentoperator-home.md) | Gibt den Namen des Stammordners des aktuellen Benutzers aus. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

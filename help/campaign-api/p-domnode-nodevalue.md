---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 21%
---
# nodeValue

Knotenwert. Der Wert hängt vom Typ des Knotens ab.

```text
nodeValue
```

## Bemerkungen

Auf diese Eigenschaft kann mit Lese- und Schreibberechtigungen zugegriffen werden. Beispiel zum Abrufen einer Betreffzeile und Hinzufügen zu den zusätzlichen Daten aus einer Abfrageaktivität in einem Workflow:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

Beispiel zum Abrufen einer Betreffzeile aus einer Anreicherungsaktivität in einem Workflow:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## Funktionen

**Eigenschaft der Klasse:** [DOMNode](c-domnode.md)

**Schreibgeschützt:**

Ja

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

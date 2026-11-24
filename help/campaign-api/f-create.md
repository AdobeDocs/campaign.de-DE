---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 17%
---
# erstellen

Erstellt eine neue Entität, die einem bestimmten Schema entspricht.

```text
create ( [content ])
```

## Parameter

**content** Eine optionale Zeichenfolge, die der XML der zu erstellenden Entität entspricht.

## Rückgabewert

Gibt die Entität in Form eines JavaScript-Objekts zurück.

## Bemerkungen

CREATE ist keine globale Funktion, sondern eine Schemamethode. Um sie aufzurufen, müssen Sie ihr das gewünschte Schema voranstellen. Beispiel:

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

Das Dokument wird nicht automatisch in der Datenbank gespeichert. Sie müssen die Methode ⌐⌐[save()](m-entity-save.md) für die Entität verwenden.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

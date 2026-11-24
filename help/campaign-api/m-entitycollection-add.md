---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 9%
---
# hinzufügen

Fügt der Sammlung eine neue Entität hinzu.

```text
add ( [index ], xml)
```

## Parameter

**index** Die Entität wird an diesem Indexpunkt hinzugefügt. Wenn dieses Argument nicht angegeben wird, wird die Entität an das Ende der Liste angehängt.

**xml** Die in das XML-Formular einzufügende Entität.

## Rückgabewert

Das erstellte Element.

## Bemerkungen

Das folgende Beispiel zeigt zwei verschiedene Möglichkeiten, ein neues Element zu einer Sammlung hinzuzufügen. Die erste Lösung übergibt die vollständige Definition des Elements an die add()-Methode, während die zweite Lösung übergibt und das leere &lt;attachment/>-Element dann die Attribute wie gewohnt zuweist.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

Die beiden Lösungen sind identisch, aber mit der zweiten können Sie die JavaScript-Typen verwenden, die Attributtypen entsprechen, während die erste nur Zeichenfolgen unterstützt.

## Funktionen

**Methode der Klasse:** [EntityCollection](c-entitycollection.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

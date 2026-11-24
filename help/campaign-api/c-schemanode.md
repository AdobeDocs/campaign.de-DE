---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 2%
---
# SchemaNode (Klasse)

Stellt das Element eines Schemas dar

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | Gibt eine Instanz von [SchemaNode](c-schemanode.md) oder null zurück, wenn der Knoten nicht vorhanden ist und der Parameter „mustExist“ auf „false“ gesetzt ist. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [children](p-schemanode-children.md) | Gibt ein -Objekt zurück, für das jede Eigenschaft ein untergeordneter Knoten ist, der anhand seines Namens indiziert wird. |
| [computeString](p-schemanode-computestring.md) | Gibt die vom aktuellen Knoten berechnete Zeichenfolge zurück. |
| [dataPolicy](p-schemanode-datapolicy.md) | Gibt eine Zeichenfolge zurück, die die Datenrichtlinie des aktuellen Knotens angibt. |
| [description](p-schemanode-description.md) | Gibt eine Zeichenfolge zurück, die den aktuellen Knoten beschreibt. |
| [defaultValue](p-schemanode-defaultvalue.md) | Gibt eine Zeichenfolge zurück, die den Standardwert des aktuellen Knotens angibt. |
| [editType](p-schemanode-edittype.md) | Gibt eine Zeichenfolge zurück, die den Bearbeitungstyp des aktuellen Knotens angibt. |
| [Auflistung](p-schemanode-enumeration.md) | Gibt ein [Enumeration](c-enumeration.md)-Objekt zurück, das die mit dem aktuellen Knoten verknüpfte Auflistung ist, oder null, wenn keine Auflistung vorhanden ist. |
| [enumerationImage](p-schemanode-enumerationimage.md) | Gibt den Namen des Bildes des aktuellen Knotens in Form einer Zeichenfolge zurück. |
| [folderModel](p-schemanode-foldermodel.md) | Gibt nur auf dem Stammknoten eine Zeichenfolge zurück, die die Ordnervorlage(n) enthält. Auf den anderen Knoten wird „undefined“ zurückgegeben. |
| [Bild](p-schemanode-image.md) | Gibt den Namen des Bildes in Form einer Zeichenfolge zurück. |
| [integrity](p-schemanode-integrity.md) | Gibt den Integritätstyp der Relation zurück. |
| [keys](p-schemanode-keys.md) | Gibt eine Tabelle mit Definitionen der Schlüssel „SchemaKey[&#x200B; des aktuellen Knotens &#x200B;](c-schemakey.md). |
| [hasEnumeration](p-schemanode-hasenumeration.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Wert des aktuellen Knotens mit einer Auflistung verknüpft ist. |
| [childrenCount](p-schemanode-childrencount.md) | Gibt eine Zahl zurück, die die Anzahl der untergeordneten Knoten angibt. |
| [hasSQLTable](p-schemanode-hassqltable.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten mit einer SQL-Tabelle verknüpft ist. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Wert des aktuellen Knotens mit einer Benutzeraufzählung verknüpft ist. |
| [Hilfe](p-schemanode-help.md) | Gibt die Hilfe-Zeichenfolge zurück. |
| [schema](p-schemanode-schema.md) | Gibt die Instanz des übergeordneten Objekts (Schema) [&#x200B; Knotens &#x200B;](c-schema.md). |
| [isAdvanced](p-schemanode-isadvanced.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten erweitert ist oder nicht. |
| [isAnyType](p-schemanode-isanytype.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten normal ist. |
| [isAttribute](p-schemanode-isattribute.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten ein Attribut ist. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Wert des aktuellen Knotens automatisch erhöht wird. |
| [isAutopk](p-schemanode-isautopk.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten ein Primärschlüssel ist. |
| [isBlob](p-schemanode-isblob.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten ein BLOB ist. |
| [isCalculated](p-schemanode-iscalculated.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Wert des aktuellen Knotens das Ergebnis einer Berechnung ist. |
| [isCDATA](p-schemanode-iscdata.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten vom CDATA-XML-Typ zugeordnet ist. |
| [isCollection](p-schemanode-iscollection.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten eine Sammlung von Unterelementen und/oder Attributen ist. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | Gibt einen booleschen Wert zurück. Wenn der hinzugefügte Wert variiert, wird während der Datensatzdeduplizierung der Standardwert (definiert in defaultValue) während der Aufzeichnung automatisch erneut angewendet. |
| [isElementOnly](p-schemanode-iselementonly.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten eine logische Untereinheit des Schemas ist. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | True, wenn der Knoten ein Link ist und wenn der Join extern ist. |
| [isFeature](p-schemanode-isfeature.md) | Gibt einen booleschen Wert zurück, der angibt, ob es sich bei dem Knoten um eine Funktion handelt. |
| [isLink](p-schemanode-islink.md) | Gibt einen booleschen Wert zurück, der angibt, ob es sich bei dem Knoten um einen Link handelt. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Knoten eine XML-Zuordnung ist. |
| [isMemo](p-schemanode-ismemo.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten durch ein Memo zugeordnet wird. |
| [isMemoData](p-schemanode-ismemodata.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten von einem MemoData zugeordnet wird. |
| [isNotNull](p-schemanode-isnotnull.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten den Nullwert berücksichtigen kann. |
| [isRequired](p-schemanode-isrequired.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Wert des aktuellen Knotens obligatorisch ist. |
| [isRoot](p-schemanode-isroot.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Knoten der Stamm des Schemas ist. |
| [isSQL](p-schemanode-issql.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten in SQL zugeordnet ist. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | Gibt einen booleschen Wert zurück, der angibt, ob die Tabelle eine temporäre Tabelle ist. Die Tabelle wird bei der Datenbankerstellung nicht erstellt. |
| [isUnbound](p-schemanode-isunbound.md) | Gibt einen booleschen Wert zurück, der angibt, ob der aktuelle Knoten über eine unbegrenzte Anzahl von untergeordneten Elementen desselben Typs verfügt. |
| [isUser](p-schemanode-isuser.md) | Gibt einen booleschen Wert zurück, der angibt, ob der Knoten vom Typ „user“ ist oder nicht. |
| [joinParts](p-schemanode-joinparts.md) | Gibt eine Tabelle von SchemaNode-Instanzen zurück, für die jedes Element eine Bedingung des Joins darstellt. |
| [label](p-schemanode-label.md) | Gibt eine Zeichenfolge zurück, die die Beschreibung des aktuellen Knotens ist. |
| [name](p-schemanode-name.md) | Gibt eine Zeichenfolge zurück, die dem Namen des aktuellen Knotens entspricht. |
| [nodePath](p-schemanode-nodepath.md) | Gibt eine Zeichenfolge zurück, die den absoluten Pfad des aktuellen Knotens darstellt. |
| [parent](p-schemanode-parent.md) | Gibt ein [SchemaNode](c-schemanode.md)-Objekt zurück, das das übergeordnete Objekt ist, oder null, wenn es keines gibt. |
| [PKSequence](p-schemanode-pksequence.md) | Gibt eine Zeichenfolge zurück, die den Namen der für den Primärschlüssel zu verwendenden Sequenz angibt. |
| [packageStatus](p-schemanode-packagestatus.md) | Gibt eine Zahl zurück, die den Paketstatus angibt. |
| [reverseLink](p-schemanode-reverselink.md) | Wenn das Element eine Relation ist, gibt ein [SchemaNode](c-schemanode.md)-Objekt zurück, das eine Umkehrrelation (über das Zielschema) darstellt. Ist dies nicht der Fall, wird die Eigenschaft nicht definiert. |
| [SQLName](p-schemanode-sqlname.md) | Der SQL-Name des Felds. Die Eigenschaft ist eine leere Zeichenfolge, wenn das Objekt kein Feld vom Typ SQL ist. |
| [SQLTable](p-schemanode-sqltable.md) | Der SQL-Name der Tabelle. Die Eigenschaft ist eine leere Zeichenfolge, wenn das Objekt nicht das Hauptelement ist oder die Schemazuordnung nicht vom Typ SQL ist. |
| [size](p-schemanode-size.md) | Die Größe des Typs der Zeichenfolge. |
| [tableDefinition](p-schemanode-tabledefinition.md) | Eine Instanz eines [SchemaNode](c-schemanode.md), bei der es sich um die Beschreibung der Tabelle handelt, die den aktuellen Knoten enthält. |
| [target](p-schemanode-target.md) | Das Hauptelement des Schemas des Link-Ziels. Wenn das Objekt keine Relation ist, wird die Eigenschaft nicht definiert. |
| [type](p-schemanode-type.md) | Gibt eine Zeichenfolge zurück, die den Werttyp des aktuellen Knotens angibt. |
| [userEnumeration](p-schemanode-userenumeration.md) | Gibt eine Zeichenfolge zurück. Dies ist der Name der vom aktuellen Knoten verwendeten Benutzeraufzählung. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 7%
---
# DOMNode (Klasse)

DOMNode ist die übergeordnete Klasse verschiedener Komponenten, aus denen ein Dokument besteht.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [insertBefore](m-domnode-insertbefore.md) | Fügen Sie einen Knoten vor einer bestimmten Position ein. |
| [replaceChild](m-domnode-replacechild.md) | Ersetzen Sie einen Knoten. |
| [removeChild](m-domnode-removechild.md) | Löschen eines Knotens. |
| [appendChild](m-domnode-appendchild.md) | Fügen Sie am Ende der Liste der Unterordner einen Knoten ein. |
| [hasChildNodes](m-domnode-haschildnodes.md) | Testet, ob der Knoten mindestens einen Unterordner hat. |
| [normalisieren](m-domnode-normalize.md) | Normalisiert den Knoten: Angrenzende Textknoten werden zusammengeführt und leere Textknoten werden gelöscht. |
| [hasAttributes](m-domnode-hasattributes.md) | Prüft, ob der Knoten mindestens ein Attribut hat. |
| [isSameNode](m-domnode-issamenode.md) | Prüft, ob die angegebene Referenz denselben Knoten darstellt. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | Prüft, ob der angegebene Namespace der Standard ist. |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | Durchsucht den URI des Namespace, der mit dem angegebenen Präfix verknüpft ist. |
| [isEqualNode](m-domnode-isequalnode.md) | Vergleicht zwei Knoten. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | Qualifizierter Knotenname. Der Name hängt vom Knotentyp ab. |
| [nodeValue](p-domnode-nodevalue.md) | Knotenwert. Der Wert hängt vom Typ des Knotens ab. |
| [nodeType](p-domnode-nodetype.md) | Knotentyp |
| [parentNode](p-domnode-parentnode.md) | Übergeordneter Knoten oder null. |
| [childNodes](p-domnode-childnodes.md) | Gibt die Liste der untergeordneten Knoten in Form einer Tabelle zurück. |
| [firstChild](p-domnode-firstchild.md) | Erster untergeordneter Knoten dieses Knotens oder null, wenn er keine untergeordneten Knoten hat. |
| [lastChild](p-domnode-lastchild.md) | Letzter untergeordneter Knoten dieses Knotens oder null, wenn er keine untergeordneten Knoten hat. |
| [nextSibling](p-domnode-nextsibling.md) | Knoten, der diesem Knoten oder null folgt. |
| [previousSibling](p-domnode-previoussibling.md) | Der Knoten, der diesem Knoten unmittelbar vorausgeht, oder null. |
| [Attribute](p-domnode-attributes.md) | Gibt eine Tabelle zurück, die die Liste der Attribute enthält, wenn der Knoten ein Element ist, andernfalls null. |
| [namespaceURI](p-domnode-namespaceuri.md) | URI des Namespace des Knotens. |
| [Präfix](p-domnode-prefix.md) | Das Namespace-Präfix dieses Knotens oder leer, wenn nicht anders angegeben. |
| [localName](p-domnode-localname.md) | Lokaler Teil des qualifizierten Knotennamens. |
| [baseURI](p-domnode-baseuri.md) | Basis-URI dieses Knotens. |
| [textContent](p-domnode-textcontent.md) | Textinhalt des Knotens. Der Wert hängt vom Typ des Knotens ab. |
| [ownerDocument](p-domnode-ownerdocument.md) | Das Dokument, zu dem dieser Knoten gehört. |

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

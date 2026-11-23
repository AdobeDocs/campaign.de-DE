---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%
---
# Schema (Klasse)

Stellt die Schemadefinition dar.

Ein Schema wird durch Aufrufen der -Methode der globalen `application`-Variablen abgerufen. Eine Instanz dieses Objekts hat ein -Objekt als Prototyp und erbt daher seine Methoden.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [toDocument](m-schema-todocument.md) | Konvertiert das Schema in ein XML-Dokumentformular. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [Auflistungen](p-schema-enumerations.md) | Gibt die Tabelle zurück, die die Liste der in [ Schema ](c-enumeration.md) Auflistungen enthält. |
| [id](p-schema-id.md) | Die Schemakennung in Form einer Zeichenfolge. |
| [isLibrary](p-schema-islibrary.md) | Gibt einen booleschen Wert zurück, der angibt, ob das Schema eine Komponentenbibliothek ist. |
| [labelSingular](p-schema-labelsingular.md) | Der Singulärname des Schemas in Form einer Zeichenfolge. |
| [mappingType](p-schema-mappingtype.md) | Die Art der Schemazuordnung in Form einer Zeichenfolge |
| [MD5](p-schema-md5.md) | Der MD5-Code des Schemas in Form einer hexadezimalen Zeichenfolge. |
| [namespace](p-schema-namespace.md) | Namespace des Schemas in Form einer Zeichenfolge. |
| [root](p-schema-root.md) | Hauptelement des Schemas oder null, wenn nicht definiert. |
| [userDescription](p-schema-userdescription.md) | Die Beschreibung des Schemas in Form einer Zeichenfolge. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

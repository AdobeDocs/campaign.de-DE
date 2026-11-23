---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 8%
---
# hmacStr

Berechnet den MD5-, SHA-1- oder SHA-256-Hash einer Zeichenfolge. Die Zeichenfolge wird vor der Berechnung automatisch in UTF-8 codiert.

```text
hmacStr (string [, key ] [, algo ])
```

## Parameter

**string** Die Zeichenfolge, in der der Hash berechnet werden soll.

**key** Key in Form einer Zeichenfolge. Es wird automatisch in UTF-8 konvertiert. Wenn der Schlüssel fehlt, verwendet der Server einen Schlüssel, der von der Instanz abhängt und nur auf dieser Instanz gültig ist.

**algo** Typ des zu verwendenden Hash. Mögliche Werte sind „MD5“, „SHA1“ oder „SHA256“. Groß-/Kleinschreibung wird ignoriert, daher können Werte in Klein- oder Großbuchstaben eingegeben werden. Der Wert „SHA1“ ist standardmäßig ausgewählt, wenn kein Parameter angegeben ist.

## Rückgabewert

Der MD5-, SHA-1- oder SHA-256-Hash (je nach ausgewähltem Hash-Typ) der als Parameter übergebenen Zeichenfolge.

## Bemerkungen

Bei MD5- und SHA-1-Typen kann der Schlüssel nach der Konvertierung in UTF-8 bis zu 64 Zeichen (512 Bit) lang sein. Beim SHA-256-Typ kann der Schlüssel nach der Konvertierung in UTF-8 bis zu 32 Zeichen (256 Bit) lang sein.

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

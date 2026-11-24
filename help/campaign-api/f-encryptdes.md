---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 8%
---
# encryptDES

> Warnung:
>
> Diese Funktion ist veraltet. Verwenden Sie [cryptString()](f-cryptstring.md).

Verschlüsselt eine Zeichenfolge mit dem DES-Algorithmus.

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parameter

**key** Der hexadezimal dargestellte Schlüssel. Der Schlüssel muss 64 Bit lang sein, d. h. 16 Hexadezimalzeichen.

**value** Die zu verschlüsselnde Zeichenfolge

**Chiffriermodus** Die Methode zum Codieren von Blöcken. Eine Zeichenfolge. d. h. „CBC“, „ECB“ oder „EDE“. Standardmäßig „CBC“.

**Initialisierungsvektor** Der Initialisierungsvektor in Form einer hexadezimalen Zeichenfolge. Genau 8 Oktetts, d. h. 16 Zeichen. Standardmäßig eine leere Zeichenfolge.

**padding** Der Abstandstyp. Eine Zeichenfolge, z. B. „PKCS5PADDING“ oder „PKCS7PADDING“. Standardmäßig ein leerer String, was bedeutet, dass &#39;\\0&#39; am Ende des zu verschlüsselnden Strings hinzugefügt wird.

## Rückgabewert

Die verschlüsselte Zeichenfolge, die in Base 64 dargestellt wird.

## Bemerkungen

* Ein DES-Schlüssel hat 56 nützliche Bits und 8 Bits, die für die Parität verwendet werden; Diese Bits werden ignoriert.
* Der effektiv durch den DES-Algorithmus verschlüsselte Wert ist die 8-Bit-Windows-1252-Darstellung der Zeichenfolge, die mit einem ASCII-0-Zeichen endet und auf ein Vielfaches von 64 Bit mit binären Nullen aufgefüllt wird.
* Der verschlüsselte Wert ist ein Vielfaches von 64-Bit-Wörtern.

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

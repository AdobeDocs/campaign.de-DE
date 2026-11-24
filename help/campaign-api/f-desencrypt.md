---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 8%
---
# DESencrypt

> Warnung:
>
> Diese Funktion ist veraltet. Verwenden Sie [cryptString()](f-cryptstring.md).

Digitalisiert eine Zeichenfolge mit dem DES-Algorithmus.

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parameter

**value** Die zu digitalisierende Zeichenfolge

**key** Der hexadezimal dargestellte Schlüssel. Der Schlüssel muss 64 Bit oder 16 Hexadezimalzeichen lang sein. Standardmäßig wird die Kennung der Datenbank verwendet.

**Chiffriermodus** Die Methode zur Blockcodierung. Ein String. d. h. „CBC“, „ECB“ oder „EDE“. Standardmäßig „CBC“.

**Initialisierungsvektor** Der Initialisierungsvektor in Form einer hexadezimalen Zeichenfolge. Genau 8 Oktetts, d. h. 16 Zeichen. Standardmäßig eine leere Zeichenfolge.

**padding** Der Auffülltyp. Eine Zeichenfolge, z. B. „PKCS5PADDING“ oder „PKCS7PADDING“. Standardmäßig ein leerer String, was bedeutet, dass am Ende des zu verschlüsselnden Strings ein &#39;\\0&#39; hinzugefügt wird.

## Rückgabewert

Die digitalisierte Zeichenfolge, die in Base 64 dargestellt wird.

## Bemerkungen

* Ein DES-Schlüssel hat 56 nützliche Bits und 8 Bits, die für die Parität verwendet werden; Diese Bits werden ignoriert.
* Der effektiv durch den DES-Algorithmus verschlüsselte Wert ist die 8-Bit-Windows-1252-Darstellung der Zeichenfolge, die mit einem ASCII-0-Zeichen endet und auf ein Vielfaches von 64 Bit mit binären Nullen aufgefüllt wird.
* Der digitalisierte Wert hat einen Mehrfach-Längen-64-Bit-Wert.

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

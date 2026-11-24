---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 11%
---
# decryptDES

> Warnung:
>
> Diese Funktion ist veraltet. Verwenden Sie [decryptString()](f-decryptstring.md).

Entschlüsselt eine Zeichenfolge mit dem DES-Algorithmus.

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## Parameter

**key** Der hexadezimal dargestellte Schlüssel. Der Schlüssel muss 64 Bit lang oder 16 Hexadezimalzeichen sein.

**value** Die in Base 64 dargestellten zu verschlüsselnden Daten.

**Chiffriermodus** Die Methode zum Codieren von Blöcken. Eine Zeichenfolge. d. h. „CBC“, „ECB“ oder „EDE“. Standardmäßig „CBC“.

**Initialisierungsvektor** Der Initialisierungsvektor in Form einer hexadezimalen Zeichenfolge. Genau 8 Oktetts, d. h. 16 Zeichen. Standardmäßig eine leere Zeichenfolge.

## Rückgabewert

Die Zeichenfolge in Klartext.

## Bemerkungen

* Ein DES-Schlüssel hat 56 nützliche Bits und 8 Bits, die für die Parität verwendet werden; Diese Bits werden ignoriert.
* Die Daten werden als 8-Bit-String in der Codepage von Windows-1252 unverschlüsselt.
* Die Länge der verschlüsselten Daten muss ein Vielfaches von 64 Bit betragen.

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

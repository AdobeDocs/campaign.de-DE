---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 11%
---
# DESpcrypt

> Warnung:
>
> Diese Funktion ist veraltet. Verwenden Sie [decryptString()](f-decryptstring.md).

Entschlüsselt Daten mit dem DES-Algorithmus.

```text
DESdecrypt (value [, key ] [, cipher mode ] [, initialization vector ])
```

## Parameter

**value** Die zu digitalisierenden Daten, dargestellt in Base 64.

**key** Der hexadezimal dargestellte Schlüssel. Der Schlüssel muss 64 Bit oder 16 Hexadezimalzeichen lang sein. Standardmäßig wird die Kennung der Datenbank verwendet.

**Chiffriermodus** Die Methode zur Blockcodierung. Ein String. d. h. „CBC“, „ECB“ oder „EDE“. Standardmäßig „CBC“.

**Initialisierungsvektor** Der Initialisierungsvektor in Form einer hexadezimalen Zeichenfolge. Genau 8 Oktetts, d. h. 16 Zeichen. Standardmäßig eine leere Zeichenfolge.

## Rückgabewert

Die unverschlüsselte Zeichenfolge.

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

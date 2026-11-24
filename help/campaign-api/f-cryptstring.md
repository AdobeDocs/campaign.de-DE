---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 38%
---
# cryptString

> Warnung:
>
> Diese Funktion ist vollständig veraltet. Weitere Informationen finden Sie auf dieser [Seite](https://experienceleague.adobe.com/de/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions).

Verschlüsselt einen String mit dem Schlüssel der Instanz oder einem anderen Schlüssel.

```text
cryptString (str [, key ] [, useSalt ])
```

## Parameter

**str** Die zu verschlüsselnde Zeichenfolge.

**key** Der AES-Verschlüsselungsschlüssel wird in Base 64: 256 Bit kodiert, wenn die Schlüssellänge 32 beträgt; 192 Bit, wenn die Schlüssellänge 24 beträgt; 128 Bit, wenn die Schlüssellänge 16 beträgt oder wenn kein Schlüssel angegeben ist.

**useSalt** Verwenden Sie ein Salz der zu verschlüsselnden Daten. Standardmäßig „true“.

## Rückgabewert

Gibt die verschlüsselte Zeichenfolge zurück.

## Bemerkungen

Die Verschlüsselung erfolgt nach folgender Methode:

* Der Unicode-String wird in einen UTF-8-String umgewandelt.
* Am Ende wird ein Häkchen hinzugefügt.
* Diese Zeichenfolge wird mit dem AES-Algorithmus im CBC-Modus (Cipher Block Chaining) mit einem Null-Initialisierungsvektor verschlüsselt. Wenn kein Schlüssel als Parameter angegeben wird, wird der Instanzschlüssel verwendet.
* Der verschlüsselte Block wird dann in Base 64 konvertiert.

Die Entschlüsselung erfolgt mit der Funktion [decryptString](f-decryptstring.md).

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

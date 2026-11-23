---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 7%
---
# MemoryBuffer (Klasse)

Stellt einen im Speicher gespeicherten binären Inhalt dar.

Ein ist ein Zwischenobjekt zum Bearbeiten von Daten in eine und aus einer Datei.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [dispose](m-memorybuffer-dispose.md) | Gibt die vom -Objekt verwendeten Ressourcen frei. |
| [LOAD](m-memorybuffer-load.md) | Lädt den Inhalt einer Datei in den Puffer. |
| [Speichern](m-memorybuffer-save.md) | Speichert den Inhalt des Puffers in eine Datei. |
| [toXML](m-memorybuffer-toxml.md) | Gibt ein XML-JavaScript-Objekt zurück, das aus dem Inhalt von [MemoryBuffer“ abgerufen ](c-memorybuffer.md). Diese Funktion ist veraltet. Verwenden Sie [toDocument()](m-memorybuffer-todocument.md) |
| [toDocument](m-memorybuffer-todocument.md) | Gibt ein XML-Dokument aus dem Textinhalt dieses Puffers zurück. |
| [toString](m-memorybuffer-tostring.md) | Gibt den Inhalt des [MemoryBuffer](c-memorybuffer.md) in Form einer Zeichenfolge zurück. |
| [fromString](m-memorybuffer-fromstring.md) | Lädt den Inhalt einer Zeichenfolge in den Puffer. |
| [toBase64](m-memorybuffer-tobase64.md) | Konvertiert den Puffer oder einen Teil des in Base 64 kodierten Strings. |
| [appendBase64](m-memorybuffer-appendbase64.md) | Fügt Daten aus einer in Base 64 kodierten Zeichenfolge an das Ende des Puffers an. |
| [removeAll](m-memorybuffer-removeall.md) | Leert den Puffer. |
| [SHA1](m-memorybuffer-sha1.md) | Berechnet die SHA-1-Signatur des MemoryBuffer-Inhalts. |
| [SHA224](m-memorybuffer-sha224.md) | Berechnet die SHA-2-224-Bit-Signatur des MemoryBuffer-Inhalts. |
| [SHA256](m-memorybuffer-sha256.md) | Berechnet die 256-Bit-Signatur des MemoryBuffer-Inhalts von SHA-2. |
| [SHA384](m-memorybuffer-sha384.md) | Berechnet die SHA-2-384-Bit-Signatur des MemoryBuffer-Inhalts. |
| [SHA512](m-memorybuffer-sha512.md) | Berechnet die SHA-2-512-Bit-Signatur des MemoryBuffer-Inhalts. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | Lädt den Inhalt einer hexadezimalen Zeichenfolge in den Puffer. |
| [toHexString](m-memorybuffer-tohexstring.md) | Konvertiert den Puffer in eine Zeichenfolge mit Hexadezimalzeichen. |
| [HMAC](m-memorybuffer-hmac.md) | Berechnet den MD5-, SHA-1- oder SHA-256-Hash des Puffers. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [size](p-memorybuffer-size.md) | Gibt die Größe des Puffers in Byte zurück. |
| [isEmpty](p-memorybuffer-isempty.md) | Gibt „true“ zurück, wenn der Puffer leer ist. |

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

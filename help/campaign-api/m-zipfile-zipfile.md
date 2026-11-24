---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 25%
---
# Zip-Datei

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Erstellt ein neues ZIP-Objekt, das mit einer Datei verknüpft ist.

```text
ZipFile (filename)
```

## Parameter

**filename** Der Name des zu ladenden oder zu erstellenden Archivs.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## Funktionen

**Methode der Klasse:** [ZipFile](c-zipfile.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

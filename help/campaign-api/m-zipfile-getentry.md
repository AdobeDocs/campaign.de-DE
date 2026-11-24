---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 16%
---
# getEntry

Extrahiert eine Datei aus dem Archiv.

```text
getEntry (filename)
```

## Parameter

**filename** Name der Datei im Archiv.

## Rückgabewert

Der ⌐ [MemoryBuffer](c-memorybuffer.md), der den Inhalt der Datei enthält.

## Bemerkungen

Das Archiv muss mit der Methode ⌐[open()](m-zipfile-open.md) geöffnet worden sein, bevor diese Methode verwendet werden kann. Andernfalls wird eine Ausnahme ausgelöst. Beispiel: Im folgenden Beispiel wird die Datei dir/content.xml aus einem Archiv extrahiert und im Ordner /tmp/ gespeichert.

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
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

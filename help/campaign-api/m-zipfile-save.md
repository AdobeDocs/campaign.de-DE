---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 18%
---
# speichern

Speichert das Archiv.

```text
save ( [filename ] [, overwrite ])
```

## Parameter

**filename** Name des Archivs. Wenn der Name nicht angegeben oder leer ist, wird das Archiv unter seinem ursprünglichen Namen gespeichert.

**Überschreiben** Bei „false“ wird das Archiv nicht gespeichert, wenn bereits eine Datei mit diesem Namen vorhanden ist, und es wird eine Ausnahme ausgelöst.

## Rückgabewert

Keine.

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

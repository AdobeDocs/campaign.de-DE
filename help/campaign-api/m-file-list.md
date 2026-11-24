---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 17%
---
# auflisten

Listet den Inhalt eines Verzeichnisses auf.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## Parameter

**mask** Die Suchmaske (\* standardmäßig).

**sort** true, um das Ergebnis zu sortieren (standardmäßig false).

**noCase** true, um die Klasse beim Sortieren zu ignorieren (standardmäßig false).

## Rückgabewert

Eine Tabelle mit der Liste der Dateien ( [Datei](c-file.md) ), die dem angegebenen Pfad und der angegebenen Maske entsprechen.

## Bemerkungen

Der Verzeichnisname muss unter Linux mit &quot;/&quot; und unter Windows mit &quot;\\&quot; enden. Beispiel:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
```

## Funktionen

**Methode der Klasse:** [File](c-file.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

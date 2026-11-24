---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 7%
---
# Datei (Klasse)

Dateiklasse

> Warnung:
>
> Der Zugriff über Datei-APIs ist auf die **var**, **sftp** und temporären Ordner von Adobe Campaign beschränkt.

Im Folgenden finden Sie ein Beispiel für die Verwendung der -Klasse zum Lesen und Verarbeiten aller Zeilen einer Datei nacheinander.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [Datei](m-file-file.md) | Erstellt ein neues Objekt, das mit einer Datei verknüpft ist. |
| [Schließen](m-file-close.md) | Schließt die Datei. |
| [copyTo](m-file-copyto.md) | Kopiert eine Datei. |
| [dispose](m-file-dispose.md) | Gibt die vom -Objekt verwendeten Ressourcen frei. |
| [flush](m-file-flush.md) | Erzwingt das Schreiben auf die Disc |
| [list](m-file-list.md) | Listet den Inhalt eines Verzeichnisses auf. |
| [mkdir](m-file-mkdir.md) | Erstellt ein Verzeichnis mit dem Pfad des aktuellen [Datei](c-file.md)-Objekts. |
| [Öffnen](m-file-open.md) | Öffnet die Datei im Lese- oder Schreibmodus. |
| [Entfernen](m-file-remove.md) | Löscht die Datei. |
| [renameTo](m-file-renameto.md) | Benennt eine Datei um. |
| [READLN](m-file-readln.md) | Liest eine Zeile der Textdatei. |
| [rmdir](m-file-rmdir.md) | Löscht das Verzeichnis (nicht kaskadierend). |
| [writeln](m-file-writeln.md) | Schreibt eine Textzeile in die Datei. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [canRead](p-file-canread.md) | Gibt „true“ zurück, wenn die Datei gelesen werden kann. |
| [canWrite](p-file-canwrite.md) | Gibt „true“ zurück, wenn die Datei geändert werden kann. |
| [vorhanden](p-file-exists.md) | Gibt „true“ zurück, wenn eine Datei oder ein Ordner mit diesem Namen vorhanden ist. |
| [fullName](p-file-fullname.md) | Gibt den Namen der Datei in absoluten Zahlen zurück. |
| [isDirectory](p-file-isdirectory.md) | Gibt „true“ zurück, wenn die Datei ein Verzeichnis ist. |
| [isFile](p-file-isfile.md) | Gibt „true“ zurück, wenn die Datei vorhanden und eine Datei ist. |
| [isOpen](p-file-isopen.md) | Gibt „true“ zurück, wenn die Datei geöffnet ist. |
| [lastModified](p-file-lastmodified.md) | Gibt das letzte Änderungsdatum in Form eines Date -Objekts zurück. |
| [name](p-file-name.md) | Gibt den Namen der Datei mit der Erweiterung zurück, jedoch ohne Pfad. |
| [path](p-file-path.md) | Gibt den vollständigen Pfad der Datei zurück, die durch das Trennzeichen beendet wird. |
| [size](p-file-size.md) | Gibt die Größe der Datei in Byte zurück. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow

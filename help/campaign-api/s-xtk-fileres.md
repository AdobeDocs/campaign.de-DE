---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 56%
---
# fileRes

Auf dem Server oder in der Datenbank gespeicherte Dateiressource

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [FilePublishing](sm-fileres-filepublishing.md) | Veröffentlicht die öffentlichen Ressourcen auf den Frontservern |
| [GetPublicFileResURL](sm-fileres-getpublicfileresurl.md) | Wiederherstellung der URL der Datei |
| [GetServerFileName](sm-fileres-getserverfilename.md) | Gibt den Dateinamen auf dem Server aus, welcher zuvor, wenn nötig, in das Upload-Verzeichnis kopiert wurde. |
| [GetURL](sm-fileres-geturl.md) | Ausgabe der Dateizugangs-URL |
| [PostUpload](sm-fileres-postupload.md) | Abschließende Speicherung einer Ressource nach dem Upload auf den Server in Abhängigkeit vom definierten Speichertyp. |
| [PreDownload](sm-fileres-predownload.md) | Bereitet den Download der Ressource in Abhängigkeit vom definierten Speichertyp vor. |
| [publishIfNeeded](sm-fileres-publishifneeded.md) | Kopiert die Datei, wenn nötig, auf die Mediaserver |
| [PublishIfNeededFromId](sm-fileres-publishifneededfromid.md) | Kopiert die Datei, wenn nötig, ausgehend von der Ressourcen-Kennung auf die Mediaserver |
| [WebPostUpload](sm-fileres-webpostupload.md) | Abschließendes Speichern der Ressource nach dem Upload (von einer Web-Seite) auf den Server in Abhängigkeit vom verwendeten Speichertyp. Ruft die Codepage und den Inhaltstyp ab. |

## Generische Methoden

| Methode | Beschreibung |
| --- | --- |
| [Erstellen](f-create.md) | Erstellt eine neue Entität, die einem bestimmten Schema entspricht. |
| [LOAD](f-load.md) | Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück. |
| [Speichern](m-entity-save.md) | Speichert eine Entität in der Datenbank |

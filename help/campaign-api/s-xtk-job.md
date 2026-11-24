---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 59%
---
# job

Auf dem Anwendungs-Server durchgeführte Batch-Aufträge

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [Rückgängig](sm-job-cancel.md) | Bricht einen Auftrag ab |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | Prüft, ob der Auftrag in Gang ist |
| [Ausführen](sm-job-execute.md) | Führt einen Auftrag synchron aus (in diesem Modus sind keine Informationen über den Fortschritt verfügbar und der Abbruch ist nicht möglich). |
| [FilesExist](sm-job-filesexist.md) | Prüft, ob Dateien bereits auf dem Server (oder in der Ressourcen-Tabelle) existieren. |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | Ausgabe der laufenden, nicht externen Aufträge |
| [GetStatus](sm-job-getstatus.md) | Abrufen von Informationen zum Verarbeitungsfortschritt. Warnung: Diese API garantiert nicht, dass eine Liste eindeutiger Protokolleinträge zurückgegeben wird (der Aufrufer muss sie mithilfe seiner ID deduplizieren). |
| [HasWarning](sm-job-haswarning.md) | Fragt ab, ob für einen Auftrag Warnhinweise oder Fehler erzeugt wurden. |
| [Aussetzen](sm-job-pause.md) | Auftrag aussetzen |
| [Senden](sm-job-submit.md) | Unterbreitet einen Auftrag für eine asynchrone Ausführung |
| [SubmitFromModel](sm-job-submitfrommodel.md) | Unterbreitet einen Auftrag von einer Vorlage ausgehend |
| [SubmitSoapCall](sm-job-submitsoapcall.md) | Unterbreitet einen Auftrag für eine asynchrone Ausführung |
| [WaitJobCancelled](sm-job-waitjobcancelled.md) | Wartet, bis der Abbruch eines Auftrags effektiv ist |

## Generische Methoden

| Methode | Beschreibung |
| --- | --- |
| [Erstellen](f-create.md) | Erstellt eine neue Entität, die einem bestimmten Schema entspricht. |
| [LOAD](f-load.md) | Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück. |
| [Speichern](m-entity-save.md) | Speichert eine Entität in der Datenbank |

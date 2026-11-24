---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%
---
# Workflow

Definition der Workflows

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [Bereinigung](sm-workflow-cleanup.md) | Löscht den Verlauf eines Workflows. |
| [DeleteResult](sm-workflow-deleteresult.md) | Löscht die Ergebnisse von einer oder mehreren Aktivitäten. |
| [Ausführen](sm-workflow-execute.md) | Führt den Workflow sofort aus und wartet auf seinen Abschluss. |
| [ExecuteInstance](sm-workflow-executeinstance.md) | Führt den Workflow sofort aus und wartet auf seinen Abschluss. |
| [GetLogin](sm-workflow-getlogin.md) | Gibt die Informationen des Ausführungskontos aus. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | Gibt die Parameter einer laufenden Workflow-Aufgabe aus |
| [Töten](sm-workflow-kill.md) | Stoppt einen Workflow bedingungslos. |
| [Aussetzen](sm-workflow-pause.md) | Setzt die Ausführung eines laufenden Workflows aus. |
| [PostEvent](sm-workflow-postevent.md) | Erzeugt ein Ereignis basierend auf einer beliebigen Aktivität. |
| [Antwort](sm-workflow-reply.md) | Antwortet auf eine laufende Aufgabe vom Typ Validierung. |
| [Neu starten](sm-workflow-restart.md) | Verknüpft einen Workflow-Stopp und einen Workflow-Start. |
| [RestartTask](sm-workflow-restarttask.md) | Erzwingt den Neustart einer oder mehrerer abgeschlossener Aufgaben. |
| [SetLogin](sm-workflow-setlogin.md) | Ändert das Ausführungskonto. |
| [Simulieren](sm-workflow-simulate.md) | Startet einen Workflow im Simulationsmodus. |
| [SimulateWithParameters](sm-workflow-simulatewithparameters.md) | Startet einen Workflow im Simulationsmodus unter Übermittlung von Parametern. |
| [laichen](sm-workflow-spawn.md) | Erstellt eine auf einer Vorlage basierende Workflow-Instanz, führt einen Patch durch und startet den Workflow. |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | Erstellt eine auf einer Vorlage basierende Workflow-Instanz und ruft die Methode [StartWithParameters](sm-workflow-startwithparameters.md) für diese Instanz auf. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | Erstellt eine auf einem Modell basierende Workflow-Instanz und ruft die Methode [StartWithParameters](sm-workflow-startwithparameters.md) oder [SimulateWithParameters](sm-workflow-simulatewithparameters.md) für diese Instanz auf. |
| [Starten](sm-workflow-start.md) | Startet einen Workflow oder nimmt ihn wieder auf. |
| [startWithParameters](sm-workflow-startwithparameters.md) | Startet einen Workflow unter Übermittlung von Parametern |
| [Anhalten](sm-workflow-stop.md) | Hält einen laufenden Workflow an. |
| [WakeUp](sm-workflow-wakeup.md) | Zieht die Ausführung aller ausstehenden Aufgaben vor. |
| [WakeupTask](sm-workflow-wakeuptask.md) | Zieht die Ausführung einer ausstehenden oder mehrerer ausstehender Aufgaben vor. |

## Generische Methoden

| Methode | Beschreibung |
| --- | --- |
| [Erstellen](f-create.md) | Erstellt eine neue Entität, die einem bestimmten Schema entspricht. |
| [LOAD](f-load.md) | Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück. |
| [Speichern](m-entity-save.md) | Speichert eine Entität in der Datenbank |

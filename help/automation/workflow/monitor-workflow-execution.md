---
product: campaign
title: Überwachen der Workflow-Ausführung
description: Überwachen der Workflow-Ausführung
feature: Workflows
role: Admin
exl-id: bc13d706-7888-42eb-9116-5538e68cd515
source-git-commit: a78019d11a0a2acbd8c0d9ba7c2082c09f90356c
workflow-type: ht
source-wordcount: '2006'
ht-degree: 100%

---

# Überwachen der Workflow-Ausführung {#monitoring-workflow-execution}

Dieser Abschnitt enthält Informationen zur Überwachung der Ausführung Ihrer Workflows.

Ein Anwendungsbeispiel zum Erstellen eines Workflows, mit dem Sie den Status einer Reihe von Workflows überwachen können, die „ausgesetzt“, „angehalten“ oder „Mit Fehlern“ sind, finden Sie zudem in [diesem Abschnitt](workflow-supervision.md#supervising-workflows).

Darüber hinaus können Administratoren der Instanz das **Audit-Protokoll** verwenden, um Aktivitäten und letzte Änderungen an Workflows und somit den Zustand Ihrer Workflows zu überprüfen. Weitere Informationen zum Audit-Protokoll finden Sie auf [dieser Seite](../../v8/reporting/audit-trail.md){target="_blank"}.

## Fortschritt anzeigen {#displaying-progress}

Die Ausführung des Workflows kann am Bildschirm verfolgt werden.

Wenn Sie auf das Symbol **[!UICONTROL Fortschritt anzeigen]** klicken, werden Workflow-Ausführung, -Status und Ergebnis der Aktivitäten am Bildschirm dargestellt.

![](assets/s_user_segmentation_toolbar_progr.png)

In diesem Fall erscheinen laufende Aktivitäten in Blau, ausstehende Aktivitäten blinken und Warnhinweise und Fehler werden in Orange bzw. Rot angezeigt. Des Weiteren werden auf den ausgehenden Transitionen die Ergebnisse der Aktivitäten eingeblendet, gefolgt vom in der Aktivität definierten Ergebnistitel sowie der Ausführungsdauer, wenn sie mehr als eine Sekunde beträgt.

![](assets/s_user_segmentation_results.png)

## Protokoll anzeigen {#displaying-logs}

Das Protokoll enthält den Verlauf der Workflow-Ausführung. Es speichert die von den Benutzern angeforderten Befehle, ausgeführte Vorgänge und aufgetretene Fehler. Sie haben die Möglichkeit:

* im Tab **[!UICONTROL Verfolgung]** das Workflow-Protokoll einzusehen.

  ![](assets/new-workflow-display-log-tab.png)

* Filtern Sie die Protokollnachrichten nach Aktivität. Klicken Sie dazu auf **[!UICONTROL Aufgaben und Protokoll anzeigen]** in der Symbolleiste über dem Diagramm, um die Registerkarten **[!UICONTROL Protokoll]** und **[!UICONTROL Aufgaben]** unterhalb des Diagramms anzuzeigen. Wählen Sie eine Aktivität aus, um alle zugehörigen Nachrichten anzuzeigen. Diese Liste enthält alle Nachrichten, wenn keine Aktivität ausgewählt ist.

  ![](assets/new-workflow-display-log-activity.png)

  >[!NOTE]
  >
  >Durch Klicken auf den Diagrammhintergrund werden alle Markierungen entfernt.

* Sie können entscheiden, nur die Nachrichten anzuzeigen, die mit einer bestimmten Aufgabe verknüpft sind. Wählen Sie dazu zunächst die Registerkarte **[!UICONTROL Aufgaben]** und anschließend eine Aktivität im Diagramm aus, um die Liste einzuschränken. Doppelklicken Sie auf eine Aufgabe, um die Informationen anzuzeigen. Die letzte Registerkarte im Fenster enthält das Protokoll.

  ![](assets/new-workflow-display-tasks-activity.png)

  Durch Klicken auf die Schaltfläche **[!UICONTROL Details...]** können Sie zusätzliche Informationen bezüglich der Aktivitätsausführung einsehen. Beispielsweise erscheinen hier die validierende Person und gegebenenfalls der Kommentar, den diese eingegeben hat.

>[!NOTE]
>
>Das Protokoll wird bei einem Neustart des Workflows nicht bereinigt. Alle Nachrichten werden beibehalten. Sollten Sie die Nachrichten einer früheren Ausführung nicht beibehalten wollen, müssen Sie den Verlauf bereinigen.

Die Nachrichten bezüglich der Ausführung der Workflow-Aktivitäten werden im Protokoll in chronologischer Reihenfolge aufgelistet.

* Protokoll einer Zielgruppenbestimmung

  Klicken Sie nach einer Zielgruppenbestimmung auf den Tab **[!UICONTROL Verfolgung]**, um die einzelnen Schritte der Ausführung nachzuvollziehen.

  ![](assets/s_user_segmentation_journal.png)

  Alle Vorgänge, Warnhinweise und Fehler werden protokolliert.

* Protokoll einer Aktivität

  Auch die Ausführung von Aktivitäten wird detailliert protokolliert. Sie haben zwei Möglichkeiten, die Nachrichten einzusehen:

   1. Markieren Sie die gewünschte Aktivität und klicken Sie auf die Schaltfläche **[!UICONTROL Aufgaben und Protokoll anzeigen]**.

      ![](assets/s_user_segmentation_show_logs.png)

      Unter dem Diagramm erscheinen nun die Tabs Protokoll und Aufgaben.

      Die Markierung einer Aktivität im Diagramm arbeitet wie ein Filter in Bezug auf das Protokoll und die Aufgabenliste.

      ![](assets/s_user_segmentation_logs.png)

   1. Klicken Sie mit der rechten Maustaste auf die gewünschte Aktivität und wählen Sie die Option **[!UICONTROL Protokoll anzeigen]**.

      ![](assets/s_user_segmentation_logs_menu.png)

      Das Protokoll öffnet sich in einem separaten Fenster.

## Verläufe bereinigen {#purging-the-logs}

Workflow-Verläufe werden nicht automatisch bereinigt: Alle Nachrichten werden standardmäßig beibehalten. Der Verlauf kann über das Menü **[!UICONTROL Datei > Aktionen]** oder durch Klicken auf die Schaltfläche **[!UICONTROL Aktionen]** in der Symbolleiste oberhalb der Liste bereinigt werden. Wählen Sie **[!UICONTROL Verlauf bereinigen]** aus. Die im Menü **[!UICONTROL Aktionen]** verfügbaren Optionen werden im Abschnitt [Aktionen-Symbolleiste](start-a-workflow.md) beschrieben.

![](assets/purge_historique.png)

## Arbeitstabellen und Workflow-Schemata {#worktables-and-workflow-schema}

Workflows verwenden diverse Arbeitstabellen, die mithilfe bestimmter Aktivitäten bearbeitet werden können. Adobe Campaign bietet über Data-Management-Aktivitäten die Möglichkeit, Spalten aus Workflow-Arbeitstabellen umzuwandeln, umzubenennen oder anzureichern. Auf diese Weise können beispielsweise Nomenklaturen angepasst oder zusätzliche Informationen erhoben werden.

Es ist des Weiteren möglich, Relationen zwischen verschiedenen Arbeitsdimensionen herzustellen und Dimensionswechsel zu definieren. So können Sie beispielsweise festlegen, dass Kommunikationen an den Beitragszahler einer Police gerichtet werden, dabei aber die Daten des Mitversicherten in den Zusatzinformationen zu berücksichtigen sind.

Die Arbeitstabellen des Workflows werden automatisch gelöscht, wenn der Workflow passiviert. Wenn Sie eine Arbeitstabelle beibehalten möchten, speichern Sie sie über die Aktivität **[!UICONTROL Listen-Update]** in einer Liste (siehe [Listen-Update](list-update.md)).

## Fehler beheben {#managing-errors}

Wenn ein Fehler auftritt, wird der Workflow ausgesetzt und die bei Fehlerauftritt ausgeführte Aktivität blinkt rot. In der Workflow-Übersicht können Sie über den Link **[!UICONTROL Workflows]** im Tab **[!UICONTROL Monitoring]** wie unten dargestellt nur Workflows mit Fehlern anzeigen.

![](assets/wf-global-view_filter_only_errors.png)

Im Explorer enthält die Listenansicht der Workflows standardmäßig die Spalte **[!UICONTROL Fehlgeschlagen]**.

![](assets/wf-explorer_errors_col.png)

Wenn ein Workflow fehlerhaft ist, werden die zur Workflow-Überwachungsgruppe gehörenden Benutzenden per E-Mail benachrichtigt, sofern ihre E-Mail-Adresse in ihrem Profil angegeben ist. Diese Gruppe ist im Feld **[!UICONTROL Verantwortliche(r)]** der Workflow-Eigenschaften ausgewählt.

![](assets/wf-properties_select-supervisors.png)

Der Benachrichtigungsinhalt wird in der Standardvorlage **[!UICONTROL Benachrichtigung des Workflow-Verantwortlichen]** konfiguriert, welche im Tab **[!UICONTROL Ausführung]** der Workflow-Eigenschaften ausgewählt werden kann. Die Benachrichtigung enthält den Namen des fehlgeschlagenen Workflows und die vom Fehler betroffene Aufgabe.

Beispiel einer Benachrichtigung:

![](assets/wf-notification_error-msg.png)

Über den Link können Sie im Web-Modus auf die Client-Konsole in Adobe Campaign zugreifen. Nach Anmeldung können Sie dann den fehlgeschlagenen Workflow bearbeiten.

![](assets/wf-notification_error-console.png)

Es besteht die Möglichkeit, das Aussetzen des Workflows im Falle von Fehlern zu vermeiden und die sich anschließenden Aufgaben wie geplant auszuführen. Bearbeiten Sie dazu den Workflow **[!UICONTROL Eigenschaften]** und wählen Sie im Abschnitt **[!UICONTROL Umgang mit Fehlern]** die Option **[!UICONTROL Ignorieren]** im Feld **[!UICONTROL Bei Fehler]** aus. Sie können dann die Anzahl der aufeinanderfolgenden Fehler angeben, die ignoriert werden können, bevor der Prozess angehalten wird.

In diesem Fall wird die fehlerhafte Aufgabe abgebrochen. Dieser Modus ist insbesondere bei Workflows mit wiederkehrenden Aktionen angebracht, die darauf ausgelegt sind, die Kampagne zu einem späteren Zeitpunkt erneut zu starten.

![](assets/wf_edit_properties_for_error_mgt.png)

>[!NOTE]
>
>Es besteht die Möglichkeit, diese Vorgehensweise individuell für jede Aktivität zu konfigurieren. Bearbeiten Sie dazu die Aktivitätseigenschaften und wählen Sie den Modus „Umgang mit Fehlern“ auf der Registerkarte **[!UICONTROL Erweitert]** aus.

## Fehler verarbeiten {#processing-errors}

Auf Aktivitätsniveau erscheint im Falle von Fehlern eine zusätzliche Transition, wenn die Option **[!UICONTROL Fehler verarbeiten]** aktiviert wurde. Auf diese Weise wird der Workflow nicht ausgesetzt, sondern bis zum Ende ausgeführt.

Dies gilt für Fehler des Dateisystems (Datei kann nicht verschoben werden, Zugriff auf das Verzeichnis nicht möglich usw.).

Fehler, die aus der Konfiguration der Aktivität resultieren, d. h. ungültige Werte (z. B. inexistentes Verzeichnis), aktivieren die zusätzliche Transition nicht.

Die Ausführung eines - manuell oder aufgrund eines Fehlers - ausgesetzten Workflows kann mithilfe der Schaltfläche **[!UICONTROL Starten]** dort wieder aufgenommen werden, wo sie unterbrochen wurde. Die fehlerhafte oder ausgesetzte Aktivität wird erneut ausgeführt, nicht jedoch die vorangehenden Aktivitäten.

Verwenden Sie die Schaltfläche **[!UICONTROL Neu starten]**, um alle Workflow-Aktivitäten erneut auszuführen.

Änderungen an bereits ausgeführten Aktivitäten werden somit nicht berücksichtigt, wenn die Workflow-Ausführung wiederaufgenommen wird.

Änderungen an noch nicht ausgeführten Aktivitäten werden jedoch berücksichtigt, wenn die Workflow-Ausführung wiederaufgenommen wird.

Änderungen an der ausgesetzten Aktivität werden bei der Wiederaufnahme der Workflow-Ausführung unter Umständen nicht korrekt berücksichtigt.

Es wird daher empfohlen, die Workflow-Ausführung nach Änderungen komplett neu zu starten.

## Instanz-Monitoring {#instance-supervision}

Die Seite **[!UICONTROL Instanz-Monitoring]** bietet die Möglichkeit, den Adobe Campaign-Server zu überwachen. Sie enthält die Liste fehlgeschlagener Workflows und Sendungen.

Auf diese Seite können Sie über den Tab **[!UICONTROL Monitoring]** zugreifen. Klicken Sie auf die Schaltfläche **[!UICONTROL Übersicht]**.

![](assets/wf-monitoring_from-homepage.png)

Um nur die fehlgeschlagenen Workflows anzuzeigen, klicken Sie auf die Schaltfläche **[!UICONTROL Workflows]** und wählen Sie aus der Dropdown-Liste den Status aus.

![](assets/wf-monitoring_edit-wf.png)

Durch Klick auf den Namen eines Workflows öffnet sich dieser und Sie können das Protokoll einsehen.

![](assets/wf-monitoring_edit-task-wf.png)

## Mehrere gleichzeitige Ausführungen verhindern {#preventing-simultaneous-multiple-executions}

Ein einzelner Workflow kann mehrere gleichzeitig ablaufende Ausführungen enthalten. In manchen Situationen sollte dies verhindert werden.

Beispielsweise könnte die Workflow-Ausführung stündlich ausgelöst werden, manchmal aber länger als eine Stunde dauern. Wenn der Workflow bereits ausgeführt wird, ist es empfehlenswert, den Start einer weiteren Ausführung zu überspringen.

Wenn vor dem Beginn eines Workflows eine Signalaktivität erfolgt und der Workflow bereits läuft, sollte das Signal übersprungen werden.

Allgemein gilt:

![](assets/workflow-reentrancy-protection-principle.png)

In dieser Situation wird eine Instanzvariable verwendet, die für alle parallelen Ausführungen von Workflows gültig ist.

Hier ist ein einfacher Test-Workflow:

![](assets/wkf_simultaneous_execution1.png)

Die **[!UICONTROL Planung]** löst jede Minute ein Ereignis aus. Mit der folgenden **[!UICONTROL Test-Aktivität]** wird die Instanzvariable **isRunning** getestet, um zu entscheiden, ob die Ausführung fortgesetzt werden soll oder nicht:

![](assets/wkf_simultaneous_execution2.png)

>[!NOTE]
>
>**isRunning** ist eine für dieses Beispiel ausgewählte Variable, und keine integrierte Variable.

In der Aktivität, die unmittelbar auf **[!UICONTROL Test]** im Zweig **yes** folgt, muss die Instanzvariable im **Initialisierungsscript** auf true gesetzt werden:

```
instance.vars.isRunning = true
```

In der letzten Aktivität im Zweig **yes** muss die Variable in im **Initialisierungsscript** wieder auf false gesetzt werden:

```
instance.vars.isRunning = false
```

Bitte beachten Sie Folgendes:

* Den aktuellen Wert der Instanzvariable können Sie im Tab **Variablen** im Workflow **Eigenschaften** prüfen.
* Beim erneuten Start eines Workflows werden die Instanzvariablen zurückgesetzt.
* In JavaScript ist ein nicht definierter Wert in einem Test auf false gesetzt. Dadurch kann die Instanzvariable noch vor ihrer Initialisierung geprüft werden.
* Sie können die aufgrund dieses Mechanismus nicht verarbeiteten Aktivitäten überwachten, indem Sie dem Initialisierungsscript des &quot;Nein&quot;-Zweigs eine Protokollierungsanweisung hinzufügen.

  ```
  logInfo("Workflow already running, parallel execution not allowed.");
  ```

Im Abschnitt [Datenaktualisierungen koordinieren](coordinate-data-updates.md) wird ein Anwendungsbeispiel vorgestellt.

## Wartung der Datenbank {#database-maintenance}

Workflows verwenden zahlreiche Arbeitstabellen, die Speicherplatz belegen und die gesamte Plattform verlangsamen, wenn sie nicht gewartet werden.

Der Workflow **Datenbankbereinigung**, auf den Sie über den Knoten **Administration > Produktion > Technische Workflows** zugreifen können, ermöglicht das Löschen veralteter Daten, um das exponentielle Anwachsen der Datenbank zu verhindern. Der Workflow wird automatisch ohne das Eingreifen der benutzenden Person ausgelöst.

Sie können auch spezifische technische Workflows erstellen, um unnötige Daten zu entfernen, die Speicherplatz belegen. Näheres dazu finden Sie in diesem [Abschnitt](#purging-the-logs).

## Handhaben von ausgesetzten Workflows {#handling-of-paused-workflows}

Die Arbeitstabellen ausgesetzter Workflows werden standardmäßig nie bereinigt. Ab Build 8880 werden Workflows, die zu lange in einem ausgesetzten Zustand angehalten werden, automatisch gestoppt und deren Arbeitstabellen bereinigt. Dieses Verhalten wird wie folgt ausgelöst:

* Sind Workflows länger als sieben Tage ausgesetzt, erscheint ein Warnhinweis im Monitoring-Dashboard (und in der Monitoring-API) und es wird eine Benachrichtigung an die Supervisoren-Gruppe gesendet.
* Dasselbe passiert jede Woche, wenn der technische Workflow **[!UICONTROL cleanupPausedWorkflows]** ausgelöst wird. Weitere Informationen zum Workflow finden Sie in [diesem Abschnitt](delivery.md).
* Nach vier Benachrichtigungen (d. h. standardmäßig nach einem Monat im ausgesetzten Zustand) wird der Workflow bedingungslos gestoppt. Ein Protokoll wird im Workflow angezeigt, nachdem er angehalten wurde. Die Tabellen werden bei der nächsten Ausführung des Workflows **[!UICONTROL Bereinigung]** bereinigt

Diese Zeiträume können mit der Option NmsServer_PausedWorkflowPeriod konfiguriert werden.

Die Verantwortlichen des Workflows sowie der Ersteller und der letzte Benutzer, der den Workflow modifiziert hat, werden benachrichtigt. Administratoren erhalten keine Benachrichtigung.

## Filtern von Workflows nach ihrem Status{#filtering-workflows-status}

Mit der Oberfläche von Campaign Classic können Sie den Ausführungsstatus aller Workflows in Ihrer Instanz mithilfe vordefinierter **Ansichten** überwachen. Um auf diese Ansichten zuzugreifen, öffnen Sie den Knoten **[!UICONTROL Administration]** / **[!UICONTROL Verfolgung]** / **[!UICONTROL Status des Workflows]**.

Folgende Ansichten stehen zur Verfügung:

* **[!UICONTROL Wird ausgeführt]**: listet alle ausgeführten Workflows auf.
* **[!UICONTROL Ausgesetzt]**: listet alle ausgesetzten Workflows auf.
* **[!UICONTROL Fehlgeschlagen]**: listet alle fehlgeschlagenen Workflows auf.
* ** ).

![](assets/workflow-monitoring-views.png)

Standardmäßig sind diese Ansichten im Ordner **[!UICONTROL Verfolgung]** aufrufbar. Sie können sie jedoch an einer Stelle Ihrer Wahl in der Ordnerstruktur neu erstellen. Auf diese Weise sind sie für Standardbenutzer ohne Administratorrechte verfügbar.

Gehen Sie dazu wie folgt vor:

1. Klicken Sie mit der rechten Maustaste auf den Ordner, in dem Sie die Ansicht hinzufügen möchten.
1. Wählen Sie unter **[!UICONTROL Ordner hinzufügen]** / **[!UICONTROL Administration]** die Ansicht aus, die Sie hinzufügen möchten.
1. Nachdem der Ordner zum Baum hinzugefügt wurde, stellen Sie sicher, dass Sie ihn als Ansicht konfigurieren, damit alle Workflows unabhängig vom Ursprungsordner angezeigt werden. Weiterführende Informationen zum Einfügen von Ansichten finden Sie auf [dieser Seite](../../v8/audiences/folders-and-views.md#turn-a-folder-to-a-view).

Zusätzlich zu diesen Ansichten können Sie Filterordner einrichten, mit denen Sie die Liste der Workflows nach ihrem Ausführungsstatus filtern können. Gehen Sie dazu wie folgt vor:

1. Rufen Sie einen Ordner vom Typ „Workflow“ auf und wählen Sie dann das Menü **[!UICONTROL Filter]** / **[!UICONTROL Erweiterter Filter]**.
1. Konfigurieren Sie den Filter so, dass das Feld **[!UICONTROL @status]** des Workflows dem Status Ihrer Wahl entspricht.
1. Speichern und benennen Sie den Filter. Er ist dann direkt in der Filterliste verfügbar.

![](assets/workflow-monitoring-filter.png)

Weitere Informationen finden Sie in den folgenden Abschnitten:

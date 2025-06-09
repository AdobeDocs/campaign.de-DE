---
product: campaign
title: Starten eines Workflows
description: Erfahren Sie, wie Sie einen Workflow starten, und lernen Sie die Symbolleiste sowie das Kontextmenü für Workflow-Aktionen kennen
feature: Workflows
level: Beginner
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: ht
source-wordcount: '1216'
ht-degree: 100%

---

# Starten, Pausieren und Stoppen eines Workflows {#starting-a-workflow}

Workflows werden grundsätzlich manuell gestartet, Nach dem Starten können sie jedoch inaktiv bleiben, je nachdem, welche Informationen über eine Planung (siehe [Planung](scheduler.md)) oder Aktivitätsplanung angegeben wurden.

Die mit der Workflow-Ausführung in Zusammenhang stehenden Prozesse (starten, anhalten, aussetzen etc.) laufen **asynchron** ab, d. h. der jeweilige Befehl wird gespeichert und erst dann ausgeführt, wenn ein Server verfügbar ist.

Anhand der Schaltflächen der Symbolleiste kann die Ausführung des Workflows gesteuert und überwacht werden.

Die im Menü **[!UICONTROL Aktionen]** und im Kontextmenü verfügbaren Befehle werden nachstehend erläutert.

>[!IMPORTANT]
>
>Beachten Sie: Von Benutzern angeforderte Aktionen (Workflow starten, stoppen, aussetzen usw.) werden nicht sofort ausgeführt, sondern in eine Warteschlange eingereiht und dort vom Workflow-Modul verarbeitet.

## Aktionen-Symbolleiste {#actions-toolbar}

Die Schaltfläche **[!UICONTROL Aktionen]** in der Symbolleiste bietet Zugriff auf zusätzliche Ausführungsoptionen in ausgewählten Workflows. Sie können auch das Menü **[!UICONTROL Datei > Aktionen]** verwenden oder mit der rechten Maustaste auf einen Workflow klicken und dann **[!UICONTROL Aktionen]** auswählen.

![](assets/purge_historique.png)

* **[!UICONTROL Starten]**

  Dieser Befehl startet die Ausführung eines Workflows. Sein Status wechselt von **In Bearbeitung**, **Ausgesetzt** oder **Abgeschlossen** in **Gestartet**. Die Workflow-Engine übernimmt die Ausführung des Workflows. Bei zuvor ausgesetzten Workflows wird die Ausführung an der Stelle wieder aufgenommen, wo sie ausgesetzt wurde. In den anderen Fällen starten die Workflows jeweils mit der ersten Aktivität.

  Der Start eines Workflows ist ein asynchroner Prozess, d. h. der jeweilige Befehl wird gespeichert und erst dann ausgeführt, wenn ein Server verfügbar ist.

* **[!UICONTROL Aussetzen]**

  Dieser Befehl überführt den Workflow in den Status **Ausgesetzt**. Bis zur Wiederaufnahme werden keine weiteren Aktivitäten gestartet, laufende Aktionen werden jedoch nicht unterbrochen.

* **[!UICONTROL Anhalten]**

  Dieser Befehl hält die Ausführung eines laufenden Workflows an. Der Status der Workflow-Instanz wechselt zu **Abgeschlossen**. Laufende Aktionen werden nach Möglichkeit unterbrochen. Gestartete Importe oder SQL-Abfragen werden sofort abgebrochen.

  >[!IMPORTANT]
  >
  >Das Anhalten eines Workflows ist ein asynchroner Prozess: Die Anfrage wird registriert und der oder die Workflow-Server brechen die laufenden Vorgänge ab. Das Anhalten einer Workflow-Instanz kann daher einige Zeit in Anspruch nehmen, insbesondere wenn der Workflow auf mehreren Servern ausgeführt wird, von denen jeder die laufenden Aufgaben abbrechen muss. Um Probleme zu vermeiden, warten Sie, bis der Stopp-Vorgang abgeschlossen ist, und führen Sie nicht mehrere Stopp-Anfragen für denselben Workflow durch.

* **[!UICONTROL Unbedingter Stopp]**

  Bei Auswahl dieses Befehls wechselt der Workflow-Status zu **[!UICONTROL Abgeschlossen]**. Dieser Befehl darf nur als letztes Mittel eingesetzt werden, wenn das normale Anhalten auch nach mehreren Minuten keine Wirkung zeigt. Verwenden Sie den unbedingten Stopp nur, wenn Sie sicher sind, dass der Workflow keine reellen laufenden Prozesse aufweist.

  >[!CAUTION]
  >
  >„Unbedingter Stopp“ steht nur Admins zur Verfügung.

* **[!UICONTROL Neu starten]**

  Dieser Befehl hält einen Workflow zunächst an und startet ihn dann erneut.In den meisten Fällen ermöglicht diese Vorgehensweise einen schnelleren Neustart als die separate Verwendung der Anhalten- und Starten-Schaltflächen. Dies ist insbesondere dann nützlich, wenn das Anhalten eines Workflows geraume Zeit in Anspruch nimmt, da der Befehl &quot;Starten&quot; erst wieder verfügbar ist, wenn der Workflow tatsächlich angehalten wurde.

  Beachten Sie, dass die Aktion **Neu starten** nicht die Workflow-Instanzvariablen löscht, wie dies bei den Aktionen **Ausführung**, **Stoppen** und **Start** der Fall ist (das Löschen der Instanzvariablen erfolgt bei der Aktion „Start“). Beim Neustart eines Workflows sind Instanzvariablen weiterhin für die Verwendung mit beibehaltenen Werten verfügbar. Zum Löschen haben Sie folgende Möglichkeiten:
   * Führen Sie die Aktionen **Anhalten** und **Starten** aus.
   * Fügen Sie am Ende der Workflow-Ausführung folgenden JavaScript-Code hinzu:

     ```
     var wkf = xtk.workflow.load(instance.id)
     wkf.variables='<variables/>'
     wkf.save()
     ```

* **[!UICONTROL Verlaufsbereinigung]**

  Mit dieser Aktion können Sie den Workflow-Verlauf bereinigen. Weitere Informationen finden Sie unter [Verläufe bereinigen](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Im Simulationsmodus starten]**

  Mithilfe dieses Befehls wird der Workflow im Simulationsmodus gestartet. Wenn Sie diesen Modus aktivieren, werden nur Aktivitäten ausgeführt, die keine Auswirkungen auf die Datenbank oder das Dateisystem haben (z. B. **[!UICONTROL Abfrage]**, **[!UICONTROL Vereinigung]**, **[!UICONTROL Schnittmenge]** usw.). Aktivitäten, die eine Auswirkung haben (z. B. **[!UICONTROL Export]**, **[!UICONTROL Import]** usw.), sowie die Aktivitäten danach (in derselben Verzweigung) werden nicht ausgeführt.

* **[!UICONTROL Vorgezogene Ausführung der ausstehenden Aufgaben]**

  Dieser Befehl bietet die Möglichkeit, so schnell wie möglich alle ausstehenden Aufgaben zu starten. Wenn Sie eine bestimmte Aufgabe starten möchten, klicken Sie auf die entsprechende Aktivität und wählen Sie **[!UICONTROL Aufgabe(n) jetzt bearbeiten]**.


* **[!UICONTROL Als Vorlage speichern]**

  Dieser Befehl erstellt eine neue, auf dem markierten Workflow basierende Workflow-Vorlage. Geben Sie im Feld **[!UICONTROL Ordner]** den gewünschten Speicherordner an.


## Best Practices für die Workflow-Ausführung {#workflow-execution-best-practices}

Verbessern Sie die Stabilität Ihrer Instanz, indem Sie die folgenden Best Practices beachten:

* **Es wird empfohlen, Workflows nicht öfter als alle 15 Minuten auszuführen**, da die Gesamt-Performance des Systems beeinträchtigt werden kann und Blockierungen in der Datenbank entstehen können.

* **Vermeiden Sie es, Ihre Workflows in einem angehaltenen Zustand zu belassen**. Wenn Sie einen temporären Workflow erstellen, stellen Sie sicher, dass er korrekt beendet werden kann und nicht in einem **[!UICONTROL pausierten]** Zustand bleibt. Wenn er pausiert ist, bedeutet dies nämlich, dass Sie die temporären Tabellen beibehalten müssen und somit die Größe der Datenbank erhöhen. Weisen Sie unter „Workflow-Eigenschaften“ Workflow-Verantwortliche zu, um eine Warnung zu senden, wenn ein Workflow fehlschlägt oder vom System ausgesetzt wird.

  So vermeiden Sie, dass Workflows ausgesetzt werden:

   * Prüfen Sie Ihre Workflows regelmäßig, um sicherzustellen, dass keine unerwarteten Fehler auftreten.
   * Bauen Sie Ihre Workflows möglichst einfach auf, indem Sie beispielsweise große Workflows in mehrere kleine unterteilen. Mit der Aktivität **[!UICONTROL Externes Signal]** können Sie Workflows durch andere Workflows auslösen.
   * Vermeiden Sie es, Aktivitäten mit Flüssen in Ihren Workflows zu deaktivieren, die Threads offen lassen und zu vielen temporären Tabellen führen, die viel Platz verbrauchen können. Behalten Sie in Ihren Workflows keine Aktivitäten im Status **[!UICONTROL Nicht aktivieren]** oder **[!UICONTROL Aktivieren, aber nicht ausführen]**.

* **Stoppen von nicht verwendeten Workflows**. Workflows, die weiterhin ausgeführt werden, halten Verbindungen zur Datenbank aufrecht.

* **Verwenden Sie den bedingungslosen Stopp so selten wie möglich**. Diese Option steht nur Admins zur Verfügung. Verwenden Sie diese Aktion nicht regelmäßig. Wenn Verbindungen, die von Workflows zur Datenbank erzeugt werden, nicht sauber geschlossen werden, beeinträchtigt dies die Performance.

* **Führen Sie nicht mehrere Stopp-Anfragen für denselben Workflow aus**. Das Anhalten eines Workflows ist ein asynchroner Prozess: Die Anfrage wird registriert und der oder die Workflow-Server brechen die laufenden Vorgänge ab. Das Anhalten einer Workflow-Instanz kann daher einige Zeit in Anspruch nehmen, insbesondere wenn der Workflow auf mehreren Servern ausgeführt wird, von denen jeder die laufenden Aufgaben abbrechen muss. Um Probleme zu vermeiden, warten Sie, bis der Stopp-Vorgang abgeschlossen ist, und vermeiden Sie, einen Workflow mehrmals anzuhalten.

## Kontextmenü {#right-click-menu}

Durch Markierung und Rechtsklick auf eine oder mehrere Aktivitäten eines Workflows können Sie speziell auf diese einwirken.

![](assets/contextual_menu.png)

Im Kontextmenü stehen folgende Optionen zur Verfügung:

**[!UICONTROL Öffnen...]** - ermöglicht den Zugriff auf die Eigenschaften der Aktivität.

**[!UICONTROL Protokoll anzeigen]** - zeigt das Ausführungsprotokoll der Aufgaben der ausgewählten Aktivität an. Weitere Informationen finden Sie unter [Protokoll anzeigen](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Aufgabe(n) jetzt bearbeiten]** - startet so schnell wie möglich alle ausstehenden Aufgaben der Aktivität.

**[!UICONTROL Workflow ab dieser Aufgabe neu starten]** - startet den Workflow ab der ausgewählten Aufgabe neu und verwendet dabei die durch die vorangehende Ausführung in der Aktivität gespeicherten Ergebnisse.

**[!UICONTROL Ausschneiden/Kopieren/Einfügen/Löschen]** - ermöglicht das Ausschneiden, Kopieren, Einfügen oder Löschen der ausgewählten Aktivität(en).

**[!UICONTROL Als Bild kopieren]** - erstellt einen Screenshot sämtlicher Aktivitäten des Workflows.

**[!UICONTROL Normale Ausführung/Aktivieren, aber nicht ausführen/Nicht aktivieren]** - sind auch im Tab **[!UICONTROL Erweitert]** der Aktivitätseigenschaften verfügbar. Sie werden unter [Ausführung](advanced-parameters.md#execution) ausführlich beschrieben.

**[!UICONTROL Speichern/Abbrechen]** - speichert oder verwirft die im Workflow vorgenommenen Änderungen.

>[!NOTE]
>
>Es ist möglich, mehrere Aktivitäten zu markieren, um einen der genannten Befehle auf sie anzuwenden.


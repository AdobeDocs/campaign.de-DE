---
product: campaign
title: Starten eines Workflows
description: Erfahren Sie, wie Sie einen Workflow starten, und lernen Sie die Symbolleiste sowie das Kontextmenü für Workflow-Aktionen kennen
feature: Workflows
level: Beginner
role: User, Admin
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 76%

---

# Starten, Pausieren und Stoppen eines Workflows {#starting-a-workflow}

Workflows werden grundsätzlich manuell gestartet, Nach dem Starten können sie jedoch inaktiv bleiben, je nachdem, welche Informationen über eine Planung (siehe [Planung](scheduler.md)) oder Aktivitätsplanung angegeben wurden.

Aktionen im Zusammenhang mit der Ausführung des Zielgruppen-Workflows (Start, Stopp, Pause usw.) sind **asynchron** Prozesse: Die Bestellung wird aufgezeichnet und wird wirksam, sobald der Server für die Anwendung verfügbar ist.

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

  Diese Aktion stoppt einen derzeit ausgeführten Workflow. Der Status der Instanz ist festgelegt auf **BEENDET**. Vorgänge, die gerade ausgeführt werden, werden nach Möglichkeit angehalten. Importe und SQL-Abfragen werden sofort abgebrochen.

  >[!IMPORTANT]
  >
  >Das Anhalten eines Workflows ist ein asynchroner Prozess: Die Anfrage wird registriert und der oder die Workflow-Server brechen die laufenden Vorgänge ab. Das Anhalten einer Workflow-Instanz kann daher einige Zeit in Anspruch nehmen, insbesondere wenn der Workflow auf mehreren Servern ausgeführt wird, von denen jeder die laufenden Aufgaben abbrechen muss. Um Probleme zu vermeiden, warten Sie, bis der Stopp-Vorgang abgeschlossen ist, und führen Sie nicht mehrere Stopp-Anfragen für denselben Workflow durch.

* **[!UICONTROL Unbedingter Stopp]**

  Bei Auswahl dieses Befehls wechselt der Workflow-Status zu **[!UICONTROL Abgeschlossen]**. Dieser Befehl darf nur als letztes Mittel eingesetzt werden, wenn das normale Anhalten auch nach mehreren Minuten keine Wirkung zeigt. Verwenden Sie den unbedingten Stopp nur, wenn Sie sicher sind, dass der Workflow keine reellen laufenden Prozesse aufweist.

  >[!CAUTION]
  >
  >Die Verwendung dieses Befehls sollte erfahrenen Benutzern vorbehalten bleiben.

* **[!UICONTROL Neu starten]**

  Dieser Befehl hält einen Workflow zunächst an und startet ihn dann erneut.In den meisten Fällen ermöglicht diese Vorgehensweise einen schnelleren Neustart als die separate Verwendung der Anhalten- und Starten-Schaltflächen. Dies ist insbesondere dann nützlich, wenn das Anhalten eines Workflows geraume Zeit in Anspruch nimmt, da der Befehl &quot;Starten&quot; erst wieder verfügbar ist, wenn der Workflow tatsächlich angehalten wurde.

* **[!UICONTROL Verlaufsbereinigung]**

  Mit dieser Aktion können Sie den Workflow-Verlauf bereinigen. Weitere Informationen finden Sie unter [Verläufe bereinigen](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Im Simulationsmodus starten]**

  Mit dieser Option können Sie den Workflow im Simulationsmodus und nicht im Echtmodus starten. Wenn Sie diesen Modus aktivieren, werden also nur Aktivitäten ausgeführt, die sich nicht auf die Datenbank oder das Dateisystem auswirken (z. B. **[!UICONTROL Abfrage]**, **[!UICONTROL Vereinigung]**, **[!UICONTROL Schnittmenge]** usw.). Aktivitäten, die Auswirkungen haben (z. **[!UICONTROL Export]**, **[!UICONTROL importieren]** usw.) sowie die nach ihnen (in derselben Verzweigung) werden nicht ausgeführt.

* **[!UICONTROL Vorgezogene Ausführung der ausstehenden Aufgaben]**

  Mit dieser Aktion können Sie alle ausstehenden Aufgaben so bald wie möglich starten. Um eine bestimmte Aufgabe zu starten, klicken Sie mit der rechten Maustaste auf ihre Aktivität und wählen Sie **[!UICONTROL Ausstehende Aufgabe(n) jetzt ausführen]**.


* **[!UICONTROL Als Vorlage speichern]**

  Diese Aktion erstellt eine neue Workflow-Vorlage basierend auf dem ausgewählten Workflow. Sie müssen den Ordner angeben, in dem sie gespeichert werden (in der **[!UICONTROL Ordner]** Feld ).


## Best Practices für die Workflow-Ausführung {#workflow-execution-best-practices}

Verbessern Sie die Stabilität Ihrer Instanz, indem Sie die folgenden Best Practices beachten:

* **Es wird empfohlen, Workflows nicht öfter als alle 15 Minuten auszuführen**, da die Gesamt-Performance des Systems beeinträchtigt werden kann und Blockierungen in der Datenbank entstehen können.

* **Vermeiden Sie es, Ihre Workflows in einem angehaltenen Zustand zu belassen**. Wenn Sie einen temporären Workflow erstellen, stellen Sie sicher, dass er korrekt abgeschlossen werden kann und nicht in einem Workflow verbleibt **[!UICONTROL Angehalten]** Bundesland. Wenn es angehalten wird, bedeutet dies, dass Sie die temporären Tabellen beibehalten müssen und somit die Größe der Datenbank erhöhen. Weisen Sie unter „Workflow-Eigenschaften“ Workflow-Verantwortliche zu, um eine Warnung zu senden, wenn ein Workflow fehlschlägt oder vom System ausgesetzt wird.

  So vermeiden Sie, dass Workflows ausgesetzt werden:

   * Prüfen Sie Ihre Workflows regelmäßig, um sicherzustellen, dass keine unerwarteten Fehler auftreten.
   * Halten Sie Ihre Workflows so einfach wie möglich, z. B. indem Sie große Workflows in mehrere verschiedene Workflows aufteilen. Sie können Folgendes verwenden **[!UICONTROL Externes Signal]** Aktivitäten führen Trigger zu ihrer Ausführung auf der Grundlage der Ausführung anderer Workflows aus.
   * Vermeiden Sie es, Aktivitäten mit Flüssen in Ihren Workflows zu deaktivieren, die Threads offen lassen und zu vielen temporären Tabellen führen, die viel Platz verbrauchen können. Behalten Sie in Ihren Workflows keine Aktivitäten im Status **[!UICONTROL Nicht aktivieren]** oder **[!UICONTROL Aktivieren, aber nicht ausführen]**.

* **Stoppen von nicht verwendeten Workflows**. Workflows, die weiterhin ausgeführt werden, halten Verbindungen zur Datenbank aufrecht.

* **Verwenden Sie den bedingungslosen Stopp so selten wie möglich**. Verwenden Sie diese Aktion nicht regelmäßig. Wenn Verbindungen, die von Workflows zur Datenbank erzeugt werden, nicht sauber geschlossen werden, beeinträchtigt dies die Performance.

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


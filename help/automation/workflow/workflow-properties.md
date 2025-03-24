---
product: campaign
title: Workflow-Eigenschaften
description: Erfahren Sie mehr über die Campaign-Workflow-Eigenschaften.
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: c6b4f4cee6f033218c77a495c39885e231c06126
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 87%

---

# Workflow-Eigenschaften{#workflow-properties}

## Ausführungs-Tab {#execution-tab}

Der Tab **[!UICONTROL Ausführung]** im Fenster der Workflow-**[!UICONTROL Eigenschaften]** enthält drei Bereiche:

![](assets/wf_execution_tab.png)

### Planung {#scheduler}

Dieser Bereich wird nur in Kampagnen-Workflows angezeigt.

* **[!UICONTROL Versandpriorität]**

  Die Workflow-Engine verarbeitet anstehende Workflows gemäß der in diesem Feld angegebenen Priorität. So werden beispielsweise alle Workflows mit einer **[!UICONTROL mittleren]** Priorität vor Workflows mit einer **[!UICONTROL niedrigen]** Priorität ausgeführt.

* **[!UICONTROL Ausführung auf einen Zeitpunkt mit geringer Auslastung verschieben]**

  Bei Aktivierung dieser Option wird der Workflow zu einem Zeitpunkt mit geringerer Auslastung gestartet. Gewisse Workflows können sich als sehr ressourcenintensiv für die Datenbank-Engine erweisen. Es kann daher interessant sein, weniger dringende Workflows zu einem Zeitpunkt mit geringer Auslastung, beispielsweise nachts, auszuführen. Zeiten mit geringer Auslastung werden im technischen Workflow **[!UICONTROL Kampagnenprozesse]** definiert.

### Ausführung {#execution}

* **[!UICONTROL Standard-Affinität]**

  Verwenden Sie dieses Feld, wenn Ihre Installation mehrere Workflow-Server aufweist, um festzulegen, auf welchem Server der Workflow laufen soll. Sollte der in diesem Feld angegebene Wert auf keinem Server existieren, bleibt der Workflow im Stand-by.

* **[!UICONTROL Verlaufsumfang (Tage)]**

  In den Arbeitstabellen der Datenbank werden der Ausführungsverlauf von Aufgaben und Ereignissen sowie das Protokoll gespeichert. Geben Sie hier an, wie lange der Verlauf für diesen Workflow beibehalten werden soll. Die in der Datenbank enthaltenen Bereinigungsprozesse löschen jeden Tag die obsoleten Verläufe. Bei Angabe von Null wird der Verlauf nie gelöscht.

* **[!UICONTROL SQL-Abfragen im Protokoll speichern]**

  Diese Funktion richtet sich an erfahrene Benutzer. Sie betrifft Workflows mit Zielgruppenbestimmungs-Aktivitäten (Abfrage, Vereinigung, Schnittmenge usw.). Wenn diese Option aktiviert wurde, werden die bei Ausführung des Workflows an die Datenbank gesendeten SQL-Abfragen in Adobe Campaign gespeichert. Auf diese Weise haben Sie die Möglichkeit, die Abfragen zu analysieren und eventuelle Probleme zu erkennen.

  Abfragen werden in diesem Fall in der Registerkarte **[!UICONTROL SQL-Logs]** angezeigt, die dem Workflow (außer bei Kampagnen-Workflows) und der Aktivität **[!UICONTROL Eigenschaften]** hinzugefügt wird. Die Registerkarte **[!UICONTROL Audit]** enthält auch SQL-Abfragen.

  ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL In der Engine ausführen]**

  Diese Option darf nur zur Problembehebung verwendet werden und nie im Produktionsalltag. Bei Aktivierung der Option wird der Workflow prioritär. Alle anderen Workflows werden bis zu seinem Abschluss von der Workflow-Engine angehalten.

* **[!UICONTROL Watchdog-Supervisor aktivieren, um den Workflow dauerhaft laufen zu lassen]**

  Diese Option zwingt Workflows dazu, nach einem Fehler automatisch neu zu starten. Nach der Aktivierung überprüft der Neustart alle 30 Sekunden den Status des Workflows und startet ihn bei Bedarf neu. Um das 30-Sekunden-Intervall anzupassen, können Sie die technische Option &quot;`XtkWorkflow_WatchdogRestartTimerTimeout`&quot; erstellen und einen ganzzahligen Datentyp verwenden, um die gewünschte Verzögerung anzugeben.

  >[!NOTE]
  >
  >Diese Option richtet sich an fortgeschrittene Benutzer und sollte nur für **technische Workflows** aktiviert werden.
  >
  >Sie ist standardmäßig für die zentralen Replikations-Workflows aktiviert, die mit dem Paket `fullFdaMkt`verfügbar sind.

### Umgang mit Fehlern {#error-management}

* **[!UICONTROL Fehlerbehebung]**

  In diesem Feld können Sie angeben, welche Aktion ausgeführt werden soll, wenn eine Workflow-Aufgabe einen Fehler ausgibt. Zwei Optionen stehen zur Verfügung:

   * **[!UICONTROL Prozess anhalten]**: der Workflow wird automatisch angehalten. Der Workflow-Status ändert sich in **[!UICONTROL Fehlgeschlagen]**. Sobald das Problem behoben ist, starten Sie den Workflow mit der Schaltfläche **[!UICONTROL Starten]** oder **[!UICONTROL Neustart]** erneut.
   * **[!UICONTROL Ignorieren]** - die den Fehler verursachende Aufgabe wechselt in den Status **[!UICONTROL Fehlgeschlagen]**, der Workflow behält jedoch den Status **[!UICONTROL Gestartet]**. Diese Konfiguration empfiehlt sich bei wiederkehrenden Aufgaben. Wenn der Workflow-Zweig eine Planungsaktivität enthält, löst diese automatisch zum nächsten geplanten Zeitpunkt die nächste Ausführung aus.

* **[!UICONTROL Folgefehler]**

  Dieses Feld wird verfügbar, wenn der Wert **[!UICONTROL Ignorieren]** im Feld **[!UICONTROL Bei Fehler]** ausgewählt wird. Sie können die Anzahl der Fehler angeben, die ignoriert werden können, bevor der Prozess angehalten wird. Sobald diese Zahl erreicht ist, wechselt der Workflow-Status zu **[!UICONTROL Fehlgeschlagen]**. Wenn der Wert dieses Felds 0 beträgt, wird der Workflow unabhängig von der Fehleranzahl nie angehalten.

* **[!UICONTROL Template]**

  Geben Sie in diesem Feld die Vorlage für die Benachrichtigung an, die die Workflow-Verantwortlichen erhalten, wenn ein Workflow den Status **[!UICONTROL Fehlgeschlagen]** annimmt.

  Die betroffenen Benutzenden werden per E-Mail benachrichtigt, wenn ihr Profil eine E-Mail-Adresse enthält. Um Workflow-Verantwortliche zu definieren, gehen Sie in den Eigenschaften zum Feld **[!UICONTROL Verantwortliche]** (Registerkarte **[!UICONTROL Allgemein]**).

  ![](assets/wf-properties_select-supervisors.png)

  Die Standardvorlage **[!UICONTROL Benachrichtigung an einen Workflow-Verantwortlichen]** enthält einen Link für den Zugriff auf die Adobe Campaign-Client-Konsole über das Web, damit die Empfängerin bzw. der Empfänger das Problem bearbeiten kann, sobald angemeldet.

  Sie haben die Möglichkeit, im Knoten **[!UICONTROL Administration > Kampagnen > Vorlagen technischer Sendungen]** eine eigene Vorlage zu erstellen.

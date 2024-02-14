---
product: campaign
title: Workflow-Eigenschaften
description: Erfahren Sie mehr über die Campaign-Workflow-Eigenschaften.
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 60%

---

# Workflow-Eigenschaften{#workflow-properties}



## Ausführungs-Tab {#execution-tab}

Der Tab **[!UICONTROL Ausführung]** im Fenster der Workflow-**[!UICONTROL Eigenschaften]** enthält drei Bereiche:

![](assets/wf_execution_tab.png)

### Planung {#scheduler}

Dieser Bereich wird nur in Kampagnen-Workflows angezeigt.

* **[!UICONTROL Versandpriorität]**

  Die Workflow-Engine verarbeitet die auszuführenden Workflows anhand des in diesem Feld definierten Prioritätskriteriums. Beispielsweise alle Workflows mit einer **[!UICONTROL Durchschnittlich]** -Priorität vor denjenigen mit einer **[!UICONTROL Niedrig]** Priorität.

* **[!UICONTROL Ausführung auf einen Zeitpunkt mit geringer Auslastung verschieben]**

  Mit dieser Option wird der Workflow-Start auf einen weniger ausgelasteten Zeitraum verschoben. Manche Workflows können im Hinblick auf die Ressourcen für die Datenbank-Engine kostspielig sein. Es wird empfohlen, die Ausführung für einen Zeitpunkt mit geringer Auslastung (z. B. nachts) zu planen. Die Zeiten mit geringer Aktivität werden in der Variablen **[!UICONTROL Kampagnenprozesse]** technischer Arbeitsablauf.

### Ausführung {#execution}

* **[!UICONTROL Standard-Affinität]**

  Verwenden Sie dieses Feld, wenn Ihre Installation mehrere Workflow-Server aufweist, um festzulegen, auf welchem Server der Workflow laufen soll. Sollte der in diesem Feld angegebene Wert auf keinem Server existieren, bleibt der Workflow im Stand-by.

* **[!UICONTROL Verlaufsumfang (Tage)]**

  In den Arbeitstabellen der Datenbank werden der Ausführungsverlauf von Aufgaben und Ereignissen sowie das Protokoll gespeichert. Geben Sie hier an, wie lange der Verlauf für diesen Workflow beibehalten werden soll. Die in der Datenbank enthaltenen Bereinigungsprozesse löschen jeden Tag die obsoleten Verläufe. Bei Angabe von Null wird der Verlauf nie gelöscht.

* **[!UICONTROL SQL-Abfragen im Protokoll speichern]**

  Diese Funktion richtet sich an erfahrene Benutzer. Sie betrifft Workflows mit Zielgruppenbestimmungs-Aktivitäten (Abfrage, Vereinigung, Schnittmenge usw.). Wenn diese Option aktiviert wurde, werden die bei Ausführung des Workflows an die Datenbank gesendeten SQL-Abfragen in Adobe Campaign gespeichert. Auf diese Weise haben Sie die Möglichkeit, die Abfragen zu analysieren und eventuelle Probleme zu erkennen.

  Abfragen werden in einer **[!UICONTROL SQL-Logs]** zum Workflow (außer Kampagnen-Workflows) und zum **[!UICONTROL Eigenschaften]** Aktivität, wenn die Option aktiviert ist. Die **[!UICONTROL Prüfung]** enthält auch SQL-Abfragen.

  ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL In der Engine ausführen]**

  Diese Option darf nur zur Problembehebung verwendet werden und nie im Produktionsalltag. Bei Aktivierung der Option wird der Workflow prioritär. Alle anderen Workflows werden bis zu seinem Abschluss von der Workflow-Engine angehalten.

### Umgang mit Fehlern       {#error-management}

* **[!UICONTROL Fehlerbehebung]**

  In diesem Feld können Sie angeben, welche Aktion ausgeführt werden soll, wenn eine Workflow-Aufgabe einen Fehler ausgibt. Zwei Optionen stehen zur Verfügung:

   * **[!UICONTROL Prozess anhalten]**: Der Workflow wird automatisch ausgesetzt. Der Workflow-Status ändert sich in **[!UICONTROL Fehlgeschlagen]**. Sobald das Problem behoben ist, starten Sie den Workflow mit dem **[!UICONTROL Starten]** oder **[!UICONTROL Neu starten]** Schaltflächen.
   * **[!UICONTROL Ignorieren]** - die den Fehler verursachende Aufgabe wechselt in den Status **[!UICONTROL Fehlgeschlagen]**, der Workflow behält jedoch den Status **[!UICONTROL Gestartet]**. Diese Konfiguration empfiehlt sich bei wiederkehrenden Aufgaben. Wenn der Workflow-Zweig eine Planungsaktivität enthält, löst diese automatisch zum nächsten geplanten Zeitpunkt die nächste Ausführung aus.

* **[!UICONTROL Folgefehler]**

  Dieses Feld wird verfügbar, wenn die Variable **[!UICONTROL Ignorieren]** -Wert in der **[!UICONTROL Bei Fehlern]** -Feld. Sie können die Anzahl der Fehler angeben, die ignoriert werden können, bevor der Prozess angehalten wird. Sobald diese Zahl erreicht ist, wechselt der Workflow-Status zu **[!UICONTROL Fehlgeschlagen]**. Wenn der Wert dieses Felds 0 beträgt, wird der Workflow unabhängig von der Fehleranzahl nie angehalten.

* **[!UICONTROL Template]**

  Geben Sie in diesem Feld die Vorlage für die Benachrichtigung an, die die Workflow-Verantwortlichen erhalten, wenn ein Workflow den Status **[!UICONTROL Fehlgeschlagen]** annimmt.

  Die betroffenen Benutzer werden per E-Mail benachrichtigt, wenn ihr Profil eine E-Mail-Adresse enthält. Um Workflow-Supervisoren zu definieren, gehen Sie zum **[!UICONTROL Supervisor(en)]** -Feld der Eigenschaften (**[!UICONTROL Allgemein]** Registerkarte).

  ![](assets/wf-properties_select-supervisors.png)

  Die **[!UICONTROL Benachrichtigung an einen Workflow-Verantwortlichen]** Die Standardvorlage enthält einen Link zum Zugriff auf die Adobe Campaign-Clientkonsole über das Web, damit der Empfänger nach der Anmeldung an dem Problem arbeiten kann.

  Sie haben die Möglichkeit, im Knoten **[!UICONTROL Administration > Kampagnen > Vorlagen technischer Sendungen]** eine eigene Vorlage zu erstellen.

---
product: campaign
title: Best Practices bei Workflows
description: Machen Sie sich mit Best Practices bei Campaign-Workflows vertraut.
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '1709'
ht-degree: 79%

---

# Best Practices bei Workflows{#workflow-best-practices}

Im Folgenden finden Sie allgemeine Richtlinien zur Optimierung der Workflow-Leistung von Campaign, zur Verbesserung Ihres Workflow-Designs und zur Auswahl der richtigen Einstellungen.

## Workflow-Ordner {#workflow-folders}

Adobe empfiehlt, Ihre Workflows in einem eigenen Ordner zu erstellen.

Wenn der Workflow die gesamte Plattform betrifft, (z. B. Bereinigungsprozesse), könnte es sinnvoll sein, einen Unterordner zum nativen Ordner **[!UICONTROL Technische Workflows]** hinzuzufügen.

## Workflow-Name {#workflow-naming}

Um die Suche und Fehlerbehebung zu vereinfachen, empfiehlt Adobe, Ihre Workflows mit eigenen Namen und Titeln zu versehen: Erläutern Sie im Beschreibungsfeld des Workflows kurz den jeweiligen Prozess, damit dessen Zweck für den Benutzer leicht ersichtlich ist.

Wenn der Workflow Teil eines mehrere Workflows umfassenden Prozesses ist, können Sie jeden Workflow durch die Angabe eines Titels exakt benennen. Zahlen sind beispielsweise eine gute Möglichkeit, Workflows zu ordnen.

Beispiel:

* 001 – Importieren – Empfänger importieren
* 002 – Importieren – Verkäufe importieren
* 003 – Importieren – Verkaufsdetails importieren
* 010 – Exportieren – Versandlogs exportieren
* 011 – Exportieren – Trackinglogs exportieren

## Workflow-Prioritätsstufe {#workflow-severity}

Sie können die Prioritätsstufe eines Workflows im Tab **[!UICONTROL Ausführung]** der Workflow-Eigenschaften konfigurieren:

* Normal
* Produktion
* Kritisch

Durch Angabe dieser Informationen bei der Erstellung eines Workflows ist die Prioritätsstufe des konfigurierten Prozesses besser ersichtlich.

Diese Option beeinflusst nur Kampagnen-Workflows.

Kampagnen-Workflows (Workflows, die als Teil einer Kampagne erstellt werden) mit höherer Prioritätsstufe werden vorgezogen, wenn die Kampagne mehrere Prozesse enthält, die gleichzeitig ausgeführt werden müssen. Standardmäßig können entsprechend der Option NmsOperation_LimitConcurrency maximal zehn Prozesse einer Kampagnen gleichzeitig ausgeführt werden. Wenn eine Kampagne beispielsweise aus 25 Workflows besteht, werden Workflows mit einer höheren Prioritätsstufe in der ersten Gruppe von zehn Prozessen ausgeführt.

## Überwachen von Workflows {#workflow-monitoring}

Alle Ihre terminierten in Produktionsumgebungen ausgeführten Workflows sollten überwacht werden, damit Sie bei Auftreten eines Fehlers benachrichtigt werden.

Wählen Sie dazu in den Workflow-Eigenschaften eine Gruppe von Supervisoren. Dies können entweder die standardmäßigen **[!UICONTROL Workflow-Supervisoren]** oder eine benutzerdefinierte Gruppe sein. Achten Sie darauf, dass zumindest ein Benutzer der Gruppe eine eingerichtete E-Mail-Adresse besitzt.

Bestimmen Sie zu Beginn der Workflow-Erstellung Workflow-Supervisoren. Diese werden bei Fehlern per E-Mail informiert. Weitere Informationen hierzu finden Sie unter [Fehler beheben](monitor-workflow-execution.md#managing-errors).

Überprüfen Sie regelmäßig den Tab **[!UICONTROL Monitoring]**, um den Gesamtstatus der aktiven Workflows anzuzeigen. Weitere Informationen hierzu finden Sie unter [Instanz-Monitoring](monitor-workflow-execution.md#instance-supervision).

Die Workflow-Heatmap ermöglicht den Administratoren der Adobe Campaign-Plattform, die Auslastung der Instanz zu überwachen und Workflows entsprechend zu planen. Weitere Informationen dazu finden Sie unter [Workflow-Monitoring](heatmap.md).

## Activities {#using-activities}

>[!CAUTION]
>
>Sie können Aktivitäten innerhalb eines Workflows kopieren und einfügen. Wir raten jedoch davon ab, Aktivitäten über verschiedene Workflows hinweg zu kopieren und einzufügen. Einige Einstellungen, die Aktivitäten wie Sendungen und Planung betreffen, können zu Konflikten und Fehlern beim Ausführen des Ziel-Workflows führen. Stattdessen empfehlen wir, Workflows zu **duplizieren**. Weitere Informationen finden Sie unter [Workflows duplizieren ](build-a-workflow.md#duplicate-workflows).

### Name der Aktivität {#name-of-the-activity}

Bei der Entwicklung Ihres Workflows erhalten alle Aktivitäten sowie alle Adobe Campaign-Objekte einen Namen. Diese Namen werden zwar vom Tool erstellt, wir empfehlen jedoch, sie bei der Konfiguration zu ändern. Geschieht dies erst zu einem späteren Zeitpunkt, besteht die Gefahr, dass dadurch der Workflow durch Aktivitäten mit Namen einer anderen früheren Aktivität unterbrochen wird. Deshalb wäre die nachträgliche Aktualisierung der Namen eine schwierige Aufgabe.

Der Aktivitätsname ist im Tab **[!UICONTROL Erweitert]** verfügbar. Behalten Sie nicht die Namen **[!UICONTROL abfrage]**, **[!UICONTROL abfrage1]**, **[!UICONTROL abfrage11]** bei, sondern benennen Sie sie beispielsweise **[!UICONTROL abfrageAbonnenten]**. Dieser Name wird im Protokoll angezeigt und gegebenenfalls auch in den SQL-Logs, was Ihnen hilft, bei der Konfiguration des Workflows Fehler zu beheben.

### Erste und letzte Aktivitäten {#first-and-last-activities}

* Beginnen Sie Ihren Workflow stets mit der Aktivität **[!UICONTROL Beginn]** oder **[!UICONTROL Planung]**. Bei Bedarf können Sie auch die Aktivität **[!UICONTROL Externes Signal]** hinzufügen.
* Pro Workflow-Verzweigung darf nur eine einzige **** Planung verwendet werden. Wenn dieselbe Verzweigung eines Workflows mehrere Planungen enthält, die miteinander verknüpft sind, steigt die Anzahl der auszuführenden Aufgaben exponentiell an, wodurch die Datenbank überlastet würde. Diese Regel gilt auch für alle Aktivitäten mit einem Tab **[!UICONTROL Planung &amp; Verlauf]**. Weitere Informationen zur [Planung](scheduler.md).

   ![](assets/wf-scheduler.png)

* Verwenden Sie in allen Workflows jeweils **[!UICONTROL Ende]**-Aktivitäten. Auf diese Weise wird temporärer Speicherplatz freigesetzt, der für Berechnungen in Workflows reserviert ist. Weitere Informationen finden Sie unter [Start und Ende](start-and-end.md).

### JavaScript innerhalb einer Aktivität {#javascript-within-an-activity}

Sie können bei der Initialisierung einer Workflow-Aktivität im Tab **[!UICONTROL Erweitert]** der jeweiligen Aktivität JavaScript hinzufügen.

Um den Workflow leichter erkennbar zu machen, empfehlen wir, am Anfang und Ende des Titels der Aktivität doppelte Bindestriche zu setzen, z. B.: -- Mein Titel --.

### Signal {#signal}

Meistens ist nicht bekannt, wo das Signal ausgelöst wurde. Um dies zu vermeiden, notieren Sie im Tab **[!UICONTROL Erweitert]** der Signalaktivität im Feld **[!UICONTROL Kommentar]** den erwarteten Auslöser eines Signals für diese Aktivität.

## Workflow-Aktualisierungen {#workflow-update}

Ein Produktions-Workflow sollte nicht direkt aktualisiert werden. Prozesse sollten zuerst in einer Entwicklungsumgebung getestet werden, außer der Prozess besteht aus einer Kampagne mit Vorlagen-Workflows. Nach der Validierung kann der Workflow für die Produktion bereitgestellt werden.

Führen Sie alle Tests in Entwicklungs- oder Staging-Umgebungen, nicht in Produktionsumgebungen durch. Die Leistung kann in einem solchen Fall nicht gewährleistet werden.

Während Workflows in einem Archivordner auf Entwicklungs- oder Testplattformen aufbewahrt werden können, sollte die Produktionsumgebung möglichst sauber gehalten werden. Entfernen Sie deshalb alte, inaktive Workflows aus der Produktionsumgebung.

## Ausführung und Leistung {#execution-and-performance}

### Logs {#logs}

Die JavaScript-Methode **[!UICONTROL logInfo()]** ist eine Lösung zum Debugging eines Workflows. Sie muss jedoch sorgfältig verwendet werden, insbesondere für häufig ausgeführte Aktivitäten: Sie kann die Protokolle überlasten und die Größe der Protokolltabelle erheblich erhöhen.

### Zwischenergebnisse beibehalten

Die **Zwischen zwei Ausführungen die ermittelte Population festhalten** speichert temporäre Tabellen zwischen zwei Ausführungen eines Workflows.

Sie ist in den Workflow-Eigenschaften verfügbar. **[!UICONTROL Allgemein]** und kann für Entwicklungs- und Testzwecke verwendet werden, um Daten zu überwachen und Ergebnisse zu überprüfen. Sie können diese Option in Entwicklungsumgebungen verwenden, sie jedoch nie in Produktionsumgebungen verwenden. Die Beibehaltung temporärer Tabellen könnte dazu führen, dass die Größe der Datenbank erheblich zunimmt und schließlich die Größenbeschränkung erreicht wird. Außerdem wird das Backup verlangsamt.

Nur die Arbeitstabellen der letzten Ausführung des Workflows werden aufbewahrt. Arbeitstabellen früherer Ausführungen werden durch den täglich durchgeführten **[!UICONTROL Bereinigungs]**-Workflow bereinigt.

>[!CAUTION]
>
>Diese Option muss **never** in einem **production** Arbeitsablauf. Diese Option wird zur Analyse der Ergebnisse verwendet und ist nur für Testzwecke konzipiert und darf daher nur in Entwicklungs- oder Staging-Umgebungen verwendet werden.


### SQL-Abfragen protokollieren

Die **SQL-Abfragen im Protokoll speichern** ist im **[!UICONTROL Ausführung]** Registerkarte der Workflow-Eigenschaften. Diese Option protokolliert alle SQL-Abfragen aus den verschiedenen Aktivitäten und bietet eine Möglichkeit zu sehen, was von der Plattform tatsächlich ausgeführt wird. Diese Option sollte jedoch nur verwendet werden **vorübergehend** während der Entwicklung **nicht in der Produktion aktiviert**.

Es empfiehlt sich, die Protokolle zu bereinigen, wenn sie nicht mehr benötigt werden. Workflow-Verläufe werden nicht automatisch bereinigt, alle Nachrichten werden standardmäßig beibehalten. Gehen Sie zur Bereinigung zu **[!UICONTROL Datei > Aktionen]** oder klicken Sie in der Symbolleiste oberhalb der Workflow-Liste auf die Schaltfläche „Aktionen“. Wählen Sie die Option „Verlauf bereinigen“ aus.
Informationen zum Bereinigen der Logs finden Sie in dieser [Dokumentation](start-a-workflow.md).

### Workflow-Planung {#workflow-planning}

Zusätzliche Best Practices sollten bei der Planung der Ausführung von Workflows angewendet werden, um Probleme zu vermeiden:

* Behalten Sie eine stabile Aktivitätsstufe am Tag bei und vermeiden Sie Spitzen, um zu verhindern, dass die Instanz überlastet wird. Verteilen Sie dazu die Startzeiten des Workflows gleichmäßig über den Tag.
* Planen Sie das Laden der Daten für die Nacht, um Ressourcenkonflikte zu reduzieren.
* Lange Workflows können sich auf die Server- und Datenbankressourcen auswirken. Teilen Sie die längsten Workflows auf, um die Bearbeitungszeit zu verkürzen.
* Um die Gesamtlaufzeit zu verkürzen, ersetzen Sie zeitaufwändige Aktivitäten durch einfachere und schnellere Aktivitäten.
* Vermeiden Sie die gleichzeitige Ausführung von mehr als 20 Workflows. Wenn zu viele Workflows gleichzeitig ausgeführt werden, kann Ihre Plattform überlastet sein und instabil werden.

### Workflow-Ausführung {#workflow-execution}

Verbessern Sie die Stabilität Ihrer Instanz, indem Sie die folgenden Best Practices implementieren:

* **Es wird empfohlen, Workflows nicht öfter als alle 15 Minuten auszuführen**, da die Gesamtleistung des Systems beeinträchtigt werden kann und Blockierungen in der Datenbank entstehen können.

* **Vermeiden Sie es, Ihre Workflows in einem angehaltenen Zustand zu belassen**. Wenn Sie einen temporären Workflow erstellen, stellen Sie sicher, dass er korrekt beendet werden kann und nicht in einem **[!UICONTROL pausierten]** Zustand bleibt. Wenn er pausiert ist, bedeutet dies nämlich, dass Sie die temporären Tabellen beibehalten müssen und somit die Größe der Datenbank erhöhen. Weisen Sie unter „Workflow-Eigenschaften“ Workflow-Supervisoren zu, um eine Warnung zu senden, wenn ein Workflow fehlschlägt oder vom System ausgesetzt wird.

   So vermeiden Sie, dass Workflows ausgesetzt werden:

   * Prüfen Sie Ihre Workflows regelmäßig, um sicherzustellen, dass keine unerwarteten Fehler auftreten.
   * Bauen Sie Ihre Workflows möglichst einfach auf, indem Sie beispielsweise große Workflows in mehrere kleine unterteilen. Mit der Aktivität **[!UICONTROL Externes Signal]** können Sie Workflows durch andere Workflows auslösen.
   * Vermeiden Sie es, Aktivitäten mit Flüssen in Ihren Workflows zu deaktivieren, die Threads offen lassen und zu vielen temporären Tabellen führen, die viel Platz verbrauchen können. Behalten Sie in Ihren Workflows keine Aktivitäten im Status **[!UICONTROL Nicht aktivieren]** oder **[!UICONTROL Aktivieren, aber nicht ausführen]**.

* **Stoppen von nicht verwendeten Workflows**. Workflows, die weiterhin ausgeführt werden, halten Verbindungen zur Datenbank aufrecht.

* **Verwenden Sie den bedingungslosen Stopp so selten wie möglich**. Verwenden Sie diese Aktion nicht regelmäßig. Wenn Verbindungen, die von Workflows zur Datenbank erzeugt werden, nicht sauber geschlossen werden, beeinträchtigt dies die Leistung.

* **Führen Sie nicht mehrere Stopp-Anfragen für denselben Workflow aus**. Das Anhalten eines Workflows ist ein asynchroner Prozess: Die Anfrage wird registriert und der oder die Workflow-Server brechen die laufenden Vorgänge ab. Das Anhalten einer Workflow-Instanz kann daher einige Zeit in Anspruch nehmen, insbesondere wenn der Workflow auf mehreren Servern ausgeführt wird, von denen jeder die laufenden Aufgaben abbrechen muss. Um Probleme zu vermeiden, warten Sie, bis der Stopp-Vorgang abgeschlossen ist, und vermeiden Sie, einen Workflow mehrmals anzuhalten.

### In der Engine ausführen {#execute-in-the-engine-option}

Vermeiden Sie in einer Produktionsumgebung die Ausführung von Workflows in der Engine. Wenn die **[!UICONTROL In der Engine ausführen]** ist in der **[!UICONTROL Workflow-Eigenschaften]**, wird der Workflow prioritär und alle anderen Workflows werden von der Workflow-Engine angehalten, bis diese beendet ist.

![](assets/wf-execute-in-engine.png)
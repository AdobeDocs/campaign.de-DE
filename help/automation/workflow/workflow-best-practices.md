---
product: campaign
title: Best Practices bei Workflows
description: Machen Sie sich mit Best Practices bei Campaign-Workflows vertraut.
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 8bcaf367-5b1f-4d31-80c9-c77df43c6ed1
TQID: https://experienceleague.adobe.com/g1krDpf-lH0uNr8ZHxGh1Uemvl0Lxd-ygskdkTaUj24
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1390
ht-degree: 77%

---

# Best Practices bei Workflows{#workflow-best-practices}

Im Folgenden finden Sie allgemeine Richtlinien zur Optimierung der Workflow-Performance von Campaign, zur Verbesserung Ihres Workflow-Designs und zur Auswahl der richtigen Einstellungen.

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

Kampagnen-Workflows (Workflows, die im Rahmen einer Kampagne/eines Vorgangs erstellt werden) mit einem höheren Schweregrad werden vorrangig ausgeführt, wenn die Kampagne über viele Prozesse verfügt, die gleichzeitig ausgeführt werden sollen. Gemäß der Option NmsOperation_LimitConcurrency können in einer Kampagne standardmäßig nur 10 Prozesse gleichzeitig ausgeführt werden. Wenn eine Kampagne beispielsweise 25 Workflows enthält, werden Workflows mit einem höheren Schweregrad im ersten Pool von 10 Prozessen ausgeführt.

## Überwachen von Workflows {#workflow-monitoring}

Alle Ihre terminierten in Produktionsumgebungen ausgeführten Workflows sollten überwacht werden, damit Sie bei Auftreten eines Fehlers benachrichtigt werden.

Wählen Sie in den Workflow-Eigenschaften eine Gruppe von Verantwortlichen aus, entweder die standardmäßige Gruppe **[!UICONTROL Workflow-Verantwortliche]** oder eine benutzerdefinierte Gruppe. Stellen Sie sicher, dass mindestens ein Benutzer zu dieser Gruppe gehört und eine E-Mail eingerichtet ist.

Bevor Sie mit dem Erstellen eines Workflows beginnen, denken Sie daran, Workflow-Supervisoren zu definieren. Im Fehlerfall werden sie per E-Mail benachrichtigt. Weitere Informationen hierzu finden Sie unter [Fehler beheben](monitor-workflow-execution.md#managing-errors).

Überprüfen Sie regelmäßig den Tab **[!UICONTROL Monitoring]**, um den Gesamtstatus der aktiven Workflows anzuzeigen. Weitere Informationen hierzu finden Sie unter [Instanz-Monitoring](monitor-workflow-execution.md#instance-supervision).

Die Workflow-Heatmap ermöglicht den Administratoren der Adobe Campaign-Plattform, die Auslastung der Instanz zu überwachen und Workflows entsprechend zu planen. Weitere Informationen dazu finden Sie unter [Workflow-Monitoring](heatmap.md).

## Aktivitäten {#using-activities}

>[!CAUTION]
>
>Sie können Aktivitäten innerhalb eines Workflows kopieren und einfügen. Wir raten jedoch davon ab, Aktivitäten über verschiedene Workflows hinweg zu kopieren und einzufügen. Einige Einstellungen, die Aktivitäten wie Sendungen und Planung betreffen, können zu Konflikten und Fehlern beim Ausführen des Ziel-Workflows führen. Stattdessen empfehlen wir, Workflows zu **duplizieren**. Weitere Informationen finden Sie unter [Workflows duplizieren &#x200B;](build-a-workflow.md#duplicate-workflows).

### Name der Aktivität {#name-of-the-activity}

Bei der Entwicklung Ihres Workflows erhalten alle Aktivitäten sowie alle Adobe Campaign-Objekte einen Namen. Auch wenn der Name vom Tool generiert wird, empfehlen wir, ihn bei der Konfiguration mit einem expliziten Namen umzubenennen. Das Risiko besteht darin, dass der Workflow durch Aktivitäten unterbrochen wird, die zuvor den Namen einer anderen Aktivität verwendet haben. Es wäre daher schwierig, die Namen nachträglich zu aktualisieren.

Der Aktivitätsname ist im Tab **[!UICONTROL Erweitert]** verfügbar. Behalten Sie nicht die simplen Namen **[!UICONTROL abfrage]**, **[!UICONTROL abfrage1]**, **[!UICONTROL abfrage11]** bei, sondern benennen Sie sie beispielsweise **[!UICONTROL abfrageAbonnenten]**. Dieser Name wird im Protokoll angezeigt und gegebenenfalls auch in den SQL-Logs, was Ihnen hilft, bei der Konfiguration des Workflows Fehler zu beheben.

### Erste und letzte Aktivitäten {#first-and-last-activities}

* Beginnen Sie Ihren Workflow stets mit der Aktivität **[!UICONTROL Beginn]** oder **[!UICONTROL Planung]**. Bei Bedarf können Sie auch die Aktivität **[!UICONTROL Externes Signal]** hinzufügen.
* Pro Workflow-Verzweigung darf nur eine einzige **&#x200B;**&#x200B;Planung verwendet werden. Wenn dieselbe Verzweigung eines Workflows mehrere Planungen enthält, die miteinander verknüpft sind, steigt die Anzahl der auszuführenden Aufgaben exponentiell an, wodurch die Datenbank überlastet würde. Diese Regel gilt auch für alle Aktivitäten mit einem Tab **[!UICONTROL Planung &amp; Verlauf]**. Weitere Informationen zur [Planung](scheduler.md).

  ![](assets/wf-scheduler.png)

* Verwenden Sie **[!UICONTROL Ende]**-Aktivitäten für jeden Workflow. Dadurch kann Adobe Campaign temporären Speicherplatz freigeben, der für Berechnungen in Workflows verwendet wird. Weitere Informationen finden Sie unter [Start und Ende](start-and-end.md).

### JavaScript innerhalb einer Aktivität {#javascript-within-an-activity}

Sie können bei der Initialisierung einer Workflow-Aktivität JavaScript hinzufügen. Dies kann auf der Registerkarte **[!UICONTROL Erweitert]** der jeweiligen Aktivität erfolgen.

Um den Workflow leichter erkennbar zu machen, empfehlen wir, am Anfang und Ende des Titels der Aktivität doppelte Bindestriche zu setzen, z. B.: -- Mein Titel --.

### Signal {#signal}

Meistens ist nicht bekannt, wo das Signal ausgelöst wurde. Um dies zu vermeiden, notieren Sie im Feld **[!UICONTROL Kommentar]** auf der Registerkarte **[!UICONTROL Erweitert]** der Signalaktivität die erwartete Herkunft eines Signals für diese Aktivität.

## Workflow-Aktualisierungen {#workflow-update}

Ein Produktions-Workflow sollte nicht direkt aktualisiert werden. Sofern der Prozess nicht aus der Erstellung einer Kampagne mit Vorlagen-Workflows besteht, sollten Prozesse zunächst in einer Entwicklungsumgebung getestet werden. Nach dieser Validierung kann der Workflow in der Produktion bereitgestellt und gestartet werden.

Führen Sie alle Tests in Entwicklungs- oder Staging-Umgebungen, nicht in Produktionsumgebungen durch. die Performance kann in einem solchen Fall nicht gewährleistet werden.

Archivierte Workflows können auf Entwicklungs- oder Testplattformen in einem archivierten Ordner gespeichert werden, aber die Produktionsumgebung sollte so sauber wie möglich bleiben. Alte Workflows sollten aus der Produktionsumgebung entfernt werden, wenn sie inaktiv sind.

## Ausführung und Performance {#execution-and-performance}

### Logs {#logs}

Die JavaScript-Methode **[!UICONTROL logInfo()]** ist eine Lösung zum Debuggen eines Workflows. Sie muss jedoch mit Bedacht verwendet werden, insbesondere für häufig ausgeführte Aktivitäten, denn sie kann die Protokolle überlasten und die Größe der Protokolltabelle erheblich erhöhen.

### Beibehaltung der Zwischenpopulationen

Die Option **Zwischen zwei Ausführungen die ermittelte Population festhalten** speichert temporäre Tabellen zwischen zwei Ausführungen eines Workflows.

Diese Option ist auf der Registerkarte **[!UICONTROL Allgemein]** der Workflow-Eigenschaften verfügbar und kann für Entwicklungs- und Testzwecke verwendet werden, um Daten zu überwachen und Ergebnisse zu überprüfen. Sie können diese Option in Entwicklungsumgebungen verwenden, sollten sie aber nie in Produktionsumgebungen verwenden. Die Beibehaltung temporärer Tabellen könnte dazu führen, dass die Größe der Datenbank erheblich zunimmt und letztendlich die Größenbeschränkung erreicht wird. Außerdem wird dadurch das Backup verlangsamt.

Nur die Arbeitstabellen der letzten Ausführung des Workflows werden aufbewahrt. Arbeitstabellen früherer Ausführungen werden durch den täglich durchgeführten **[!UICONTROL Bereinigungs]**-Workflow bereinigt.

>[!CAUTION]
>
>Diese Option darf **nie** in einem **Produktions**-Workflow aktiviert werden. Diese Option wird zur Analyse der Ergebnisse verwendet und ist nur für Testzwecke konzipiert und darf daher nur in Entwicklungs- oder Staging-Umgebungen verwendet werden.


### Protokollieren von SQL-Abfragen

Die Option **SQL-Abfragen im Protokoll speichern** ist auf der Registerkarte **[!UICONTROL Ausführung]** der Workflow-Eigenschaften verfügbar. Diese Option protokolliert alle SQL-Abfragen aus den verschiedenen Aktivitäten und zeigt an, was von der Plattform tatsächlich ausgeführt wird. Diese Option sollte jedoch nur **vorübergehend** während der Entwicklung verwendet und **nicht in der Produktion aktiviert werden**.

Es empfiehlt sich, die Protokolle zu entfernen, wenn sie nicht mehr benötigt werden. Workflow-Verläufe werden nicht automatisch bereinigt: Alle Nachrichten werden standardmäßig beibehalten. Gehen Sie zur Bereinigung zu **[!UICONTROL Datei > Aktionen]** oder klicken Sie in der Symbolleiste oberhalb der Workflow-Liste auf die Schaltfläche „Aktionen“. Wählen Sie die Option „Verlauf bereinigen“ aus.
Informationen zum Bereinigen der Logs finden Sie in dieser [Dokumentation](start-a-workflow.md).

### Workflow-Planung {#workflow-planning}

Die folgenden Best Practices sollten zusätzlich bei der Planung der Ausführung von Workflows angewendet werden, um Probleme zu vermeiden:

* Achten Sie auf ein über den Tag verteiltes stabiles Aktivitätsniveau und vermeiden Sie Spitzen, um zu verhindern, dass die Instanz überlastet wird. Verteilen Sie dazu die Startzeiten des Workflows gleichmäßig über den Tag.
* Planen Sie das Laden der Daten für die Nacht, um Ressourcenkonflikte zu reduzieren.
* Lange Workflows können sich auf die Server- und Datenbankressourcen auswirken. Teilen Sie die längsten Workflows auf, um die Verarbeitungszeit zu reduzieren.
* Um die Gesamtlaufzeit zu verkürzen, ersetzen Sie zeitaufwändige Aktivitäten durch einfachere und schnellere Aktivitäten.
* Vermeiden Sie die gleichzeitige Ausführung von mehr als 20 Workflows. Wenn zu viele Workflows gleichzeitig ausgeführt werden, kann Ihre Plattform durch Überlastung instabil werden.


### In der Engine ausführen {#execute-in-the-engine-option}

Vermeiden Sie in einer Produktionsumgebung die Ausführung von Workflows in der Engine. Wenn die Option **[!UICONTROL In der Engine ausführen]** in den **[!UICONTROL Workflow-Eigenschaften]** aktiviert ist, hat dieser Workflow Priorität und alle anderen Workflows werden von der Workflow-Engine angehalten, bis dieser beendet ist.

![](assets/wf-execute-in-engine.png)

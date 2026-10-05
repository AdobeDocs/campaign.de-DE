---
product: campaign
title: Steuerungsaktivitäten in Workflows
description: Liste der Fluss-Steuerungsaktivitäten
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 904f2d94-bd3e-4c46-aeab-2ef77a7bdeee
TQID: 'https://experienceleague.adobe.com/ASEN6-oLFuS4se4B0hreK-ufXzIoWLquNRc5t2G8UF4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 100%
---
# Steuerungsaktivitäten in Workflows{#about-flow-control-activities}

Bei den folgenden Aktivitäten handelt es sich um Datenbankaktivitäten, d. h. sie werden zur Koordinierung der Workflow-Aktivitäten verwendet.

* **[Warnhinweis](alert.md)**: sendet eine Benachrichtigung an einen Benutzer oder eine Benutzergruppe.
* **[AND-Join](and-join.md)**: wartet, bis alle parallel ablaufenden Aufgaben beendet sind, bevor mit der Ausführung des Workflows fortgefahren wird.
* **[Validierung](approval.md)**: sendet eine E-Mail an einen Benutzer oder eine Benutzergruppe und wartet auf die Validierung, bevor die Ausführung fortgesetzt wird.
* **[Externes Signal](external-signal.md)**: aktiviert eine ausgehende Transition als Reaktion auf ein externes Signal.
* **[Verzweigung](fork.md)**: ermöglicht es Ihnen, alle ausgehende Transitionen zu aktivieren.
* **[Sprung (Start- und Zielpunkt)](jump-start-point-and-end-point.md)**: ermöglicht die Implementierung von Transitionen ohne Verknüpfungen.
* **[Start und Ende](start-and-end.md)**: markieren den Anfangs- bzw. den Endpunkt eines Workflows.
* **[Planung](scheduler.md)**: dient der Konfiguration einer Ausführungsplanung für den Workflow.
* **[Unter-Workflow](sub-workflow.md)**: startet die Ausführung eines weiteren Workflows.
* **[Test](test.md)**: aktiviert eine Transition in Abhängigkeit vom Ergebnis eines Tests.
* **[Zeitliche Beschränkung](time-constraint.md)**: setzt die Ausführung einer Aufgabe für eine bestimmte Dauer aus.
* **[Warten](wait.md)**: aktiviert eine ausgehende Transition nach einer definierten Dauer.
  <!--* **Task**: lets you configure task execution. Refer to the [Task](task.md) section.-->

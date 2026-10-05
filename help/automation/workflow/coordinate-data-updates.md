---
product: campaign
title: Koordinieren von Datenaktualisierungen
description: Koordinieren von Datenaktualisierungen
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9faf7ee7-07c1-415b-b234-a945994792c7
TQID: 'https://experienceleague.adobe.com/DmafsXGIr-CWPruj9mDR-XmcnWHeMk75-Sm-70-aCk4'
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
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 100%
---
# Koordinieren von Datenaktualisierungen{#coordinating-data-updates}



Das folgende Anwendungsbeispiel erläutert die Erstellung eines Workflows, mit dem begleitende Aktualisierungen bei der mehrmaligen Ausführung eines Workflows verwaltet werden können.

Dadurch soll überprüft werden, ob der Aktualisierungsprozess beendet wurde, bevor ein weiterer Aktualisierungsvorgang ausgeführt wird. Wir werden zu diesem Zweck eine Instanzvariable erstellen und im Workflow testen, ob die Instanz ausgeführt wird, um zu entscheiden, ob die Ausführung des Workflows fortgesetzt und die Aktualisierung durchgeführt werden soll.

![](assets/uc_dataupdate_wkf.png)

Der vorliegende Workflow besteht aus folgenden Aktivitäten:

* **Planung:** Hiermit wird der Workflow zu bestimmten Zeiten durchgeführt.
* **Test:** Hiermit wird geprüft, ob der Workflow bereits ausgeführt wird.
* **Abfrage** und **Daten-Update:** falls der Workflow noch nicht ausgeführt wird; gefolgt von der Aktivität **Ende,** durch die die Instanzvariable des Workflows auf false zurückgesetzt wird.
* **Ende:** falls der Workflow bereits ausgeführt wird.

Gehen Sie zur Erstellung des Workflows wie folgt vor:

1. Fügen Sie die Aktivität **Planung** hinzu und konfigurieren Sie deren Häufigkeit nach Bedarf.
1. Fügen Sie die Aktivität **Test** hinzu, um zu prüfen, ob der Workflow bereits durchgeführt wird, und konfigurieren Sie sie gemäß den unten stehenden Angaben.

   >[!NOTE]
   >
   >„isRunning“ ist die für dieses Beispiel ausgewählte Instanzvariable. Dies ist keine integrierte Variable.

   ![](assets/uc_dataupdate_test.png)

1. Fügen Sie eine Aktivität **Ende** zur **Nein**-Verzweigung hinzu. Dadurch erfolgt keine Ausführung, falls der Workflow bereits ausgeführt wird.
1. Fügen Sie die gewünschten Aktivitäten zur **Ja**-Verzweigung hinzu. Für unser Beispiel sind dies die Aktivitäten **Abfrage** und **Daten-Update**.
1. Öffnen Sie die erste Aktivität und fügen Sie den Befehl **instance.vars.isRunning = true** auf dem Tab **[!UICONTROL Erweitert]** hinzu. Auf diese Weise wird die Instanzvariable auf „wird ausgeführt“ gesetzt.

   ![](assets/uc_dataupdate_query.png)

1. Fügen Sie am Ende der **[!UICONTROL Ja]**-Verzweigung eine **Ende**-Aktivität an und geben Sie danach den Befehl **instance.vars.isRunning = false** im Tab **[!UICONTROL Erweitert]** ein.

   Dadurch wird keine Aktion aufgeführt, solange der Workflow ausgeführt wird.

   ![](assets/uc_dataupdate_end.png)

**Verwandte Themen:**

* [Mehrere gleichzeitige Ausführungen verhindern](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)
* [Aktivität &quot;Daten-Update&quot;](update-data.md)

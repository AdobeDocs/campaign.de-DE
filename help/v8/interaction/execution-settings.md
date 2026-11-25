---
product: campaign
title: Ausführungsparameter
description: Ausführungsparameter
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: simulating-offers
exl-id: e2dea4a0-9ed8-47b6-a16b-eeee653d2290
TQID: 'https://experienceleague.adobe.com/k2-e-laXDXtVyBJnoiyKAdNHKiS3nB-t1X1cEaqeudM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 74%
---
# Ausführungsparameter{#execution-settings}



Beim Erstellen einer Simulation können Sie bei Bedarf Ausführungseinstellungen festlegen. Auf diese Weise können Sie die Ausführung der Simulation in Abhängigkeit von ihrer Prioritätsstufe auf einen Zeitpunkt mit geringer Auslastung verschieben und die SQL-Abfragen im Protokoll speichern. Diese Stufe ist optional.

Eine Änderung dieser Parameter ist im späteren Verlauf im Tab **[!UICONTROL Allgemein]** des Simulationsfensters möglich.

![Registerkarte „Allgemein“ einer Simulation mit Ausführungseinstellungen: Planung niedriger Aktivitäten, SQL-Protokollierung und Prioritätenliste.](assets/offer_simulation_008.png)

* **[!UICONTROL Ausführung auf einen Zeitpunkt mit geringer Aktivität planen]** : dient der Planung der Simulation auf der Grundlage der ausgewählten Priorität (niedrig, Durchschnitt oder hoch), um die Leistung von Adobe Campaign zu optimieren.
* **[!UICONTROL Priorität]**: auf die Simulation angewendete Dringlichkeit, die den Ausführungsbeginn entsprechend verschiebt. Wenn die Option **[!UICONTROL Ausführung auf einen Zeitpunkt mit geringer Auslastung verschieben]** aktiviert wurde, wählt der Workflow der Kampagnenvorgänge einen Zeitpunkt mit geringer Aktivität, um die Simulation zu starten.
* **[!UICONTROL SQL-Abfragen im Protokoll speichern]**: Diese Funktion ist erfahrenen Benutzenden vorbehalten. Bei Aktivierung wird dem Protokoll eine Registerkarte hinzugefügt, in der die SQL-Abfragen angezeigt werden. Dies erleichtert die Fehlerbehebung, wenn die Simulation fehlschlägt.

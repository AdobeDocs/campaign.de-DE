---
product: campaign
title: Aggregat-Update
description: Erfahren Sie mehr über die Workflow-Aktivität "Aggregat-Update".
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: 'https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw'
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 70%
---
# Aggregat-Update{#update-aggregate}

Die in [Cubes](../../v8/reporting/gs-cubes.md) für Berichtszwecke definierten Aggregate können mit einer bestimmten Aktivität aktualisiert werden. Bei der Konfiguration des Aggregats ist ein **[!UICONTROL Workflow]** verfügbar.

Weitere Informationen zu Cubes und Aggregaten finden Sie unter [Aggregate in Cubes](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Um ein Aggregat zu aktualisieren, bearbeiten Sie die Aktivität **[!UICONTROL Aggregat aktualisieren]** und wählen Sie den zu aktualisierenden Cube und das Aggregat aus.

Sie können eine **vollständige Aktualisierung** oder eine **partielle Aktualisierung** durchführen.

![Aggregat-Aktivität mit den Feldern Cube und Aggregat sowie den Optionen Vollständige Aktualisierung oder Teilaktualisierung aktualisieren.](assets/update-aggregate-details.png)

Standardmäßig wird bei jeder Berechnung eine vollständige Aktualisierung ausgeführt. Um eine partielle Aktualisierung zu aktivieren, wählen Sie die entsprechende Option aus und definieren Sie die Aktualisierungsbedingungen.

![Bearbeiten des Fensters Aktualisierungsbedingung mit einem Filter für das Erstellungsdatum nach dem aktuellen Datum abzüglich 1 Monat.](assets/update-aggregate-partial.png)

Es empfiehlt sich, eine **[!UICONTROL Planungsaktivität]** hinzuzufügen, um die Aktualisierungshäufigkeit der Berechnungen festzulegen.

---
product: campaign
title: Segmente
description: Segmente
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 2%

---

# Segmente{#cells}

Die **[!UICONTROL Zellen]** -Aktivität bietet eine Ansicht der verschiedenen Teilmengen als Datenspalten. Es erleichtert die Manipulation von Teilmengen und dient auch der Nutzung von Personalisierungsfunktionen.

![](assets/wf_split_cells.png)

Diese Aktivität kann so konfiguriert werden, dass sie bestimmte Parameter entsprechend den Benutzeranforderungen eingibt. Die Details der Teilmengen werden standardmäßig in einem dedizierten Fenster über die **[!UICONTROL Zellen]** und **[!UICONTROL Erweitert]** Registerkarten.

![](assets/wf_split_cells_with_customization.png)

Im folgenden Beispiel wurde das Formular geändert: a **[!UICONTROL Daten]** wurde hinzugefügt, um die Zuordnung eines Angebots und einer Prioritätsstufe für jede Teilmenge zu ermöglichen.

![](assets/cells-activity-sample.png)

Für diese Konfiguration wurden die folgenden Informationen zum Workflow-Formular im **[!UICONTROL Administration > Konfigurationen > Formulare]** Knoten des Adobe Campaign-Explorer:

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

Die Personalisierung von Formularen sollte erfahrenen Benutzern vorbehalten bleiben. Weitere Informationen hierzu finden Sie in diesem .

---
product: campaign
title: Segmente
description: Segmente
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
TQID: https://experienceleague.adobe.com/io5sW8Sd5PlrMn4F6i-wdM05BeZiQ5FX6KPl2ncymQU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 124
ht-degree: 100%

---

# Segmente{#cells}

Die Aktivität **[!UICONTROL Segmente]** bietet eine Ansicht der verschiedenen Teilmengen in Form von Datenspalten. Dies erleichtert die Bearbeitung von Teilmengen und ermöglicht die Nutzung von Personalisierungsfunktionen.

![](assets/wf_split_cells.png)

Diese Aktivität kann so konfiguriert werden, dass bestimmte Parameter entsprechend den Benutzeranforderungen eingegeben werden. Standardmäßig werden die Details der einzelnen Teilmengen in einem eigenen Fenster über die Registerkarten **[!UICONTROL Segmente]** und **[!UICONTROL Erweitert]** angezeigt.

![](assets/wf_split_cells_with_customization.png)

Im folgenden Beispiel wurde das Eingabeformular geändert: Es wurde die Registerkarte **[!UICONTROL Daten]** hinzugefügt, um für jede Teilmenge die Zuordnung eines Angebots und einer Prioritätsstufe zu ermöglichen.

![](assets/cells-activity-sample.png)

Für diese Konfiguration wurden im Knoten **[!UICONTROL Administration > Konfigurationen > Eingabeformulare]** des Explorers von Adobe Campaign die folgenden Informationen zum Workflow-Formular hinzugefügt:

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

Die Personalisierung von Eingabeformularen sollte erfahrenen Personen vorbehalten bleiben.
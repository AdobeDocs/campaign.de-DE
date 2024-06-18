---
product: campaign
title: Inkrementelle Abfrage
description: Erfahren Sie mehr über die Workflow-Aktivität "Inkrementelle Abfrage".
feature: Workflows, Targeting Activity
role: User
exl-id: 3e9f92c3-080f-441b-a15a-2ec9d056d1f9
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Inkrementelle Abfrage{#incremental-query}



Inkrementelle Abfragen ermöglichen die regelmäßig wiederkehrende Auswahl einer Zielgruppe nach bestimmten Kriterien unter Ausschluss der Population, die in früheren Durchgängen bereits aufgrund dieser Kriterien ausgewählt wurde.

Die zuvor ausgewählten Populationen werden nach Workflow-Instanz und nach Aktivität gespeichert. Dies bedeutet, dass zwei gestartete Workflows, die auf derselben Vorlage basieren, nicht den gleichen Verlauf aufweisen. Zwei auf derselben inkrementellen Abfrage basierende Aufgaben innerhalb einer Workflow-Instanz hingegen teilen sich ein und denselben Verlauf.

Die Konfiguration der Abfrage entspricht der von Standardabfragen, aber die Ausführung wird geplant.

**Verwandte Themen:**

* [Anwendungsfall: Vierteljährliches Listen-Update mithilfe einer inkrementellen Abfrage](quarterly-list-update.md)
* [Abfragen erstellen](query.md#creating-a-query)

>[!CAUTION]
>
>Wenn das Ergebnis der inkrementellen Abfrage bei einer ihrer Ausführungen gleich **0** ist, wird der Workflow bis zur nächsten geplanten Ausführung der Abfrage ausgesetzt. Die auf die inkrementelle Abfrage folgenden Transitionen und Aktivitäten werden somit nicht vor der nächsten Ausführung aktiviert.

Gehen Sie dazu wie folgt vor:

1. Aktivieren Sie auf der Registerkarte **[!UICONTROL Planung und Verlauf]** die Option **[!UICONTROL Ausführung planen]**. Nach Erstellung bleibt die Aufgabe aktiv, aber sie startet nur zu den in der Planung angegebenen Zeitpunkten, um die Abfrage auszuführen. Wenn die Option deaktiviert wurde, wird die Abfrage **einmalig und sofort** ausgeführt.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Ändern...]**.

   Im sich öffnenden **[!UICONTROL Planungsassistent]**-Fenster können Sie den Ausführungsrhythmus und den Gültigkeitszeitraum definieren.

   ![](assets/s_user_segmentation_wizard_11.png)

1. Klicken Sie zur Bestätigung Ihrer Eingaben auf **[!UICONTROL Beenden]**.

   ![](assets/s_user_segmentation_wizard_valid.png)

1. Im unteren Bereich des Tabs **[!UICONTROL Planung &amp; Verlauf]** können Sie nähere Angaben zum Verlauf machen.

   ![](assets/edit_request_inc.png)

   * **[!UICONTROL Verlaufsumfang (Tage)]**

     Bereits berücksichtigte Empfänger bleiben die angegebene Anzahl an Tagen im Verlauf. Bei Angabe von &quot;0&quot; werden Empfänger nie aus dem Verlauf gelöscht.

   * **[!UICONTROL Verlauf beim Start beibehalten]**

     Bei Auswahl dieser Option wird der Verlauf bei der Aktivierung der Aktivität nicht gelöscht.

   * **[!UICONTROL Name der SQL-Tabelle]**

     Mithilfe dieses Felds kann die Standard-SQL-Tabelle, die den Verlauf enthält, überschrieben werden.

## Ausgabeparameter {#output-parameters}

* tableName
* schema
* recCount

Anhand der drei Werte lässt sich die durch die Abfrage ermittelte Population identifizieren. **[!UICONTROL tableName]** ist der Name der Tabelle, welche die Kennungen der Zielgruppe enthält, **[!UICONTROL schema]** ist das Schema der Population, (in der Regel nms:recipient) und **[!UICONTROL recCount]** ist die Anzahl der Elemente in der Tabelle.

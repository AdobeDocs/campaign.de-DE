---
product: campaign
title: Abfrage mit Gruppierungsverwaltung
description: Erfahren Sie, wie Sie Abfragen mit Hilfe der Gruppierungsverwaltung durchführen können
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 6fc4ef67-5d75-4c8c-8bcc-41e3ed155ca2
TQID: https://experienceleague.adobe.com/-OBJg0XeJowHsyunWoCdl6K434cs-p08xMFRKJmz--4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 302
ht-degree: 100%

---

# Abfrage mit Gruppierungsverwaltung {#querying-using-grouping-management}



Im folgenden Beispiel werden die E-Mail-Domains gesucht, die bei früheren Sendungen mehr als 30-mal kontaktiert wurden.

* Welche Tabelle soll ausgewählt werden?

  Die Empfängertabelle (nms:recipient)

* Felder, die als Ausgabespalten verwendet werden sollen?

  E-Mail-Domain und Primärschlüssel (mit Zählung)

* Nach welchen Kriterien werden die Daten gruppiert?

  Nach E-Mail-Domain mit einer Anzahl von über 30 Primärschlüsseln. Dieser Vorgang wird mit der Option **[!UICONTROL Group by + Having]** ausgeführt. **[!UICONTROL Group by + Having]** ermöglicht die Gruppierung von Daten („group by“) und die Auswahl dessen, was gruppiert ist („having“).

Gehen Sie wie folgt vor:

1. Öffnen Sie das **[!UICONTROL generische Abfragetool]** und wählen Sie die Empfängertabelle (**nms:recipient**).

   ![](assets/query_editor_02.png)

1. Im Fenster **[!UICONTROL Zu extrahierende Daten]** wählen Sie die Felder **[!UICONTROL E-Mail-Domain]** und **[!UICONTROL Primärschlüssel]** aus. Führen Sie eine Zählung des Felds **[!UICONTROL Primärschlüssel]** durch.

1. Kreuzen Sie die Option **[!UICONTROL Gruppierungen verwalten (GROUP BY + HAVING)]** an.

   ![](assets/query_editor_nveau_29.png)

1. Ordnen Sie im Fenster **[!UICONTROL Sortierung]** die E-Mail-Domains in absteigender Reihenfolge. Kreuzen Sie hierfür in der Spalte **[!UICONTROL Absteigende Sortierung]** die Option **[!UICONTROL Ja]** an. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/query_editor_nveau_70.png)

1. Wählen Sie dann im Fenster **[!UICONTROL Datenfilter]** die Option **[!UICONTROL Filterbedingungen]**. Wechseln Sie zum Fenster **[!UICONTROL Zielelemente]** und klicken Sie auf **[!UICONTROL Weiter]**.
1. Klicken Sie im Fenster **[!UICONTROL Gruppierung der Daten]** auf **[!UICONTROL Hinzufügen]** und wählen Sie das Feld **[!UICONTROL E-Mail-Domain]** aus.

   Die Gruppierung (GROUP BY) erfolgt an dieser Stelle. Das Fenster wird nur angezeigt, wenn die Option **[!UICONTROL Gruppierungen verwalten (GROUP BY + HAVING)]** angekreuzt wurde.

   ![](assets/query_editor_blocklist_04.png)

1. Geben Sie anschließend im Fenster **[!UICONTROL Gruppierbedingung]** eine Primärschlüsselanzahl von über 30 an. So werden nur die E-Mail-Domains ausgegeben, die mehr als 30-mal kontaktiert wurden.

   Dieses Fenster wird ebenfalls nur angezeigt, wenn die Option **[!UICONTROL Gruppierungen verwalten (GROUP BY + HAVING)]** angekreuzt wurde. Hier erfolgt die Filterung des Ergebnisses der Gruppierung (HAVING).

   ![](assets/query_editor_blocklist_05.png)

1. Da in unserem Beispiel keine spezielle Formatierung erforderlich ist, können Sie im Fenster **[!UICONTROL Datenformatierung]** direkt auf **[!UICONTROL Weiter]** klicken.
1. Klicken Sie anschließend auf **[!UICONTROL Datenvorschau starten]**. Das Ergebnis zeigt nur eine E-Mail-Domain, die mehr als 30-mal kontaktiert wurde.

   ![](assets/query_editor_blocklist_06.png)

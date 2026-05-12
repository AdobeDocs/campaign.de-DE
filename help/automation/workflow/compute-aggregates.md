---
product: campaign
title: Durchführen der Aggregat-Berechnung
description: Erfahren Sie, wie Sie Aggregate in Abfragen berechnen
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 00e564b5-3c8e-45d4-b240-c872a8b8ccb6
TQID: https://experienceleague.adobe.com/ubtfw1irqKiD8mrRqD2L3UI-kGwhdBiSmBTjIfp-4NE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 245
ht-degree: 62%

---

# Durchführen der Aggregat-Berechnung {#performing-aggregate-computing}

In diesem Beispiel wird die Anzahl der Empfänger gesucht, die in Berlin wohnen, geordnet nach Geschlecht.

* Welche Tabelle soll ausgewählt werden?

  Die Empfängertabelle (**nms:recipient**)

* Welche Felder sollen in der Ausgabespalte ausgewählt werden?

  Primärschlüssel (mit Zählung) und Geschlecht

* Nach welchen Kriterien sind die Empfänger zu filtern?

  Empfänger, die in Berlin wohnhaft sind

Gehen Sie wie folgt vor:

1. Konfigurieren Sie im Fenster **[!UICONTROL Zu extrahierende Daten]** wie im vorangehenden Beispiel eine Primärschlüssel-Zählung. Fügen Sie das Feld **[!UICONTROL Geschlecht]** zu den Ausgabespalten hinzu. Kreuzen Sie die Option **[!UICONTROL Gruppieren]** der Spalte **[!UICONTROL Geschlecht]** an. Auf diese Weise werden die Empfänger nach Geschlecht angeordnet.

   ![](assets/query_editor_nveau_27.png)

1. In diesem Beispiel ist keine **[!UICONTROL Sortierung]** erforderlich. Sie können somit direkt auf **[!UICONTROL Weiter]** klicken.
1. Konfigurieren Sie einen Datenfilter. Hier möchten Sie die Auswahl auf Kontakte beschränken, die in London leben.

   ![](assets/query_editor_22.png)

   >[!NOTE]
   >
   >Bei Werten wird zwischen Groß- und Kleinschreibung unterschieden. Wenn der Wert „London“ in die Bedingung ohne Großbuchstaben eingegeben wird und die Empfängerliste das Wort „London“ mit einem Großbuchstaben enthält, schlägt die Abfrage fehl.

1. Auch im Fenster **[!UICONTROL Datenformatierung]** können Sie direkt auf **[!UICONTROL Weiter]** klicken.
1. Klicken Sie anschließend auf **[!UICONTROL Datenvorschau starten]**.

   Es gibt drei separate Werte für jede Sortierung nach Geschlecht: **2** für weiblich, **1** für männlich und **0** wenn das Geschlecht unbekannt ist. In diesem Beispiel enthält die Liste 10 Frauen, 16 Männer und 2 Personen, deren Geschlecht nicht bekannt ist.

   ![](assets/query_editor_agregat_04.png)

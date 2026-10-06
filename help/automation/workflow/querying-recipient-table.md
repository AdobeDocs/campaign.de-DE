---
product: campaign
title: Abfrage der Empfängertabelle
description: Erfahren Sie, wie Sie die Empfängertabelle abfragen
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 7f859ce9-7ab8-46e1-8bd6-43aaffe30da2
TQID: 'https://experienceleague.adobe.com/puAVnnwm21KiCWWCR5ZaexXnqysPINAkWAlcnR-gr1g'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 100%
---
# Abfrage der Empfängertabelle {#querying-recipient-table}



In diesem Beispiel werden die Namen und E-Mail-Adressen der Empfänger gesucht, deren E-Mail-Domain &quot;web.de&quot; ist und die nicht in Berlin wohnen.

* Welche Tabelle soll ausgewählt werden?

  Die Empfängertabelle (nms:recipient)

* Felder, die als Ausgabespalten verwendet werden sollen

  E-Mail, Name, Wohnort und Kundennummer

* Nach welchen Kriterien sind die Empfänger zu filtern?

  Nach Wohnort und E-Mail-Domain

* Wird das Ergebnis sortiert?

  Ja, nach **[!UICONTROL Kundennummer]** und **[!UICONTROL Nachname]**.

Gehen Sie wie folgt vor:

1. Klicken Sie auf **[!UICONTROL Tools > Generischer Abfrage-Editor…]** und wählen Sie die Tabele **Empfänger** (**nms:recipient**). Klicken Sie nun auf **[!UICONTROL Weiter]**.
1. Wählen Sie: **[!UICONTROL Nachname]**, **[!UICONTROL Vorname]**, **[!UICONTROL E-Mail]**, **[!UICONTROL Ort]** und **[!UICONTROL Kundennummer]**. Diese Felder werden zu **[!UICONTROL Ausgabespalten]**. Klicken Sie nun auf **[!UICONTROL Weiter]**.

   ![](assets/query_editor_03.png)

1. Sortieren Sie die Spalten, um sie in der richtigen Reihenfolge anzuzeigen. Hier möchten wir die Kundennummer in absteigender und die Namen in alphabetischer Reihenfolge sortieren. Klicken Sie nun auf **[!UICONTROL Weiter]**.

   ![](assets/query_editor_04.png)

1. Wählen Sie im Fenster **[!UICONTROL Datenfilter]** die Option **[!UICONTROL Filterbedingungen]** aus, um die Abfrageergebnisse einzuschränken, und klicken Sie auf **[!UICONTROL Weiter]**.
1. Das Fenster **[!UICONTROL Zielelement]** dient der Konfiguration der Filterbedingungen.

   Definieren Sie die folgende Filterbedingung: Empfangende, deren E-Mail-Domain gleich „orange.co.uk“ ist. Wählen Sie also **E-Mail-Domain (@domain)** in der Spalte **[!UICONTROL Ausdruck]**, **gleich** in der Spalte **[!UICONTROL Operator]** und geben Sie „orange.co.uk“ in der Spalte **[!UICONTROL Wert]** ein.

   ![](assets/query_editor_05.png)

1. Bei Bedarf können Sie auf die Schaltfläche **[!UICONTROL Werteverteilung]** klicken, um eine Verteilung basierend auf der E-Mail-Domain interessierter Personen anzuzeigen. Für jede E-Mail-Domain in der Datenbank ist ein Prozentsatz verfügbar. Andere Domains als „orange.co.uk“ werden angezeigt, bis der Filter angewendet wird.

   Die Zusammenfassung der Abfrage wird unten im Fenster angezeigt, hier also **E-Mail-Domain gleich web.de**.

1. Klicken Sie nun auf **[!UICONTROL Vorschau]**, um die Ergebnisse der Abfrage zum bisherigen Zeitpunkt anzusehen. Es werden nur Empfänger angezeigt, deren E-Mail-Domain &quot;web.de&quot; ist.

   ![](assets/query_editor_nveau_17.png)

1. Ändern Sie die Abfrage, um nur die Empfänger anzuzeigen, die nicht in Berlin wohnen.

   Wählen Sie **[!UICONTROL Ort (location/@city)]** in der Spalte **[!UICONTROL Ausdruck]**, den Operator **[!UICONTROL ungleich]** und geben Sie **[!UICONTROL Berlin]** in der Spalte **[!UICONTROL Wert]** ein.

   ![](assets/query_editor_08.png)

1. Dadurch gelangen Sie zum Fenster **[!UICONTROL Datenformatierung]**. Überprüfen Sie die Spaltenreihenfolge. Verschieben Sie die Spalte „Ort“ nach oben unter die Spalte „Kundennummer“.

   Entfernen Sie das Kreuz aus der &quot;Vorname&quot;-Checkbox, um dieses Feld im Ergebnis nicht anzuzeigen.

   ![](assets/query_editor_nveau_15.png)

1. Klicken Sie im Fenster **[!UICONTROL Datenvorschau]** auf **[!UICONTROL Datenvorschau starten]**. Diese Funktion berechnet das Ergebnis der Abfrage.

   Im Tab **[!UICONTROL Ergebnis in Spalten]** wird das Ergebnis der Abfrage in Spaltenform angezeigt.

   Das Ergebnis zeigt alle Empfangenden mit der E-Mail-Domain „orange.co.uk“, die nicht in London leben. Die Spalte „Vorname“ wird nicht angezeigt, da sie im vorherigen Schritt deaktiviert wurde. Die Kundennummern werden in absteigender Reihenfolge sortiert.

   ![](assets/query_editor_nveau_12.png)

   Im Tab **[!UICONTROL XML-Ergebnis]** können Sie das Ergebnis im XML-Format einsehen.

   ![](assets/query_editor_nveau_13.png)

   Auf der Registerkarte **[!UICONTROL Erzeugte SQL-Abfragen]** wird das Abfrageergebnis im SQL-Format angezeigt.

   ![](assets/query_editor_nveau_14.png)

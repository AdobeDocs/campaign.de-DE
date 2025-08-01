---
product: campaign
title: Abfrage der Empfängertabelle
description: Erfahren Sie, wie Sie die Empfängertabelle abfragen
feature: Query Editor
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 7f859ce9-7ab8-46e1-8bd6-43aaffe30da2
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: ht
source-wordcount: '452'
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

1. Klicken Sie auf **[!UICONTROL Werkzeuge > Generisches Abfragetool...]** und wählen Sie die Tabelle **Empfängerinnen und Empfänger** (**nms:recipient**). Klicken Sie nun auf **[!UICONTROL Weiter]**.
1. Wählen Sie: **[!UICONTROL Nachname]**, **[!UICONTROL Vorname]**, **[!UICONTROL E-Mail]**, **[!UICONTROL Ort]** und **[!UICONTROL Kundennummer]**. Diese Felder werden zu **[!UICONTROL Ausgabespalten]**. Klicken Sie nun auf **[!UICONTROL Weiter]**.

   ![](assets/query_editor_03.png)

1. Sortieren Sie die Spalten in der gewünschten Anzeigereihenfolge, hier beispielsweise die Kundennummern in absteigender und die Nachnamen in alphabetischer Reihenfolge. Klicken Sie nun auf **[!UICONTROL Weiter]**.

   ![](assets/query_editor_04.png)

1. Wählen Sie im Fenster **[!UICONTROL Datenfilter]** die Option **[!UICONTROL Filterbedingungen]** aus, um die Abfrageergebnisse einzuschränken, und klicken Sie auf **[!UICONTROL Weiter]**.
1. Das Fenster **[!UICONTROL Zielelement]** dient der Konfiguration der Filterbedingungen.

   Definieren Sie die folgende Filterbedingung: Empfangende, deren E-Mail-Domain gleich „orange.co.uk“ ist. Wählen Sie also **E-Mail-Domain (@domain)** in der Spalte **[!UICONTROL Ausdruck]**, **gleich** in der Spalte **[!UICONTROL Operator]** und geben Sie „orange.co.uk“ in der Spalte **[!UICONTROL Wert]** ein.

   ![](assets/query_editor_05.png)

1. Bei Bedarf können Sie die Schaltfläche **[!UICONTROL Werteverteilung]** auswählen. Dann werden die in der Datenbank enthaltenen E-Mail-Domains und deren Häufigkeit angezeigt. Auch alle anderen Domains werden angezeigt, da der Filter noch nicht aktiv ist.

   Die Zusammenfassung der Abfrage wird unten im Fenster angezeigt, hier also **E-Mail-Domain gleich web.de**.

1. Klicken Sie nun auf **[!UICONTROL Vorschau]**, um die Ergebnisse der Abfrage zum bisherigen Zeitpunkt anzusehen. Es werden nur Empfänger angezeigt, deren E-Mail-Domain &quot;web.de&quot; ist.

   ![](assets/query_editor_nveau_17.png)

1. Ändern Sie die Abfrage, um nur die Empfänger anzuzeigen, die nicht in Berlin wohnen.

   Wählen Sie **[!UICONTROL Ort (location/@city)]** in der Spalte **[!UICONTROL Ausdruck]**, den Operator **[!UICONTROL ungleich]** und geben Sie **[!UICONTROL Berlin]** in der Spalte **[!UICONTROL Wert]** ein.

   ![](assets/query_editor_08.png)

1. Im Fenster **[!UICONTROL Datenformatierung]** können Sie die Anzeigereihenfolge der Ausgabespalten festlegen. Benutzen Sie die Pfeile, um die Zeile &quot;Ort&quot; nach oben unmittelbar unter &quot;Kundennummer&quot; zu verschieben.

   Entfernen Sie das Kreuz aus der &quot;Vorname&quot;-Checkbox, um dieses Feld im Ergebnis nicht anzuzeigen.

   ![](assets/query_editor_nveau_15.png)

1. Im letzten Schritt, der **[!UICONTROL Datenvorschau]**, wird das Abfrageergebnis berechnet. Klicken Sie hierfür auf **[!UICONTROL Datenvorschau starten]**.

   Im Tab **[!UICONTROL Ergebnis in Spalten]** wird das Ergebnis der Abfrage in Spaltenform angezeigt.

   Die Ergebnistabelle enthält alle Empfänger, deren E-Mail-Domain &quot;web.de&quot; ist, und die nicht in Berlin wohnen. Die Vornamen werden nicht angezeigt, da diese Spalte im verangehenden Schritt abgewählt wurde. Die Kundennummern wurden in absteigender Reihenfolge sortiert.

   ![](assets/query_editor_nveau_12.png)

   Im Tab **[!UICONTROL XML-Ergebnis]** können Sie das Ergebnis im XML-Format einsehen.

   ![](assets/query_editor_nveau_13.png)

   Auf der Registerkarte **[!UICONTROL Erzeugte SQL-Abfragen]** wird das Abfrageergebnis im SQL-Format angezeigt.

   ![](assets/query_editor_nveau_14.png)

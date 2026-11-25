---
product: campaign
title: Abfrage mit einer Viele-zu-viele-Beziehung
description: Erfahren Sie, wie Sie mit einer Viele-zu-viele-Beziehung Abfragen durchführen können
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: c320054d-7f67-4b12-aaa7-785945bf0c18
TQID: 'https://experienceleague.adobe.com/BnWR5Pz41h-CeMuyGKXKBmhRHGcuSShWerJpOWAN7W0'
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
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 77%
---
# Abfrage mit einer Viele-zu-viele-Beziehung {#querying-using-a-many-to-many-relationship}



In diesem Beispiel werden die Empfangenden gesucht, die innerhalb der letzten sieben Tage nicht kontaktiert wurden. Diese Abfrage betrifft alle Sendungen.

Außerdem wird die Konfiguration eines von einem Sammlungselement (orangefarbener Knoten) ausgehenden Filters gezeigt. Sammlungselemente stehen im Fenster **[!UICONTROL Feldauswahl]** zur Verfügung.

* Welche Tabelle soll ausgewählt werden?

  Die Empfängertabelle (**nms:recipient**)

* Felder, die als Ausgabespalten verwendet werden sollen?

  Primärschlüssel, Nachname, Vorname und E-Mail

* Nach welchen Kriterien sind die Empfänger zu filtern?

  Nach den Versandlogs der Empfänger, bis 7 Tage vor dem Tagesdatum

Gehen Sie wie folgt vor:

1. Öffnen Sie den generischen Abfrage-Editor und wählen Sie die Empfängertabelle **[!UICONTROL (nms:recipient)]** aus.
1. Wählen Sie im Fenster **[!UICONTROL Zu extrahierende Daten]** die Felder **[!UICONTROL Primärschlüssel]**, **[!UICONTROL Vorname]**, **[!UICONTROL Nachname]** und **[!UICONTROL E-Mail]**.

   ![Daten zum Extrahieren eines Fensters mit Primärem Schlüssel, Vorname, Nachname und als Ausgabespalten aufgeführter E-Mail](assets/query_editor_nveau_33.png)

1. Ordnen Sie im Sortierfenster die Nachnamen in alphabetischer Reihenfolge.

   ![Sortierungsfenster mit der Sortieroption, die für die Nachnamenspalte auf Ja festgelegt ist](assets/query_editor_nveau_34.png)

1. Wählen Sie dann im **[!UICONTROL Datenfilter]**-Fenster die Option **[!UICONTROL Filterbedingungen]**.
1. Anschließend wird im Fenster **[!UICONTROL Zielelement]** in zwei Schritten die gesuchte Filterbedingung zum Extrahieren von Profilen ohne Trackinglogs in den letzten 7 Tagen erstellt. Das Element, das Sie auswählen müssen, ist eine n:n-Relation.

   * Wählen Sie also im **[!UICONTROL Ausdruck]**-Feld das durch einen orangefarbenen Knoten symbolisierte Sammlungselement **[!UICONTROL Versandlogs der Empfänger (broadLog)]**.

     ![Feld zur Auswahl des Fensters mit ausgewähltem Sammlungselement der Empfänger-Versandlogs (broadLog)](assets/query_editor_nveau_67.png)

     Wählen Sie den Operator **[!UICONTROL existiert nicht als]**. Sie müssen keinen zweiten Wert in dieser Zeile auswählen.

   * Der Inhalt der zweiten Filterbedingung hängt von der ersten ab. Hier wird das Feld **[!UICONTROL Ereignisdatum]** aus der Tabelle **[!UICONTROL Versandlogs der Empfänger]** vorgeschlagen, da eine Relation mit dieser Tabelle besteht.

     ![Feld zur Auswahl eines Fensters, in dem die Felder mit den Versandlogs der Empfänger aufgelistet sind, mit hervorgehobener Option „Ereignisdatum (@eventDate)](assets/query_editor_nveau_36.png)

     Wählen Sie also **[!UICONTROL Ereignisdatum]** und den Operator **[!UICONTROL größer als oder gleich]** aus. Wählen Sie den Wert **[!UICONTROL DaysAgo (7)]** aus. Klicken Sie hierzu im Feld **[!UICONTROL Wert]** auf **[!UICONTROL Ausdruck bearbeiten]**. Wählen Sie im Fenster **[!UICONTROL Formeltyp]** die Option **[!UICONTROL Datumsfunktionen]** und **[!UICONTROL Aktuelles Datum abzüglich n Tage]**. Geben Sie den Wert „7“ ein.

     ![Fenster „Formeltyp“ mit dem Wert „Prozess am“ und „Aktuelles Datum abzüglich n Tage“ auf 7 gesetzt](assets/query_editor_nveau_37.png)

     Hiermit ist die Konfiguration der Filterbedingung abgeschlossen.

     ![Fenster des Zielelements mit dem Filter: Es gibt keine Versandlogs wie das Ereignisdatum, das 7 Tage davor oder danach liegt](assets/query_editor_nveau_38.png)

1. Im Fenster **[!UICONTROL Datenformatierung]** können Sie die Anzeige dahingehend ändern, dass alle Nachnamen in Großbuchstaben angezeigt werden. Klicken Sie hierfür in der Zeile **[!UICONTROL Nachname]** auf **[!UICONTROL Schreibweise]** und wählen Sie **[!UICONTROL Alles in Großbuchstaben]** aus der Dropdownliste.

   ![Datenformatierungsfenster mit hervorgehobener Option „Umwandlung für Nachnamen in Großbuchstaben wechseln“](assets/query_editor_nveau_39.png)

1. Verwenden Sie die Funktion **[!UICONTROL Berechnetes Feld hinzufügen]**, um eine neue Spalte zu erstellen.

   Fügen Sie in diesem Beispiel ein berechnetes Feld mit dem Vor- und Nachnamen der Empfangenden in einer Spalte hinzu. Klicken Sie also auf **[!UICONTROL Berechnetes Feld hinzufügen]**. Geben Sie im Fenster **[!UICONTROL Definition eines berechneten Export-Feldes]** einen Titel und einen internen Namen für die neue Spalte ein. Wählen Sie den Typ **[!UICONTROL JavaScript-Ausdruck]** aus der Dropdown-Liste. Geben Sie folgenden Ausdruck ein:

   ```
   var rep = source._firstName+" - "+source._lastName
   return rep
   ```

   ![Ausdruckseditor von JavaScript für die Spalte Vorname - Nachname mit dem Skript, das beide Felder verkettet](assets/query_editor_nveau_40.png)

   Klicken Sie auf **[!UICONTROL OK]**. Die Konfiguration des **[!UICONTROL Datenformatierung]**-Fensters ist abgeschlossen.

   Weiterführende Informationen zum Hinzufügen berechneter Felder finden Sie in diesem Abschnitt.

1. Das Ergebnis wird im Fenster **[!UICONTROL Datenvorschau]** angezeigt. Empfangende, die in den letzten 7 Tagen nicht kontaktiert wurden, werden in alphabetischer Reihenfolge angezeigt. Namen werden in Großbuchstaben angezeigt und die Spalte mit Vor- und Nachnamen wurde erstellt.

   ![Datenvorschau-Fenster, in dem Empfänger mit der hinzugefügten Spalte Vorname - Nachname aufgelistet werden](assets/query_editor_nveau_41.png)

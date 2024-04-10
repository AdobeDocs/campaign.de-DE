---
product: campaign
title: Abfrage mit einer Viele-zu-viele-Beziehung
description: Erfahren Sie, wie Sie mit einer Viele-zu-viele-Beziehung Abfragen durchführen können
feature: Query Editor
role: User, Data Engineer
exl-id: c320054d-7f67-4b12-aaa7-785945bf0c18
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 64%

---

# Abfrage mit einer Viele-zu-viele-Beziehung {#querying-using-a-many-to-many-relationship}



In diesem Beispiel werden die Empfänger gesucht, die innerhalb der letzten sieben Tage nicht kontaktiert wurden.

Außerdem wird die Konfiguration eines von einem Sammlungselement (orangefarbener Knoten) ausgehenden Filters gezeigt. Auf Sammlungselemente kann im Fenster **[!UICONTROL Feldauswahl]** zugegriffen werden.

* Welche Tabelle soll ausgewählt werden?

  Die Empfängertabelle (**nms:recipient**)

* Felder, die als Ausgabespalten verwendet werden sollen?

  Primärschlüssel, Nachname, Vorname und E-Mail

* Nach welchen Kriterien sind die Empfänger zu filtern?

  Nach den Versandlogs der Empfänger, bis 7 Tage vor dem Tagesdatum

Gehen Sie wie folgt vor:

1. Öffnen Sie das generische Abfragetool und wählen Sie die Empfängertabelle (**[!UICONTROL nms:recipient]**).
1. Wählen Sie im Fenster **[!UICONTROL Zu extrahierende Daten]** die Felder **[!UICONTROL Primärschlüssel]**, **[!UICONTROL Vorname]**, **[!UICONTROL Nachname]** und **[!UICONTROL E-Mail]**.

   ![](assets/query_editor_nveau_33.png)

1. Ordnen Sie im Sortierfenster die Nachnamen in alphabetischer Reihenfolge.

   ![](assets/query_editor_nveau_34.png)

1. Wählen Sie dann im **[!UICONTROL Datenfilter]**-Fenster die Option **[!UICONTROL Filterbedingungen]**.
1. Anschließend wird im Fenster **[!UICONTROL Zielelement]** in zwei Schritten die gesuchte Filterbedingung erstellt. Es handelt sich bei dem auszuwählenden Kollektionselement um eine n:n-Relation.

   * Wählen Sie also im **[!UICONTROL Ausdruck]**-Feld das durch einen orangefarbenen Knoten symbolisierte Sammlungselement **[!UICONTROL Versandlogs der Empfänger (broadLog)]**.

     ![](assets/query_editor_nveau_67.png)

     In diesem Fall ist der zu wählende Operator **[!UICONTROL nicht wie]** und es wird kein Wert angegeben.

   * Der Inhalt der zweiten Filterbedingung hängt von der ersten ab. Hier gilt Folgendes **[!UICONTROL Ereignisdatum]** Das Feld wird direkt im **[!UICONTROL Versandlogs der Empfänger]** Tabelle, da ein Link zu dieser Tabelle vorhanden ist.

     ![](assets/query_editor_nveau_36.png)

     Auswählen **[!UICONTROL Ereignisdatum]** mit dem **[!UICONTROL Größer oder gleich]** Operator. Wählen Sie die **[!UICONTROL Vor Tagen (7)]** Wert. Klicken Sie dazu auf **[!UICONTROL Ausdruck bearbeiten]** in der **[!UICONTROL Wert]** Feld. In der **[!UICONTROL Formeltyp]** Fenster, auswählen **[!UICONTROL Verarbeitung nach Daten]** und **[!UICONTROL Aktuelles Datum abzüglich n Tage]**, wobei „7“ als Wert angegeben wird.

     ![](assets/query_editor_nveau_37.png)

     Hiermit ist die Konfiguration der Filterbedingung abgeschlossen.

     ![](assets/query_editor_nveau_38.png)

1. In der **[!UICONTROL Datenformatierung]** Fenster, die Nachnamen werden in Großbuchstaben geändert. Klicken Sie auf die Schaltfläche **[!UICONTROL Nachname]** Zeile in der **[!UICONTROL Transformation]** Spalte und auswählen **[!UICONTROL Großschreibung verwenden]** im Dropdown-Menü.

   ![](assets/query_editor_nveau_39.png)

1. Verwenden Sie die Funktion **[!UICONTROL Berechnetes Feld hinzufügen]**, um eine neue Spalte zu erstellen.

   In diesem Beispiel fügen Sie ein berechnetes Feld mit dem Vor- und Nachnamen der Empfänger in einer einzigen Spalte hinzu. Klicken Sie auf die Schaltfläche **[!UICONTROL Berechnetes Feld hinzufügen]** Funktion. In der **[!UICONTROL Berechnete Felddefinition exportieren]** ein, geben Sie einen Titel und einen internen Namen ein und wählen Sie **[!UICONTROL JavaScript-Ausdruck]** Typ. Geben Sie dann folgenden Ausdruck ein:

   ```
   var rep = source._firstName+" - "+source._lastName
   return rep
   ```

   ![](assets/query_editor_nveau_40.png)

   Klick **[!UICONTROL OK]**. Die **[!UICONTROL Datenformatierung]** Das Fenster ist konfiguriert.

   Weiterführende Informationen zum Hinzufügen berechneter Felder finden Sie in diesem Abschnitt.

1. Im Fenster **[!UICONTROL Datenvorschau]** können Sie das Ergebnis prüfen. Es werden die Empfänger angezeigt, die innerhalb der letzten sieben Tage vor dem aktuellen Tagesdatum nicht kontaktiert worden sind. Die Nachnamen sind in Großbuchstaben und alphabetisch geordnet. Eine weitere Spalte zeigt Vor- und Nachnamen in einem Feld an.

   ![](assets/query_editor_nveau_41.png)

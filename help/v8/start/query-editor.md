---
title: Erstellen von Abfragen in Campaign v8
description: Erfahren Sie, wie Sie Abfragen erstellen
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: 46f97303adf21e88aaa3417c6596dcb62e453c9e
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 88%

---

# Campaign-Datenbank abfragen

Das Abfragetool von Adobe Campaign ist auf mehreren Ebenen der Software zu finden: zum Erstellen einer Zielpopulation, zum Segmentieren von Kundinnen und Kunden, zum Extrahieren und Filtern von Trackinglogs, zum Erstellen von Filtern usw.

Mit dem Adobe Campaign-Abfragetool können Sie eine Datenbank mithilfe eines dedizierten Assistenten abfragen: dem generischen Abfragetool. Der Zugriff darauf erfolgt über das Menü **[!UICONTROL Werkzeuge > Generisches Abfragetool...]** Sie können damit in einer Datenbank gespeicherte Informationen extrahieren sowie organisieren, gruppieren, sortieren usw. So kann ein Benutzer beispielsweise die Empfängerinnen und Empfänger abrufen, die innerhalb eines bestimmten Zeitraums mehr als x-mal auf einen Link in einem Newsletter geklickt haben. Mit diesem Tool können Sie Ergebnisse nach Bedarf sammeln, sortieren und anzeigen.

Alle Abfrageoptionen in Adobe Campaign werden über dieses Tool gesteuert. So lassen sich z. B. Einschränkungsfilter im Tool erstellen und speichern. Derart angelegte Benutzerfilter sind dadurch auch in der Abfrageaktivität eines Zielgruppen-Workflows verfügbar.

Abfragen werden entweder mit den in der ausgewählten Tabelle enthaltenen Feldern oder mithilfe einer Formel durchgeführt.

Folgende Schritte sind auszuführen, um eine Abfrage in Adobe Campaign zu erstellen:

1. Wählen Sie die Arbeitstabelle aus. Siehe [1. Schritt - Tabelle auswählen](#step-1---choose-a-table).
1. Wählen Sie die zu extrahierenden Daten aus. Siehe [2. Schritt - Zu extrahierende Daten auswählen](#step-2---choose-data-to-extract).
1. Definieren Sie die Sortierreihenfolge für die Daten. Siehe [3. Schritt - Daten sortieren](#step-3---sort-data).
1. Filtern Sie die Daten. Siehe [4. Schritt - Daten filtern](#step-4---filter-data).
1. Formatieren Sie die Daten. Siehe [5. Schritt - Daten formatieren](#step-5---format-data).
1. Zeigen Sie das Ergebnis an. Siehe [6. Schritt - Vorschau der Daten anzeigen](#step-6---preview-data).


>[!NOTE]
>
>* Alle diese Schritte können im generischen Abfragetool durchgeführt werden. In anderen Anwendungskontexten sind u. U. gewisse Schritte nicht nötig.
>
>* Weitere Informationen zu Abfragen und deren Erstellung finden Sie in der [ zum Campaign-Workflow ](../../automation/workflow/query.md).

Um die Campaign-Datenbank abzufragen, öffnen Sie **Generischer Abfrage-Editor** und führen Sie die folgenden Schritte aus:

## &#x200B;1. Schritt – Tabelle auswählen {#step-1---choose-a-table}

Wählen Sie im Fenster **[!UICONTROL Dokumenttyp]** die Tabelle aus, die die Daten enthält, für die Sie eine Abfrage erstellen möchten. Filtern Sie die Daten bei Bedarf mithilfe des Filterfelds oder der Schaltfläche **[!UICONTROL Filter]**.

![](assets/query_editor_nveau_21.png)

## &#x200B;2. Schritt – Zu extrahierende Daten auswählen {#step-2---choose-data-to-extract}

Wählen Sie im Fenster **[!UICONTROL Zu extrahierende Daten]** die Felder aus, die als Spalten angezeigt werden sollen.

Wählen Sie beispielsweise: **[!UICONTROL Alter]**, **[!UICONTROL Primärschlüssel]**, **[!UICONTROL E-Mail-Domain]** und **[!UICONTROL Ort]**. Die Ergebnisse werden durch diese Auswahl bestimmt. Die Anzeigereihenfolge der Ausgabespalten kann mithilfe der blauen Pfeile an der rechten Seite des Fensters angepasst werden.

![](assets/query_editor_nveau_01.png)

Sie können einen Ausdruck definieren, indem Sie eine Formel oder eine Aggregatfunktion einfügen. Klicken Sie hierfür in der Spalte **[!UICONTROL Ausdruck]** auf **[!UICONTROL Ausdruck bearbeiten]**.

![](assets/query_editor_nveau_97.png)

Sie können Ausgabespaltendaten gruppieren: Aktivieren Sie dazu **[!UICONTROL Ja]** in der Spalte **[!UICONTROL Gruppe]** des Fensters **[!UICONTROL Zu extrahierende Daten]**. Diese Funktion erzeugt ein Ergebnis um die ausgewählte Gruppierungsachse. Ein Beispiel für eine Abfrage mit Gruppierung wird in [diesem Abschnitt](../../automation/workflow/query-delivery-info.md) dargestellt.

![](assets/query_editor_nveau_56.png)

* Die Funktion **[!UICONTROL Gruppierungen verwalten (GROUP BY + HAVING)]** erlaubt sowohl die Gruppierung (&quot;group by&quot;) als auch die Filterung der Daten, die gruppiert wurden (&quot;having&quot;). Sie wird auf die Ausgabespalten angewendet. Beispielsweise können die Empfänger nach Altersklassen gruppiert und nur die Klasse 35 bis 50 Jahre angezeigt werden.

  Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](../../automation/workflow/query-grouping-management.md).

* Die Funktion **[!UICONTROL Duplikate löschen (DISTINCT)]** dedupliziert die Daten in den Ausgabespalten, d. h. doppelte Einträge werden nicht angezeigt. Sollen z. B. Nachname, Vorname und E-Mail-Adresse der Empfänger angezeigt werden, wird für mehrere Datensätze mit identischem Nachnamen, Vornamen und E-Mail-Adresse nur ein Datensatz angezeigt.

## &#x200B;3. Schritt – Daten sortieren {#step-3---sort-data}

Im Fenster **[!UICONTROL Sortierung]** können Sie die Reihenfolge der Datenanzeige bestimmen. Mithilfe der Pfeile lässt sich die Spaltenreihenfolge verändern:

* Wenn Sie die Option **[!UICONTROL Sortierung]** ankreuzen, wird der Inhalt der jeweiligen Spalte von A bis Z sortiert (oder aufsteigend, wenn es sich um Zahlen handelt).
* Für eine Ordnung von Z bis A (oder absteigend, wenn es sich um Zahlen handelt) muss zusätzlich die Option **[!UICONTROL Absteigende Sortierung]** angekreuzt werden. Eine absteigende Sortierung bietet sich z. B. bei der Anzeige von Verkaufszahlen an, wo die meistverkauften Artikel am Listenanfang angezeigt werden sollen.

Im folgenden Beispiel werden die Daten nach dem Alter der Empfänger, vom jüngsten bis zum ältesten, sortiert.

![](assets/query_editor_nveau_57.png)

## &#x200B;4. Schritt – Daten filtern {#step-4---filter-data}

Um die Daten einzuschränken, bietet das Abfragetool die Möglichkeit, Filter zu verwenden.

Die angebotenen Filter hängen von der der Abfrage zugrunde liegenden Tabelle ab.

![](assets/query_editor_nveau_09.png)

Nach Auswahl der **[!UICONTROL Filterbedingungen]** gelangen Sie zum Abschnitt **[!UICONTROL Zielelemente]**. Hier können Sie festlegen, wie die anzuzeigenden Daten gefiltert werden sollen.

* Um einen neuen Filter zu erstellen, wählen Sie die Felder, Operatoren und Werte aus, die für die Erstellung der zu verifizierenden Formel erforderlich sind, sodass Daten ausgewählt werden können. Sie können auch mehrere Bedingungen kombinieren, wie auf [ Seite beschrieben](filter-conditions.md).
* Sie haben auch die Möglichkeit, zuvor erstellte Filter zu verwenden. Öffnen Sie die Dropdown-Liste der Schaltfläche **[!UICONTROL Hinzufügen]**, klicken Sie auf **[!UICONTROL Vordefinierter Filter]** und wählen Sie den gewünschten Filter aus.

  ![](assets/query_editor_15.png)

* Die im **[!UICONTROL Generischen Abfragetool]** erstellten Filter können in anderen Abfragen der Anwendung verwendet werden (und umgekehrt). Klicken Sie hierzu auf das Symbol **[!UICONTROL Speichern]**.

  >[!NOTE]
  >
  >Die Erstellung und Verwendung von Filtern wird im Kapitel [Filteroptionen](filter-conditions.md) erläutert.

In unten stehendem Beispiel sollen nur deutschsprachige Empfänger ausgewählt werden. Erstellen Sie also die Bedingung: Sprache **gleich** Deutsch.

![](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>Sie können direkt auf eine Option zugreifen, indem Sie die folgende Formel in das Feld **Wert** eingeben: **$(options:OPTION_NAME)**.

Durch Auswahl des Tabs **[!UICONTROL Vorschau]** können Sie das Ergebnis der Filterbedingung überprüfen. In unserem Beispiel werden alle deutschsprachigen Empfänger mit Nachname, Vorname und E-Mail-Adresse angezeigt.

![](assets/query_editor_nveau_98.png)

Für Benutzer, die diese Programmiersprache beherrschen, kann die **[!UICONTROL Entsprechende SQL-Abfrage]** angezeigt werden.

![](assets/query_editor_nveau_99.png)

## &#x200B;5. Schritt – Daten formatieren {#step-5---format-data}

Nach der Auswahl der Einschränkungsfilter gelangen Sie in das Fenster der **[!UICONTROL Datenformatierung]**. Hier können Sie die Anzeigereihenfolge der Ausgabespalten festlegen, die Schreibweise (Groß- oder Kleinschreibung) der Daten ändern oder die Spaltentitel anpassen. Außerdem besteht die Möglichkeit, berechnete Felder hinzuzufügen.

>[!NOTE]
>
>Weitere Informationen zu den Arten von berechneten Feldern finden Sie unter [Berechnete Felder erstellen](filter-conditions.md#creating-calculated-fields).

Eine nicht-angekreuzte Spalte wird nicht im Datenvorschaufenster angezeigt.

![](assets/query_editor_nveau_10.png)

In der Spalte **[!UICONTROL Schreibweise]** haben Sie die Möglichkeit, Groß- und Kleinschreibung zu verändern. Wählen Sie eine Zeile aus und klicken Sie in die Spalte **[!UICONTROL Schreibweise]**. Wählen Sie zwischen:

* **[!UICONTROL Alles in Kleinbuchstaben]**,
* **[!UICONTROL Alles in Großbuchstaben]**,
* **[!UICONTROL Ersten Buchstaben großschreiben]**.

![](assets/query_editor_nveau_42.png)

## &#x200B;6. Schritt – Vorschau der Daten anzeigen {#step-6---preview-data}

Im letzten Schritt, der **[!UICONTROL Datenvorschau]**, können Sie sich das Ergebnis der Abfrage ansehen. Wählen Sie hierfür **[!UICONTROL Datenvorschau starten]** aus. Das Ergebnis liegt in Spalten oder im XML-Format vor. Wählen Sie **[!UICONTROL Erzeugte SQL-Abfragen]** aus, um sich die SQL-Entsprechung der Abfrage anzusehen.

Im vorliegenden Beispiel wurden die Daten nach dem Alter der ausgewählten Empfänger in aufsteigender Reihenfolge geordnet.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>Standardmäßig werden in der **[!UICONTROL Datenvorschau]** die 200 ersten Zeilen angezeigt. Geben Sie einen anderen Wert im Feld **[!UICONTROL Angezeigte Zeilen]** ein und klicken Sie auf **[!UICONTROL Datenvorschau starten]**.



**Verwandte Themen** 

* [Workflow-Abfrageaktivität](../../automation/workflow/query.md)
* [Abfrage der Empfängertabelle](../../automation/workflow/querying-recipient-table.md)
* [Filterbedingungen](filter-conditions.md)
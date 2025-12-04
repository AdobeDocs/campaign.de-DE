---
title: Erstellen von Abfragen in Campaign v8
description: Erfahren Sie, wie Sie in der Client-Konsole von Campaign Abfragen erstellen.
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: edd495a377559007dad7158c9ab4a4917d89ae73
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 28%

---

# Campaign-Datenbank abfragen

Abfragen werden entweder mit den in der ausgewählten Tabelle enthaltenen Feldern oder mithilfe einer Formel durchgeführt.

Folgende Schritte sind auszuführen, um eine Abfrage in Adobe Campaign zu erstellen:

1. [Wählen Sie die Arbeitstabelle](#step-1---choose-a-table).
1. [Zu extrahierende Daten auswählen](#step-2---choose-data-to-extract).
1. [Definieren Sie den Datensortiermodus](#step-3---sort-data).
1. [Definieren Sie Datenfilteroptionen](#step-4---filter-data).
1. [Konfigurieren der Datenformatierung](#step-5---format-data).
1. [Vorschau der Abfrageergebnisse](#step-6---preview-data).

Alle diese Schritte sind im [generischen Abfrage-Editor](query-editor.md) verfügbar. Beim Erstellen einer Abfrage in einem anderen Kontext können einige Schritte fehlen. Weitere Informationen zu Abfragen finden Sie auch in der [Dokumentation zur Workflow-Abfrageaktivität](../../automation/workflow/query.md).


## &#x200B;1. Schritt – Tabelle auswählen {#step-1---choose-a-table}

Um die Campaign-Datenbank abzufragen, öffnen Sie **[Generischer Abfrage-Editor](query-editor.md)** und wählen Sie im Fenster **[!UICONTROL Dokumenttyp]** die Tabelle aus, die die abzufragenden Daten enthält.

![](assets/query_editor_nveau_21.png)

Filtern Sie die Daten bei Bedarf mithilfe des Filterfelds oder der Schaltfläche **[!UICONTROL Filter]**.

## &#x200B;2. Schritt – Zu extrahierende Daten auswählen {#step-2---choose-data-to-extract}

Wählen Sie auf dem **[!UICONTROL Zu extrahierende Daten]** die Felder aus, die Sie in die Ausgabe aufnehmen möchten. Diese Felder definieren die in den Ergebnissen angezeigten Spalten.

Sie können beispielsweise **[!UICONTROL Alter]**, **[!UICONTROL Primärer Schlüssel]**, **[!UICONTROL E-Mail-Domain]** und **[!UICONTROL Stadt]**. Die Ausgabe wird entsprechend dieser Auswahl strukturiert. Um die Reihenfolge der Spalten anzupassen, verwenden Sie die blauen Pfeile auf der rechten Seite des Fensters.

![](assets/query_editor_nveau_01.png)

Sie können einen Ausdruck ändern, indem Sie entweder eine Formel hinzufügen oder einen Prozess auf eine Aggregatfunktion anwenden. Um einen Ausdruck zu bearbeiten, klicken Sie auf das **[!UICONTROL Ausdruck]** und wählen Sie dann **[!UICONTROL Ausdruck bearbeiten]** aus.

![](assets/query_editor_nveau_97.png)

Sie können die in den Ausgabespalten angezeigten Daten gruppieren. Wählen Sie dazu **[!UICONTROL Ja]** in der Spalte **[!UICONTROL Gruppe]** des Fensters **[!UICONTROL Zu extrahierende Daten]** aus. Die Ergebnisse werden dann basierend auf der ausgewählten Gruppierungsachse aggregiert. Ein Beispiel für eine Abfrage mithilfe von Gruppierung finden Sie [diesem Abschnitt](../../automation/workflow/query-delivery-info.md).

![](assets/query_editor_nveau_56.png)

* Mit **[!UICONTROL Option Gruppierungen verwalten (GROUP BY + HAVING]** können Sie Ergebnisse gruppieren und Bedingungen auf diese Gruppen anwenden. Sie gilt für alle Felder in den Ausgabespalten. Beispielsweise können Sie damit Werte aus einer Ausgabespalte gruppieren und dann die Ergebnisse filtern, um nur bestimmte Informationen abzurufen, z. B. Empfänger zwischen 35 und 50 Jahren.

  Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](../../automation/workflow/query-grouping-management.md).

Mit **[!UICONTROL Option „Doppelte Zeilen entfernen (DISTINCT)]** werden identische Zeilen aus der Ausgabe entfernt (dedupliziert). Wenn Sie beispielsweise **Nachname**, **Vorname** und **E-Mail** als Ausgabespalten auswählen, werden alle Datensätze mit denselben Werten in allen drei Feldern als Duplikate betrachtet. In den Ergebnissen wird nur eine Instanz beibehalten, sodass jeder Kontakt nur einmal angezeigt wird.

## &#x200B;3. Schritt – Daten sortieren {#step-3---sort-data}

Im Fenster **[!UICONTROL Sortierung]** können Sie die Reihenfolge der Datenanzeige bestimmen. Mithilfe der Pfeile lässt sich die Spaltenreihenfolge verändern:

* Wenn Sie die Option **[!UICONTROL Sortierung]** ankreuzen, wird der Inhalt der jeweiligen Spalte von A bis Z sortiert (oder aufsteigend, wenn es sich um Zahlen handelt).
* Für eine Ordnung von Z bis A (oder absteigend, wenn es sich um Zahlen handelt) muss zusätzlich die Option **[!UICONTROL Absteigende Sortierung]** angekreuzt werden. Eine absteigende Sortierung bietet sich z. B. bei der Anzeige von Verkaufszahlen an, wo die meistverkauften Artikel am Listenanfang angezeigt werden sollen.

Im folgenden Beispiel werden die Daten nach dem Alter der Empfänger, vom jüngsten bis zum ältesten, sortiert.

![](assets/query_editor_nveau_57.png)

## &#x200B;4. Schritt – Daten filtern {#step-4---filter-data}

Mit dem Abfrage-Editor können Sie Daten filtern, um Ihre Ergebnisse einzugrenzen. Die verfügbaren Filter hängen von der Tabelle ab, die Sie abfragen.

![](assets/query_editor_nveau_09.png)

Nach Auswahl **[!UICONTROL Filterbedingungen]** wird der Abschnitt **[!UICONTROL Target-Elemente]** geöffnet. Hier können Sie die Regeln für das Filtern der zu erfassenden Daten definieren.

* Um einen neuen Filter zu erstellen, wählen Sie die Felder, Operatoren und Werte aus, die zum Erstellen der Bedingung erforderlich sind. Sie können auch mehrere Bedingungen kombinieren, wie [auf dieser Seite) &#x200B;](filter-conditions.md).

* Um einen vorhandenen Filter wiederzuverwenden, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**, wählen Sie **[!UICONTROL Vordefinierter Filter]** und wählen Sie den gewünschten Filter aus.

  ![](assets/query_editor_15.png)

Im **[!UICONTROL Generischen Abfrage-Editor]** erstellte Filter können in anderen Abfrageanwendungen wiederverwendet werden. Umgekehrt gilt dies auch. Um einen Filter für die spätere Verwendung zu speichern, klicken Sie auf das Symbol **[!UICONTROL Speichern]**.

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

Nach dem Konfigurieren der Einschränkungsfilter wird das Fenster **[!UICONTROL Datenformatierung]** geöffnet. In diesem Fenster können Sie die Ausgabespalten neu anordnen, Daten umwandeln und die Schreibweise der Spaltentitel anpassen. Sie können auch Formeln auf das Endergebnis anwenden, indem Sie ein berechnetes Feld erstellen.

>[!NOTE]
>
>Weitere Informationen zu den Arten von berechneten Feldern finden Sie unter [Berechnete Felder erstellen](filter-conditions.md#creating-calculated-fields).

Nicht aktivierte Spalten werden im Datenvorschaufenster ausgeblendet.

![](assets/query_editor_nveau_10.png)

In der Spalte **[!UICONTROL Schreibweise]** haben Sie die Möglichkeit, Groß- und Kleinschreibung zu verändern. Wählen Sie eine Zeile aus und klicken Sie in die Spalte **[!UICONTROL Schreibweise]**. Wählen Sie zwischen:

* **[!UICONTROL Alles in Kleinbuchstaben]**,
* **[!UICONTROL Alles in Großbuchstaben]**,
* **[!UICONTROL Ersten Buchstaben großschreiben]**.

![](assets/query_editor_nveau_42.png)

## &#x200B;6. Schritt – Vorschau der Daten anzeigen {#step-6---preview-data}

Das Fenster **[!UICONTROL Datenvorschau]** markiert die letzte Phase des Abfrageprozesses. Klicken Sie **[!UICONTROL Vorschau der Daten starten]** um Ihre Ergebnisse zu überprüfen, die in Spalten oder im XML-Format angezeigt werden können. Um die zugrunde liegende SQL-Abfrage zu überprüfen, öffnen Sie die Registerkarte **[!UICONTROL Erzeugte SQL-Abfragen]**. In diesem Schritt können Sie überprüfen, ob sich Ihre Abfrage wie erwartet verhält, bevor Sie sie weiter verwenden.

Im vorliegenden Beispiel wurden die Daten nach dem Alter der ausgewählten Empfänger in aufsteigender Reihenfolge geordnet.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>Wie bei allen in der Konsole verfügbaren Listen werden standardmäßig nur die ersten 200 Zeilen im Fenster **[!UICONTROL Datenvorschau“]**. Geben Sie eine Zahl in das Feld **[!UICONTROL Anzuzeigende Zeilen“ ein]** klicken Sie auf **[!UICONTROL Vorschau der Daten starten]**. [Weitere Informationen](../config/ui-settings.md#manage-and-customize-lists)



**Verwandte Themen**

* [Workflow-Abfrageaktivität](../../automation/workflow/query.md)
* [Abfrage der Empfängertabelle](../../automation/workflow/querying-recipient-table.md)
* [Filterbedingungen](filter-conditions.md)
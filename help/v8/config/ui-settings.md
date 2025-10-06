---
title: Einstellungen der Campaign-Benutzeroberfläche
description: Erfahren Sie, wie Sie die Einstellungen der Campaign-Benutzeroberfläche anpassen können.
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 2898fe400e9bf53fc2fe8fde26ccc61ec43bc69e
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 97%

---

# Einstellungen der Campaign-Benutzeroberfläche {#ui-settings}

## Standardeinheiten {#default-units}

In Adobe Campaign können Werte für Felder, die eine Dauer angeben (z. B. Gültigkeitsdauer der Ressourcen, Validierungs-Deadline einer Aufgabe usw.), in den folgenden **Einheiten** ausgedrückt werden:

* **[!UICONTROL s]** für Sekunden
* **[!UICONTROL min]** für Minuten
* **[!UICONTROL h]** für Stunden
* **[!UICONTROL T]** für Tage

## Anpassen von Campaign Explorer{#customize-explorer}

Sie können Ordner zu Campaign Explorer hinzufügen, Ansichten erstellen und Berechtigungen zuweisen.

Auf [dieser Seite](../audiences/folders-and-views.md) erfahren Sie, wie Sie Ordner und Ansichten verwalten.

## Verwalten und Anpassen von Listen {#customize-lists}

In der Campaign-Client-Console werden die Daten in Listen angezeigt. Sie können diese Listen Ihren Bedürfnissen entsprechend anpassen. Sie können beispielsweise Spalten hinzufügen, Daten filtern, Einträge zählen und Ihre Einstellungen speichern und freigeben.

Darüber hinaus können Sie Filter erstellen und speichern.  Weitere Informationen über Filter finden Sie auf [dieser Seite](../audiences/create-filters.md).

### Anzahl der Einträge {#number-of-records}

Standardmäßig lädt Adobe Campaign die 200 ersten Datensätze einer Liste in den Arbeitsspeicher. Dies bedeutet, dass eventuell nicht alle Datensätze einer Tabelle angezeigt werden. Sie haben die Möglichkeit, die Anzahl an Datensätzen einer Liste zu zählen und zusätzliche Datensätze in den Arbeitsspeicher zu laden.

Im rechten unteren Bereich der Listenanzeige zeigt ein **Zähler** die Anzahl an geladenen Datensätzen sowie die Gesamt-Datensatzanzahl an (unter Berücksichtigung aller angewendeten Filter):

![Anzeigen der Gesamtzahl der Einträge in einer Liste](assets/number-of-records.png)

Wenn rechts anstelle der Gesamtzahl ein Fragezeichen angezeigt wird, wie etwa `240/?`, klicken Sie auf den Zähler, um die Berechnung zu starten.

Um zusätzliche Einträge zu laden und anzuzeigen, klicken Sie auf **[!UICONTROL Weiter laden]**. Standardmäßig werden 200 Einträge geladen. Um die standardmäßige Anzahl der Einträge zu ändern, die geladen werden sollen, verwenden Sie das Symbol **[!UICONTROL Liste konfigurieren]** in der rechten unteren Ecke der Liste. Im Listenkonfigurationsfenster können Sie dann durch Klicken auf **[!UICONTROL Erweiterte Parameter]** (unten links) die Anzahl der abzurufenden Zeilen ändern.

Klicken Sie zum Laden aller Einträge mit der rechten Maustaste auf die Liste und wählen Sie **[!UICONTROL Alles laden]**.

>[!CAUTION]
>
>Wenn eine Liste eine große Menge an Einträgen enthält, kann das vollständige Laden einige Zeit in Anspruch nehmen.
>

### Hinzufügen und Entfernen von Spalten {#add-columns}

Für jede Liste kann die native Spaltenkonfiguration angepasst werden, um weitere Informationen anzuzeigen oder nicht verwendete Spalten auszublenden.

Wenn Daten in der Detailansicht eines Eintrags sichtbar sind, klicken Sie mit der rechten Maustaste auf das Feld und wählen Sie **[!UICONTROL Der Liste hinzufügen]** aus.

![Hinzufügen eines Felds in der Liste](assets/add-in-the-list.png)

Die Spalte wird rechts von den bereits angezeigten Spalten hinzugefügt.

![Hinzufügen einer Feldspalte](assets/add-a-column.png)

Sie können auch den Listenkonfigurationsbildschirm verwenden, um Spalten hinzuzufügen und zu entfernen:

1. Klicken Sie in einer Eintragsliste auf das Symbol **[!UICONTROL Liste konfigurieren]** unten rechts.
1. Doppelklicken Sie auf die Felder, die der Liste **[!UICONTROL Verfügbare Felder]** hinzugefügt werden sollen, und sie werden zur Liste **[!UICONTROL Ausgabespalten]** hinzugefügt.

   ![Listenkonfigurationsbildschirm](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Erweiterte Felder werden standardmäßig nicht angezeigt. Um sie anzuzeigen, klicken Sie auf das Symbol **Erweiterte Felder anzeigen** unten rechts in der Liste der verfügbaren Felder.
   >
   >Die Art der Felder (SQL-Felder, verknüpfte Tabellen, berechnete Felder usw.) wird durch verschiedene Symbole verdeutlicht. Für das jeweils ausgewählte Feld wird unter der Liste der verfügbaren Felder die entsprechende Beschreibung angezeigt.
   >

1. Mit den Pfeilen nach oben/unten können Sie die **Anzeigereihenfolge** ändern.

1. Wählen Sie **[!UICONTROL OK]** aus, um die Konfigurationen zu bestätigen und das Ergebnis anzuzeigen.

Wenn Sie eine Spalte entfernen möchten, wählen Sie sie aus und klicken Sie auf das **Papierkorb**-Symbol.

Sie können das Symbol **[!UICONTROL Werteverteilung]** verwenden, um die Aufteilung der Werte für das ausgewählte Feld im aktuellen Ordner anzeigen.

![](assets/value-distribution.png)


### Erstellen einer neuen Spalte {#create-a-new-column}

Sie können neue Spalten erstellen, um zusätzliche Felder in der Liste anzuzeigen.

Gehen Sie wie folgt vor, um eine Spalte zu erstellen:

1. Klicken Sie in einer Eintragsliste auf das Symbol **[!UICONTROL Liste konfigurieren]** unten rechts.
1. Klicken Sie auf das Symbol **[!UICONTROL Hinzufügen]**, um ein neues Feld in der Liste anzuzeigen.
1. Konfigurieren Sie Feld, das in der Spalte hinzugefügt werden soll.


### Anzeigen von Daten in Unterordnern {#display-sub-folders-records}

Bei Listen stehen zwei verschiedene Anzeigemodi zur Verfügung:

* Alle im ausgewählten Ordner enthaltenen Einträge (Standard)
* Alle im ausgewählten Ordner und dessen Unterordnern enthaltenen Einträge

Um zwischen den beiden Anzeigemodi zu wechseln, klicken Sie in der Campaign-Symbolleiste auf **[!UICONTROL Unterordner anzeigen]**.

### Speichern einer Listenkonfiguration {#saving-a-list-configuration}

Die Listenkonfigurationen werden für jede Benutzerin und jeden Benutzer lokal definiert. Wenn der lokale Cache gelöscht wird, werden lokale Konfigurationen deaktiviert.

Standardmäßig gelten die Einstellungsparameter für alle Listen mit dem entsprechenden Ordnertyp. Wenn Sie die Weise ändern, wie die Empfängerliste in einem Ordner angezeigt wird, wird diese Konfiguration auf alle anderen Empfängerordner angewendet.

Sie können mehr als eine Konfiguration speichern, um sie auf verschiedene Ordner desselben Typs anzuwenden. Die Konfiguration wird mit den Eigenschaften des Ordners gespeichert, der die Daten enthält, und kann erneut angewendet werden.

Gehen Sie folgendermaßen vor, um eine Listenkonfiguration zu speichern, damit sie wiederverwendet werden kann:

1. Klicken Sie im Explorer mit der rechten Maustaste auf den Ordner, der die angezeigten Daten enthält.
1. Wählen Sie **[!UICONTROL Eigenschaften]** aus.
1. Wählen Sie **[!UICONTROL Erweiterte Parameter]** aus und geben Sie im Feld **[!UICONTROL Konfiguration]** einen Namen ein.
1. Wählen Sie **[!UICONTROL OK]** und danach **[!UICONTROL Speichern]** aus.

Sie können diese Konfiguration dann auf jeden anderen Ordner desselben Typs anwenden. Weitere Informationen über Ordner finden Sie auf [dieser Seite](../audiences/folders-and-views.md).

### Exportieren einer Liste {#exporting-a-list}

Um Daten aus einer Liste zu exportieren, müssen Sie einen Export-Assistenten verwenden. Um darauf zuzugreifen, wählen Sie die zu exportierenden Elemente in der Liste aus, klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Exportieren…]** aus.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Listenelemente dürfen nicht mithilfe der Kopieren/Einfügen-Funktion exportiert werden.

### Sortieren einer Liste {#sorting-a-list}

Listen enthalten oft große Datenmengen, die sortiert und mit einfachen oder erweiterten Filtern eingeschränkt werden können. Während die Sortierung eine Anzeige aller Datensätze in steigender oder fallender Reihenfolge nach sich zieht, wird durch Anwendung von Filtern unter Kombination verschiedener Kriterien die Auswahl der anzuzeigenden Datensätze eingeschränkt.

Durch die Auswahl eines Spaltentitels werden die Daten aufsteigend oder absteigend sortiert oder die Sortierung aufgehoben. Ein blauer Pfeil vor dem Spaltentitel zeigt an, dass nach dieser Spalte sortiert wurde und ob es sich um eine auf- oder absteigende Sortierung handelt. Ein roter Unterstrich bedeutet, dass die Sortierung sich auf in der Datenbank indizierte Daten bezieht. Dieser Sortiermodus trägt zur Optimierung der Sortiervorgänge bei.

Sie können die Sortierung konfigurieren oder Sortierkriterien kombinieren. Gehen Sie dazu folgendermaßen vor:

1. Wählen Sie rechts unten von der Liste **[!UICONTROL Liste konfigurieren]** aus.
1. Wählen Sie im Listenkonfigurationsfenster den Tab **[!UICONTROL Sortierung]** aus.
1. Wählen Sie die zu sortierenden Felder und die Sortierrichtung aus (auf- oder absteigend).
1. Die Priorität der Sortierkriterien hängt von der Reihenfolge der Sortierungsspalten ab. Diese Reihenfolge kann mithilfe der Pfeile rechts in der Symbolleiste angepasst werden.

   Die Anzeige der Spalten in der Liste ist unabhängig von der Priorität der Sortierkriterien.

1. Wählen Sie **[!UICONTROL OK]** aus, um die Einstellungen zu bestätigen und das Ergebnis anzuzeigen.


## Zusätzliche Ressourcen

* **[Erste Schritte mit der Campaign-Benutzeroberfläche](../start/campaign-ui.md)** - Erfahren Sie, wie Sie die Benutzeroberfläche von Adobe Campaign aufrufen und durchsuchen können.
* **[Arbeiten mit Auflistungen](../config/enumerations.md)** - Standardisieren von Feldwerten mit vordefinierten Dropdown-Listen für eine schnellere, konsistentere Dateneingabe.

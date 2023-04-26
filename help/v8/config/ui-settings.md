---
title: Einstellungen der Campaign-Benutzeroberfläche
description: Erfahren Sie, wie Sie die Einstellungen der Campaign-Benutzeroberfläche anpassen können.
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 5251885f0493eb41f93d07f0e22dcf77926e69dd
workflow-type: tm+mt
source-wordcount: '1945'
ht-degree: 38%

---

# Einstellungen der Campaign-Benutzeroberfläche {#ui-settings}

## Standardeinheiten {#default-units}

In Adobe Campaign können Werte für Felder, die eine Dauer angeben (z. B. Gültigkeitsdauer der Ressourcen, Validierungszeitraum einer Aufgabe usw.), wie folgt ausgedrückt werden: **Einheiten**:

* **[!UICONTROL s]** für Sekunden
* **[!UICONTROL min]** für Minuten
* **[!UICONTROL h]** für Stunden
* **[!UICONTROL T]** für Tage

## Anpassen von Campaign Explorer{#customize-explorer}

Sie können Ordner zu Campaign Explorer hinzufügen, Ansichten erstellen und Berechtigungen zuweisen.

Auf [dieser Seite](../audiences/folders-and-views.md) erfahren Sie, wie Sie Ordner und Ansichten verwalten.

## Verwalten und Anpassen von Listen{#customize-lists}

In der Campaign-Clientkonsole werden die Daten in Listen angezeigt. Sie können diese Listen Ihren Bedürfnissen entsprechend anpassen. Sie können beispielsweise Spalten hinzufügen, Daten filtern, Datensätze zählen, Ihre Einstellungen speichern und freigeben.

Darüber hinaus können Sie Filter erstellen und speichern.  Weitere Informationen zu Filtern in [diese Seite](../audiences/create-filters.md).

### Anzahl der Datensätze {#number-of-records}

Standardmäßig lädt Adobe Campaign die 200 ersten Datensätze einer Liste in den Arbeitsspeicher. Dies bedeutet, dass eventuell nicht alle Datensätze einer Tabelle angezeigt werden. Sie haben die Möglichkeit, die Anzahl an Datensätzen einer Liste zu zählen und zusätzliche Datensätze in den Arbeitsspeicher zu laden.

Im rechten unteren Bereich der Listenanzeige zeigt ein **Zähler** die Anzahl an geladenen Datensätzen sowie die Gesamt-Datensatzanzahl an (unter Berücksichtigung aller angewendeten Filter):

![Gesamtzahl der Datensätze in einer Liste anzeigen](assets/number-of-records.png)

Wenn anstelle der Zahl auf der rechten Seite ein Fragezeichen angezeigt wird, z. B. `240/?`klicken Sie auf den Zähler, um die Berechnung zu starten.

Um zusätzliche Datensätze zu laden und anzuzeigen, klicken Sie auf **[!UICONTROL Weiter laden]**. Standardmäßig werden 200 Datensätze geladen. Um die Standardanzahl der zu ladenden Datensätze zu ändern, verwenden Sie die **[!UICONTROL Liste konfigurieren]** rechts unten in der Liste. Im Listenkonfigurationsfenster können Sie dann durch Klicken auf **[!UICONTROL Erweiterte Parameter]** (unten links) die Anzahl der abzurufenden Zeilen ändern.

Klicken Sie zur Laden aller Datensätze mit der rechten Maustaste auf die Liste und wählen Sie **[!UICONTROL Alles laden]**.

>[!CAUTION]
>
>Wenn eine Liste eine große Menge an Datensätzen enthält, kann das vollständige Laden einige Zeit in Anspruch nehmen.

### Spalten hinzufügen und entfernen {#add-columns}

Für jede Liste kann die integrierte Spaltenkonfiguration angepasst werden, um weitere Informationen anzuzeigen oder nicht verwendete Spalten auszublenden.

Wenn Daten in der Detailansicht eines Datensatzes sichtbar sind, klicken Sie mit der rechten Maustaste auf das Feld und wählen Sie **[!UICONTROL In Liste hinzufügen]**.

![Hinzufügen eines Felds in der Liste](assets/add-in-the-list.png)

Die Spalte wird rechts von den bereits angezeigten Spalten hinzugefügt.

![Feldspalte hinzufügen](assets/add-a-column.png)

Sie können auch den Listenkonfigurationsbildschirm verwenden, um Spalten hinzuzufügen und zu entfernen:

1. Klicken Sie in einer Datensatzliste auf **[!UICONTROL Liste konfigurieren]** rechts unten.
1. Doppelklicken Sie auf die Felder, die im **[!UICONTROL Verfügbare Felder]** list: werden sie zum **[!UICONTROL Ausgabespalten]** Liste.

   ![Listenkonfigurationsbildschirm](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Erweiterte Felder werden standardmäßig nicht angezeigt. Um sie anzuzeigen, klicken Sie auf die **Erweiterte Felder anzeigen** rechts unten in der Liste der verfügbaren Felder.
   >
   >Die Art der Felder (SQL-Felder, verknüpfte Tabellen, berechnete Felder usw.) wird durch verschiedene Symbole verdeutlicht. Für das jeweils ausgewählte Feld wird unter der Liste der verfügbaren Felder die entsprechende Beschreibung angezeigt.

1. Mit den Nach-oben-/Nach-unten-Pfeilen können Sie die **Anzeigereihenfolge**.

1. Wählen Sie **[!UICONTROL OK]** aus, um die Konfigurationen zu bestätigen und das Ergebnis anzuzeigen.

Wenn Sie eine Spalte entfernen möchten, wählen Sie sie aus und klicken Sie auf die Schaltfläche **Papierkorb** Symbol.

Sie können die **[!UICONTROL Werteverteilung]** -Symbol, um die Werteverteilung für das ausgewählte Feld im aktuellen Ordner anzuzeigen.

![](assets/value-distribution.png)


### Neue Spalte erstellen {#create-a-new-column}

Sie können neue Spalten erstellen, um zusätzliche Felder in der Liste anzuzeigen.

Gehen Sie wie folgt vor, um eine Spalte zu erstellen:

1. Klicken Sie in einer Datensatzliste auf **[!UICONTROL Liste konfigurieren]** rechts unten.
1. Klicken Sie auf **[!UICONTROL Hinzufügen]** , um ein neues Feld in der Liste anzuzeigen.
1. Konfigurieren Sie das in der Spalte hinzuzufügende Feld.


### Anzeigen von Daten in Unterordnern {#display-sub-folders-records}

Bei Listen stehen zwei verschiedene Anzeigemodi zur Verfügung:

* Alle im ausgewählten Ordner enthaltenen Datensätze (Standard)
* Alle im ausgewählten Ordner und dessen Unterordnern enthaltenen Datensätze

Um von einem Anzeigemodus zum anderen zu wechseln, klicken Sie auf **[!UICONTROL Anzeigen von Unterebenen]** in der Kampagnen-Symbolleiste.

### Speichern einer Listenkonfiguration {#saving-a-list-configuration}

Die Listenkonfigurationen werden für jeden Benutzer lokal definiert. Wenn der lokale Cache gelöscht wird, werden lokale Konfigurationen deaktiviert.

Standardmäßig gelten die Parameter für Einstellungen für alle Listen mit dem entsprechenden Ordnertyp. Wenn Sie die Anzeige der Empfängerliste in einem Ordner ändern, wird diese Konfiguration auf alle anderen Empfängerordner angewendet.

Sie können mehr als eine Konfiguration speichern, um sie auf verschiedene Ordner desselben Typs anzuwenden. Die Konfiguration wird mit den Eigenschaften des Ordners gespeichert, der die Daten enthält, und kann erneut angewendet werden.

Gehen Sie wie folgt vor, um eine Listenkonfiguration zu speichern, damit sie wiederverwendet werden kann:

1. Klicken Sie im Explorer mit der rechten Maustaste auf den Ordner, der die angezeigten Daten enthält.
1. Wählen Sie **[!UICONTROL Eigenschaften]** aus.
1. Wählen Sie **[!UICONTROL Erweiterte Parameter]** aus und geben Sie im Feld **[!UICONTROL Konfiguration]** einen Namen ein.
1. Wählen Sie **[!UICONTROL OK]** und danach **[!UICONTROL Speichern]** aus.

Sie können diese Konfiguration dann auf jeden anderen Ordner desselben Typs anwenden. Weitere Informationen zu Ordnern in [diese Seite](../audiences/folders-and-views.md).

### Exportieren einer Liste {#exporting-a-list}

Zum Export von Listendaten steht Ihnen der Export-Assistent zur Verfügung. Markieren Sie die zu exportierenden Datensätze und klicken Sie mit der rechten Maustaste auf die Liste. Wählen Sie dann im Kontextmenü die Option **[!UICONTROL Exportieren...]**.

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




## Arbeiten mit Auflistungen {#enumerations}

Eine Auflistung (auch als &quot;Auflistungsliste&quot;bezeichnet) ist eine Liste von Werten, die vom System zum Ausfüllen von Feldern vorgeschlagen werden. Verwenden Sie Auflistungen, um die Werte dieser Felder zu standardisieren, die Dateneingabe zu unterstützen oder in Abfragen zu verwenden.

Die Werteliste erscheint als Dropdown-Liste, aus der Sie den im Feld einzufügenden Wert auswählen können. Die Dropdown-Liste ermöglicht auch eine prädiktive Eingabe: Geben Sie die ersten Buchstaben ein, und der Antrag wird in den übrigen Buchstaben ausgefüllt.

Die Bestimmung der Werte für Auflistungsfelder und ihre Verwaltung (Hinzufügen/Löschen eines Werts) erfolgen über den Verzeichnisknoten **[!UICONTROL Administration > Plattform > Auflistungen]**.

![Auflistungen aufrufen](assets/enumerations-menu.png)

### Auflistungstypen {#types-of-enum}

Auflistungen werden im **[!UICONTROL Administration > Plattform > Auflistungen]** Ordner des Explorer.

Sie können: Öffnen, System, Emoticon oder geschlossen.

* Ein **Öffnen** -Auflistung ermöglicht es Benutzern, neue Werte direkt in die auf dieser Auflistung basierenden Felder einzufügen.
* A **Geschlossen** -Auflistung verfügt über eine feste Liste von Werten, die nur über die **[!UICONTROL Administration > Plattform > Auflistungen]** Ordner des Explorer.
* Ein **Emoticon** -Auflistung wird verwendet, um die Emoticon-Liste zu aktualisieren. Weitere Informationen
* A **System** -Auflistung ist mit Systemfeldern verknüpft und enthält einen internen Namen.

Für **Öffnen** und **Geschlossen** Auflistungen, spezifische Optionen sind verfügbar:

* **Einfache Auflistung** ist der Standardtyp.
* **Alias-Verwaltung** -Auflistung wird verwendet, um die in der Datenbank gespeicherten Auflistungswerte zu harmonisieren. [Weitere Informationen](#alias-cleansing)
* **Reserviert für Klassierung** ist eine Option, mit der Sie Cube-Werte mit dieser Auflistung verknüpfen können. [Weitere Informationen](../reporting/gs-cubes.md)


### Alias-Verwaltung {#alias-cleansing}

In den Auflistungsfeldern können Sie einen Wert auswählen oder einen benutzerdefinierten Wert eingeben, der in der Dropdown-Liste nicht verfügbar ist. Benutzerdefinierte Werte können zu den vorhandenen Auflistungswerten hinzugefügt werden, als neuer - in diesem Fall der **[!UICONTROL Öffnen]** muss ausgewählt sein. Diese benutzerdefinierten Werte können mithilfe von Alias-Cleansing-Funktionen bereinigt werden. Wenn beispielsweise ein Benutzer `Adob` anstelle von `Adobe`, kann der Alias-Bereinigungsprozess automatisch durch den richtigen Begriff ersetzen.

>[!CAUTION]
>
>Die Bereinigung von Daten ist ein kritischer Prozess, der auf die Daten in der Datenbank einwirkt. Adobe Campaign aktualisiert Daten gebündelt, was zur Löschung von gewissen Werten führen kann. Dieser Vorgang ist daher erfahrenen Benutzern vorbehalten.

Aktivieren Sie die **[!UICONTROL Alias-Verwaltung]** Option zur Verwendung von Datenbereinigungsfunktionen für eine Auflistung. Wenn diese Option ausgewählt ist, wird die **[!UICONTROL Alias]** wird unten im Fenster angezeigt.

Wenn ein Benutzer einen Wert eingibt, der nicht in einer Alias-Bereinigungs-Auflistung vorhanden ist, wird er zum **Werte** Liste. Sie können [Alias aus diesen Werten erstellen](#convert-to-alias)oder [Erstellen neuer Alias von Grund auf](#create-alias).

#### Alias erstellen{#create-alias}

Gehen Sie wie folgt vor, um einen Alias zu erstellen:

1. Klicken **[!UICONTROL Hinzufügen]** Schaltfläche des **[!UICONTROL Alias]** Registerkarte.
1. Geben Sie den zu konvertierenden Alias an und wählen Sie in der Dropdown-Liste den anzuwendenden Wert aus.

   ![Neuen Alias erstellen](assets/new-alias.png)

1. Klicken **[!UICONTROL Ok]** und bestätigen Sie.

1. Speichern Sie Ihre Änderungen. Die Ersetzung von Werten erfolgt durch die **Alias-Verwaltung** -Workflow, der jede Nacht ausgeführt wird. Weitere Informationen finden Sie unter [Datenbereinigung durchführen](#running-data-cleansing).

Bei allen auf dieser Auflistung basierenden Feldern, wenn ein Benutzer den Wert eingibt **Adobe** in einem Feld &quot;Firma&quot;(in der Adobe Campaign-Konsole in einem Webformular) wird es automatisch durch den Wert ersetzt **Adobe**.

#### Falsche Werte in Alias konvertieren{#convert-to-alias}

Sie können auch einen vorhandenen Auflistungswert in einen Alias konvertieren. Um dies durchzuführen:

1. Klicken Sie in der Liste der Werte einer Auflistung mit der rechten Maustaste darauf und navigieren Sie zu **[!UICONTROL Aktionen... > Werte in Alias konvertieren..]**.

   ![Wert in Alias konvertieren](assets/convert-into-aliases.png)

1. Wählen Sie die Werte aus, die in Alias konvertiert werden sollen, und klicken Sie auf **[!UICONTROL Nächste]**.
1. Klicken Sie auf **[!UICONTROL Starten]**, um die Konvertierung zu starten.

   Nach Abschluss der Ausführung werden die Aliase der Liste im **Alias** Registerkarte. Sie können einen korrekten Wert verknüpfen, um falsche Einträge zu ersetzen. Um dies durchzuführen:

1. Wählen Sie einen zu bereinigenden Wert aus.
1. Klicken Sie auf **Detail..** Schaltfläche.
1. Wählen Sie den neuen Wert in der Dropdown-Liste aus.

   ![Neuen Alias erstellen](assets/define-new-alias.png)


>[!NOTE]
>
>Sie können die Vorkommen eines Alias im **[!UICONTROL Treffer]** in der Spalte **[!UICONTROL Alias]** Unterregisterkarte. Er zeigt an, wie oft dieser Wert eingegeben wurde.  [Weitere Informationen](#calculate-entry-occurrences).

#### Datenbereinigung durchführen {#running-data-cleansing}

Die Datenbereinigung wird von der **[!UICONTROL Alias-Verwaltung]** technischer Arbeitsablauf. Er wird standardmäßig täglich ausgeführt.

Die Bereinigung kann auch über die **[!UICONTROL Werte bereinigen...]** Link.

Der Link **[!UICONTROL Erweiterte Parameter...]** ermöglicht die Festlegung des Datums, ab dem die gesammelten Werte berücksichtigt werden.

Klicken Sie auf die Schaltfläche **[!UICONTROL Starten]**, um die Datenbereinigung zu beginnen.

##### Vorkommen überwachen {#calculate-entry-occurrences}

Mit dem Untertab **[!UICONTROL Alias]** einer Auflistung kann die Anzahl der Erscheinungen eines Alias unter allen eingegebenen Werten angezeigt werden. Es handelt sich bei dieser Information um eine Schätzung. Sie wird in der Spalte **[!UICONTROL Treffer]** angezeigt.

>[!CAUTION]
>
>Die Berechnung der Alias-Eingabeanzahl kann lange dauern.

Sie können die Trefferberechnung manuell über die **[!UICONTROL Werte bereinigen...]** Link. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Erweiterte Parameter...]** und wählen Sie die gewünschten Optionen aus.

* **[!UICONTROL Anzahl der Alias-Erscheinungen aktualisieren]**: Ermöglicht es, die bereits berechneten Treffer ab dem angegebenen Berücksichtigungsdatum zu aktualisieren.
* **[!UICONTROL Anzahl der Alias-Erscheinungen von Beginn an neu berechnen]**: Ermöglicht die Durchführung der Berechnung auf der gesamten Adobe-Campaign-Plattform.

Sie können auch einen dedizierten Workflow erstellen, um die Berechnung automatisch in bestimmten Abständen durchzuführen, beispielsweise jede Woche.

Erstellen Sie hierfür eine Kopie des Workflows **[!UICONTROL Alias-Verwaltung]**, passen Sie die Planung an und konfigurieren Sie in der Aktivität **[!UICONTROL Bereinigung der Auflistungswerte]** folgende Parameter:

* **-updateHits**, um die Anzahl der Alias-Erscheinungen zu aktualisieren;
* **-updateHits:full**, um die Anzahl aller Alias-Erscheinungen neu zu berechnen.

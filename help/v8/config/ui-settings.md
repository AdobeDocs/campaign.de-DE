---
title: Einstellungen der Campaign-Benutzeroberfläche
description: Erfahren Sie, wie Sie die Einstellungen der Campaign-Benutzeroberfläche anpassen können.
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 0b4483e0f16f14582a1a4bc28b0e1ff719823ef3
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 29%

---

# Einstellungen der Campaign-Benutzeroberfläche {#ui-settings}

## Auflistungen {#enumerations}

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

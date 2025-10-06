---
title: Verwalten von Aufzählungen
description: Erfahren Sie, wie Sie mit Aufzählungen arbeiten.
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 89%

---

# Arbeiten mit Aufzählungen {#enumerations}

Eine Auflistung (auch als Auflistungsliste bezeichnet) ist eine vordefinierte Liste von Werten, die Sie zum Ausfüllen bestimmter Felder verwenden können. Auflistungen helfen, Feldwerte zu standardisieren, die Dateneingabe konsistenter zu gestalten und Abfragen zu vereinfachen.

Sofern verfügbar, werden die Werte in einer Dropdown-Liste angezeigt. Sie können entweder einen Wert direkt auswählen oder mit der Eingabe beginnen - eine prädiktive Eingabe schlägt übereinstimmende Werte vor und führt sie automatisch aus.

![](assets/enum_values.png)

Einige Konsolenfelder werden mit Auflistungen konfiguriert. Wenn eine Auflistung **offen** ist, können Sie auch neue Werte direkt in das Feld einfügen.

![Zugreifen auf Aufzählungen](assets/enumerations-menu.png)

## Aufzählungstypen {#types-of-enum}

Aufzählungen werden im Ordner **[!UICONTROL Administration > Plattform > Aufzählungen]** des Explorers gespeichert.

Sie können von einem der folgenden Typen sein: Offen, System, Emoticon oder Geschlossen.

* Eine Aufzählung des Typs **Offen** ermöglicht es Benutzerinnen und Benutzern, neue Werte direkt in die auf dieser Aufzählung basierenden Felder einzufügen.
* Ein Aufzählung des Typs **Geschlossen** verfügt über eine feste Liste von Werten, die nur über den Ordner **[!UICONTROL Administration > Plattform > Aufzählungen]** des Explorers geändert werden kann.
* Eine Aufzählung des Typs **Emoticon** wird verwendet, um die Emoticon-Liste zu aktualisieren. Weitere Informationen
* Eine Aufzählung des Typs **System** ist mit Systemfeldern verknüpft und enthält einen internen Namen.

Für Aufzählungen des Typs **Offen** und **Geschlossen** sind spezifische Optionen verfügbar:

* **Einfache Aufzählung** ist der Standardtyp.
* **Alias-Verwaltung** für die Aufzählung wird verwendet, um die in der Datenbank gespeicherten Aufzählungswerte zu harmonisieren. [Weitere Informationen](#alias-cleansing)
* **Reserviert für Klassierung** ist eine Option, durch die Sie Cube-Werte mit dieser Aufzählung verknüpfen können. [Weitere Informationen](../reporting/gs-cubes.md)


## Alias-Bereinigung {#alias-cleansing}

In den Aufzählungsfeldern können Sie einen Wert auswählen oder einen benutzerdefinierten Wert eingeben, der in der Dropdown-Liste nicht verfügbar ist. Benutzerdefinierte Werte können zu den vorhandenen Aufzählungswerten als neue Werte hinzugefügt werden – in diesem Fall muss die Option **[!UICONTROL Offen]** ausgewählt sein. Diese benutzerdefinierten Werte können mithilfe der Funktionen der Alias-Verwaltung bereinigt werden. Wenn beispielsweise eine Benutzerin oder ein Benutzer `Adob` anstelle von `Adobe` eingibt, kann der Vorgang der Alias-Verwaltung dies automatisch durch den richtigen Begriff ersetzen.

>[!CAUTION]
>
>Die Datenbereinigung ist ein kritischer Prozess, der sich auf die Daten in der Datenbank auswirkt. Adobe Campaign aktualisiert Daten gebündelt, was zur Löschung von gewissen Werten führen kann. Dieser Vorgang ist daher erfahrenen Benutzerinnen und Benutzern vorbehalten.

Aktivieren Sie die Option **[!UICONTROL Alias-Verwaltung]**, um Datenbereinigungsfunktionen für eine Aufzählung zu verwenden. Wenn diese Option ausgewählt ist, wird unten im Fenster die Registerkarte **[!UICONTROL Alias]** angezeigt.

Wenn ein Wert eingegeben wird, der nicht in der Aufzählung einer Alias-Verwaltung vorhanden ist, wird er zur **Werte**-Liste hinzugefügt. Sie können [Aliase aus diesen Werten erstellen](#convert-to-alias) oder [neue Aliase von Grund auf erstellen](#create-alias).

### Erstellen eines Alias{#create-alias}

Gehen Sie wie folgt vor, um einen Alias zu erstellen:

1. Wählen Sie auf der Registerkarte **[!UICONTROL Alias]** die Schaltfläche **[!UICONTROL Hinzufügen]**.
1. Geben Sie den Alias an, der konvertiert werden soll, und wählen Sie in der Dropdown-Liste den anzuwendenden Wert aus.

   ![Erstellen eines neuen Alias](assets/new-alias.png)

1. Klicken Sie auf **[!UICONTROL OK]** und bestätigen Sie.

1. Speichern Sie Ihre Änderungen. Die Ersetzung von Werten erfolgt durch den Workflow der **Alias-Verwaltung**, der jede Nacht ausgeführt wird. Weitere Informationen finden Sie unter [Datenbereinigung durchführen](#running-data-cleansing).

Wenn der Wert **Adob** in einem firmenbezogenen Feld (in der Adobe Campaign-Client-Konsole, in einem Web-Formular) eingegeben wird, wird er in allen Feldern, die auf dieser Aufzählung basieren, automatisch durch den Wert **Adobe** ersetzt.

### Konvertieren eines falschen Werts in einen Alias{#convert-to-alias}

Sie können auch einen vorhandenen Aufzählungswert in einen Alias konvertieren. Um dies durchzuführen:

1. Klicken Sie mit der rechten Maustaste in der Werteliste einer Aufzählung und navigieren Sie zu **[!UICONTROL Aktionen… > Werte in Alias konvertieren…]**.

   ![Konvertieren eines Wertes in einen Alias](assets/convert-into-aliases.png)

1. Wählen Sie die Werte aus, die in Aliasse konvertiert werden sollen, und klicken Sie auf **[!UICONTROL Weiter]**.
1. Klicken Sie auf **[!UICONTROL Starten]**, um die Konvertierung zu starten.

   Nach Abschluss der Ausführung werden die Aliasse auf der Registerkarte **Alias** der Liste hinzugefügt. Sie können einen korrekten Wert verknüpfen, um falsche Einträge zu ersetzen. Um dies durchzuführen:

1. Wählen Sie einen zu bereinigenden Wert aus.
1. Klicken Sie auf die Schaltfläche **Detail…**.
1. Wählen Sie den neuen Wert in der Dropdown-Liste aus.

   ![Erstellen eines neuen Alias](assets/define-new-alias.png)


>[!NOTE]
>
>Sie können die Anzahl von Eingaben eines Alias in der **[!UICONTROL Treffer]**-Spalte auf der Unterregisterkarte **[!UICONTROL Alias]** nachverfolgen. Sie zeigt an, wie oft dieser Wert eingegeben wurde.  [Weitere Informationen](#calculate-entry-occurrences).

### Durchführen einer Datenbereinigung {#running-data-cleansing}

Die Datenbereinigung wird vom technischen Workflow der **[!UICONTROL Alias-Verwaltung]** durchgeführt. Er wird standardmäßig täglich ausgeführt.

Die Datenbereinigung kann über den Link **[!UICONTROL Werte bereinigen…]** ausgelöst werden.

Der Link **[!UICONTROL Erweiterte Parameter...]** ermöglicht die Festlegung des Datums, ab dem die gesammelten Werte berücksichtigt werden.

Klicken Sie auf die Schaltfläche **[!UICONTROL Starten]**, um die Datenbereinigung zu beginnen.

### Überwachen der Eingabeanzahl {#calculate-entry-occurrences}

Mit der Unterregisterkarte **[!UICONTROL Alias]** einer Aufzählung kann die Anzahl der Vorkommen eines Alias unter allen eingegebenen Werten angezeigt werden. Es handelt sich bei dieser Information um eine Schätzung. Sie wird in der Spalte **[!UICONTROL Treffer]** angezeigt.

>[!CAUTION]
>
>Die Berechnung der Alias-Eingabeanzahl kann lange dauern.
>

Sie können die Trefferberechnung manuell über den Link **[!UICONTROL Werte bereinigen…]** ausführen. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Erweiterte Parameter…]** und wählen Sie die gewünschten Optionen aus.

* **[!UICONTROL Anzahl der Alias-Erscheinungen aktualisieren]**: Ermöglicht es, die bereits berechneten Treffer ab dem angegebenen Berücksichtigungsdatum zu aktualisieren.
* **[!UICONTROL Anzahl der Alias-Erscheinungen von Beginn an neu berechnen]**: Ermöglicht die Durchführung der Berechnung auf der gesamten Adobe Campaign-Plattform.

Sie können auch einen dedizierten Workflow erstellen, um die Berechnung automatisch in bestimmten Abständen durchzuführen, beispielsweise jede Woche.

Erstellen Sie hierfür eine Kopie des Workflows **[!UICONTROL Alias-Verwaltung]**, passen Sie die Planung an und konfigurieren Sie in der Aktivität **[!UICONTROL Bereinigung der Aufzählungswerte]** folgende Parameter:

* **-updateHits**, um die Anzahl der Alias-Erscheinungen zu aktualisieren;
* **-updateHits:full**, um alle Alias-Treffer neu zu berechnen.

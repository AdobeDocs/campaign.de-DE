---
title: Verwalten von Aufzählungen
description: Erfahren Sie, wie Sie mit Aufzählungen arbeiten.
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 56%

---

# Verwalten von Aufzählungen {#manage-enumerations}

Eine Auflistung (auch als Auflistungsliste bezeichnet) ist eine vordefinierte Liste von Werten, die Sie zum Ausfüllen bestimmter Felder verwenden können. Auflistungen helfen, Feldwerte zu standardisieren, die Dateneingabe konsistenter zu gestalten und Abfragen zu vereinfachen.

Sofern verfügbar, werden die Werte in einer Dropdown-Liste angezeigt. Sie können entweder einen Wert direkt auswählen oder mit der Eingabe beginnen - eine prädiktive Eingabe schlägt übereinstimmende Werte vor und führt sie automatisch aus.

![](assets/enum_values.png)

Einige Konsolenfelder werden mit Auflistungen konfiguriert. Wenn eine Auflistung **offen** ist, können Sie auch neue Werte direkt in das Feld einfügen.

## Zugreifen auf Auflistungen

Die in diesen Feldern verwendeten Werte werden zentral verwaltet. Sie können sie in der Explorer-Struktur unter **Administration“,** (Platform`>` **&#x200B;**&#x200B;Auflistungen`>` hinzufügen **bearbeiten** aktualisieren oder löschen.

* Im oberen Abschnitt befindet sich die Liste der Felder, für die eine Auflistung bestimmt wurde.
* Im unteren Abschnitt werden die verfügbaren Werte aufgelistet.

Wenn eine Auflistung **[!UICONTROL Offen]** ist, können Benutzerinnen und Benutzer einen neuen Wert direkt in das entsprechende Feld in der Benutzeroberfläche eingeben.

Wenn eine Auflistung **[!UICONTROL Geschlossen]** ist, können neue Werte nur über das Menü **Auflistung** hinzugefügt werden.

## Neuen Wert hinzufügen

Um einen neuen Auflistungswert zu erstellen, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**.

![](assets/enumeration_screen.png)

Geben Sie den Titel des Werts ein.


## Alias-Bereinigung {#alias-cleansing}

In den Auflistungsfeldern können Sie andere Werte als Auflistungswerte eingeben. Diese Werte können entweder, wie sie sind, gespeichert oder aber bereinigt werden.

>[!CAUTION]
>
>Die Bereinigung von Daten ist ein kritischer Prozess, der auf die Daten in der Datenbank einwirkt. Adobe Campaign aktualisiert Daten gebündelt, was zur Löschung von gewissen Werten führen kann. Dieser Vorgang ist daher erfahrenen Benutzern vorbehalten.

Der eingegebene Wert kann:

* den Werten der Auflistung hinzugefügt werden. Hierzu muss der Typ **[!UICONTROL Offen]** ausgewählt werden;
* oder automatisch durch den entsprechenden Alias ersetzt: In diesem Fall muss dieser Fall dann auf der Registerkarte **[!UICONTROL Alias]** der Auflistungsliste definiert werden,
* in der Liste der Alias gespeichert werden. Die Zuordnung des Alias kann zu einem späteren Zeitpunkt erfolgen.

### Erstellen eines Alias {#creating-an-alias}

Die Option **[!UICONTROL Alias-Verwaltung]** ermöglicht es, die Alias für die ausgewählte Auflistung zu verwalten. Wenn diese Option ausgewählt ist, wird unten im Fenster die Registerkarte **[!UICONTROL Alias]** angezeigt.

Gehen Sie wie folgt vor, um einen Alias zu erstellen:

1. Navigieren Sie zur Auflistung und aktualisieren Sie jeden Klick auf **[!UICONTROL Hinzufügen]**.

   ![](assets/enumeration_alias_create.png)

1. Geben Sie den zu konvertierenden Alias und den anzuwendenden Wert an und klicken Sie auf **[!UICONTROL OK]**.

1. Überprüfen Sie die Parameter vor dem Bestätigen des Vorgangs.

>[!CAUTION]
>
>Sobald dieser Schritt bestätigt wurde, können die vorherigen Werte möglicherweise nicht wiederhergestellt werden: Sie werden ersetzt.

Wenn also ein Benutzer den Wert **NEILSEN** in einem Feld „Firma“ (in der Adobe Campaign-Konsole oder in einem Formular) eingibt, wird er automatisch durch den Wert **NIELSEN Ltd.“**. Die Wertersetzung wird vom Workflow **Alias-Verwaltung** ausgeführt. Weitere Informationen finden Sie unter [Datenbereinigung durchführen](#running-data-cleansing).

![](assets/enumeration_alias_use.png)

### Werte in Aliase konvertieren {#values-into-aliases}

Sie können vorhandene Werte in Aliase konvertieren. Gehen Sie dazu wie folgt vor:

1. Klicken Sie mit der rechten Maustaste in die Werteliste und wählen Sie **[!UICONTROL Werte in Aliase konvertieren…]**.

1. Wählen Sie die zu konvertierenden Werte aus und klicken Sie auf **[!UICONTROL Weiter]**.

1. Klicken Sie auf **[!UICONTROL Starten]**, um die Konvertierung zu starten.

Nach erfolgreicher Konvertierung wird der Alias der Alias-Liste hinzugefügt.

### Aliastreffer abrufen {#alias-hits}

Wenn Benutzer Werte eingeben, die nicht in der Auflistung enthalten sind, werden sie auf der Registerkarte **[!UICONTROL Alias]** gespeichert.

Der technische **Alias-Verwaltung**-Workflow ruft diese Werte jede Nacht ab, um die Auflistung zu aktualisieren. Weitere Informationen finden Sie unter [Datenbereinigung durchführen](#running-data-cleansing).

Bei Bedarf kann die Spalte **[!UICONTROL Treffer]** anzeigen, wie oft dieser Wert eingegeben wurde. Die Berechnung dieses Werts kann jedoch sowohl zeit- als auch speicherintensiv sein. Weitere Informationen hierzu finden Sie unter [Eingabeanzahl berechnen](#calculating-entry-occurrences).

### Durchführen einer Datenbereinigung {#run-data-cleansing}

Die Datenbereinigung wird vom technischen Workflow der **[!UICONTROL Alias-Verwaltung]** durchgeführt. Die für die Auflistungen festgelegten Konfigurationen werden während der Ausführung des Workflows berücksichtigt. Siehe [Workflow Alias-Verwaltung](#alias-cleansing-workflow).

Die Datenbereinigung kann über den Link **[!UICONTROL Werte bereinigen...]** ausgelöst werden.

Der Link **[!UICONTROL Erweiterte Parameter...]** ermöglicht die Festlegung des Datums, ab dem die gesammelten Werte berücksichtigt werden.

Klicken Sie auf die Schaltfläche **[!UICONTROL Starten]**, um die Datenbereinigung zu beginnen.

### Eingabeanzahl berechnen {#entry-occurrences}

Die Unterregisterkarte **[!UICONTROL Alias]** einer Auflistung kann die Anzahl der Vorkommen eines Alias unter allen eingegebenen Werten anzeigen. Es handelt sich bei dieser Information um eine Schätzung. Sie wird in der Spalte **[!UICONTROL Treffer]** angezeigt.

>[!CAUTION]
>
>Die Berechnung der Anzahl der Alias-Erscheinungen kann zeitaufwändig sein. Diese Funktion sollte daher mit Vorsicht angewandt werden.

Sie können die Trefferberechnung manuell über den Link **[!UICONTROL Werte bereinigen…]** ausführen. Klicken Sie hierfür auf den Link **[!UICONTROL Erweiterte Parameter...]** und wählen Sie die gewünschte(n) Option(en) aus.

* **[!UICONTROL Anzahl der Alias-Erscheinungen aktualisieren]**: Ermöglicht es, die bereits berechneten Treffer ab dem angegebenen Berücksichtigungsdatum zu aktualisieren.
* **[!UICONTROL Anzahl der Alias-Erscheinungen von Beginn an neu berechnen]**: Ermöglicht die Durchführung der Berechnung auf der gesamten Adobe Campaign-Plattform.

Sie können auch einen dedizierten Workflow erstellen, um die Berechnung automatisch in bestimmten Abständen durchzuführen, beispielsweise jede Woche.

Erstellen Sie hierfür eine Kopie des Workflows **[!UICONTROL Alias-Verwaltung]**, passen Sie die Planung an und konfigurieren Sie in der Aktivität **[!UICONTROL Bereinigung der Aufzählungswerte]** folgende Parameter:

* **-updateHits**, um die Anzahl der Alias-Erscheinungen zu aktualisieren;
* **-updateHits:full**, um alle Alias-Treffer neu zu berechnen.

### Alias-Verwaltungs-Workflow {#alias-cleansing-workflow}

Der Workflow **Alias-Verwaltung** führt die Bereinigung der Aufzählungswerte durch. Er wird standardmäßig täglich ausgeführt.

Der Alias-Verwaltungs-Workflow ist über den Verzeichnisknoten **[!UICONTROL Administration > Betreibung > Technische Workflows]** zugänglich.



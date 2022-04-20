---
title: Datensynchronisierung über CRM-Connectoren
description: Daten zwischen Campaign und Ihrem CRM verwalten
feature: Salesforce Integration, Microsoft CRM Integration
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: 495eff0f3b5926c8f91939bcb296bc36086cb8cd
workflow-type: tm+mt
source-wordcount: '1409'
ht-degree: 52%

---

# Daten zwischen Campaign und Ihrem CRM-System synchronisieren {#data-synchronization}

Die Datensynchronisation zwischen Adobe Campaign und Ihrem CRM wird vom **CRM-Connector** Workflow-Aktivität.

Erstellen Sie zum Importieren der Daten aus Microsoft Dynamics in Adobe Campaign beispielsweise folgenden Workflow:

![](assets/ms-dyn-wf.png)

Dieser Workflow importiert die Kontakte über Microsoft Dynamics, synchronisiert sie mit den in Adobe Campaign vorhandenen Daten, löscht doppelte Kontakte und aktualisiert die Adobe Campaign-Datenbank.

Die Aktivität **[!UICONTROL CRM-Connector]** muss für die Synchronisation der Daten konfiguriert werden.

![](assets/crm-connector-ms-dyn.png)

Mit dieser Aktivität können Sie:

* Aus dem CRM-System importieren – [Weitere Informationen](#importing-from-the-crm)
* In das CRM-System exportieren – [Weitere Informationen](#exporting-to-the-crm)
* Objekte importieren, die im CRM gelöscht wurden – [Weitere Informationen](#importing-objects-deleted-in-the-crm)
* Objekte im CRM löschen – [Weitere Informationen](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

Wählen Sie das externe Konto aus, das dem CRM-System entspricht, mit dem Sie die Synchronisation konfigurieren möchten, und wählen Sie dann das zu synchronisierende Objekt aus: Konten, Möglichkeiten, Leads, Kontakte usw.

![](assets/crm-remote-obj.png)

Die Konfiguration der Aktivität hängt von der gewählten Option ab und wird im Folgenden dargestellt:

## Import aus dem CRM {#importing-from-the-crm}

Zum Import von CRM-Daten in Adobe Campaign ist ein Workflow nach folgendem Muster zu erstellen:

![](assets/crm-wf-import.png)

1. Wählen Sie den Vorgang vom Typ **[!UICONTROL Import aus CRM]**.
1. Im **[!UICONTROL Remote-Objekt]** in der Dropdown-Liste auswählen, wählen Sie das zu importierende Objekt aus. Dieses Objekt entspricht einer der Tabellen, die während der Connector-Konfiguration in Adobe Campaign erstellt wurden.
1. Im **[!UICONTROL Remote-Felder]** die zu importierenden Felder.

   Um ein Feld hinzuzufügen, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** in der Symbolleiste und anschließend auf **[!UICONTROL Ausdruck bearbeiten]**.

   Ändern Sie bei Bedarf das Datenformat mithilfe der Dropdown-Liste der **[!UICONTROL Konversion]** Spalten. Mögliche Konvertierungstypen werden im Abschnitt [diesem Abschnitt](#data-format).

   >[!CAUTION]
   >
   >Um die Objekte aus dem CRM-System mit denen in der Adobe-Campaign-Anwendung zu verknüpfen, wird die Kennung des CRM-Datensatzes benötigt. Diese wird automatisch bei Bestätigung des Dialogfensters hinzugefügt.
   >
   >Außerdem ist das Datum der letzten CRM-seitigen Änderung erforderlich, um einen inkrementellen Datenimport zu ermöglichen.

1. Sie können die zu importierenden Daten nach Bedarf filtern. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Filter bearbeiten...]** Link.

   Im folgenden Beispiel importiert Adobe Campaign nur Kontakte, die nach dem 1. November 2021 aktiv waren.

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >Die Einschränkungen im Zusammenhang mit Datenfiltermodi werden im Abschnitt [diesem Abschnitt](#filtering-data).

1. Wählen Sie die **[!UICONTROL Automatischer Index verwenden...]** Option zur automatischen Verwaltung der inkrementellen Synchronisation von Objekten zwischen Ihrem CRM-System und Adobe Campaign, abhängig vom Datum und der letzten Änderung.

   Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#variable-management).

### Variablen verwalten {#variable-management}

Aktivieren Sie die **[!UICONTROL Automatischer Index]** -Option, um nur die seit dem letzten Import geänderten Objekte abzurufen.

![](assets/use-auto-index.png)

Das Datum der letzten Synchronisation wird in einer im Konfigurationsfenster angezeigten Option gespeichert. Standardmäßig ist dies: **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**.

>[!NOTE]
>
>Dieser Hinweis gilt nur für die allgemeine **[!UICONTROL CRM-Connector]**-Aktivität. Für andere CRM-Aktivitäten läuft der Prozess automatisch ab.
>
>Diese Option muss manuell unter **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]** erstellt und ausgefüllt werden. Es muss sich um eine Textoption handeln, deren Wert dem folgenden Format entspricht: **jjjj/MM/tt hh:mm:ss**.
> 
>Diese Option muss bei jedem weiteren Import manuell aktualisiert werden.

Sie können jedoch auch ein anderes CRM-Remote-Feld angeben, um die letzten Änderungen zu identifizieren.

Unten stehende Felder kommen (in der angegebenen Reihenfolge) zur Anwendung:

* Bei Microsoft Dynamics: **modifiedon**,
* Bei Salesforce.com: **LastModifiedDate**, **SystemModstamp**.

Die Aktivierung der Option **[!UICONTROL Automatischer Index]** erzeugt drei Variablen, die im Synchronisations-Workflow über eine **[!UICONTROL JavaScript]**-Aktivität genutzt werden können. Diese Variablen sind:

* **vars.crmOptionName**: Name der Option, die das letzte Importdatum enthält.
* **vars.crmStartImport**: Startdatum (einschließlich) des letzten Datenimports.
* **vars.crmEndDate**: Enddatum des letzten Datenimports (ausgeschlossen).

   >[!NOTE]
   >
   >Diese Daten werden im folgenden Format angezeigt: **jjjj/MM/tt hh:mm:ss**.

### Daten filtern {#filtering-data}

Um eine effiziente Funktionsweise mit den diversen CRM-Systemen sicherzustellen, sind bei der Filtererstellung folgende Regeln zu beachten:

* Jedes Filterniveau darf nur einen Operatortyp verwenden.
* Der AND-NOT-Operator wird nicht unterstützt.
* Vergleiche dürfen sich nur auf Werte vom Typ &quot;ist leer&quot;/&quot;ist nicht leer&quot; oder auf Zahlen beziehen. Der Wert (rechte Spalte) wird ausgewertet und das Ergebnis muss eine Zahl sein. JOIN-Vergleiche werden nicht unterstützt.
* Der in der rechten Spalte angegebene Wert wird in JavaScript ausgewertet.
* Vergleiche vom Typ JOIN werden nicht unterstützt.
* Der Ausdruck (linke Spalte) muss zwingend ein Feld sein. Er darf weder eine Kombination aus mehreren Ausdrücken, noch eine Ziffer usw. sein.

### Sortierreihenfolge {#order-by}

In Microsoft Dynamics und Salesforce.com haben Sie die Möglichkeit, die zu importierenden Remote-Felder auf- oder absteigend zu sortieren.

Klicken Sie hierfür auf **[!UICONTROL Sortierreihenfolge]** und fügen Sie die Spalten zur Liste hinzu.

Die Spaltenreihenfolge der Liste zeigt die Sortierreihenfolge an:

![](assets/crm-import-order.png)

### Datensatz-Identifizierung {#record-identification}

Anstatt Elemente zu importieren, die in Ihr CRM-System integriert (und möglicherweise gefiltert) sind, können Sie eine zuvor im Workflow berechnete Population verwenden.

Kreuzen Sie hierfür die Option **[!UICONTROL Die zuvor berechnete Population verwenden]** an und geben Sie das die Remote-Kennung enthaltende Feld an.

Wählen Sie anschließend die aus der Eingangspopulation zu importierenden Felder wie in unten stehendem Beispiel aus:

![](assets/use-population-calc-upstream.png)

## Export in das CRM {#exporting-to-the-crm}

Exportieren Sie Adobe Campaign-Daten in Ihr CRM-System, um den gesamten Inhalt in Ihre CRM-Datenbank zu kopieren.

Um Daten in Ihr CRM zu exportieren, erstellen Sie den folgenden Workflow:

![](assets/crm-export-diagram.png)

1. Wählen Sie den Vorgang vom Typ **[!UICONTROL Export in das CRM]**.
1. Navigieren Sie zu **[!UICONTROL Remote-Objekt]** und wählen Sie das zu exportierende Objekt aus. Dieses Objekt entspricht einer der Tabellen, die bei der Connector-Konfiguration in Adobe Campaign erstellt wurden.

   >[!CAUTION]
   >
   >Die Exportfunktion der **[!UICONTROL CRM-Connector]** Aktivitäten können Felder in Ihr CRM einfügen oder aktualisieren. Um Feldaktualisierungen im CRM zu aktivieren, geben Sie den Primärschlüssel der Remote-Tabelle an. Wenn der Schlüssel fehlt, werden Daten eingefügt, anstatt aktualisiert zu werden.

1. Wenn Sie schnellere Exporte durchführen müssen, überprüfen Sie die  **[!UICONTROL In Batches exportieren]** -Option.

   ![](assets/crm-export-batch.png)

1. Im **[!UICONTROL Zuordnung]** Abschnitt, klicken Sie auf **[!UICONTROL Neu]** um die zu exportierenden Felder und deren Zuordnung in Ihrem CRM-System anzugeben.

   Um ein Feld hinzuzufügen, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** in der Symbolleiste und anschließend auf **[!UICONTROL Ausdruck bearbeiten]**.

   >[!NOTE]
   >
   >Wenn für ein Feld keine Übereinstimmung definiert ist, können die Werte nicht aktualisiert werden: sie werden direkt in Ihr CRM eingefügt.

   Ändern Sie bei Bedarf das Datenformat mithilfe der Dropdown-Liste der **[!UICONTROL Konversion]** Spalten. Mögliche Konvertierungstypen werden im Abschnitt [diesem Abschnitt](#data-format).

   >[!NOTE]
   >
   >Die Liste der zu exportierenden Datensätze und das Ergebnis des Exports werden in einer temporären Datei gespeichert, auf die zugegriffen werden kann, bis der Workflow abgeschlossen oder neu gestartet wurde. Auf diese Weise können Sie den Prozess bei Fehlern sicher starten.

## Ergänzende Konfigurationen {#additional-configurations}

### Datenformat {#data-format}

Sie können das Datenformat beim Import in oder aus Ihrem CRM-System sofort konvertieren.

Wählen Sie hierzu in der entsprechenden Spalte die anzuwendende Konvertierung aus.

![](assets/crm-task-import.png)

Im **[!UICONTROL Standard]**-Modus entspricht die Konvertierung zumeist einem einfachen Kopieren/Einfügen der Daten. Die verschiedenen Zeitzonen werden in jedem Fall berücksichtigt.

Darüber hinaus sind folgende Konvertierungen möglich:

* **[!UICONTROL Nur Datum]**: löscht die Felder vom Typ Datum + Uhrzeit .
* **[!UICONTROL Ohne Zeitversatz]**: bricht die im Standardmodus angewendete Zeitzonenverwaltung ab.
* **[!UICONTROL Kopieren/Einfügen]**: verwendet Rohdaten wie Zeichenfolgen (keine Konvertierung).

### Fehlerverarbeitung {#error-processing}

Im Rahmen von Datenimporten oder -exporten können Sie einen spezifischen Prozess auf Fehler und Zurückweisungen anwenden. Wählen Sie dazu die **[!UICONTROL Zurückweisungen in einer Datei speichern]** und **[!UICONTROL Fehler verarbeiten]** Optionen in **[!UICONTROL Verhalten]** Registerkarte.

![](assets/crm-export-options.png)

Mit diesen Optionen werden die entsprechenden ausgehenden Transitionen hinzugefügt.

![](assets/crm-export-transitions.png)

Fügen Sie dann die relevanten Aktivitäten ein, um Daten zu verarbeiten. Fügen Sie beispielsweise eine **Warten** und planen Sie weitere Versuche auf Fehler.

Die ausgehende Transition **[!UICONTROL Zurückweisung]** verleiht Ihnen Zugang zum Ausgabeschema, welches die Spalten für Fehlermeldungen und -Codes und enthält. Bei Salesforce.com lautet die Spalte **errorSymbol** (Fehlersymbol, unterscheidet sich vom Fehler-Code), **errorMessage** (Beschreibung des Fehlerkontexts).

## Import der im CRM gelöschten Objekte {#importing-objects-deleted-in-the-crm}

Sie können in Ihrem CRM-System gelöschte Objekte in Adobe Campaign importieren.

1. Wählen Sie den Vorgang vom Typ **[!UICONTROL Import der im CRM gelöschten Objekte]** aus.
1. Navigieren Sie zu **[!UICONTROL Remote-Objekt]** in der Dropdown-Liste und wählen Sie das vom Prozess betroffene Objekt aus. Dieses Objekt entspricht einer der Tabellen, die bei der Connector-Konfiguration in Adobe Campaign erstellt wurden.
1. Geben Sie den Löschzeitraum an, der im Abschnitt **[!UICONTROL Startdatum]** und **[!UICONTROL Enddatum]** -Felder (Datumsangaben sind enthalten).

   >[!CAUTION]
   >
   >Der Löschzeitraum muss mit Ihren CRM-spezifischen Einschränkungen übereinstimmen. Bei Salesforce.com können beispielsweise Elemente, die vor mehr als 30 Tagen gelöscht wurden, nicht wiederhergestellt werden.

## Löschung von Objekten im CRM {#deleting-objects-in-the-crm}

Um Objekte in Ihrem CRM-System zu löschen, geben Sie den Primärschlüssel der zu löschenden Remote-Elemente an.

Im Tab **[!UICONTROL Verhalten]** kann die Zurückweisungsverarbeitung aktiviert werden. Dies erzeugt eine weitere ausgehende Transition aus der **[!UICONTROL CRM-Connector]**-Aktivität. Konsultieren Sie diesbezüglich die [Fehlerverarbeitung](#error-processing).

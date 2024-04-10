---
product: campaign
title: HTTP-Übertragung
description: Erfahren Sie mehr über die Workflow-Aktivität "HTTP-Übertragung".
feature: Workflows
exl-id: 73bacf61-ac03-4a5c-b03b-6dfbe3fb9538
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 82%

---

# HTTP-Übertragung{#web-download}



Die **HTTP-Übertragung** lädt Dateien über eine explizite URL, ein externes Konto oder eine Adobe Campaign-Instanz unter Verwendung des Hypertext Transfer Protocols (HTTP). Sowohl die GET- als auch die POST-Methode können zur Anwendung kommen.

## Eigenschaften {#properties}

1. **Auswahl der Webdatei**

   Die Angabe der zu übertragenden Datei kann entweder über eine explizite URL, über ein externes HTTP-Konto oder über eine Adobe-Campaign-Instanz erfolgen. Folgende Parameter stehen zur Verfügung:

   * **[!UICONTROL Explizite URL]**: Die URL wird im entsprechenden Feld angegeben. Die URL kann Variablen enthalten.

     ![](assets/download_web_edit.png)

   * Bei Verwendung eines **[!UICONTROL externen Kontos]** wird das Konto aus der Dropdown-Liste ausgewählt und die zu ladende Datei angegeben.

     Externe Konten werden über das konfiguriert. **[!UICONTROL Administration > Plattform > Externe Konten]** Knoten der Adobe Campaign-Baumstruktur. Die Kontoparameter können über das **[!UICONTROL Link bearbeiten]** Symbol.

     ![](assets/download_web_edit_external.png)

   * **[!UICONTROL Adobe-Campaign-Instanz]**: Die Übertragung erfolgt über eine Adobe-Campaign-Instanz.

     ![](assets/download_web_edit_instance.png)

1. **Verlaufserstellung**

   Der Link **[!UICONTROL Verlaufsparameter der Dateien...]** ermöglicht die Angabe des Speicherverzeichnisses für die übertragenen Dateien und der Bereinigungsparameter.

   ![](assets/download_web_edit_hist.png)

   Folgende Optionen stehen zur Verfügung:

   * **[!UICONTROL Standard-Speicherverzeichnis verwenden]**: Die Datei wird immer verschoben, bevor sie verarbeitet wird. Wenn diese Option aktiviert ist, wird die Datei in das standardmäßige Speicherverzeichnis (das **Vars** Verzeichnis des Adobe Campaign-Installationsordners). Um ein Speicherverzeichnis anzugeben, deaktivieren Sie das Kontrollkästchen und geben Sie den Pfad in der **[!UICONTROL Speicherverzeichnis]** Feld
   * **[!UICONTROL Anzahl Dateien]**: Geben Sie die Anzahl an Dateien an, die maximal im Speicherverzeichnis beibehalten werden soll.
   * **[!UICONTROL Maximale Größe (in MB)]**: Geben Sie die Größe an, die das Speicherverzeichnis nicht überschreiten darf (in Megabytes).

   Jede Datei wird mindestens 24 Stunden aufbewahrt, bevor Sie den Bereinigungsregeln unterzogen wird. Die Bereinigung erfolgt zu Beginn der Aktivität und berücksichtigt daher nicht die Dateien der aktuellen Workflow-Ausführung.

   Die Löschung beginnt jeweils mit den ältesten Dateien und endet mit den neuesten. Die ältesten Dateien werden gelöscht bis beide Bereinigungsregeln geprüft wurden. Wenn beispielsweise die maximale Anzahl auf 100 begrenzt wurde, enthält das Speicherverzeichnis stets die 100 vor Beginn des Workflows neuesten Dateien, zuzüglich der vom laufenden Workflow übertragenen Dateien.

   Wenn Sie für die Optionen **[!UICONTROL Anzahl Dateien]** und **[!UICONTROL Maximale Größe (in MB)]** keine Grenzwerte vorschreiben möchten, können Sie jeweils den Wert 0 angeben.

1. **Erweiterte Parameter**

   Der Link **[!UICONTROL Erweiterte Parameter...]** bietet Zugriff auf folgende Optionen:

   ![](assets/download_web_edit_advanced.png)

   Die Option **[!UICONTROL Fehler verarbeiten]** wird im Abschnitt [Verarbeitungsfehler](monitor-workflow-execution.md#processing-errors) erläutert.

## Ausgabeparameter {#output-parameters}

* filename: Vollständiger Name der übertragenen Datei.

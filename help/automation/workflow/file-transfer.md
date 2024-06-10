---
product: campaign
title: Dateiübertragung
description: Erfahren Sie mehr über die Workflow-Aktivität "Dateiübertragung".
feature: Workflows, Data Management
role: User
exl-id: 794de398-f35d-4c2b-af29-d6fd38eb9394
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---

# Dateiübertragung{#file-transfer}

Mit der Aktivität **Dateiübertragung** können Sie Dateien senden und empfangen, das Vorhandensein von Dateien prüfen oder Dateien auf einem Server auflisten. Hierfür können die Protokolle Azure Blob Storage, Amazon Simple Storage Service (S3), FTP oder SFTP verwendet werden.
Bei Verwendung einer S3-, Azure Blob Storage- oder SFTP-Verbindung ist es außerdem möglich, Segmentdaten über die Echtzeit-Kundendatenplattform von Adobe in Adobe Campaign zu importieren. Weitere Informationen hierzu finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=de){target="_blank"}.

## Eigenschaften {#properties}

Wählen Sie im Feld **[!UICONTROL Aktion]** die auszuführende Aktivität aus.

![](assets/file_transfert_action.png)

Die weitere Konfiguration hängt von der gewählten Aktion ab.

1. **Dateiempfang**

   Zum Empfang von auf einem Remote-Server gespeicherten Dateien ist im Feld **[!UICONTROL Aktion]** die Option **[!UICONTROL Dateiempfang]** auszuwählen und die URL anzugeben.

   ![](assets/file_transfert_edit.png)

   Aktivieren Sie das Kontrollkästchen **[!UICONTROL Externes Konto verwenden]**, um ein Konto aus den Azure Blob Storage-, S3-, FTP- oder SFTP-Konten auszuwählen, die im Knoten **[!UICONTROL Administration > Plattform > Externe Konten]** des Navigationsbaums konfiguriert sind. Geben Sie danach an, welches Verzeichnis auf dem Server die Dateien enthält, die heruntergeladen werden sollen.

   ![](assets/file_transfert_edit_external.png)

1. **Dateiübertragung**

   Um eine Datei an einen Server zu senden, wählen Sie **[!UICONTROL Datei-Upload]** im Feld **[!UICONTROL Aktion]**. Sie müssen den Ziel-Server im Abschnitt **[!UICONTROL Remote-Server]** des Editors angeben. Die Parameter sind mit denen für eingehende Dateien identisch. Siehe oben.

   Die Quelldatei kann aus der vorherigen Aktivität stammen. In diesem Fall muss die Option **[!UICONTROL Durch vorhergehende Aktivität erzeugte Datei verwenden]** ausgewählt sein.

   ![](assets/file_transfert_edit_send.png)

   Dies kann sich auch auf eine oder mehrere andere Dateien beziehen. Um sie auszuwählen, deaktivieren Sie die Option und klicken Sie auf **[!UICONTROL Einfügen]**. Geben Sie den Zugriffspfad der zu sendenden Datei an. Um eine weitere Datei hinzuzufügen, klicken Sie erneut auf **[!UICONTROL Einfügen]**. Die Dateien haben nun alle ihre eigenen Registerkarten.

   ![](assets/file_transfert_source.png)

   Mithilfe der Pfeile kann die Reihenfolge der Tabs angepasst werden. Die Dateien werden in dieser Reihenfolge an den Server übertragen.

   Bei Auswahl der Option **[!UICONTROL Verlauf der übertragenen Dateien speichern]** werden die verschiedenen Übertragungen im Verzeichnis protokolliert.

1. **Existenztest einer Datei**

   Um das Vorhandensein einer Datei zu prüfen, wählen Sie im Feld **[!UICONTROL Aktion]** die Option **[!UICONTROL Existenztest einer Datei]** aus. Die Konfiguration des Remote-Servers entspricht der für das Herunterladen einer Datei. Weiterführende Informationen hierzu finden Sie in diesem [Abschnitt](#properties).

   ![](assets/file_transfert_edit_test.png)

1. **Dateiauflistung**

   Um eine Liste der vorhandenen Dateien zu erhalten, wählen Sie im Feld **[!UICONTROL Aktion]** die Option **[!UICONTROL Dateiauflistung]** aus. Die Konfiguration des Remote-Servers entspricht der für das Herunterladen einer Datei. Weiterführende Informationen hierzu finden Sie in diesem [Abschnitt](#properties).

   Die Option **[!UICONTROL Alle Dateien auflisten]**, die bei Auswahl der Aktion **[!UICONTROL Dateiauflistung]** erscheint, ermöglicht es, alle auf dem Server befindlichen Dateien in der Ereignisvariable **vars.filenames** zu erfassen. Die Dateinamen werden durch `\n`-Zeichen getrennt angegeben.

Zwei weitere Optionen stehen generell für die Dateiübertragung zur Verfügung:

* Die Option **[!UICONTROL Fehlen von Dateien bearbeiten]** erzeugt eine Transition, die aktiviert wird, wenn im angegebenen Verzeichnis keine Datei vorhanden ist.
* Die Option **[!UICONTROL Fehler verarbeiten]** wird im Abschnitt [Verarbeitungsfehler](monitor-workflow-execution.md#processing-errors) erläutert.

Der Link **[!UICONTROL Erweiterte Parameter...]** bietet Zugriff auf folgende Optionen:

![](assets/file_transfert_advanced.png)

* **[!UICONTROL Quelldateien nach der Übertragung löschen]**

  Löscht die Dateien auf dem Remote-Server. Wenn Sie diese Option deaktiviert lassen, müssen Sie die Größe des archivierten Inhalts im SFTP-Verzeichnis manuell überwachen.

* **[!UICONTROL SSL verwenden]**

  Verwendet eine gesicherte Verbindung bei der Dateiübertragung (SSL-Protokoll).

* **[!UICONTROL Sitzungsprotokolle anzeigen]**

  Ruft die Logs zur Azure Blob Storage-, S3-, FTP- bzw. SFTP-Übertragung ab und fügt sie in die Workflow-Logs ein.

* **[!UICONTROL Passiven Modus deaktivieren]**

  Ermöglicht es, den für die Übertragung zu verwendenden Verbindungsport anzugeben.

Über den Link **[!UICONTROL Verlaufsparameter der Dateien...]** besteht Zugriff auf Optionen, die im Abschnitt [HTTP-Übertragung](web-download.md) (im Schritt **[!UICONTROL Verlaufserstellung]**) beschrieben werden.

## Eingabeparameter {#input-parameters}

* filename

  Vollständiger Name der übertragenen Datei.

## Ausgabeparameter {#output-parameters}

* filename

  Vollständiger Name der empfangenen Datei, wenn die Option **[!UICONTROL Durch vorhergehende Aktivität erzeugte Datei verwenden]** angekreuzt wurde.

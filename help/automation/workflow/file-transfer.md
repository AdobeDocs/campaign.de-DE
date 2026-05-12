---
product: campaign
title: Dateiübertragung
description: Erfahren Sie mehr über die Workflow-Aktivität "Dateiübertragung".
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 794de398-f35d-4c2b-af29-d6fd38eb9394
TQID: https://experienceleague.adobe.com/VeDBB3FCIUIkD-IEdPlUtjhX9CKFiQptIH-eys-iG2o
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 644
ht-degree: 80%

---

# Dateiübertragung{#file-transfer}

Mit der Aktivität **Dateiübertragung** können Sie Dateien senden und empfangen, das Vorhandensein von Dateien prüfen oder Dateien auf einem Server auflisten. Hierfür können die Protokolle Azure Blob Storage, Amazon Simple Storage Service (S3), FTP oder SFTP verwendet werden.
Bei Verwendung einer S3-, Azure Blob Storage- oder SFTP-Verbindung ist es außerdem möglich, Segmentdaten über die Echtzeit-Kundendatenplattform von Adobe in Adobe Campaign zu importieren. Weitere Informationen hierzu finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=de){target="_blank"}.

## Eigenschaften {#properties}

Wählen Sie im Feld **[!UICONTROL Aktion]** die auszuführende Aktivität aus.

![](assets/file_transfert_action.png)

Die weitere Konfiguration hängt von der gewählten Aktion ab.

1. **Dateiempfang**

   Um auf einem Remote-Server gespeicherte Dateien zu empfangen, wählen Sie **[!UICONTROL Datei herunterladen]** im Feld **[!UICONTROL Aktion]** aus. Die URL muss im entsprechenden Feld angegeben werden.

   ![](assets/file_transfert_edit.png)

   Aktivieren Sie das Kontrollkästchen **[!UICONTROL Externes Konto verwenden]**, um ein Konto aus den Azure Blob Storage-, S3-, FTP- oder SFTP-Konten auszuwählen, die im Knoten **[!UICONTROL Administration > Plattform > Externe Konten]** des Navigationsbaums konfiguriert sind. Geben Sie danach an, welches Verzeichnis auf dem Server die Dateien enthält, die heruntergeladen werden sollen.

   ![](assets/file_transfert_edit_external.png)

1. **Dateiübertragung**

   Um eine Datei an einen Server zu senden, wählen Sie **[!UICONTROL Datei-Upload]** im Feld **[!UICONTROL Aktion]**. Sie müssen den Ziel-Server im Abschnitt **[!UICONTROL Remote-Server]** des Editors angeben. Die Parameter sind mit denen für eingehende Dateien identisch. Siehe oben.

   Die Quelldatei kann aus der vorherigen Aktivität stammen. In diesem Fall muss die Option **[!UICONTROL Durch vorhergehende Aktivität erzeugte Datei verwenden]** ausgewählt sein.

   ![](assets/file_transfert_edit_send.png)

   Dies kann sich auch auf eine oder mehrere andere Dateien beziehen. Um sie auszuwählen, deaktivieren Sie die Option und klicken Sie auf **[!UICONTROL Einfügen]**. Geben Sie den Zugriffspfad der zu sendenden Datei an. Um eine weitere Datei hinzuzufügen, klicken Sie erneut auf **[!UICONTROL Einfügen]**. Die Dateien haben nun alle ihre eigenen Registerkarten.

   ![](assets/file_transfert_source.png)

   Mit den Pfeilen können Sie die Reihenfolge der Registerkarten ändern. Dies bezieht sich auf die Reihenfolge, in der Dateien an den Server gesendet werden.

   Mit **[!UICONTROL Option „Verlauf der gesendeten Dateien]**&quot; können Sie die gesendeten Dateien verfolgen. Auf diesen Verlauf kann über das Verzeichnis zugegriffen werden.

1. **Existenztest einer Datei**

   Um das Vorhandensein einer Datei zu testen, wählen Sie die Option **[!UICONTROL Testen, um zu sehen, ob]** Datei vorhanden ist **[!UICONTROL im Feld Aktion]** aus. Die Konfiguration des Remote-Servers entspricht der Konfiguration für den Datei-Download. Weiterführende Informationen hierzu finden Sie in diesem [Abschnitt](#properties).

   ![](assets/file_transfert_edit_test.png)

1. **Dateiauflistung**

   Um die Dateien aufzulisten, wählen Sie die Option **[!UICONTROL Dateiauflistung]** aus dem Feld **[!UICONTROL Aktion]** aus. Die Konfiguration des Remote-Servers entspricht der für den Empfang von Dateien. Weiterführende Informationen hierzu finden Sie in diesem [Abschnitt](#properties).

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

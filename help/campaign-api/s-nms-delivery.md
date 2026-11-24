---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# delivery

Schema eines Versands oder einer Versandvorlage

Eine Vorlage ist eine Versandvorlage mit allen erforderlichen Parametern. Eine Versandvorlage kann manuell von der Client-Konsole aus oder beim Eintreten eines Ereignisses ausgeführt werden (gestartet von der Planung oder programmgesteuert von einem SOAP-Aufruf aus).

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | Fügt ein Kontigent zu einem in Vorbereitung befindlichen Versand hinzu |
| [BuildForward](sm-delivery-buildforward.md) | Erstellt die HTML-Seite |
| [BuildMirror](sm-delivery-buildmirror.md) | Erstellt die HTML-Mirrorseite |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | Erstellt die HTML-Mirrorseite |
| [BuildPreview](sm-delivery-buildpreview.md) | Erstellt die Vorschau eines Versandinhalts oder einer Ausgabedateizeile (im externen Modus). |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | Erstellt die Vorschau eines Versandinhalts oder einer Ausgabedateizeile (im externen Modus). |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDeliverys](sm-delivery-cleanupdeliveries.md) | Veranlasst beim Mid-Sourcing-Server die Löschung bestimmter Sendungen |
| [CollectLogs](sm-delivery-collectlogs.md) | Erstellt eine Tabelle mit sämtlichen Versandlogs einer Versandliste |
| [CreateFromModel](sm-delivery-createfrommodel.md) | Erstellung eines Versands von einer Vorlage ausgehend (durch den internen Namen bezeichnet) |
| [DeployTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | Transaktionsnachricht auf Ausführungsinstanzen veröffentlichen. Gibt bei erfolgreicher Veröffentlichung „true“ und andernfalls „false“ zurück. |
| [DeployTriggerMessages](sm-delivery-deploytriggermessages.md) | Ausgewählte Transaktionsnachrichten in den Ausführungsinstanzen veröffentlichen |
| [DiagnoseHTML](sm-delivery-diagnosehtml.md) | Startet die Prüfung des HTML-Inhalts |
| [DispatchImages](sm-delivery-dispatchimages.md) | Veranlasst den Anwendungs-Server, die Bilder an den Mid-Sourcing-Server zu senden |
| [ExecCommand](sm-delivery-execcommand.md) | Führt einen Befehl in Bezug auf den Versand aus |
| [ExecuteJob](sm-delivery-executejob.md) | Führt einen asynchronen Vorgang im Bezug auf einen Versand aus. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | Abschließende Analyse eines Versands im Mid-Sourcing-Modus. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | Ruft die letzten Protokolllogs und den Versandstatus ab. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | Gibt die Liste der den Versand betreffenden Dateien aus, die auf dem Server verfügbar sind. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | Ruft die zuletzt aktualisierten Versandlogs in Bezug auf Mid-Sourcing-Sendungen ab. |
| [GetMidDeliverys](sm-delivery-getmiddeliveries.md) | Ruft den Status der zuletzt im Mid-Sourcing-Modus aktualisierten Sendungen ab. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | Gibt den Xtk-Schlüssel des Mid-Sourcing-Servers aus |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | Ruft die URL einer HTML-Mirrorseite ab. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | Konvertiert HTML-Inhalt in einfachen Text |
| [ImagePublishing](sm-delivery-imagepublishing.md) | Führt die Anschlussvorgänge aus: Verschieben des Bildes in einen spezifischen Ordner und tatsächliches Online-Stellen |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | Installiert eine Transaktionsnachrichtenvorlage auf der Ausführungsinstanz |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | Ist am Ende der Nachrichtenvorbereitung aufzurufen, außer im Mid-Sourcing-Modus (private Methode). |
| [LaunchFCP](sm-delivery-launchfcp.md) | Startet einen Testversand |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | Lädt eine Komponenten-Liste zur Vorab-Bearbeitung einschließlich der abhängigen Elemente (Gestaltungsbausteine, Optionen, zusätzliche Script-Objekte usw.). |
| [Aussetzen](sm-delivery-pause.md) | Setzt einen laufenden Versand aus |
| [Play](sm-delivery-play.md) | Startet einen Versand. |
| [Vorbereiten](sm-delivery-prepare.md) | Analysiert den Versand: Zielgruppenbestimmung und Personalisierung |
| [PrepareAndStart](sm-delivery-prepareandstart.md) | Analysiert den Versand und startet ihn, wenn kein Fehler aufgetreten ist. |
| [PrepareFromId](sm-delivery-preparefromid.md) | Analysiert einen Versand |
| [PrepareMessage](sm-delivery-preparemessage.md) | Nachrichtenpersonalisierung |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | Nachrichtenpersonalisierung |
| [PrepareMultipartRelated](sm-delivery-preparemultipartrelated.md) | Speichert die in die E-Mail einzuschließenden Bilder in der Datenbank |
| [PrepareNotification](sm-delivery-preparenotification.md) | Analysiert eine Benachrichtigung, die einem existierenden Versand hinzugefügt wurde. |
| [PrepareProof](sm-delivery-prepareproof.md) | Versandanalyse zur Vorbereitung des Testversands |
| [PrepareTarget](sm-delivery-preparetarget.md) | Zählung und Schlichtung der Versandzielgruppe |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | Zählung und Schlichtung der Versandzielgruppe |
| [PreviewExtraction](sm-delivery-previewextraction.md) | Extraktionsdateivorschau |
| [PriorizeLogs](sm-delivery-prioritizelogs.md) | Priorisiert Versandlogs einer Versandliste |
| [PriorizeTarget](sm-delivery-prioritizetarget.md) | Schlichtung der Versandzielgruppe |
| [QueueNotification](sm-delivery-queuenotification.md) | Einreihung einer Kreation in die Warteschlange und Unterbreitung einer Benachrichtigung von einer Vorlage ausgehend. |
| [RecomputeStats](sm-delivery-recomputestats.md) | Aktualisiert Sendungs- und Trackingstatistiken eines Versands. |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | Speichert die URLs dieses Versands als URL-Vorlagen. |
| [Anhalten](sm-delivery-stop.md) | Schließt einen laufenden Versand ab. |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | Fügt die Informationen bezüglich der Mirrorseitenerzeugung für eine Versandkontingentkollektion hinzu. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | Fügt die Informationen bezüglich der Mirrorseitenerzeugung für eine Versandkontingentkollektion hinzu. |
| [SubmitDelivery](sm-delivery-submitdelivery.md) | Erstellung und Unterbreitung eines Versands von einer Vorlage ausgehend (durch den internen Namen bezeichnet) |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | Erstellung und Unterbreitung eines Versands von einer Vorlage ausgehend (durch die interne Kennung bezeichnet) |
| [SubmitJob](sm-delivery-submitjob.md) | Unterbreitet einen asynchron auszuführenden Auftrag bezüglich eines Versands |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | Unterbreitet einen Versand im Mid-Sourcing-Modus |
| [SubmitNotification](sm-delivery-submitnotification.md) | Erstellung und Unterbreitung einer Benachrichtigung von einer Versandvorlage ausgehend |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | Aktualisiert den Status der Versandlogs, verarbeitet die Fehler und aktualisiert den Versandzähler. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | Muss aufgerufen werden, wenn gespeicherte Sendungen geändert wurden, um in anderen Threads jeweils die aktuelle Version zu haben (private Methode) |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | Ändert den imageConfig-Knoten, damit die bereits auf dem Server befindlichen Bilder berücksichtigt werden. |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | Prüft die Kohärenz der zur Schubdefinition angegebenen Informationen. |

## Generische Methoden

| Methode | Beschreibung |
| --- | --- |
| [Erstellen](f-create.md) | Erstellt eine neue Entität, die einem bestimmten Schema entspricht. |
| [LOAD](f-load.md) | Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück. |
| [Speichern](m-entity-save.md) | Speichert eine Entität in der Datenbank |

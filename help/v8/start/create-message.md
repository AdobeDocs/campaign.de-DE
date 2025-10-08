---
title: Erstellen Ihres ersten Versands
description: Erstellen Ihres ersten Versands
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 56d5628312ea3dedf9335dd0933811e4bf66eb97
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 99%

---

# Erstellen Ihres ersten Versands {#create-a-msg}

Auf dieser Seite erfahren Sie, wie Sie einen einmaligen Versand erstellen. Sie können für Ihre Anwendungsfälle weitere Versandtypen erstellen. Weitere Informationen zu den verschiedenen Versandtypen und deren Erstellung finden Sie auf [dieser Seite](gs-message.md).

Dies sind die wichtigsten Schritte beim Erstellen eines einmaligen Versands:

1. **Einen neuen Versand erstellen**.  [mehr dazu](#create-the-delivery)

1. **Versandinhalt festlegen**. [Weitere Informationen](#content-of-the-delivery)

1. **Zielpopulation bestimmen**. [Weitere Informationen](#target-population)

Anschließend können Sie Ihre Nachrichten mit Adobe Campaign vorbereiten, testen, senden und überwachen.

>[!NOTE]
>
>Die in diesem Abschnitt beschriebenen Schritte setzen voraus, dass alle Empfängerinnen und Empfänger sowie deren Profile in einer Datenbank gespeichert sind, außer bei externen Sendungen. Siehe [Auswählen externer Empfängerinnen und Empfänger](#selecting-external-recipients).

## Erstellen des Versands {#create-the-delivery}

Gehen Sie wie folgt vor, um einen Versand zu erstellen:

1. Navigieren Sie zur Versandliste und klicken Sie auf **[!UICONTROL Erstellen]**.
1. Wählen Sie den Versandkanal aus. Wählen Sie dazu die entsprechende Versandvorlage aus der Dropdown-Liste aus.

   ![](../send/assets/select-the-new-template.png)

   Es gibt für jeden installierten Kanal (E-Mail, Fax, Telefon, Mobile-Kanäle (Push, SMS), Briefpost, X (Twitter) usw.) eine integrierte Vorlage. Die in der Liste verfügbaren Kanäle hängen von Ihrer Lizenz ab.

   Sie können neue Versandvorlagen erstellen, um bestimmte Parameter vorab an Ihre Anforderungen anzupassen. [Weitere Informationen](../send/create-templates.md).

1. Geben Sie im Feld **[!UICONTROL Titel]** einen Namen für den Versand ein.

   (Optional) Sie können dem Versand außerdem einen Code zuordnen. Diese Informationen werden in der Versandliste angezeigt, sind für die Empfängerinnen und Empfänger der Nachrichten jedoch nicht sichtbar.

1. (Optional) Geben Sie im Feld **[!UICONTROL Beschreibung]** weitere, den Versand betreffende Informationen ein.
1. (Optional) Wählen Sie die Versandart im entsprechenden Feld aus. Diese Information ist insbesondere für die Versandverfolgung nützlich, da Sie die Sendungen in Listen und Abfragen nach diesem Kriterium filtern können.
1. Klicken Sie auf **[!UICONTROL Fortfahren]**, um das Fenster „Nachrichteninhalt“ anzuzeigen.

## Festlegen des Versandinhalts {#content-of-the-delivery}

Der Versandinhalt ist bereit zur Konfiguration. Die Definition des Versandinhalts erfolgt für jeden Kanal einzeln. Weiterführende Informationen dazu finden Sie im entsprechenden Abschnitt:

* [Definieren des E-Mail-Inhalts](../send/email.md)
* [Definieren des SMS-Inhalts](../send/sms/sms-content.md)
* [Definieren des Direkt-Mail-Inhalts](../send/direct-mail.md)
* [Definieren des Inhalts einer Push-Benachrichtigung](../send/push.md)


## Definieren der Zielgruppe {#target-population}

Für jeden Versand können verschiedene Zielgruppen bestimmt werden:

* **Hauptzielgruppe**: Profile, die Nachrichten erhalten. [Weitere Informationen](#select-the-main-target)
* **Testversand-Zielgruppe**: Profile, die Testversandnachrichten erhalten. Ein Testversand dient der Validierung einer Nachricht, bevor sie an die Hauptzielgruppe gesendet wird. [Weitere Informationen](#select-the-proof-target)

Zusätzlich können Sie im Rahmen einer Marketing-Kampagne Folgendes hinzufügen:

* **Testadressen**: Empfängerinnen und Empfänger, die nicht zur Zielgruppe des Versands gehören, aber den Versand erhalten. [Weitere Informationen](../audiences/test-profiles.md)
* **Kontrollgruppen**: Population, die den Versand nicht erhält und verwendet wird, um das Verhalten und die Auswirkungen der Kampagne zu verfolgen. [Weitere Informationen](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Auswahl der Hauptempfänger des Versands {#select-the-main-target}

Meistens wird die Hauptzielgruppe aus der Adobe Campaign-Datenbank extrahiert (Standardmodus). Empfängerinnen und Empfänger können aber auch in einer [externen Datei](#selecting-external-recipients) gespeichert werden.

Um die Versandempfänger auszuwählen, gehen Sie wie folgt vor:

1. Wählen Sie im Versand-Editor **[!UICONTROL An]** aus.
1. Wählen Sie die erste Option, wenn Ihre Empfänger in der Datenbank gespeichert sind.

   ![](../send/sms/assets/audience_to.png){zoomable="yes"}

1. Wählen Sie das [Zielgruppen-Mapping](../audiences/target-mappings.md) in der Dropdown-Liste **[!UICONTROL Zielgruppen-Mapping]** aus. 
1. Wählen Sie zur Konfiguration von Einschränkungsfiltern die Schaltfläche **[!UICONTROL Hinzufügen]** aus.

   ![](assets/target-type.png){width="60%" align="left" zoomable="yes"}

   Wählen Sie einen Filtertyp aus und klicken Sie auf **[!UICONTROL Weiter]**, um die Bedingungen zu definieren. Sie können die gefilterten Empfängerinnen und Empfänger über die Registerkarte **[!UICONTROL Vorschau]** anzeigen. Bei gewissen Zieltypen ermöglicht die Schaltfläche **[!UICONTROL Zielgruppe einschränken]** die Kombination verschiedener Zielgruppenbestimmungskriterien.

   Folgende Zieltypen stehen zur Verfügung:

   * **[!UICONTROL Filterbedingungen]**: Verwenden Sie diese Option, um eine benutzerdefinierte Abfrage zum Abrufen der Empfänger zu definieren. Informationen zum Erstellen einer Abfrage finden Sie in [diesem Abschnitt](../start/query-editor.md).
   * **[!UICONTROL Empfängerliste]**: Verwenden Sie diese Option, um eine Profilliste auszuwählen. Weitere Informationen zu Listen finden Sie in [diesem Abschnitt](../audiences/create-audiences.md).
   * **[!UICONTROL Empfänger]**: Verwenden Sie diese Option, um ein bestimmtes Profil in der Datenbank auszuwählen.
   * **[!UICONTROL Empfänger aus einem Ordner]**: Verwenden Sie diese Option, um alle Profile in einem bestimmten Ordner auszuwählen.
   * **[!UICONTROL Versandempfänger]**: Verwenden Sie diese Option, um die Zielgruppe anhand der Empfängerinnen und Empfängern eines Versands zu erstellen. Sie müssen dann den Versand in der Liste auswählen:

     ![](assets/target-recipient-delivery.png)

   * **[!UICONTROL Empfänger von Sendungen eines bestimmten Ordners]**: Verwenden Sie diese Option, um die Zielgruppe aus den in einem bestimmten Ordner enthaltenen Empfänger-Sendungen zu erstellen.

     ![](assets/target-delivery-folder.png)

     Sie können außerdem die Liste der Empfänger nach deren Verhalten beim Empfang früherer E-Mails einschränken:

     ![](assets/target-filter-behavior.png)

     >[!NOTE]
     >
     >Die Option **[!UICONTROL Unterordner einbeziehen]** dehnt den Kreis der Empfänger auf die in Unterordnern des ausgewählten Knotens enthaltenen Sendungen aus.

   * **[!UICONTROL Abonnenten eines Informationsdienstes]**: Angabe des Newsletters, den die Empfängerinnen und Empfänger abonniert haben müssen, um in die Zielgruppe des Versands aufgenommen zu werden.

     ![](assets/target-service.png)

   * **[!UICONTROL Benutzerfilter]**: Mit dieser Option können Sie auf vorkonfigurierte Filter zugreifen, um sie als Filterkriterien für Profile in der Datenbank zu verwenden.  Weiterführende Informationen zu Benutzerfiltern finden Sie in [diesem Abschnitt](../audiences/create-filters.md#default-filters).
   * Mit der Option **[!UICONTROL Empfänger von diesem Segment ausschließen]** können Sie Empfängerinnen und Empfänger als Zielgruppe auswählen, die nicht den definierten Zielkriterien entsprechen. Um diese Option zu verwenden, aktivieren Sie das entsprechende Kontrollkästchen und wenden Sie dann die Zielgruppenbestimmung an (wie zuvor definiert), um die resultierenden Profile auszuschließen.

1. Geben Sie im Feld **[!UICONTROL Titel]** einen Namen für diese Zielgruppenbestimmung ein. Der Titel entspricht standardmäßig dem Titel der ersten Zielgruppenbestimmung. Bei der Kombination von Filterkriterien wird empfohlen, einen expliziten Namen zu verwenden.
1. Klicken Sie auf **[!UICONTROL Beenden]**, um die Optionen der Zielgruppenbestimmung zu bestätigen.

   Die derart festgelegten Targeting-Kriterien werden im mittleren Bereich des Hauptzielgruppe-Tabs zusammengefasst. Durch Klick auf ein Kriterium können Sie seinen Inhalt (Konfiguration und Vorschau) prüfen. Klicken Sie auf das rote Kreuz rechts, um das Kriterium zu löschen.

   ![](assets/target-remove-criterion.png)

### Auswahl externer Empfänger {#selecting-external-recipients}

Sie können Nachrichten an Profile senden, die nicht in der Datenbank, sondern in einer externen Datei gespeichert sind. Gehen Sie wie folgt vor, um beispielsweise einen Versand an Empfangende auszuführen, die aus einer Textdatei importiert wurden:

1. Wählen Sie den Link **[!UICONTROL An]** aus, um die Empfänger Ihres Versands festzulegen.
1. Wählen Sie die Option **[!UICONTROL In einer externen Datei definiert]** aus.
1. Wählen Sie die Datei mit den Empfangenden aus.
1. Wählen Sie beim Import der Empfangenden den Link **[!UICONTROL Dateiformat definieren...]** aus, um die externe Datei auszuwählen und zu konfigurieren.

   Weitere Informationen zum Datenimport finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/de/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs#step-2---source-file-selection){target="_blank"}.

1. Wählen Sie **[!UICONTROL Beenden]** und konfigurieren Sie Ihren Versand als Standardversand.

>[!CAUTION]
>
>Schließen Sie beim Definieren des Nachrichteninhalts für einen E-Mail-Versand an externe Empfangende keinen Link zur Mirrorseite ein. Die Seite kann bei dieser Versandart nicht erstellt werden.

### Ausschlussparameter {#define-exclusion-settings}

Bei der Definition der [Zielgruppe eines Versands](#target-population) wird die Registerkarte **[!UICONTROL Ausschlüsse]** verwendet, um die Anzahl an Nachrichten zu begrenzen. Die Standardparameter werden empfohlen, Sie können die Einstellungen nach Bedarf anpassen. Diese Optionen sollten jedoch nur von Profis geändert werden, um Missbrauch und Fehler zu vermeiden.

>[!CAUTION]
>
>Erfahrene Benutzende können diese Einstellungen für bestimmte Anwendungsfälle ändern. Adobe empfiehlt jedoch, die Standardkonfiguration beizubehalten.

Sie können Adressen, für die die maximal zulässige Anzahl von aufeinanderfolgenden Fehlern erreicht wurde oder deren Qualitätsindex unter der in diesem Fenster angegebenen Schwelle liegt, vom Versand ausschließen.  Das Gleiche gilt für nicht-qualifizierte Adressen, d. h. solche, für die keine Informationen vonseiten des Dienstleisters übermittelt wurden.

Um die Standardkonfiguration zu ändern, klicken Sie auf den Link **[!UICONTROL Bearbeiten...]**.

![](assets/target-exclusion-settings.png)

+++ Siehe die verfügbaren Optionen

* **[!UICONTROL Doppelte Adressen vom Versand ausschließen]**: Diese Option ist standardmäßig aktiviert und entfernt doppelte E-Mail-Adressen während des Versands.  Die Vorgehensweise hängt dabei von der Art der Verwendung der Adobe Campaign-Software und den in der Datenbank enthaltenen Daten ab. Der Wert dieser Option kann für jede Versandvorlage konfiguriert werden.
* **[!UICONTROL Schließen Sie Empfangende aus, die nicht mehr kontaktiert]** werden möchten, d. h. Empfangende, deren E-Mail-Adressen sich auf einer Blockierungsliste („Opt-out“) befinden. Diese Option muss ausgewählt bleiben, um die Berufsethik des E-Marketings einzuhalten.
* **[!UICONTROL Adressen in Quarantäne ausschließen]**: Mit dieser Option können Sie alle Adressen von Profilen aus der Zielgruppe ausschließen, die sich in Quarantäne befinden.  Es wird dringend empfohlen, diese Option aktiviert zu lassen. Weitere Informationen zur Quarantäneverwaltung finden Sie in [diesem Abschnitt](../send/quarantines.md).
* **[!UICONTROL Versand begrenzen]**: Die Begrenzung erfolgt auf eine bestimmte Anzahl an Nachrichten. Mit dieser Option können Sie die maximale Anzahl der zu versendenden Nachrichten eingeben. Wenn der Inhalt der Zielgruppe die angegebene Anzahl von Nachrichten überschreitet, wird eine Zufallsauswahl auf die Zielgruppe angewendet.  Behalten Sie den Wert „0“ bei, um alle Nachrichten zu senden.
* **[!UICONTROL In der Zielgruppe doppelt enthaltene Einträge (identische Kennung) beibehalten]**: Mit dieser Option können mehrere Sendungen an Empfangende gesendet werden, die verschiedene Zielgruppenbestimmungskriterien erfüllen.
+++


### Auswählen der Empfangenden von Testversandnachrichten {#select-the-proof-target}

Bei E-Mail-Sendungen können Sie Testsendungen durchführen, um Ihren Nachrichteninhalt zu überprüfen. Mit Testsendungen können Sie den Ausschluss-Link, die Mirrorseite und andere Links testen, die Nachricht validieren, die Anzeige von Bildern überprüfen und mögliche Fehler erkennen. Außerdem können Sie das Design und die Darstellung auf verschiedenen Geräten testen.

Ein Testversand dient der Validierung einer Nachricht, bevor sie an die Haupt-Zielgruppe gesendet wird. Die Empfängerinnen und Empfänger des Testversands sind für die Validierung der Nachricht verantwortlich: Rendering, Inhalt, Personalisierungseinstellungen, Konfiguration.

Weiterführende Informationen zu Testversand-Empfangenden und zum Testversand finden Sie in [diesem Abschnitt](../send/preview-and-proof.md#send-proofs).


#### Anleitungsvideo {#seeds-and-proofs-video}

In diesem Video erfahren Sie, wie Sie einer vorhandenen E-Mail Testadressen und Testsendungen hinzufügen und diese ausführen.

>[!VIDEO](https://video.tv.adobe.com/v/3447008?quality=12&captions=ger)

Weitere Anleitungsvideos zu Campaign Classic finden Sie [hier](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=de).

## Vorbereiten und Validieren des Versands {#validate-the-delivery}

Der erstellte und konfigurierte Versand muss vor dem Senden an die Hauptzielgruppe validiert werden.

Gehen Sie dazu wie folgt vor:

1. **Versand analysieren** – hier erfolgt die Vorbereitung der zu sendenden Nachrichten. [Weitere Informationen](../send/delivery-analysis.md).

1. **Testsendungen durchführen** – hier erfolgt die Überprüfung von Inhalt, URLs, Personalisierung usw. [Weitere Informationen](../send/preview-and-proof.md).

>[!IMPORTANT]
>
>Die beiden oben genannten Schritte **müssen** nach jeder Änderung am Nachrichteninhalt ausgeführt werden.


## Konfigurieren und Durchführen des Versands {#configuring-and-sending-the-delivery}

Greifen Sie auf die Versandparameter zu, um weitere Einstellungen zu konfigurieren und festzulegen, wie Ihre Nachrichten gesendet werden. Sie können eine Versandpriorität definieren, das Senden von Schüben einrichten, die Einstellungen für erneute Versuche konfigurieren und die Ausführung Ihres Versands testen. Nachdem diese Konfiguration abgeschlossen ist, können Sie das Senden bestätigen.  Nachrichten werden dann entweder sofort oder basierend auf dem für den Versand festgelegten Zeitplan gesendet.

Auf [dieser Seite](../send/configure-and-send.md) erfahren Sie, wie Sie die Versandeinstellungen konfigurieren.

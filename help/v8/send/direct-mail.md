---
title: Senden von Briefpost mit Adobe Campaign
description: Erste Schritte mit Briefpost in Campaign
feature: Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 91%

---

# Erstellen von Briefpost-Sendungen

Ein Briefpost-Versand erzeugt eine Extraktionsdatei, die die Daten der Zielpopulation enthält. Sie können diese Datei dann für den Provider freigeben, der Nachrichten an die Zielpopulationen sendet.

Die Schritte zum Generieren der Datei sind:

1. [Versand erstellen](#creating-a-direct-mail-delivery)
1. [Definieren der Zielgruppe](#defining-the-direct-mail-audience)
1. [Dateiinhalt festlegen](#defining-the-direct-mail-content)
1. [Versand validieren](#validating)
1. [Versand starten](#start-delivery)

## Versand erstellen{#creating-a-direct-mail-delivery}

Erstellen Sie anhand der Vorlage einen Briefpost-Versand. Sie können die integrierte Vorlage **[!UICONTROL Briefpost-Versand (Papier)]** duplizieren und konfigurieren.

Gehen Sie wie folgt vor, um einen neuen Briefpost-Versand zu erstellen:

>[!NOTE]
>
>Allgemeine Methoden zur Versanderstellung finden Sie in [diesem Abschnitt](../start/create-message.md).

1. Erstellen Sie einen neuen Versand beispielsweise im Versand-Dashboard.
1. Wählen Sie die Versandvorlage **Briefpost-Versand (Papier)** aus.

   ![](assets/direct_mail.png)

1. Geben Sie für Ihren Versand einen Titel, einen Code und eine Beschreibung ein. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](../start/create-message.md#create-the-delivery).
1. Klicken Sie auf **Fortfahren**, um die Eingaben zu bestätigen und in das Fenster der Nachrichtenkonfiguration zu gelangen.

## Zielgruppe definieren{#defining-the-direct-mail-audience}

Die Empfängerprofile müssen mindestens ihren Namen und ihre Anschrift enthalten.

Postanschriften sind berechnete Felder. Standardmäßig kann eine Anschrift bis zu sechs Zeilen haben: Die erste enthält den Vor- und Nachnamen der Empfängerin bzw. des Empfängers, die folgenden Zeilen die für die Zustellung erforderlichen Informationen (z. B. Straße und Zusätze) und die letzte Zeile Postleitzahl und Ort. Die Definition des standardmäßig berechneten Felds „postAddress“ kann im nms::recipient-Schema überprüft werden.

Eine Anschrift gilt als vollständig angegeben, wenn die Felder Name, Postleitzahl und Ort nicht leer sind. Empfängerinnen und Empfänger mit unvollständigen Adressen werden von Direkt-Mail-Sendungen ausgeschlossen.

Weiterführende Informationen finden Sie in [diesem Abschnitt](../start/create-message.md#target-population).

## Dateiinhalt festlegen{#defining-the-direct-mail-content}

Definieren Sie mithilfe des Extraktionsassistenten die Informationen (Spalten), die in die Ausgabedatei exportiert werden sollen.

Im Feld **[!UICONTROL Datei]** ist der Name der die extrahierten Daten enthaltenden Datei anzugeben. Die Schaltfläche rechts ermöglicht die Verwendung von Personalisierungsfeldern, um den Namen zu erstellen.

Standardmäßig wird die Extraktionsdatei erstellt und auf dem Server gespeichert. Sie können es auf Ihrem Computer speichern. Um dies zu tun, aktivieren Sie die Option **[!UICONTROL Nach dem Export erzeugte Datei herunterladen]**. In diesem Fall sind der Pfad zum lokalen Speicherverzeichnis und der Dateiname anzugeben.

![](assets/s_ncs_user_mail_delivery_local_file.png)

Bei einem Briefpost-Versand wird der Extraktionsinhalt über den Link **[!UICONTROL Extraktionsdateiformat bearbeiten...]** konfiguriert.

![](assets/s_ncs_user_mail_delivery_format_link.png)

Über diesen Link gelangen Sie in den Extraktions-Assistenten, mit dessen Hilfe die zu exportierenden Daten (Spalten) festgelegt werden.

![](assets/s_ncs_user_mail_delivery_format_wz.png)

Sie können eine personalisierte URL in die Extraktionsdatei einfügen. Weitere Informationen hierzu finden Sie in der Adobe Campaign Classic-[&#x200B; (Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/publishing-a-web-form.html?lang=de){target="_blank"}.

>[!NOTE]
>
>Dieser Assistent enthält die Schritte des Exportassistenten, die in der Adobe Campaign Classic-Dokumentation [&#x200B; sind](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-export-jobs.html?lang=de){target="_blank"}.

## Versand überprüfen{#validating}

Überprüfen Sie das Ergebnis der Analyse und den Inhalt der Ausgabedatei.

Im Rahmen einer Marketing-Kampagne wird die Extraktionsdatei am Extraktionsdatum erstellt. Sie können den Inhalt der extrahierten Datei anzeigen, validieren oder das Format ändern und die Extraktion bei Bedarf neu starten. Nachdem die Datei validiert wurde, können Sie die Benachrichtigungs-E-Mail an den Router senden. Weitere Informationen finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=de){target="_blank"}.

In [diesem Abschnitt](../start/create-message.md#validate-the-delivery) werden globale Konzepte zur Validierung eines Versands vorgestellt.

Die Ausgabedatei eines Briefpost-Versands wird während der Versandanalyse generiert. Der Inhalt der Datei hängt von den ausgewählten Ausgabespalten ab (siehe diesen [Datei](#defining-the-direct-mail-content)).

>[!NOTE]
>
>Die Analysephase wird in diesem [&#x200B; beschrieben](delivery-analysis.md).

Bei der Erzeugung der Datei werden keine Empfängerinformationen (z. B. Versandlogs) aktualisiert. Der Vorgang kann daher problemlos unterbrochen werden.

Prüfen Sie jetzt das Ergebnis der Analyse und klicken Sie dann auf **[!UICONTROL Absendung bestätigen]**, um die Nachrichten an die gewählte Zielgruppe zu senden. Durch Bestätigung des Pop-ups wird der Versand gestartet.

Mit der Absendebestätigung wird die Extraktion der Daten in die angegebene Datei gestartet.

![](assets/s_ncs_user_postal_del_send_confirm_postal.png)

Nun können Sie den Assistenten schließen und die Versand-Logs auf der Registerkarte **[!UICONTROL Versand]** ansehen, auf die Sie über die Detailansicht des Versands zugreifen können.

Sie können den Abrufmodus der Versandlogs auf der Registerkarte **[!UICONTROL Analyse]** der Versandeigenschaften konfigurieren.

Dabei stehen zwei Modi zur Verfügung:

* **[!UICONTROL Nachrichten werden nach Validierung als gesendet betrachtet]** (Standardmodus): In diesem Funktionsmodus werden alle Versandlogs aktualisiert, sobald der Benutzer den Versand bestätigt (ihr Status wechselt von &#39;Versand ausstehend&#39; zu &#39;Gesendet&#39;). Der Versand wechselt dann automatisch in den Status **[!UICONTROL Abgeschlossen]**.
* **[!UICONTROL Ergebnisdatei listet gesendete und fehlgeschlagene Nachrichten]**: Dieser Modus ermöglicht eine Aktualisierung der Versandlogs mittels einer externen Datei vom Dienstleister. In diesem Fall ist die Erstellung eines Workflows zur Verarbeitung dieser Informationen notwendig, um den Status der Versandlogs zu aktualisieren.

  >[!NOTE]
  >
  >Nach der Aktualisierung der Versandlogs muss der Versandstatus vom Benutzer in **[!UICONTROL Abgeschlossen]** geändert werden.

## Versand starten{#start-delivery}

Nachdem Sie die Extraktionsdatei validiert haben, klicken Sie auf **Absendung bestätigen**. Über eine Bestätigungsnachricht können Sie den Versand starten.

Mit der Bestätigung wird die Extraktion der Daten in die angegebene Datei gestartet.

Im Rahmen einer Marketing-Kampagne werden die Extraktionsdateien nach Erteilung aller Validierungen über einen speziellen Workflow erstellt, der in einer Standardkonfiguration automatisch gestartet wird, wenn bei einem Briefpostversand die Extraktion ausstehend ist. Weiterführende Informationen finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=de){target="_blank"}.

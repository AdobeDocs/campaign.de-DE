---
product: campaign
title: Anhänge erstellen
description: Anhänge erstellen
feature: Email
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 27d13642-2971-466b-818d-39328c198b14
TQID: 'https://experienceleague.adobe.com/4GMBlA0-rTnn8kBciPmJLozcPU1qmwM9-5sTFhxkua4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 50d1fd2e-0fc9-5627-bbc9-02dbc9d15e08
    internal-label: Email
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '1397'
ht-degree: 79%
---
# Anhängen von Dateien an eine E-Mail{#attaching-files}

## Über E-Mail-Anhänge {#about-email-attachments}

Sie können an einen E-Mail-Versand eine oder mehrere Dateien anhängen.

>[!NOTE]
>
>Zur Vermeidung von Leistungsproblemen wird empfohlen, nicht mehr als einen Anhang pro E-Mail hinzuzufügen. Der empfohlene Schwellenwert kann über die Liste der Campaign-Optionen konfiguriert werden. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic](https://experienceleague.adobe.com/de/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options#delivery).

Sie haben zwei Möglichkeiten:

* Datei unverändert anhängen.
* Den Inhalt des Anhangs für jeden Empfänger personalisieren. In diesem Fall ist die Erstellung eines **berechneten Anhangs** erforderlich. Der Titel des Anhangs wird für jede Nachricht zum Zeitpunkt des Versands berechnet und kann somit Empfänger-spezifisch sein. Die personalisierten Anhänge vor dem Senden in eine PDF-Datei umwandeln, wenn Sie über die Lizenz für **Variable Digital Printing** verfügen.

>[!NOTE]
>
>Diese Konfiguration wird in der Regel in den Versandvorlagen vorgenommen. Weiterführende Informationen hierzu finden Sie auf dieser [Seite](../send/create-templates.md).

## Schutzmechanismen {#attachments-guardrails}

Um Performance-Probleme zu vermeiden, dürfen die in den E-Mails enthaltenen Bilder nicht größer als 100 KB sein. Diese standardmäßig festgelegte Beschränkung kann in der Option `NmsDelivery_MaxDownloadedImageSize` geändert werden. Adobe empfiehlt jedoch dringend, große Bilder in E-Mail-Sendungen zu vermeiden.

Adobe empfiehlt außerdem, die Größe und Anzahl der angehängten Dateien zu begrenzen. Standardmäßig kann nur eine Datei als Anhang zu einer E-Mail hinzugefügt werden. Dieser Schwellenwert kann in der Option `NmsDelivery_MaxRecommendedAttachments` konfiguriert werden.

Weitere Informationen finden Sie in der Liste der Campaign-Optionen in der [Dokumentation zu Campaign Classic](https://experienceleague.adobe.com/de/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options#delivery):

## Lokale Datei anhängen {#attaching-a-local-file}

Gehen Sie wie folgt vor, um eine lokale Datei an einen Versand anzuhängen.

>[!NOTE]
>
>Sie können auch mehrere Dateien an einen Versand anhängen. Anlagen können in jedem Format, einschließlich ZIP-Format, vorliegen.

1. Wählen Sie den Link **[!UICONTROL Anhänge]**.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**.
1. Klicken Sie auf **[!UICONTROL Datei...]**, um die Datei auszuwählen, die an den Versand angehängt werden soll.

   ![Der Dialog Angehängte Dateien bearbeiten mit dem Menü Hinzufügen und Datei öffnen… ausgewählt, um eine Datei an einen E-Mail-Versand anzuhängen](assets/s_ncs_user_wizard_email_attachement.png)

Sie können die Datei auch per Drag-and-Drop direkt in das Versandfeld **[!UICONTROL Anhänge]** ziehen oder das Symbol für **[!UICONTROL Datei anfügen]** in der Symbolleiste des Versandassistenten verwenden.

![Symbol Anhängen in der Symbolleiste des Versandassistenten, neben dem Abschnitt E-Mail-Parameter &#x200B;](assets/s_ncs_user_wizard_add_file_ico.png)

Sobald Sie die Datei ausgewählt haben, wird sie auf den Server geladen, um zum Zeitpunkt des Versandstarts zur Verfügung zu stehen. Sie wird im Feld **[!UICONTROL Anhänge]** aufgeführt.

![E-Mail-Parameter mit der hochgeladenen Datei im Feld „Anhänge“](assets/s_ncs_user_wizard_email_attachement_e.png)

## Berechneten Anhang erstellen {#creating-a-calculated-attachment}

Wenn Sie einen berechneten Anhang erstellen, kann der Name des Anhangs während der Analyse oder des Versands jeder Nachricht berechnet werden. Er hängt von der Empfängerin bzw. dem Empfänger ab. Es kann auch personalisiert und in PDF konvertiert werden.

![Der Dialog „Angehängte Dateien bearbeiten“ mit dem Menü „Hinzufügen“ geöffnet und Berechneter Anhang… ausgewählt](assets/s_ncs_user_wizard_attachment.png)

Gehen Sie wie folgt vor, um einen personalisierten Anhang zu erstellen:

1. Wählen Sie den Link **[!UICONTROL Anhänge]**.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie **[!UICONTROL Berechneter Anhang]**.
1. Wählen Sie in der Dropdown-Liste des **[!UICONTROL Typ]**-Felds eine der folgenden Berechnungsmodi aus:

![Dialogfeld Anlagendefinition mit der Dropdown-Liste Typ mit den vier berechneten Anlagenoptionen](assets/s_ncs_user_wizard_email01_136.png)

Folgende Optionen stehen zur Verfügung:

* **Dateiname wird bei der Erstellung der Versandvorlage angegeben**
* **Dateiinhalt wird zum Zeitpunkt der Absendung für jede Nachricht personalisiert und in PDF konvertiert**
* **Dateiname wird bei der Versandanalyse berechnet (unabhängig vom Empfänger)**
* **Dateiname wird bei der Absendung für jede Nachricht berechnet (kann vom Empfänger abhängen)**

### Lokale Datei anhängen {#attach-a-local-file}

Wenn der Anhang eine lokale Datei ist, wählen Sie die Option **[!UICONTROL Dateiname wird bei der Erstellung der Versandvorlage angegeben]**. Die Datei wird lokal ausgewählt und auf den Server geladen. Gehen Sie wie folgt vor:

1. Geben Sie im Feld **[!UICONTROL Lokale Datei]** den gewünschten Anhang an.
1. Vergeben Sie gegebenenfalls einen Titel. Der Titel ersetzt den Dateinamen, wenn er in Messaging-Systemen angezeigt wird. Wenn nichts angegeben ist, wird standardmäßig der Dateiname verwendet.

   ![Registerkarte „Allgemein“ der Anlagendefinition mit den Feldern „Typ“, „Bezeichnung“ und „Lokale Datei“ sowie der Option „Datei auf den Server hochladen“](assets/s_ncs_user_wizard_email_calc_attachement_02.png)

1. Wählen Sie, wenn nötig, die Option **[!UICONTROL Datei auf den Server laden]** und klicken Sie auf den Link **[!UICONTROL Auf dem Server aktualisieren...]**, um den Vorgang zu starten.

   ![Upload-Fortschrittsfenster, in dem die Protokollmeldungen und die Dateiübertragung auf den Server mit 100 % angezeigt werden](assets/s_ncs_user_wizard_email_calc_attachement_01.png)

Nun kann die Datei als Anhang der auf dieser Vorlage beruhenden Sendungen verwendet werden.

### Personalisierte Nachricht anhängen {#attach-a-personalized-message}

Mit der Option **[!UICONTROL Dateiinhalt wird zum Zeitpunkt der Absendung für jede Nachricht personalisiert und in PDF konvertiert]** können Sie eine Datei mit Personalisierungsfeldern (z. B. für den Vor- und Nachnamen des Empfängers) auswählen.

![Textverarbeitungsdokument, das die Personalisierungsfelder Vorname und Nachname des Empfängers für einen PDF-Anhang enthält](assets/s_ncs_user_wizard_email_calc_attachement_06.png)

Gehen Sie wie folgt vor, um diese Art von Anhang zu konfigurieren:

1. Wählen Sie die hochzuladende Datei aus.
1. Vergeben Sie gegebenenfalls einen Titel.
1. Wählen Sie die Option **[!UICONTROL Datei auf den Server laden]**, klicken Sie auf den Link **[!UICONTROL Auf dem Server aktualisieren]** und starten Sie den Upload in dem sich öffnenden Fenster.
1. Sie können eine Vorschau anzeigen. Wählen Sie dazu eine Empfängerin bzw. einen Empfänger aus.

   ![Dialogfeld für die Anlagendefinition, in dem die personalisierte PDF für eine aus der Liste „Vorschau“ ausgewählte Empfängerin oder einen ausgewählten Empfänger in der Vorschau angezeigt wird](assets/s_ncs_user_wizard_email_calc_attachement_07.png)

1. Analysieren und starten Sie den Versand.

   Jeder Empfänger enthält eine personalisierte PDF-Datei im E-Mail-Anhang.

   ![Erhaltene E-Mail mit einem personalisierten PDF-Anhang, der geöffnet wird, um den Empfängernamen in der Begrüßung anzuzeigen](assets/s_ncs_user_wizard_email_calc_attachement_08.png)



### Berechnete Datei anhängen {#attach-a-calculated-file}

Sie können den Namen des Anhangs während der Versandvorbereitung berechnen lassen. Wählen Sie dazu die Option **[!UICONTROL Dateiname wird bei der Versandanalyse berechnet (unabhängig vom Empfänger)]** aus.

>[!NOTE]
>
>Diese Option ist nur für Sendungen vorgesehen, die durch einen externen Vorgang oder einen Workflow abgeschickt werden.

1. Geben Sie den Titel an, der für den Anhang verwendet werden soll.
1. Geben Sie den Pfad und den genauen Namen der Datei im Eingabefenster an.

   >[!IMPORTANT]
   >
   >Die Datei muss sich auf dem Server befinden.

   ![Anlagendefinition mit einem Skript zur Berechnung von Dateipfad und -name, einschließlich des Datums, während der Versandanalyse](assets/s_ncs_user_wizard_email_calc_attachement_04.png)

1. Analysieren und starten Sie den Versand.

   Im Analyseprotokoll können Sie die Berechnung des Dateinamens nachvollziehen.

   ![Versandanalyseprotokoll mit hervorgehobener Zeile mit dem Ergebnis „Berechneter Dateiname des Anhangs“](assets/s_ncs_user_wizard_email_calc_attachement_05.png)

### Personalisierte Datei anhängen {#attach-a-personalized-file}

Bei der Auswahl eines Anhangs können Sie die Option **[!UICONTROL Der Dateiname wird während des Versands für jede Empfängerin bzw. jeden Empfänger berechnet (kann von der Empfängerin bzw. dem Empfänger abhängen)]** auswählen. Dann können Sie Personalisierungsdaten der Empfängerin bzw. des Empfängers dem Namen der zu versendenden Datei zuordnen.

>[!NOTE]
>
>Diese Option ist nur für Sendungen vorgesehen, die durch einen externen Vorgang oder einen Workflow abgeschickt werden.

1. Geben Sie den Titel an, der für den Anhang verwendet werden soll.
1. Geben Sie den Pfad und den genauen Namen der Datei im Eingabefenster an. Wenn der Dateiname personalisiert ist, können Sie die Personalisierungsfelder für die relevanten Werte verwenden.

   ![Anlagendefinition unter Verwendung des Nachnamens des Empfängers im Dateipfad, um für jeden Empfänger eine andere Datei auszuwählen](assets/s_ncs_user_wizard_email_calc_attachement_010.png)

   >[!IMPORTANT]
   >
   >Die Datei muss sich auf dem Server befinden.

1. Analysieren und starten Sie den Versand.

   In unten stehendem Beispiel wurde die angehängte Datei über den mithilfe der Zusammenführungsfelder konfigurierten Namen gewählt.

   ![Erhaltene E-Mail mit einer angehängten Datei, deren Name aus dem Nachnamen des Empfängers erstellt wurde](assets/s_ncs_user_wizard_email_calc_attachement_011.png)

### Einstellungen für den Anhang {#attachment-settings}

Für die ersten beiden Optionen können Sie **[!UICONTROL Datei auf den Server hochladen]** durch Auswahl der entsprechenden Option wählen. Über den Link **[!UICONTROL Datei auf dem Server aktualisieren]** können Sie mit dem Hochladen beginnen.

![Registerkarte „Allgemein“ der Anlagendefinition mit ausgewählter Option „Datei auf dem Server hochladen“ und dem Link „Auf dem Server aktualisieren“](assets/s_ncs_user_wizard_email01_137.png)

Eine Nachricht bestätigt, dass die Datei erfolgreich hochgeladen wurde:

![Anlagendefinition, die anzeigt, dass die Datei bereits auf dem Server existiert](assets/s_ncs_user_wizard_email01_1371.png)

Ein Warnhinweis erscheint, wenn die Datei geändert wurde:

![Anlagendefinition, die den Warnhinweis anzeigt, dass die lokale Datei nicht mit der Datei auf dem Server übereinstimmt](assets/s_ncs_user_wizard_email01_1372.png)

Im **[!UICONTROL Erweitert]**-Tab können Sie für Anhänge die folgenden Optionen konfigurieren:

* Auswahl der Empfänger, die den Anhang erhalten sollen. Kreuzen Sie die Option **[!UICONTROL Empfängerfilter bezüglich des Anhangs aktivieren]** an und geben Sie im Eingabefenster in Form eines JavaScripts das Auswahlkriterium an.
* Erstellung eines Scripts, um den Dateinamen zu personalisieren.

  Geben Sie Ihren Text im Fenster ein und verwenden Sie die in der Dropdown-Liste verfügbaren Personalisierungsfelder. Im folgenden Beispiel ist der Dateiname personalisiert und enthält das heutige Datum und den Namen der empfangenden Person.

  ![Registerkarte Erweitert mit einem Skript, das den Dateinamen des Anhangs und die E-Mail mit dem resultierenden Namen personalisiert](assets/s_ncs_user_wizard_email_calc_attachement_09.png)

---
product: campaign
title: Senden eines Berichts an eine Liste
description: Erfahren Sie, wie Sie mit einem Workflow einen Bericht an eine Liste senden.
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
TQID: 'https://experienceleague.adobe.com/d8vslZcVX8-e0GRGP4PVRB4opH11d-1B33nGO3uei3s'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 77%
---
# Senden eines Berichts an eine Liste{#send-a-report-to-a-list}

Im folgenden Anwendungsbeispiel soll jeden Monat der Standardbericht zu den **[!UICONTROL Trackingindikatioren]** erzeugt und als PDF an eine Empfängerliste gesendet werden.

![Monatlicher Berichts-Workflow mit Planung, JavaScript-Code und Versand sowie die E-Mail mit „indicators.pdf“-Anlage.](assets/use_case_report_intro.png)

Die Umsetzung des Anwendungsbeispiels gliedert sich in folgende Schritte:

* Erstellen Sie eine Empfängerliste für diesen Bericht. [Weitere Informationen](#step-1--create-the-recipient-list).
* Erstellen Sie eine Versandvorlage, die bei jeder Ausführung des Workflows einen neuen Versand erstellt. [Weitere Informationen](#step-2--create-the-delivery-template).
* Erstellen Sie einen Workflow, der den Bericht im PDF-Format erzeugt und an die Empfängerliste sendet. [Weitere Informationen](#step-3--create-the-workflow).

## &#x200B;1. Schritt: Erstellen der Empfängerliste {#step-1--create-the-recipient-list}

Gehen Sie wie folgt vor, um eine Liste der gewünschten Empfänger zu erstellen:

1. Navigieren Sie zur Registerkarte **[!UICONTROL Profile und Zielgruppen]** und klicken Sie auf den Link **[!UICONTROL Listen]**.
1. Wählen Sie die **[!UICONTROL Erstellen]**-Schaltfläche aus.
1. Wählen Sie **[!UICONTROL Neue Liste]** aus und erstellen Sie eine neue Empfängerliste, an die der Bericht gesendet werden soll.

Weitere Informationen zum Erstellen von Listen finden Sie unter [Erstellen von Profil-Audiences in Campaign](../../v8/audiences/create-audiences.md).

## &#x200B;2. Schritt: Erstellen der Versandvorlage {#step-2--create-the-delivery-template}

Gehen Sie wie folgt vor, um eine Versandvorlage zu erstellen:

1. Gehen Sie im Adobe Campaign-Explorer zum Knoten **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** und duplizieren Sie die integrierte Vorlage **[!UICONTROL E-Mail-Versand]**.

   Weiterführende Informationen zur Erstellung von Versandvorlagen finden Sie unter [Arbeiten mit Versandvorlagen](../../v8/send/create-templates.md).

1. Konfigurieren Sie die Vorlage, indem Sie Titel, Zielgruppe (d. h. die zuvor erstellte Empfängerliste), Betreff und Inhalt angeben.

   Bei jeder Ausführung des Workflows wird der Bericht **[!UICONTROL Tracking-Indikatoren]** aktualisiert, wie in [Schritt 3: Erstellen des Workflows](#step-3--creating-the-workflow) erklärt wird.

1. Um die neueste Version des Berichts in den Versand einzubeziehen, müssen Sie einen **[!UICONTROL berechneten Anhang]** hinzufügen:

   * Klicken Sie auf den Link **[!UICONTROL Anhänge]** und dann auf den Pfeil neben der Schaltfläche **[!UICONTROL Hinzufügen]**. Wählen Sie **[!UICONTROL Berechneter Anhang...]** aus

     ![Fenster „Angehängte Dateien bearbeiten“ mit dem Menü „Hinzufügen“ öffnen und ausgewähltem „Berechneter Anhang“.](assets/use_case_report_4.png)

   * Wählen Sie in der Dropdown-Liste **[!UICONTROL Typ]** die letzte Option aus: **[!UICONTROL Dateiname wird beim Versand jeder Nachricht berechnet (kann vom Empfängerprofil abhängen)]**.

     ![Anlagendefinition mit Dateityp, der beim Versand für jede Nachricht und jeden Bericht mit dem Titel „Bericht“ berechnet wird.](assets/use_case_report_5.png)

     Der im Feld **[!UICONTROL Titel]** angegebene Wert erscheint nicht im tatsächlichen Versand.

   * Geben Sie in der Textzone den Pfad und den Namen der Datei ein.

     ![Registerkarte „Allgemein“ der Anlagendefinition mit dem in die Textzone eingegebenen Dateipfad /tmp/indicators.pdf.](assets/use_case_report_6.png)

     >[!CAUTION]
     >
     >Pfad und Name müssen mit den Werten übereinstimmen, die in der **[!UICONTROL JavaScript-Code]**-Aktivität des Workflows eingegeben wurden (siehe [Schritt 3: Erstellen des Workflows](#step-3--creating-the-workflow)).

   * Wählen Sie die Registerkarte **[!UICONTROL Erweitert]** aus und markieren Sie **[!UICONTROL Script erstellen zur Berechnung des Dateinamens, der beim Empfänger angezeigt wird]**. Geben Sie in der Textzone den Namen des Anhangs im endgültigen Versand ein.

     ![Registerkarte „Erweitert“ für die Anlagendefinition mit dem Script-Namen der überprüften Datei und der eingegebenen Datei „latest-report.pdf“.](assets/use_case_report_6b.png)

## Schritt 3: Erstellen des Workflows {#step-3--creating-the-workflow}

Erstellen Sie für diesen Anwendungsfall den folgenden Workflow.

![Monatliche Berichtsindikatoren für Workflows: Planung, JavaScript-Code, dann Versand.](assets/use_case_report_8.png)

Es werden drei Aktivitäten verwendet:

* Eine **[!UICONTROL Planungsaktivität]**, die den Workflow einmal monatlich ausführt,
* Eine **[!UICONTROL JavaScript-Code]**-Aktivität, die den Bericht im PDF-Format generiert,
* Eine **[!UICONTROL Versandaktivität]**, die auf die zuvor erstellte Versandvorlage verweist.

Um den Workflow zu erstellen, gehen Sie wie folgt vor:

1. Navigieren Sie zum Knoten **[!UICONTROL Administration > Betreibung > Technische Workflows]** des Campaign-Explorers und erstellen Sie einen neuen Ordner, in dem Sie Ihre Workflows speichern können.
1. Erstellen Sie einen neuen Workflow.

   ![Dialogfeld „Neuer Workflow“ unter Administration > Produktion > Technische Workflows mit einem Beschriftungsfeld und der Schaltfläche „Speichern“.](assets/use_case_report_7.png)

1. Ziehen Sie eine **[!UICONTROL Planung]** in das Diagramm und konfigurieren Sie sie dahingehend, dass der Workflow an jedem ersten Montag eines Monats ausgeführt wird.

   ![Planungsaktivität, die um 12:00:00 Uhr morgens am ersten Montag jedes Monats ausgelöst wird.](assets/use_case_report_9.png)

   Weiterführende Informationen zur Konfiguration der Planung finden Sie im Abschnitt [Planung](scheduler.md).

1. Schließen Sie eine **[!UICONTROL JavaScript-Code]**-Aktivität an.

   ![JavaScript-Code-Aktivität mit dem Skript, das ReportName, Path, ExportFormat und den Aufruf „xtk.report.export“ definiert.](assets/use_case_report_10.png)

   Geben Sie folgenden Code ein:

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   mit den folgenden Variablen:

   * **var reportName**: der interne Name des Berichts in doppelten Anführungszeichen. Im vorliegenden Beispiel lautet der interne Name des **Trackingindikatoren**-Berichts &quot;deliveryFeedback&quot;.
   * **Var-Pfad**: Geben Sie den Speicherpfad der Datei („tmp“), den Namen, den Sie der Datei geben möchten („deliveryFeedback“), und die Dateierweiterung („.pdf“) ein. In diesem Fall haben wir den internen Namen als Dateinamen verwendet. Die Werte müssen zwischen doppelten Anführungszeichen stehen und durch ein „+“-Zeichen getrennt werden.

     >[!CAUTION]
     >
     >Die Datei muss auf dem Server gespeichert werden. Sie müssen den gleichen Pfad und den gleichen Namen wie in der Registerkarte **[!UICONTROL Allgemein]** des Fensters „Bearbeiten“ für den berechneten Anhang eingeben, wie [Schritt 2: Erstellen der Versandvorlage](#step-2--create-the-delivery-template)) beschrieben.

   * **var exportFormat**: Format des Anhangs (&quot;PDF&quot;).
   * **var _ctx** (Kontext): Im vorliegenden Beispiel wird der Bericht **[!UICONTROL Trackingindikatoren]** im allgemeinen Kontext verwendet.

1. Fügen Sie abschließend eine **[!UICONTROL Versandaktivität]** mit den folgenden Optionen hinzu:

   ![Versandaktivität: Neu aus Vorlage, Vorbereitung und Start, ausgehende Transition und Verarbeitungsfehler nicht aktiviert.](assets/use_case_report_11.png)

   * Im Bereich **[!UICONTROL Versand]**: Aktivieren Sie die Option **[!UICONTROL Neu, basierend auf einer Vorlage erstellt]** und wählen Sie die zuvor erstellte Vorlage aus.
   * In den Bereichen **[!UICONTROL Empfänger]** und **[!UICONTROL Inhalt]**: Aktivieren Sie **[!UICONTROL Werden bzw. Wird im Versand angegeben]**.
   * **[!UICONTROL Auszuführende Aktion]**: Wählen Sie **[!UICONTROL Vorbereiten und starten]** aus.
   * Deaktivieren Sie die Optionen **[!UICONTROL Ausgehende Transition erzeugen]** und **[!UICONTROL Fehler verarbeiten]**.

1. Speichern Sie Ihre Änderungen und starten Sie den Workflow. Die Nachricht wird an jeden ersten Montag des Monats zusammen mit dem angehängten Bericht an die Empfängerliste gesendet.

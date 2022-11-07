---
product: campaign
title: Senden eines Berichts an eine Liste
description: Erfahren Sie, wie Sie mit einem Workflow einen Bericht an eine Liste senden.
feature: Workflows
source-git-commit: 4c3caa8e31c2076d32a03a8778a28edce50cde63
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 34%

---


# Senden eines Berichts an eine Liste{#send-a-report-to-a-list}

Im folgenden Anwendungsbeispiel soll jeden Monat der Standardbericht zu den **[!UICONTROL Trackingindikatioren]** erzeugt und als PDF an eine Empfängerliste gesendet werden.

![](assets/use_case_report_intro.png)

Die Umsetzung des Anwendungsbeispiels gliedert sich in folgende Schritte:

* Erstellen Sie eine Empfängerliste für diesen Bericht. [Weitere Informationen](#step-1--create-the-recipient-list).
* Erstellen Sie eine Versandvorlage, die bei jeder Workflow-Ausführung einen neuen Versand erstellt. [Weitere Informationen](#step-2--create-the-delivery-template).
* Erstellen Sie einen Workflow, der den Bericht im PDF-Format erzeugt und an die Empfängerliste sendet. [Weitere Informationen](#step-3--create-the-workflow).

## Schritt 1: Empfängerliste erstellen {#step-1--create-the-recipient-list}

Gehen Sie wie folgt vor, um eine Empfängerliste zu erstellen:

1. Navigieren Sie zum **[!UICONTROL Profile und Zielgruppen]** klicken Sie auf die **[!UICONTROL Listen]** Link.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Erstellen]**.
1. Wählen Sie **[!UICONTROL Neue Liste]** aus und erstellen Sie eine neue Empfängerliste, an die der Bericht gesendet werden soll.

Weitere Informationen zum Erstellen von Listen finden Sie unter [diesem Abschnitt](../../v8/audiences/create-audiences.md).

## Schritt 2: Versandvorlage erstellen {#step-2--create-the-delivery-template}

Gehen Sie wie folgt vor, um die Versandvorlage zu erstellen:

1. Navigieren Sie zum **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** Knoten des Adobe Campaign-Explorer erstellen und die **[!UICONTROL E-Mail-Versand]** integrierte Vorlage.

   Weiterführende Informationen zur Erstellung von Versandvorlagen finden Sie im Abschnitt [diesem Abschnitt](../../v8/send/create-templates.md).

1. Geben Sie die Vorlagenparameter ein: Titel, Zielgruppe (die Liste der zuvor erstellten Empfänger), Betreff und Inhalt.

   Bei jeder Ausführung des Workflows wird die **[!UICONTROL Trackingindikatoren]** Der Bericht wird wie unter [Schritt 3: Workflow erstellen](#step-3--creating-the-workflow)).

1. Um die neueste Version des Berichts in den Versand einzubeziehen, müssen Sie einen **[!UICONTROL berechneten Anhang]** hinzufügen:

   * Klicken Sie auf **[!UICONTROL Anhänge]** und klicken Sie auf den Pfeil neben dem **[!UICONTROL Hinzufügen]** Schaltfläche. Auswählen **[!UICONTROL Berechneter Anhang...]**.

      ![](assets/use_case_report_4.png)

   * Im **[!UICONTROL Typ]** Dropdownliste die neueste Option auswählen: **[!UICONTROL Dateiname wird bei der Zustellung jeder Nachricht berechnet (kann dann vom Empfängerprofil abhängen)]**.

      ![](assets/use_case_report_5.png)

      Der im Feld **[!UICONTROL Titel]** angegebene Wert erscheint nicht im tatsächlichen Versand.

   * Geben Sie in der Textzone den Pfad und den Namen der Datei ein.

      ![](assets/use_case_report_6.png)

      >[!CAUTION]
      >
      >Pfad und Name müssen mit den im **[!UICONTROL JavaScript-Code]** Typaktivität des Workflows, wie hier beschrieben: [Schritt 3: Workflow erstellen](#step-3--creating-the-workflow).

   * Wählen Sie die **[!UICONTROL Erweitert]** Registerkarte und aktivieren **[!UICONTROL Script des Dateinamens, der in den gesendeten E-Mails angezeigt wird]**. Geben Sie in der Textzone den Namen des Anhangs im endgültigen Versand ein.

      ![](assets/use_case_report_6b.png)

## Schritt 3: Workflow erstellen {#step-3--creating-the-workflow}

Erstellen Sie für diesen Anwendungsfall den folgenden Workflow.

![](assets/use_case_report_8.png)

Es werden drei Aktivitäten verwendet:

* A **[!UICONTROL Planung]** -Aktivität, die den Workflow einmal monatlich ausführt,
* A **[!UICONTROL JavaScript-Code]** -Aktivität, die den Bericht im PDF-Format generiert,
* A **[!UICONTROL Versand]** -Aktivität, die auf die zuvor erstellte Versandvorlage verweist.

Gehen Sie wie folgt vor, um diesen Workflow zu erstellen:

1. Navigieren Sie zum **[!UICONTROL Administration > Betreibung > Technische Workflows]** Knoten von Campaign verwenden und erstellen Sie einen neuen Ordner, in dem Sie Ihre Workflows speichern können.
1. Erstellen Sie einen neuen Workflow.

   ![](assets/use_case_report_7.png)

1. Ziehen Sie eine **[!UICONTROL Planung]** in das Diagramm und konfigurieren Sie sie dahingehend, dass der Workflow an jedem ersten Montag eines Monats ausgeführt wird.

   ![](assets/use_case_report_9.png)

   Weiterführende Informationen zur Konfiguration der Planung finden Sie im Abschnitt [Planung](scheduler.md).

1. Schließen Sie eine **[!UICONTROL JavaScript-Code]**-Aktivität an.

   ![](assets/use_case_report_10.png)

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

   * **var reportName**: der interne Name des Berichts in Anführungsstrichen. Im vorliegenden Beispiel lautet der interne Name des **Trackingindikatoren**-Berichts &quot;deliveryFeedback&quot;.
   * **var path**: Geben Sie den Speicherpfad der Datei (&quot;tmp&quot;), den Namen, den Sie der Datei geben möchten (&quot;deliveryFeedback&quot;), und die Dateierweiterung (&quot;.pdf&quot;) ein. In diesem Fall haben wir den internen Namen als Dateinamen verwendet. Die Werte müssen zwischen doppelten Anführungszeichen und durch das Zeichen &quot;+&quot;getrennt sein.

      >[!CAUTION]
      >
      >Die Datei muss auf dem Server gespeichert werden. Sie müssen denselben Pfad und denselben Namen wie im **[!UICONTROL Allgemein]** Registerkarte des Bearbeitungsfensters für den berechneten Anhang, wie detailliert [here](#step-2--create-the-delivery-template)).

   * **var exportFormat**: Format des Anhangs (&quot;PDF&quot;).
   * **var _ctx** (Kontext): Im vorliegenden Beispiel wird der Bericht **[!UICONTROL Trackingindikatoren]** im allgemeinen Kontext verwendet.

1. Fertigstellen durch Hinzufügen einer **[!UICONTROL Versand]** -Aktivität mit den folgenden Optionen:

   ![](assets/use_case_report_11.png)

   * Im Bereich **[!UICONTROL Versand]**: Aktivieren Sie die Option **[!UICONTROL Neu, basierend auf einer Vorlage erstellt]** und wählen Sie die zuvor erstellte Vorlage aus.
   * In den Bereichen **[!UICONTROL Empfänger]** und **[!UICONTROL Inhalt]**: Aktivieren Sie **[!UICONTROL Werden bzw. Wird im Versand angegeben]**.
   * **[!UICONTROL Auszuführende Aktion]**: select **[!UICONTROL Vorbereiten und Starten]**.
   * Deaktivieren Sie die **[!UICONTROL Ausgehende Transition erzeugen]** und **[!UICONTROL Fehler verarbeiten]** Optionen.

1. Speichern Sie Ihre Änderungen und starten Sie den Workflow. Die Nachricht wird jeden ersten Monat im Monat zusammen mit dem beigefügten Bericht an die Empfängerliste gesendet.
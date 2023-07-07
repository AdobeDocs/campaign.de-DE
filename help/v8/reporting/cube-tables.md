---
product: campaign
title: Verwenden von Cubes zum Erstellen von Datenberichten
description: Erfahren Sie, wie Sie Cubes zum Erstellen von Berichten verwenden
feature: Reporting
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 100%

---

# Verwenden von Cubes zur Datenanalyse{#use-cubes-to-create-reports}

Verwenden Sie Cubes, um Berichte zu erstellen und um Daten aus der Datenbank zu identifizieren und auszuwählen. Sie haben folgende Möglichkeiten:

* Erstellung von Cube-basierten Berichten. [Weitere Informationen](#explore-the-data-in-a-report).
* Sammeln Sie die Daten in der Datenbank und gruppieren Sie sie in Listen, um beispielsweise Zielgruppen und Sendungen zu identifizieren und zu erstellen. [Weitere Informationen](#build-a-target-population).
* Fügen Sie eine Pivot-Tabelle in einen Bericht ein und verweisen Sie auf einen darin vorhandenen Cube. [Weitere Informationen](#insert-a-pivot-table-into-a-report).

## Erkunden der Daten in einem Bericht {#explore-the-data-in-a-report}

### Schritt 1: Erstellen eines Cube-basierten Berichts {#step-1---create-a-report-based-on-a-cube}

Nachdem der [Cube konfiguriert ist](cube-indicators.md), kann er als Vorlage für die Erstellung eines neuen Berichts verwendet werden.

Gehen Sie wie folgt vor, um einen auf einem vorhandenen Cube basierenden Bericht zu erstellen:

1. Klicken Sie im Tab **[!UICONTROL Berichte]** auf die Schaltfläche **[!UICONTROL Erstellen]** und wählen Sie den zuvor erstellten Cube aus.

   ![](assets/new-report-based-on-cube.png)

1. Klicken Sie zur Bestätigung auf die Schaltfläche **[!UICONTROL Erstellen]**: Der Bildschirm zur Konfiguration und Ansicht des Berichts wird geöffnet.

   Die ersten beiden verfügbaren Dimensionen werden standardmäßig in Spalten- und Zeilenform angezeigt, die Tabelle enthält jedoch keine Werte. Klicken Sie auf das zentrale Symbol, um sie zu erzeugen:

   ![](assets/cube-report-config.png)

1. Sie können die Dimensionen von einer Achse in die andere verschieben, sie löschen, neue Kennzahlen hinzufügen etc. Verwenden Sie hierzu die entsprechenden Symbole.

   ![](assets/cube-switch-axis.png)

   Diese Vorgänge werden nachfolgend beschrieben.

### Schritt 2: Auswahl der Zeilen und Spalten {#step-2---select-lines-and-columns}

Die Standardanzeige beinhaltet die ersten beiden Dimensionen des Cubes (in unserem Beispiel: Alter und Stadt).

Über die oberhalb der jeweiligen Achse gelegenen **[!UICONTROL Hinzufügen]**-Schaltflächen können weitere Dimensionen hinzugefügt werden.

![](assets/cube-switch.png)

1. Wählen Sie die Dimensionen aus, die in den Zeilen und Spalten der Tabelle angezeigt werden sollen. Verwenden Sie dazu Drag-and-Drop für die verfügbaren Dimensionen.
1. Wählen Sie die der Tabelle hinzuzufügende Dimension aus den verfügbaren Dimensionen aus:
   ![](assets/cube-select-dimension.png)

1. Legen Sie die Parameter dieser Dimension fest.

   ![](assets/cube-dimension-param.png)

   Diese Parameter hängen vom Datentyp der ausgewählten Dimension ab.

   Beispielsweise können für Daten mehrere Ebenen verfügbar sein. Weitere Informationen hierzu finden Sie unter [Anzeigen von Kennzahlen](customize-cubes.md#display-measures).

   In diesem Fall sind die folgenden Optionen verfügbar:

   ![](assets/cube-config.png)

   Sie können

   * die Daten beim Laden auszuklappen: Die Werte werden bei Aktivierung dieser Option bei jeder Aktualisierung des Berichts angezeigt (Standardwert: Nein);
   * das Ergebnis am Zeilenende anzuzeigen: Für in Spalten angezeigte Daten wird eine zusätzliche Option angeboten, um das Gesamtergebnis am Ende der Zeile anzuzeigen. In diesem Fall wird der Tabelle eine zusätzliche Spalte hinzugefügt (Standardwert: Ja);
   * die Daten zu sortieren: Die Spaltenwerte können nach Wert, Titel oder Kennzahl sortiert werden (Standardwert: Nach Wert);
   * die Werte absteigend (A-Z, 0-9) oder aufsteigend (Z-A, 9-0) anzuzeigen;
   * die Anzahl der beim Laden anzuzeigenden Spalten ändern (Standardwert: 200).

1. Klicken Sie zur Bestätigung auf **[!UICONTROL OK]**: Die Dimension wird den existierenden Dimensionen hinzugefügt.

   Das gelbe Banner oberhalb der Tabelle zeigt an, dass Sie Änderungen vorgenommen haben. Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, wenn diese berücksichtigt werden sollen.

   ![](assets/cube-in-report.png)

### Schritt 3: Konfiguration der anzuzeigenden Kennzahlen {#step-3---configure-the-measures-to-display}

Nachdem die Zeilen und Spalten definiert wurden, wählen Sie aus, welche Kennzahlen angezeigt werden sollen. Standardmäßig wird nur eine Kennzahl angezeigt.

Gehen Sie wie folgt vor, um Kennzahlen hinzuzufügen und zu konfigurieren:

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Kennzahlen]**.

   ![](assets/cube-measure-button.png)

1. Wählen Sie mit der Schaltfläche **[!UICONTROL Kennzahl verwenden]** eine der vorhandenen Kennzahlen aus.

   ![](assets/cube-add-measure.png)

   Wählen Sie die anzuzeigenden Informationen und die Formatierungsoptionen aus. Die Liste der Optionen hängt vom Typ der Kennzahl ab.

   ![](assets/cube-measure-options.png)

   Eine übergreifende Konfiguration der Kennzahlen ist über das Symbol **[!UICONTROL Konfiguration der Pivot-Tabelle bearbeiten]** möglich.

   ![](assets/cube-pivot-table-config.png)

   Sie können insbesondere bestimmen, ob die Titel der Kennzahlen angezeigt werden sollen. [Weitere Informationen](customize-cubes.md#configure-the-display).

1. Sie können neue Kennzahlen auf Basis bestehender erstellen. Klicken Sie dazu auf **[!UICONTROL Kennzahl erstellen]** und konfigurieren Sie diese.

   ![](assets/cube-create-new-measure.png)

   Folgende Kennzahltypen sind möglich:

   * Kombination von Kennzahlen: ermöglicht die Erstellung der neuen Kennzahl auf Basis von existierenden Kennzahlen.

     Für diese Kennzahlen stehen folgende Funktionen zur Verfügung: Summe, Differenz, Produkt und Rate.

   * Anteil: ermöglicht die Berechnung der Anzahl an für eine gegebene Dimension gemessenen Datensätzen. Der Anteil kann in Bezug auf eine Dimension oder eine Unter-Dimension berechnet werden.
   * Abweichung: ermöglicht die Berechnung der Abweichungen der Werte einer Ebene.
   * Abweichung vom Durchschnitt: ermöglicht die Berechnung der Abweichungen in jeder Gruppe von entsprechenden Zellen in Bezug auf den Wertedurschnitt. Sie können zum Beispiel die jeweilige Einkaufsmenge der existierenden Segmente vergleichen.

   Sobald die Kennzahl erstellt ist, wird sie dem Bericht hinzugefügt.

   ![](assets/cube-display-new-measure.png)

   Sobald Sie eine Kennzahl erstellt haben, können Sie sie bearbeiten und ihre Konfiguration ändern. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Kennzahlen]** und navigieren Sie zur Registerkarte der zu bearbeitenden Kennzahl.

   Klicken Sie anschließend auf die Schaltfläche **[!UICONTROL Dynamische Kennzahl bearbeiten]**, um auf die Einstellungen zuzugreifen.

## Erstellen einer Zielpopulation {#build-a-target-population}

Die basierend auf Cubes erstellten Berichte ermöglichen den Abruf von Daten aus der Datenbank und deren Speicherung in einer Liste.

Gehen Sie wie folgt vor, um eine Population in einer Liste zu gruppieren:

1. Markieren Sie durch Klick die Zellen, die die abzurufenden Populationen enthalten, und klicken Sie auf das Symbol **[!UICONTROL Zum Warenkorb hinzufügen]**.

   ![](assets/cube-add-to-cart.png)

   Wiederholen Sie diesen Vorgang so oft wie nötig, um die unterschiedlichen Profile zu sammeln.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Warenkorb anzeigen]**, um den Inhalt einzusehen, bevor er exportiert wird.

   ![](assets/cube-show-cart.png)

1. Verwenden Sie die Schaltfläche **[!UICONTROL Exportieren]**, um die Artikel im Warenkorb in einer Liste zu gruppieren.

   Geben Sie den Namen der Liste an und wählen Sie den gewünschten Exporttyp aus.

   ![](assets/cube-export-report.png)

   Klicken Sie auf **[!UICONTROL Starten]**, um mit dem Export zu beginnen.

1. Nach Abschluss des Exports bestätigt eine Nachricht seine korrekte Ausführung und die Anzahl der verarbeiteten Datensätze.

   ![](assets/cube-export-confirm.png)

   Sie können den Inhalt des Warenkorbs beibehalten oder löschen.

   Die neue Liste ist über die Registerkarte **[!UICONTROL Profile und Ziele]** verfügbar.

   ![](assets/cube-list-available.png)

## Einfügen von Pivot-Tabellen in Berichte {#insert-a-pivot-table-into-a-report}

Um eine Tabelle zu erstellen und die Daten in einem Cube zu erkunden, gehen Sie wie folgt vor:

1. Erstellen Sie einen neuen Bericht mit einer einzigen Seite und fügen Sie eine Pivot-Tabelle ein.

   ![](assets/cube-insert-in-report.png)

1. Im Tab **[!UICONTROL Daten]** haben Sie die Möglichkeit, einen existierenden Cube auszuwählen. Auf diese Weise werden automatisch die Dimensionen und Kennzahlen angezeigt, die zuvor konfiguriert wurden.

   ![](assets/cube-selected-in-report.png)

   Auf diese Weise können Sie den anzuzeigenden Bericht erstellen. Weitere Informationen finden Sie unter [Schritt 2: Auswahl der Zeilen und Spalten](#step-2---select-lines-and-columns).

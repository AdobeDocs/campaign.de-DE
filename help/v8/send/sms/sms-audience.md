---
title: Zielgruppenauswahl für SMS
description: Erfahren Sie, wie Sie die Zielgruppe für einen SMS-Versand einrichten.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: e0603a4d-cde1-4199-a164-bf0c992ba937
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: ht
source-wordcount: '532'
ht-degree: 100%

---

# Auswählen der Zielgruppe für den SMS-Versand {#sms-audience}

Bevor Sie Ihre Zielgruppe auswählen, können Sie [hier](../../audiences/gs-audiences.md) mehr über Zielgruppen erfahren.

Meistens wird die Hauptzielgruppe eines Versands aus der Adobe Campaign-Datenbank extrahiert (Standardmodus). Die Zielgruppe kann aber auch in einer externen Datei gespeichert sein. [Weitere Informationen finden Sie in diesem Abschnitt](#external-audience).

## Zielgruppe in Adobe Campaign

Gehen Sie wie folgt vor, um die Zielgruppe für Ihren Versand auszuwählen:

1. Klicken Sie im Versandeditor auf den Link **[!UICONTROL An]**. Daraufhin wird das Fenster **[!UICONTROL Auswahl der Zielgruppe]** geöffnet:

1. Da die Zielgruppe in der Adobe Campaign-Datenbank gespeichert ist, wählen Sie auf der Registerkarte **[!UICONTROL Hauptzielgruppe]** die Option **[!UICONTROL Von der Datenbank ausgehend definiert]** aus.

   ![](assets/audience_to.png){zoomable="yes"}

1. Wählen Sie in der Dropdown-Liste die Option **[!UICONTROL Zielgruppen-Mapping]** aus. Die Adobe Campaign-Standardeinstellung für Zielgruppen-Mapping ist „Empfänger“, basierend auf dem Schema **[!UICONTROL nms:recipient]**.

   Es sind weitere Zielgruppen-Zuordnungen verfügbar, von denen sich einige auf Ihre spezifische Konfiguration beziehen können. Weitere Informationen zu Zielgruppen-Mappings finden Sie unter [Arbeiten mit Zielgruppen-Mappings](../../audiences/target-mappings.md).

1. Wählen Sie zur Konfiguration von Einschränkungsfiltern die Schaltfläche **[!UICONTROL Hinzufügen]** aus.

   Sie haben die Wahl zwischen verschiedenen Filtertypen:

   ![](assets/audience_filters.png){zoomable="yes"}

   Wählen Sie den gewünschten Zieltyp aus und klicken Sie auf die Schaltfläche **[!UICONTROL Weiter]**.

   Folgende Zieltypen werden standardmäßig vorgeschlagen:

   * **[!UICONTROL Filterbedingungen]**: Ermöglicht die Definition einer Abfrage und Anzeige des Ergebnisses.
   * **[!UICONTROL Empfängerliste]**: Ermöglicht die Auswahl einer Liste, die Sie vorbereitet haben und die Ihre Zielgruppe enthält.
   * **[!UICONTROL Empfänger]**: Ermöglicht die direkte Auswahl einer Empfängerin oder eines Empfängers in der Tabelle.
   * **[!UICONTROL Empfänger aus einem Ordner]**: Ermöglicht die Auswahl eines Ordners im Explorer-Navigationsbaum.
   * **[!UICONTROL Versandempfänger]**: Ermöglicht die Auswahl der Zielgruppe eines früheren Versands.
   * **[!UICONTROL Empfänger von Sendungen eines bestimmten Ordners]**: Ermöglicht die Auswahl der Zielgruppe aller Sendungen in einem bestimmten Ordner.
   * **[!UICONTROL Abonnenten eines Informationsdienstes]**: Angabe des Newsletters, den die Empfängerinnen und Empfänger abonniert haben müssen, um in die Zielgruppe des Versands aufgenommen zu werden.
   * **[!UICONTROL Benutzerdefinierte Filter]**: Ermöglicht die Nutzung vordefinierter Filter.

   Mit der Option **[!UICONTROL Empfänger von diesem Segment ausschließen]** können Sie Empfängerinnen und Empfänger als Zielgruppe auswählen, die nicht den definierten Zielkriterien entsprechen. Um diese Option zu verwenden, aktivieren Sie das entsprechende Kontrollkästchen und wenden Sie dann die Zielgruppenbestimmung an (wie zuvor definiert), um die resultierenden Profile auszuschließen.

1. Geben Sie den Namen Ihrer Zielgruppe in das Feld „Titel“ ein und klicken Sie auf die Schaltfläche **[!UICONTROL Beenden]**, um Ihre Zielgruppe zu validieren.

   ![](assets/audience_finish.png){zoomable="yes"}

   Sie können die erforderlichen Zielpopulationen durch erneutes Klicken auf die Schaltfläche **[!UICONTROL Hinzufügen]** hinzufügen. Sie können auch welche löschen, indem Sie auf das X nach dem Titel klicken.

## Zielgruppe in einer externen Datei {#external-audience}

Sie können Adobe Campaign verwenden, um einen Versand an eine Zielgruppe durchzuführen, die nicht in der Datenbank, sondern in einer externen Datei vorhanden ist.

Gehen Sie dazu wie folgt vor:

1. Klicken Sie im Versandeditor auf den Link **[!UICONTROL An]**. Daraufhin wird das Fenster **[!UICONTROL Auswahl der Zielgruppe]** geöffnet:

1. Wählen Sie die Option **[!UICONTROL In einer externen Datei definiert]** aus.

   ![](assets/audience_externalfile.png){zoomable="yes"}

1. Standardmäßig werden Empfängerinnen und Empfänger in die Datenbank importiert. In diesem Fall müssen Sie die Option **[!UICONTROL Zielgruppen-Mapping]** auswählen. Weitere Informationen zu Zielgruppen-Mappings finden Sie unter [Arbeiten mit Zielgruppen-Mappings](../../audiences/target-mappings.md).

   Andernfalls können Sie auch **[!UICONTROL Empfänger nicht in die Datenbank importieren]** auswählen.

1. Wählen Sie beim Import der Datei den Link **[!UICONTROL Dateiformat definieren]** aus, um die externe Datei auszuwählen und zu konfigurieren.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Beenden]**, um die Zielgruppe zu validieren.

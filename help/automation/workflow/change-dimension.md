---
product: campaign
title: Dimensionsänderung in einem Workflow
description: Erfahren Sie, wie Sie die Aktivität Dimensionsänderung verwenden
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 75%

---

# Dimensionsänderung{#change-dimension}

Verwenden Sie die **[!UICONTROL Dimensionsänderung]** Aktivität , um die Zielgruppendimension beim Erstellen einer Audience zu ändern. Diese Aktivität verschiebt die Achse je nach Datenvorlage und Eingabedimension. Sie wechseln beispielsweise von der Dimension &quot;Verträge&quot;zur Dimension &quot;Kunden&quot;.

Sie können diese Aktivität auch verwenden, um die zusätzlichen Spalten der neuen Zielgruppe zu definieren und Kriterien zur Datendeduplizierung zu definieren.

So konfigurieren Sie die **[!UICONTROL Dimensionsänderung]** -Aktivität verwenden, gehen Sie wie folgt vor:

1. Wählen Sie im Feld **[!UICONTROL Dimensionsänderung]** die neue Zielgruppendimension aus.

   ![](assets/s_user_change_dimension_param1.png)

1. Sie können entscheiden, ob alle oder nur bestimmte Elemente in der ausgehenden Transition übermittelt werden sollen. Im vorliegenden Beispiel wird die Anzahl der möglichen Dubletten auf 2 begrenzt.

   ![](assets/s_user_change_dimension_limit.png)

   Wenn Sie nur einen Datensatz beibehalten wollen, erscheint im Arbeitsschema eine Kollektion, welche alle Datensätze, die nicht im Endergebnis enthalten sind, enthält. Anhand dieser Kollektion können Sie, wie bei anderen Kollektionen auch, Aggregate berechnen oder Informationen abrufen.

   Wenn Sie beispielsweise von der Dimension **[!UICONTROL Kunden]** zur Dimension **[!UICONTROL Empfänger]** wechseln, können Sie die Kunden eines bestimmten Geschäfts unter Angabe der getätigten Käufe abrufen.

1. Wenn Sie nicht alle Datensätze beibehalten, können Sie die Deduplizierungsparameter bestimmen.

   ![](assets/s_user_change_dimension_param2.png)

   Mithilfe der blauen Pfeile lässt sich die Reihenfolge der Dublettenverarbeitung bestimmen.

   Im vorliegenden Beispiel erfolgt die Deduplizierung zunächst über die E-Mail-Adresse und bei Bedarf anschließend über die Kundennummer.

1. Im **[!UICONTROL Ergebnis]**-Tab kann die Hinzufügung von Zusatzinformationen konfiguriert werden.

   Sie können beispielsweise den Bezirk anhand der Postleitzahl wiederherstellen, indem Sie eine **Substring**-Funktion verwenden. Gehen Sie dazu wie folgt vor:

   * Klicken Sie auf den Link **[!UICONTROL Daten hinzufügen...]** und kreuzen Sie die Option **[!UICONTROL Daten in Relation mit der Filterdimension]** an.

      ![](assets/wf_change-dimension_sample_01.png)

      >[!NOTE]
      >
      >Informationen zur Erstellung und Verwaltung von Zusatzspalten finden Sie unter [Daten hinzufügen](query.md#add-data).

   * Wählen Sie die ursprüngliche Zielgruppendimension aus (vor der Dimensionsänderung), markieren Sie die **[!UICONTROL Kundennummer]** und klicken Sie auf **[!UICONTROL Ausdruck bearbeiten]****[!UICONTROL .]**

      ![](assets/wf_change-dimension_sample_02.png)

   * Klicken Sie auf die Schaltfläche **[!UICONTROL Erweiterte Auswahl]** und kreuzen Sie die Option **[!UICONTROL Formel von einem Ausdruck ausgehend erstellen]** an.

      ![](assets/wf_change-dimension_sample_03.png)

   * Verwenden Sie die Funktionsliste, um die Formel zu erstellen.

      ![](assets/wf_change-dimension_sample_04.png)

   * Geben Sie abschließend einen Titel für die neu erstellte Spalte an.

      ![](assets/wf_change-dimension_sample_05.png)

1. Starten Sie den Workflow, um das Ergebnis zu prüfen. Die folgenden Abbildungen zeigen die Tabellen vor und nach der Dimensionsänderung sowie die Struktur der Workflow-Tabellen:

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)

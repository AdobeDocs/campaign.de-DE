---
product: campaign
title: Dimensionsänderung in einem Workflow
description: Erfahren Sie, wie Sie die Aktivität der Dimensionsänderung verwenden
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 100%

---

# Ändern der Dimension{#change-dimension}

Verwenden Sie die Aktivität **[!UICONTROL Dimensionsänderung]**, um die Zielgruppendimension beim Erstellen einer Audience zu ändern. Diese Aktivität verschiebt die Achse je nach Datenvorlage und der eingegebenen Dimension. Sie wechseln beispielsweise von der Dimension &quot;Verträge&quot; zur Dimension &quot;Kunden&quot;.

Sie können diese Aktivität auch verwenden, um die zusätzlichen Spalten der neuen Zielgruppe und Kriterien zur Datendeduplizierung zu definieren.

>[!IMPORTANT]
>
>Beachten Sie, dass die Aktivitäten **[!UICONTROL Dimension ändern]** und **[!UICONTROL Datenquelle ändern]** nicht in einer Zeile hinzugefügt werden sollten. Wenn Sie beide Aktivitäten nacheinander verwenden müssen, muss die Aktivität **[!UICONTROL Anreicherung]** zwischen ihnen enthalten sein. Dadurch wird eine ordnungsgemäße Ausführung sichergestellt und potenzielle Konflikte oder Fehler werden vermieden.

Um die Aktivität **[!UICONTROL Dimensionsänderung]** zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Wählen Sie im Feld **[!UICONTROL Dimensionsänderung]** die neue Zielgruppendimension aus.

   ![](assets/s_user_change_dimension_param1.png)

1. Sie können entscheiden, ob alle oder nur bestimmte Elemente in der ausgehenden Transition übermittelt werden sollen. Im vorliegenden Beispiel wird die Anzahl der möglichen Dubletten auf 2 begrenzt.

   ![](assets/s_user_change_dimension_limit.png)

   Wenn Sie nur einen Datensatz beibehalten wollen, erscheint im Arbeitsschema eine Sammlung, welche alle Datensätze, die nicht im Endergebnis enthalten sind, enthält. Anhand dieser Sammlung können Sie, wie bei anderen Sammlungen auch, Aggregate berechnen oder Informationen abrufen.

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
     >Weitere Informationen zur Erstellung und Verwendung von Zusatzspalten finden Sie unter [Daten hinzufügen](query.md#add-data).

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

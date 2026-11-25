---
product: campaign
title: Dimensionsänderung in einem Workflow
description: Erfahren Sie, wie Sie die Aktivität der Dimensionsänderung verwenden
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
TQID: 'https://experienceleague.adobe.com/BkGTNKy7N35h3jO5-Ao2x2-nClcv96wqT2AqIsAXlSA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 72%
---
# Dimensionsänderung{#change-dimension}

Verwenden Sie die Aktivität **[!UICONTROL Dimensionsänderung]**, um die Zielgruppendimension beim Erstellen einer Audience zu ändern. Diese Aktivität verschiebt die Achse je nach Datenvorlage und der eingegebenen Dimension. Sie wechseln beispielsweise von der Dimension &quot;Verträge&quot; zur Dimension &quot;Kunden&quot;.

Sie können diese Aktivität auch verwenden, um die zusätzlichen Spalten der neuen Zielgruppe und Kriterien zur Datendeduplizierung zu definieren.

>[!IMPORTANT]
>
>Beachten Sie, dass die Aktivitäten **[!UICONTROL Dimension ändern]** und **[!UICONTROL Datenquelle ändern]** nicht in einer Zeile hinzugefügt werden sollten. Wenn Sie beide Aktivitäten nacheinander verwenden müssen, muss die Aktivität **[!UICONTROL Anreicherung]** zwischen ihnen enthalten sein. Dadurch wird eine ordnungsgemäße Ausführung sichergestellt und potenzielle Konflikte oder Fehler werden vermieden.

Um die Aktivität **[!UICONTROL Dimensionsänderung]** zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Wählen Sie im Feld **[!UICONTROL Dimensionsänderung]** die neue Zielgruppendimension aus.

   ![Dimensionsfeld der Aktivität ändern, wobei der Feldselektor geöffnet und Abonnements als neue Dimension ausgewählt sind](assets/s_user_change_dimension_param1.png)

1. Bei der Dimensionsänderung können Sie alle Elemente beibehalten oder die in der Ausgabe beizubehalten Elemente auswählen. Im folgenden Beispiel ist der Wert für „Max. Anzahl der Duplikate“ auf 2 gesetzt.

   ![Option Anzahl der Elemente im neuen Dokument in der Zielgruppenbestimmung begrenzen, wobei das Feld Limit auf 2 gesetzt ist](assets/s_user_change_dimension_limit.png)

   Wenn Sie nur einen Eintrag beibehalten möchten, wird im Arbeitsschema eine Sammlung angezeigt, die alle Einträge enthält, die nicht im Endergebnis enthalten sind (da nur Eintrag beibehalten wird). Wie alle anderen Sammlungen können Sie mit dieser Sammlung Aggregate berechnen oder Informationen in Spalten abrufen.

   Wenn Sie beispielsweise von der Dimension **[!UICONTROL Kunden]** zur Dimension **[!UICONTROL Empfänger]** wechseln, können Sie die Kunden eines bestimmten Geschäfts unter Angabe der getätigten Käufe abrufen.

1. Wenn Sie nicht alle Datensätze beibehalten, können Sie die Deduplizierungsparameter bestimmen.

   ![Deduplizierungsdialogfeld, in dem die Felder E-Mail und Kontonummer mit den Pfeilen aufgelistet sind, die ihre Priorität festlegen](assets/s_user_change_dimension_param2.png)

   Mithilfe der blauen Pfeile lässt sich die Reihenfolge der Duplikatverarbeitung bestimmen.

   Im vorliegenden Beispiel erfolgt die Deduplizierung zunächst über die E-Mail-Adresse und bei Bedarf anschließend über die Kundennummer.

1. Im **[!UICONTROL Ergebnis]**-Tab kann die Hinzufügung von Zusatzinformationen konfiguriert werden.

   Sie können beispielsweise den Bezirk anhand der Postleitzahl wiederherstellen, indem Sie eine **Substring**-Funktion verwenden. Gehen Sie dazu wie folgt vor:

   * Klicken Sie auf den Link **[!UICONTROL Daten hinzufügen...]** und kreuzen Sie die Option **[!UICONTROL Daten in Relation mit der Filterdimension]** an.

     ![Registerkarte Ergebnis Datenlink hinzufügen, die den Assistenten Zusätzliche Daten mit Daten öffnet, die mit der ausgewählten Filterdimension verknüpft sind](assets/wf_change-dimension_sample_01.png)

     >[!NOTE]
     >
     >Weitere Informationen zur Erstellung und Verwendung von Zusatzspalten finden Sie unter [Daten hinzufügen](query.md#adding-data).

   * Wählen Sie die ursprüngliche Zielgruppendimension aus (vor der Dimensionsänderung), markieren Sie die **[!UICONTROL Kundennummer]** und klicken Sie auf **[!UICONTROL Ausdruck bearbeiten]**&#x200B;**[!UICONTROL .]**

     ![Assistent für zusätzliche Daten mit Postleitzahl aus der Unterstruktur „Standort“, die als Ausgabespalte und Bearbeitungsausdruck hinzugefügt wurde](assets/wf_change-dimension_sample_02.png)

   * Klicken Sie auf die Schaltfläche **[!UICONTROL Erweiterte Auswahl]** und kreuzen Sie die Option **[!UICONTROL Formel von einem Ausdruck ausgehend erstellen]** an.

     ![Schaltfläche „Erweiterte Auswahl“ öffnet den Formeltyp mit der ausgewählten Option „Formel mit einem Ausdruck bearbeiten“](assets/wf_change-dimension_sample_03.png)

   * Verwenden Sie die Funktionsliste, um die Formel zu erstellen.

     ![Ausdruckseditor mit der Formel Teilzeichenfolge der Postleitzahl aus dem Zeichen 1 mit der Länge 2 und der Liste der Funktionen](assets/wf_change-dimension_sample_04.png)

   * Geben Sie abschließend einen Titel für die neu erstellte Spalte an.

     ![Ausgabespalten mit der Bezeichnung County und dem Ausdruck Substring(zip/postcode, 1, 2)](assets/wf_change-dimension_sample_05.png)

1. Führen Sie den Workflow aus, um das Ergebnis dieser Konfiguration anzuzeigen. Die folgenden Abbildungen zeigen die Tabellen vor und nach der Dimensionsänderung sowie die Struktur der Workflow-Tabellen:

   ![Zeigt die Zieloption auf der Dimension Transition vor Änderung mit ihren Daten und ihrem Schema in der Population anzeigen an](assets/wf_change-dimension_sample_06.png)

   ![Zeigt die Zieloption nach der Dimensionsänderung an, wobei die Daten mit der Spalte „Land“ und dem neuen Schema angezeigt werden](assets/wf_change-dimension_sample_07.png)

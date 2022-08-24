---
product: campaign
title: Erstellen von Filtern
description: Erfahren Sie, wie Sie bei Abfragen einen Filter erstellen können
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Erstellen von Filtern {#creating-a-filter}



Filter werden in Adobe Campaign über Filterbedingungen definiert, die ähnlich wie Abfragen erstellt werden.

>[!NOTE]
>
>Näheres zu Filtern und deren Erstellung erfahren Sie hier:

Der Knoten **[!UICONTROL Administration > Konfiguration > Vordefinierte Filter]** enthält alle in Listen und Übersichten verwendeten Filter.

Beispielsweise kann die Benutzerliste nach **[!UICONTROL Aktiven Konten]** gefiltert werden:

![](assets/query_editor_filter_sample_1.png)

Der entsprechende Filter enthält die Abfrage bezüglich des Werts **[!UICONTROL Gesperrtes Konto]** des **[!UICONTROL Benutzer]**-Schemas:

![](assets/query_editor_filter_sample_2.png)

Dieselbe Liste kann mit dem Filter **[!UICONTROL Nach Login oder Titel]** nach dem im Eingabefeld erfassten Wert durchsucht werden:

![](assets/query_editor_filter_sample_3.png)

Dieser Filter wird wie folgt konfiguriert:

![](assets/query_editor_filter_sample_4.png)

Um dem Filter zu entsprechen, muss das Benutzerkonto eine der folgenden Bedingungen erfüllen:

* Der Titel enthält die im Eingabefeld erfassten Zeichen;
* der Benutzername enthält die im Eingabefeld erfassten Zeichen;
* die Beschreibung enthält die im Eingabefeld erfassten Zeichen.

>[!NOTE]
>
>Bei Verwendung der Funktion **[!UICONTROL Upper]** werden bei einer Abfrage Groß- und Kleinschreibung nicht beachtet.

Die Spalte **[!UICONTROL Berücksichtigt wenn]** ermöglicht die Konfiguration von Voraussetzungen dafür, dass die Filterbedingungen zum Tragen kommen. Die Zeichen **$(/tmp/@text)** entsprechen dem Inhalt des dem Filter zugeordneten Eingabefelds:

![](assets/query_editor_filter_sample_5.png)

Hier ist **$(/tmp/@text)=&#39;Filiale&#39;**.

Der Ausdruck **$(/tmp/@text)!=&#39;&#39;** prüft jede Bedingung, wenn das Eingabefeld nicht leer ist.

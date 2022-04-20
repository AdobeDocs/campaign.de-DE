---
title: Ordner und Ansichten
description: Erfahren Sie, wie Sie Ordner und Ansichten im Campaign Explorer verwalten.
feature: Audiences, Profiles, Application Settings
role: Data Engineer
level: Beginner
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
source-git-commit: 67d08660431f02d2a18f39b3270cc7c7b62ed40e
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 5%

---

# Verwalten von Ordner und Ansichten {#folders-and-views}

Kampagnenordner sind Knoten im Explorer-Baum. Je nach Typ enthalten sie bestimmte Datentypen.

Eine Ansicht ist ein bestimmter Ordner, der keine Daten enthält, aber Daten anzeigt, die physisch in anderen Ordnern desselben Typs gespeichert sind. Wenn Sie beispielsweise einen Versandordner in eine Ansicht umwandeln, werden in diesem Ordner alle Sendungen angezeigt. Diese Daten können dann gefiltert werden.


>[!NOTE]
>Um Ansichten von Standardordnern zu unterscheiden, wird ihr Name in hellblau anstelle von schwarz angezeigt.

Beachten Sie, dass Sie Ordner Berechtigungen zuweisen können, um den Zugriff auf bestimmte Daten zu beschränken. [Weitere Informationen](#restrict-access-to-a-folder)

## Best Practices beim Arbeiten mit Ordnern

* **Verwenden integrierter Ordner** um es allen am Projekt beteiligten Personen zu erleichtern, die Anwendung zu verwenden, zu warten und Fehler zu beheben. Erstellen Sie keine benutzerdefinierten Ordnerstrukturen für Empfänger, Listen, Sendungen usw., sondern verwenden Sie die Standardordner wie **Administration**, **Profile und Zielgruppen**, **Kampagnenverwaltung**.

* **Erstellen von Unterordnern** speichern Sie beispielsweise Ihre technischen Workflows im integrierten Ordner: **[!UICONTROL Administration > Betreibung > Technische Workflows]** und erstellen Sie Unterordner pro Workflow-Typ.

* **Benennungskonvention definieren und anwenden** Sie können beispielsweise die Workflows in alphabetischer Reihenfolge benennen, sodass sie in der Ausführungsreihenfolge sortiert werden, z. B.:

   A1 - Empfänger importieren, beginnt um 10:00 Uhr; A2 - Tickets importieren, beginnt um 11:00 Uhr.

## Ordner erstellen{#create-a-folder}

Klicken Sie zum Erstellen eines Ordners mit der rechten Maustaste auf einen vorhandenen Ordner und verwenden Sie das Kontextmenü.

Um denselben Ordnertyp wie den von Ihnen ausgewählten zu erstellen, wählen Sie die erste Option im Kontextmenü aus. Wählen Sie beispielsweise im Ordner Empfänger die Option **[!UICONTROL Neuen Ordner &quot;Empfänger&quot;erstellen]**.

![](assets/create-recipient-folder.png)

Sie können den neuen Ordner per Drag-and-Drop verschieben, um den Campaign-Explorer-Navigationsbaum nach Bedarf zu organisieren.

Um einen anderen Ordnertyp zu erstellen, klicken Sie mit der rechten Maustaste auf einen vorhandenen Ordner und wählen Sie **[!UICONTROL Neuen Ordner hinzufügen]**. Je nach den zu speichernden Daten können Sie alle Ordnertypen erstellen.

![](assets/add-new-folder.png)

>[!CAUTION]
>Diese Änderungen gelten für alle Campaign-Benutzer.

## Ordner in eine Ansicht umwandeln{#turn-a-folder-to-a-view}

Eine Ansicht ist ein bestimmter Ordner, der keine Daten enthält, aber Daten anzeigt, die physisch in anderen Ordnern desselben Typs gespeichert sind.

Sie können jeden Ordner in eine Ansicht umwandeln, der Ordner muss jedoch leer sein. Alle im Ordner gespeicherten Daten werden gelöscht, wenn Sie den Ordner in eine Ansicht umwandeln.

>[!CAUTION]
>
>Eine Ansicht zeigt Daten an und bietet Zugriff darauf, selbst wenn die Daten nicht physisch im Ansichtsordner gespeichert sind. Um Zugriff auf den Inhalt zu erhalten, muss der Benutzer über die entsprechenden Berechtigungen in den Quellordnern verfügen, zumindest über Lesezugriff.
>
>Um Zugriff auf eine Ansicht zu gewähren, ohne Zugriff auf ihren Quellordner zu gewähren, gewähren Sie keinen Lesezugriff auf den übergeordneten Knoten des Quellordners.

Im folgenden Beispiel erstellen wir einen neuen Ordner, in dem nur US-Sendungen basierend auf ihrem internen Namen angezeigt werden.

1. Erstellen Sie eine **[!UICONTROL Sendungen]** Ordner und benennen Sie ihn **US-Sendungen**.
1. Klicken Sie mit der rechten Maustaste auf diesen Ordner und wählen Sie **[!UICONTROL Eigenschaften...]** aus.
1. Wählen Sie im Tab **[!UICONTROL Einschränkung]** die Option **[!UICONTROL Dieser Ordner ist eine Ansicht]**: Nun werden alle Sendungen der Datenbank in diesem Ordner angezeigt.

   ![](assets/this-folder-is-a-view.png)

1. Definieren Sie im mittleren Bereich des Fensters die Filterkriterien des Abfrageeditors: Nur die dem Filter entsprechenden Sendungen werden im Ordner angezeigt.

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >Erfahren Sie, wie Sie Abfragen erstellen in [diese Seite](create-filters.md#advanced-filters)


>[!CAUTION]
>
>Bei der Verwaltung [Transaktionsnachrichten](../send/transactional.md) -Ereignisse, die **[!UICONTROL Echtzeit-Ereignisse]** oder **[!UICONTROL Batch-Ereignisse]** -Ordner dürfen nicht als Ansichten auf den Ausführungsinstanzen festgelegt werden, da dies zu Berechtigungsproblemen führen kann.

## Organisieren von Ordnern{#organize-your-folders}

Standardmäßig wird oben in der Hierarchie ein neuer Ordner hinzugefügt.

Durchsuchen Sie die **Unterordner** -Registerkarte von Ordnereigenschaften, um die Unterordner zu organisieren.

Sie können die Ordner mit den Pfeilen rechts verschieben oder die **[!UICONTROL Sortieren Sie die Unterordner in alphabetischer Reihenfolge]** -Option, um sie automatisch zu sortieren.

![](assets/sort-folders.png)


## Daten in einem Ordner filtern{#filter-data-in-a-folder}

Um in einem Ordner gespeicherte Daten zu filtern, greifen Sie auf die Ordnereigenschaften zu und wählen Sie die Registerkarte Einschränkung aus.

Der folgende Ordner enthält beispielsweise nur Kontakte mit einer E-Mail-Adresse, deren Ursprung nicht als &quot;extern&quot;gekennzeichnet ist oder leer ist.

![](assets/add-a-filter-to-a-folder.png)


## Ordnerzugriff beschränken{#restrict-access-to-a-folder}

Verwenden Sie Berechtigungen für Ordner, um den Zugriff auf Campaign-Daten zu organisieren und zu steuern.

Gehen Sie wie folgt vor, um Berechtigungen für einen bestimmten Campaign-Ordner zu bearbeiten:

1. Klicken Sie mit der rechten Maustaste auf den entsprechenden Ordner und wählen Sie **[!UICONTROL Eigenschaften...]**.
1. Navigieren Sie zum **[!UICONTROL Sicherheit]** um die Berechtigungen für diesen Ordner anzuzeigen.

   ![](assets/folder-permissions.png)

* nach **eine Gruppe oder einen Benutzer autorisieren**, klicken Sie auf die **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe oder den Benutzer aus, der Berechtigungen für diesen Ordner zuweisen soll.
* nach **Verbieten einer Gruppe oder eines Operators** klicken **[!UICONTROL Löschen]** und wählen Sie die Gruppe oder den Benutzer aus, um die Autorisierung für diesen Ordner zu entfernen.
* nach **die einer Gruppe oder einem Benutzer zugewiesenen Berechtigungen auswählen**, wählen Sie die Gruppe oder den Benutzer aus, wählen Sie die Zugriffsberechtigungen aus, die Sie gewähren möchten, und heben Sie die Auswahl der anderen auf.

### Berechtigungen ausdehnen {#propagate-permissions}

Um Berechtigungen und Zugriffsberechtigungen zu erweitern, wählen Sie die **[!UICONTROL Propagat]** in den Ordnereigenschaften.

Die in diesem Fenster definierten Berechtigungen werden dann auf alle Unterordner des aktuellen Knotens angewendet. Sie können diese Berechtigungen immer für jeden Unterordner überschreiben.

>[!NOTE]
>
>Deaktivieren Sie die **[!UICONTROL Propagat]** -Option für einen Ordner deaktiviert ihn nicht für die Unterordner: müssen Sie sie für jeden Unterordner explizit löschen.

### Allen Benutzern Zugriff gewähren {#grant-access-to-all-operators}

Im **[!UICONTROL Sicherheit]** auswählen, wählen Sie die **[!UICONTROL Systemordner]** , um allen Benutzern ungeachtet ihrer Berechtigungen Zugriff zu gewähren.

Wenn diese Option deaktiviert ist, müssen Sie den Benutzer (oder seine Gruppe) explizit wieder in die Liste der Berechtigungen aufnehmen, damit er Zugriff erhält.

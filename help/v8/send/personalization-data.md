---
title: Personalisierungsdatenquellen
description: Erfahren Sie, welche Quellen für die Personalisierung verwendet werden können
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 39%

---


# Personalisierungsdatenquellen{#personalization-data}

Personalisierungsdaten können aus verschiedenen Quellen abgerufen werden: Datenquelle der Campaign-Datenbank, Datenquelle der externen Datei oder Datenquelle der externen Datenbank.

## Datenquelle der Campaign-Datenbank

Im häufigsten werden Personalisierungsdaten in der Datenbank gespeichert. Beispielsweise sind &quot;Personalisierungsfelder der Empfänger&quot;alle in der Empfängertabelle definierten Felder, Standardfelder (typischerweise: Nachname, Vorname, Adresse, Stadt, Geburtsdatum usw.) oder benutzerdefinierten Feldern.

![Personalisierungsfelder einer Kampagne in einer E-Mail](assets/perso-campaign-datasource.png)


## Datenquelle der externen Datei

Sie können eine externe Datei verwenden, die alle in Spalten definierten Felder enthält. Diese Datei wird bei der Definition eines Nachrichtenversands als Eingabe verwendet. Sie können diese Profile auch in die Datenbank einfügen.

Um die als Datenquelle zu verwendende Datei auszuwählen, klicken Sie im Fenster zur Nachrichtenerstellung auf den Link An und wählen Sie die Option **In einer externen Datei definiert** -Option. Nach dem Laden der Datei können Sie in den Personalisierungsoptionen über die Option **Felder aus der Datei** eingeben.

![Personalisierungsdaten aus einer Datei](assets/perso-from-file.png)


## FDA-Datenquelle

Personalisierungsdaten können von einer externen Tabelle bis hin zu [Federated Data Access](../connect/fda.md).  Wenn Sie Ihre Sendungen mithilfe von Daten aus der externen Datenbank personalisieren möchten, erfassen Sie die Daten, die in einem Workflow verwendet werden sollen, um sie in einer temporären Tabelle verfügbar zu machen.

Fügen Sie dazu eine **Abfrage** -Aktivität im Zielgruppen-Workflow und verwenden Sie die **Daten hinzufügen...** zur Auswahl der externen Datenbank. Der detaillierte Prozess ist verfügbar unter [diesem Abschnitt](../../automation/workflow/query.md#adding-data).

Verwenden Sie dann die Daten aus der temporären Tabelle, um Ihren Versand zu personalisieren. Sobald die Abfrageaktivität konfiguriert ist, greifen Sie in den Personalisierungsoptionen auf die externen Daten über die **Target-Erweiterung** eingeben.

![Personalisierungsdaten aus einer externen Datenbank](assets/perso-external-db.png)

Bei der Verwendung externer Daten, auf die über die FDA zugegriffen wird, wird empfohlen, die Nachrichtenpersonalisierung in einem dedizierten Workflow mit dem **Personalisierungsdaten mit einem Workflow vorbereiten** wie unten beschrieben.

### Optimieren der Personalisierung {#optimize-personalization}

Mit der folgenden Option können Sie die Personalisierung optimieren: Verwenden Sie dazu im **[!UICONTROL Analyse]**-Tab der Versandeigenschaften die Option **[!UICONTROL Personalisierungsdaten mit einem Workflow vorbereiten]**.

Diese Option ermöglicht es, im Zuge der Versandanalyse automatisch einen Workflow zu erstellen und auszuführen, welcher alle auf eine Zielgruppe bezogenen Daten in einer temporären Tabelle speichert (insbesondere Daten aus über FDA verknüpften Tabellen).

Wenn Sie die Option aktivieren, kann sich die Leistung der Versandanalyse bei der Verarbeitung großer Datenmengen erheblich verbessern, insbesondere wenn die Personalisierungsdaten aus einer externen Tabelle via FDA stammen. [Weitere Informationen](../connect/fda.md).

Um diese Option zu verwenden, gehen Sie wie folgt vor:

1. Erstellen Sie eine Kampagne.
1. Im **[!UICONTROL Zielbestimmungen und Workflows]** im Tab Ihrer Kampagne eine **Abfrage** -Aktivität zu Ihrem Workflow hinzu.
1. Hinzufügen einer **[!UICONTROL E-Mail-Versand]** -Aktivität in den Workflow ein und öffnen Sie ihn.
1. Gehen Sie zum Tab **[!UICONTROL Analyse]** der **[!UICONTROL Versandeigenschaften]** und wählen Sie die Option **[!UICONTROL Personalisierungsdaten mit einem Workflow vorbereiten]** aus.
1. Konfigurieren Sie den Versand und starten Sie den Workflow, um mit der Analyse zu beginnen.

Nach Abschluss der Analyse werden die Personalisierungsdaten mithilfe eines technischen Workflows, der während der Analyse eingerichtet wird, in einer temporären Tabelle gespeichert.

Dieser Workflow ist nicht in der Adobe-Campaign-Benutzeroberfläche sichtbar. Er ist lediglich ein technisches Hilfsmittel, um Personalisierungsdaten rasch zu speichern und zu handhaben.

Gehen Sie nach dem Abschluss der Analyse zu den Workflow-**[!UICONTROL Eigenschaften]** und wählen Sie den Tab **[!UICONTROL Variablen]** aus. Dort wird der Name der temporären Tabelle angezeigt. Mit diesem Namen können Sie einen SQL-Aufruf durchführen, um die darin enthaltenen IDs anzuzeigen.

## Personalisierungsdaten in einem Workflow

Wenn ein Versand im Kontext eines Workflows erstellt wird, können Sie die Daten aus der temporären Workflow-Tabelle verwenden. Die in der temporären Arbeitstabelle des Workflows gespeicherten Daten stehen für Personalisierungsaufgaben zur Verfügung. Daten können in Personalisierungsfeldern verwendet werden.

Diese Daten werden in der **[!UICONTROL Target-Erweiterung]** Menü. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](../../automation/workflow/use-workflow-data.md#target-data).





---
title: Importieren von Profilen in Campaign
description: Erfahren Sie mehr über das Importieren von Kontakten in Campaign.
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 90%

---

# Importieren von Profilen aus einer Datei{#create-profiles}

Um Ihre Campaign-Datenbank zu füllen, können Sie [Profile manuell hinzufügen](create-profiles.md) oder wie unten beschrieben importieren Sie können auch importierte Dateien verwenden, um Kontaktdaten zu aktualisieren.

## Importieren von Profilen mit einem Workflow {#import-profiles-with-a-wf}

Workflows sind eine nützliche Methode, um Importverfahren zu automatisieren. Sie helfen Ihnen bei der Standardisierung Ihrer Datenverwaltungsaufgaben, egal ob Sie Daten von einer lokalen Datei oder von einem SFTP-Server importieren.

### Daten aus einer Liste verwenden: Liste lesen {#data-from-read-list}

Bereiten Sie Ihre Daten in einer Datei vor und strukturieren Sie sie, um sie mithilfe eines Workflows zu importieren. [Weitere Informationen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html).

### Daten aus einer Datei laden {#data-from-a-file}

Die im Workflow verarbeiteten Daten können aus einer strukturierten Datei stammen, die in Adobe Campaign importiert wird. [Weitere Informationen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html).

Nachdem die Daten erfasst wurden, können Sie sie in Ihren Workflows verwenden, um beispielsweise einen Versand anzureichern oder die Datenbank zu aktualisieren. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html).

## Einmalige Importe{#import-jobs}

Adobe Campaign bietet eine allgemeine Importfunktion, mit der Sie beispielsweise eine Liste von Kunden oder potenziellen Kunden extrahieren können, die dann Teil einer Zielpopulation werden, oder Sie können Ihre Datenbank mit Daten aus externen Dateien versorgen.

Allgemeine Importe werden über das Menü **[!UICONTROL Profile und Zielgruppen > Vorgänge]** auf der Adobe Campaign-Startseite verwaltet.

![](assets/new-import-job.png)

Die Schritte zur Durchführung eines allgemeinen Imports werden in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=de#getting-started){target=&quot;_blank&quot;} detailliert beschrieben.

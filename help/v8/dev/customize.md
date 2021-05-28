---
solution: Campaign v8
product: Adobe Campaign
title: Instanz anpassen
description: Erfahren Sie, wie Sie Ihre Instanz anpassen können.
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 83%

---

# Instanz anpassen{#gs-ac-custom}

Erfahren Sie, wie Sie **Ihre Campaign-Instanz anpassen**

>[!CAUTION]
>
>Eine Anpassung von Adobe Campaign sollte nur von erfahrenen Benutzer vorgenommen werden.

## Neue Datenfelder und Schemata erstellen

Adobe Campaign nutzt Datenschemata für folgende Aufgaben:

* Definieren der Verknüpfung zwischen den Datenobjekten im Programm mit den zugrunde liegenden Datenbanktabellen
* Definieren von Beziehungen zwischen den unterschiedlichen Datenobjekten in Campaign
* Definieren und Beschreiben der einzelnen Felder eines jeden Objekts

Um ein Feld etwa einer vorhandenen Tabelle namens &quot;Empfänger&quot; (nms:recipient) hinzuzufügen, müssen Sie dieses Schema erweitern.

Es stehen zwei Modi zur Tabellenerweiterung zur Verfügung:

* Über die Oberfläche mithilfe des Assistenten **Neues Feld**

   [!DNL :arrow_upper_right:] Erfahren Sie, wie Sie in der Dokumentation zu  [Campaign Classic v7 schnell ein neues Feld hinzufügen können.](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=de#configuring-campaign-classic)

* Programmgesteuert durch Erweiterung des Schemas

   [!DNL :bulb:] Näheres dazu, wie Sie ein vorhandenes Schema erweitern, finden Sie in [diesem Abschnitt](../dev/extend-schema.md).


Sie können auch neue Tabellen in der Campaign-Datenbank erstellen und das integrierte Datenmodell erweitern.

Um einen komplett neuen Datentyp hinzuzufügen, der in Adobe Campaign nicht standardmäßig zur Verfügung gestellt wird (z. B. eine Vertragstabelle), können Sie direkt ein benutzerdefiniertes Schema erstellen. Weiterführende Informationen hierzu finden Sie in [diesem Beispiel](../dev/create-schema.md#example--creating-a-contract-table).

**Verwandte Themen**

[!DNL :arrow_upper_right:] Beispiel für die Schemabearbeitung in der Dokumentation zu  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#configuring-campaign-classic)

[!DNL :arrow_upper_right:] Anwendungsbeispiel: ein Feld mit einer vorhandenen Referenztabelle in der  [Campaign Classic v7-Dokumentation verknüpfen](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#uc-link)


## Eingabefelder ändern

Campaign-Eingabeformulare sind an Ihre Implementierung anpassbar. Sie können Formularfelder hinzufügen oder entfernen, indem Sie den XML-Inhalt ändern.

[!DNL :bulb:] Näheres dazu, wie Sie ein vorhandenes Eingabedatum ändern oder ein neues Formular erstellen, finden Sie in [diesem Abschnitt](../dev/forms.md).

## Anpassen von Dashboards{#gs-custom-dashboards}

In der Benutzeroberfläche von Adobe Campaign werden zahlreiche Web-Anwendungen bereitgestellt, die es Ihnen ermöglichen, auf Empfänger, Sendungen, Kampagnen, gespeicherte Assets usw. zuzugreifen, sie zu verwalten und mit ihnen zu interagieren. In der Benutzeroberfläche erscheinen sie in Form von Dashboards, die aus einer einzigen Seite bestehen.

Die nativen Web-Anwendungen sind im Knoten &quot;Administration&quot; > &quot;Konfiguration&quot; > &quot;Web-Anwendungen&quot; gespeichert.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie in der Dokumentation zu  [Campaign Classic v7 eine Übersichtsseite in Campaign erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=de#creating-a-single-page-web-application)


## Listen anpassen und Filter erstellen {#gs-lists-and-filters}

### Daten aus Dashboards abrufen

Die in Campaign verfügbaren Listen beinhalten vordefinierter Filter, um die Navigation und Datenvisualisierung zu erleichtern.

[!DNL :arrow_upper_right:] Weitere Informationen zu Filteroptionen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=de#about-filtering)


### Datenzugriff über den Explorer

Beim Navigieren in der Explorer-Struktur von Adobe Campaign werden die in der Datenbank enthaltenen Daten in Listen angezeigt. Sie können diese Listen filtern, Suchvorgänge durchführen und Informationen hinzufügen sowie Daten filtern und sortieren.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Listen konfigurieren und eine Listenkonfiguration in der  [Campaign Classic v7-Dokumentation speichern.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=de#getting-started)


Sie können Filter auf diese Listen anwenden, um nur die vom Operator benötigten Daten anzuzeigen. Dann können Aktionen für die gefilterten Daten ausgeführt werden. Mit der Filterkonfiguration können Sie Daten aus einer Liste dynamisch auswählen. Beim Ändern der Daten werden die gefilterten Daten aktualisiert.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Daten in der Dokumentation zu  [Campaign Classic v7 filtern.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=de#typology-of-available-filters)

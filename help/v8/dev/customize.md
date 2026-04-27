---
title: Anpassen der Instanz
description: Erfahren Sie, wie Sie Ihre Instanz anpassen können.
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 79%

---

# Anpassen der Instanz {#gs-ac-custom}

Erfahren Sie, wie Sie **Ihre Campaign-Instanz anpassen**.

>[!CAUTION]
>
>Eine Anpassung von Adobe Campaign sollte nur von erfahrenen Benutzer vorgenommen werden.

## Neue Datenfelder und Schemata erstellen

Adobe Campaign nutzt Datenschemata für folgende Aufgaben:

* Definieren der Verknüpfung zwischen den Datenobjekten im Programm mit den zugrunde liegenden Datenbanktabellen
* Definieren von Beziehungen zwischen den unterschiedlichen Datenobjekten in Campaign
* Definieren und Beschreiben der einzelnen Felder eines jeden Objekts

Um beispielsweise ein Feld zu einer vorhandenen Tabelle hinzuzufügen, z. B. der Empfängertabelle (nms:recipient), müssen Sie dieses Schema erweitern.

Es stehen zwei Modi zur Tabellenerweiterung zur Verfügung:

* Über die Oberfläche mithilfe des Assistenten **Neues Feld**

  Wie Sie ein neues Feld schnell in Campaign hinzufügen, erfahren Sie in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=de#configuring-campaign-classic){target="_blank"}

* Programmgesteuert durch Erweiterung des Schemas. Näheres dazu, wie Sie ein vorhandenes Schema erweitern, finden Sie in [diesem Abschnitt](../dev/extend-schema.md).

Sie können auch neue Tabellen in der Campaign-Datenbank erstellen und das integrierte Datenmodell erweitern.

Um einen komplett neuen Datentyp hinzuzufügen, der in Adobe Campaign nicht standardmäßig zur Verfügung gestellt wird (z. B. eine Vertragstabelle), können Sie direkt ein benutzerdefiniertes Schema erstellen. Weiterführende Informationen hierzu finden Sie in [diesem Beispiel](../dev/create-schema.md#example--creating-a-contract-table).

**Verwandte Themen**

Beispiel zur Schemabearbeitung in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#configuring-campaign-classic){target="_blank"}

Anwendungsfall: Verknüpfen eines Felds mit einer vorhandenen Referenztabelle in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#uc-link){target="_blank"}


## Eingabefelder ändern

Campaign-Eingabeformulare sind an Ihre Implementierung anpassbar. Sie können Formularfelder hinzufügen oder entfernen, indem Sie den XML-Inhalt ändern.

Näheres dazu, wie Sie ein vorhandenes Eingabeformular ändern oder ein neues Formular erstellen, finden Sie in [diesem Abschnitt](../dev/forms.md).

## Anpassen von Dashboards{#gs-custom-dashboards}

Die Benutzeroberfläche von Adobe Campaign nutzt viele Web-Anwendungen für den Zugriff auf, die Verwaltung und die Interaktion mit Empfängern, Sendungen, Kampagnen, Lagern usw. Sie werden in der Benutzeroberfläche in Form von Dashboards mit nur einer Seite angezeigt.

Die integrierten Web-Anwendungen werden im Ordner **Administration > Konfiguration > Web-Anwendungen** des Explorers gespeichert.

Wie Sie eine Übersichtsseite in Campaign erstellen, erfahren Sie in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=de#creating-a-single-page-web-application){target="_blank"}


## Anpassen von Listen und Erstellen von Filtern {#gs-lists-and-filters}

Die in Campaign verfügbaren Listen beinhalten vordefinierte Filter, um die Navigation und Datenvisualisierung zu erleichtern.

Beim Navigieren in der Explorer-Struktur von Adobe Campaign werden die in der Datenbank enthaltenen Daten in Listen angezeigt. Sie können diese Listen filtern, Suchvorgänge durchführen und Informationen hinzufügen sowie Daten filtern und sortieren.

Weitere Informationen, wie Sie Listen konfigurieren und Listenkonfigurationen speichern können, finden Sie auf [dieser Seite](../start/campaign-ui.md).

Sie können Filter auf diese Listen anwenden, um nur die vom Operator benötigten Daten anzuzeigen. Dann können Aktionen für die gefilterten Daten ausgeführt werden. Mit der Filterkonfiguration können Sie Daten aus einer Liste dynamisch auswählen. Beim Ändern der Daten werden die gefilterten Daten aktualisiert.

Weitere Informationen zu Filteroptionen finden Sie auf [dieser Seite](../audiences/create-filters.md).

---
solution: Campaign v8
product: Adobe Campaign
title: Instanz anpassen
description: Erfahren Sie, wie Sie Ihre Instanz anpassen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 11%

---

# Anpassen der Instanz{#gs-ac-custom}

Erfahren Sie, wie Sie **Ihre Campaign-Instanz anpassen**

>[!CAUTION]
>
>Die Anpassung von Adobe Campaign ist erfahrenen Benutzern vorbehalten.

## Neue Datenfelder und Schemata erstellen

Adobe Campaign nutzt Datenschemata, um:

* Definieren der Verknüpfung von Datenobjekten innerhalb der Anwendung mit zugrunde liegenden Datenbanktabellen
* Relationen zwischen den verschiedenen Datenobjekten in der Campaign-Anwendung definieren
* Definieren und Beschreiben der einzelnen Felder in den einzelnen Objekten

Um beispielsweise ein Feld zu einer vorhandenen Tabelle hinzuzufügen, z. B. die Empfängertabelle (nms:recipient), müssen Sie dieses Schema erweitern.

Es stehen zwei Tabellenerweiterungsmodi zur Verfügung:

* Über die Benutzeroberfläche mithilfe des Assistenten **Neues Feld**

   [!DNL :arrow_upper_right:] Erfahren Sie, wie Sie in der Dokumentation zu  [Campaign Classic v7 schnell ein neues Feld hinzufügen können.](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programmatische Erweiterung des Schemas

   [!DNL :bulb:] In  [diesem Abschnitt](../dev/extend-schema.md) erfahren Sie, wie Sie ein vorhandenes Schema erweitern.


Sie können auch neue Tabellen in der Campaign-Datenbank erstellen und das integrierte Datenmodell erweitern.

Um einen völlig neuen Datentyp hinzuzufügen, der in Adobe Campaign nicht nativ vorhanden ist (z. B. eine Vertragstabelle), können Sie direkt ein benutzerdefiniertes Schema erstellen. Weitere Informationen hierzu finden Sie in [diesem Beispiel](../dev/create-schema.md#example--creating-a-contract-table).

**Verwandte Themen**

[!DNL :arrow_upper_right:] Beispiel für die Schemabearbeitung in der Dokumentation zu  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

[!DNL :arrow_upper_right:] Anwendungsbeispiel: ein Feld mit einer vorhandenen Referenztabelle in der  [Campaign Classic v7-Dokumentation verknüpfen](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Ändern der Eingabeformulare

Campaign-Formulare können an Ihre Implementierung angepasst werden. Sie können Formularfelder hinzufügen oder entfernen, indem Sie den XML-Inhalt ändern.

[!DNL :bulb:] In  [diesem Abschnitt](../dev/forms.md) erfahren Sie, wie Sie ein vorhandenes Formular ändern oder ein neues erstellen.

## Anpassen von Dashboards{#gs-custom-dashboards}

In der Benutzeroberfläche von Adobe Campaign werden zahlreiche Webanwendungen bereitgestellt, die es Ihnen ermöglichen, auf Empfänger, Sendungen, Kampagnen, gespeicherte Assets etc. zuzugreifen, sie zu verwalten und mit ihnen zu interagieren. In der Benutzeroberfläche erscheinen sie in Form von Dashboards, die aus einer einzigen Seite bestehen.

Die nativen Webanwendungen sind im Knoten Administration > Konfiguration > Webanwendungen gespeichert.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie in der Dokumentation zu  [Campaign Classic v7 eine Übersichtsseite in Campaign erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Listen anpassen und Filter erstellen {#gs-lists-and-filters}

### Zugriff auf Daten aus Dashboards

Campaign-Listen enthalten vordefinierte Filter, die die Navigation und die Datenvisualisierung erleichtern.

[!DNL :arrow_upper_right:] Weitere Informationen zu Filteroptionen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Zugriff auf Daten aus dem Explorer

Wenn Sie in der Adobe Campaign Explorer-Struktur navigieren, werden die in der Datenbank enthaltenen Daten in Listen angezeigt. Sie können diese Listen filtern, Suchvorgänge durchführen und Informationen hinzufügen sowie Daten filtern und sortieren.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Listen konfigurieren und eine Listenkonfiguration in der  [Campaign Classic v7-Dokumentation speichern.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


Sie können Filter auf diese Listen anwenden, um nur die vom Benutzer benötigten Daten anzuzeigen. Anschließend können die gefilterten Daten bearbeitet werden. Mit der Filterkonfiguration können Sie Daten aus einer Liste dynamisch auswählen. Wenn die Daten geändert werden, werden die gefilterten Daten aktualisiert.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Daten in der Dokumentation zu  [Campaign Classic v7 filtern.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)

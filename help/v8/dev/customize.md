---
solution: Campaign
product: Adobe Campaign
title: Instanz anpassen
description: Erfahren Sie, wie Sie Ihre Instanz anpassen können
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
translation-type: tm+mt
source-git-commit: ddf60fb823cb0df99bdf3bc99f17d7a1abe6a33b
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 11%

---

# Anpassen der Instanz{#gs-ac-custom}

Erfahren Sie, wie Sie **Ihre Kampagne anpassen**

>[!CAUTION]
>
>Die Anpassung des Adobe Campaigns ist nur für erfahrene Benutzer vorgesehen.

## Neue Datenfelder und Schemas erstellen

Adobe Campaign nutzt Data Schemas, um:

* Definieren der Bindung von Datenobjekten innerhalb der Anwendung an zugrunde liegende Datenbanktabellen
* Definieren von Verknüpfungen zwischen den verschiedenen Datenobjekten in der Kampagne
* Definieren und Beschreiben der einzelnen Felder in den einzelnen Objekten

Um beispielsweise ein Feld zu einer vorhandenen Tabelle hinzuzufügen, z. B. der Tabelle &quot;Empfänger&quot;(nms:Empfänger), müssen Sie dieses Schema erweitern.

Es stehen zwei Tabellenerweiterungsmodi zur Verfügung:

* Über die Oberfläche mithilfe des Assistenten **Neues Feld**

   :arrow_upper_right: Erfahren Sie, wie Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic) schnell ein neues Feld in Kampagne hinzufügen

* Programmatische Ausweitung des Schemas

   :bulb: Erfahren Sie, wie Sie ein vorhandenes Schema in [diesem Abschnitt](../dev/extend-schema.md) erweitern.


Sie können auch neue Tabellen in der Kampagnen-Datenbank erstellen und das integrierte Datenmodell erweitern.

Um einen völlig neuen Datentyp hinzuzufügen, der in Adobe Campaign nicht standardmäßig vorhanden ist (z. B. eine Vertragstabelle), können Sie direkt ein benutzerdefiniertes Schema erstellen. Weitere Informationen hierzu finden Sie in [diesem Beispiel](../dev/create-schema.md#example--creating-a-contract-table).

**Verwandte Themen**

:arrow_upper_right: Schema-Edition in [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

:arrow_upper_right: Verwendungsfall: Verknüpfen eines Felds mit einer vorhandenen Referenztabelle in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Ändern der Eingabefelder

Formulare für die Eingabe von Kampagnen können an Ihre Implementierung angepasst werden. Sie können Formularfelder hinzufügen oder entfernen, indem Sie den XML-Inhalt ändern.

:bulb: Erfahren Sie, wie Sie ein vorhandenes Eingabedatum ändern oder ein neues Formular in [diesem Abschnitt](../dev/forms.md) erstellen.

## Dashboard{#gs-custom-dashboards} anpassen

In der Benutzeroberfläche von Adobe Campaign werden zahlreiche Webanwendungen bereitgestellt, die es Ihnen ermöglichen, auf Empfänger, Sendungen, Kampagnen, gespeicherte Assets etc. zuzugreifen, sie zu verwalten und mit ihnen zu interagieren. In der Benutzeroberfläche erscheinen sie in Form von Dashboards, die aus einer einzigen Seite bestehen.

Die nativen Webanwendungen sind im Knoten Administration > Konfiguration > Webanwendungen gespeichert.

:arrow_upper_right: Informationen zum Erstellen einer Übersichtsseite in Kampagne in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Listen anpassen und Filter {#gs-lists-and-filters} erstellen

### Daten aus Dashboards abrufen

Listen der Kampagne werden mit Vordefinierte Filtern geliefert, um die Navigation und Datenvizualisierung zu erleichtern.

:arrow_upper_right: Weitere Informationen zu Filteroptionen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Zugriff auf Daten aus dem Explorer

Wenn Sie in der Adobe Campaign Explorer-Struktur navigieren, werden die in der Datenbank enthaltenen Daten in Listen angezeigt. Sie können diese Listen filtern, Suchvorgänge durchführen und Informationen hinzufügen sowie Daten filtern und sortieren.

:arrow_upper_right: Informationen zum Konfigurieren von Listen und Speichern einer Liste in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


Sie können Filter auf diese Listen anwenden, um nur die vom Operator benötigten Daten anzuzeigen. Dann können Aktionen für die gefilterten Daten ausgeführt werden. Mit der Filterkonfiguration können Sie Daten aus einer Liste dynamisch auswählen. Wenn die Daten geändert werden, werden die gefilterten Daten aktualisiert.

:arrow_upper_right: Informationen zum Filtern von Daten in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)

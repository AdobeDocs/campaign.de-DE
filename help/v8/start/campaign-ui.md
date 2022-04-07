---
title: Campaign-Arbeitsbereich kennenlernen
description: Erfahren Sie, wie Sie den Campaign-Arbeitsbereich durchsuchen und verwenden
feature: Overview
role: Data Engineer
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: b54a39ee6d106d68446878815c068571e310aaa3
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 32%

---

# Benutzeroberfläche von Campaign

## Zugriff auf die Campaign-Benutzeroberfläche

Der Campaign-Arbeitsbereich ist über die [Client-Konsole](../dev/general-architecture.md) aufrufbar.

Erfahren Sie, wie Sie die Campaign Client Console in [diesem Abschnitt](../start/connect.md).

![](assets/home-page.png)

Sie können auch einen Webbrowser verwenden, um auf Campaign zuzugreifen. In diesem Zusammenhang ist nur ein Teil der Campaign-Funktionen verfügbar. [Weitere Informationen](#web-browser)

## Benutzeroberfläche durchsuchen

Sobald Sie mit Campaign verbunden sind, gelangen Sie auf die Startseite. Durchsuchen Sie die Links, um auf Funktionen zuzugreifen. Die in der Benutzeroberfläche verfügbaren Funktionen hängen von Ihren Optionen und Berechtigungen ab.

Greifen Sie über die Links im mittleren Bereich der Startseite auf die Hilfematerialien von Campaign, die Community und die Support-Website zu.

Über die Registerkarten im oberen Abschnitt können Sie die wichtigsten Funktionen von Campaign durchsuchen:

![](assets/overview-home.png)

>[!NOTE]
>
>Die Liste der Hauptfunktionen, auf die Sie zugreifen können, hängt von Ihren Berechtigungen und Ihrer Implementierung ab.

Für jede Funktion können Sie auf die wichtigsten Funktionen im **[!UICONTROL Browsen]** Abschnitt. Die **[!UICONTROL Mehr]** -Link ermöglicht den Zugriff auf alle anderen Komponenten.

Wenn Sie beispielsweise zum **[!UICONTROL Profile und Zielgruppen]** auf die Empfängerlisten, Abonnements, existierende Zielgruppen-Workflows und die Verknüpfungen zur Erstellung dieser Komponenten zugreifen können.

![](assets/overview-list.png)

Wenn Sie ein Element auf dem Bildschirm auswählen, wird es in eine neue Registerkarte geladen, sodass Sie Inhalt einfach durchsuchen können.

![](assets/new-tab.png)

## Element erstellen {#create-an-element}

Verwenden Sie Tastaturbefehle in der **[!UICONTROL Erstellen]** auf der linken Bildschirmseite neue Elemente hinzufügen. Sie können auch die **[!UICONTROL Erstellen]** oberhalb der Liste, um der aktuellen Liste neue Elemente hinzuzufügen.

Nutzen Sie beispielsweise auf der Seite der Sendungen die Schaltfläche **[!UICONTROL Erstellen]**, um einen neuen Versand anzulegen.

![](assets/new-recipient.png)

## Webbrowser verwenden {#web-browser}

Sie können auch über einen Webbrowser auf eine Untergruppe von Campaign-Funktionen zugreifen.

Die Benutzeroberfläche für den Web-Zugriff ähnelt der Benutzeroberfläche der Konsole. Von einem Browser aus können Sie dieselben Funktionen zum Navigieren und Anzeigen wie in der Konsole verwenden, aber Sie können nur einen reduzierten Satz von Aktionen für Kampagnen durchführen. Sie können beispielsweise Kampagnen anzeigen und abbrechen, aber keine Kampagnen ändern.

![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über den Campaign-Webzugriff](../start/connect.md#web-access).

## Zugriff auf Campaign Explorer {#ac-explorer-ui}

Durchsuchen Sie den Campaign Explorer, um auf alle Funktionen und Einstellungen von Adobe Campaign zuzugreifen.

![](assets/explorer.png)

In diesem Arbeitsbereich können Sie auf die Explorer-Struktur zugreifen, um alle Funktionen und Optionen zu durchsuchen.

Im linken Bereich wird der Campaign Explorer -Navigationsbaum angezeigt. Dort können Sie alle Komponenten und Einstellungen Ihrer Instanz durchsuchen - basierend auf Ihren Berechtigungen.

Im oberen Bereich wird die Liste der Datensätze des aktuellen Ordners angezeigt. Diese Listen können vollständig angepasst werden. [Weitere Informationen](customize-ui.md)

Im unteren Bereich werden die Details des ausgewählten Datensatzes angezeigt.


## Sprachen

Die Benutzeroberfläche von Campaign v8 ist in den folgenden Sprachen verfügbar:

* Englisch (UK)
* Englisch (US)
* Französisch
* Deutsch
* Japanisch

Die Sprache wird während des Installationsprozesses ausgewählt.

>[!CAUTION]
>
>Die Sprache kann nach der Instanzerstellung nicht mehr geändert werden.

Die Sprache wirkt sich auf Datums- und Uhrzeitformate aus.


Die Hauptunterschiede zwischen US-amerikanischem Englisch und britischem Englisch sind:

<table> 
 <thead> 
  <tr> 
   <th> Formate<br /> </th> 
   <th> Englisch (US)<br /> </th> 
   <th> Englisch (EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Datum<br /> </td> 
   <td> Woche beginnt am Sonntag<br /> </td> 
   <td> Woche beginnt am Montag<br /> </td> 
  </tr> 
  <tr> 
   <td> Kurzform des Datums<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>z. B.: 09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>z. B.: 25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Kurzform des Datums mit Uhrzeit<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>z. B.: 09/25/2018 10:47:25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>z. B.: 25/09/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>

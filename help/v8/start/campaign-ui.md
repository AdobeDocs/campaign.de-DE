---
title: Benutzeroberfläche von Campaign kennenlernen
description: Erfahren Sie, wie Sie die Benutzeroberfläche von Campaign durchsuchen und verwenden
feature: Overview
role: User
level: Beginner
source-git-commit: 8666c04f0e98cd6444af831d47056c46019c6088
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 38%

---

# Entdecken Sie die Benutzeroberfläche {#ui-client-console}

Sie können über die Clientkonsole oder die Webbenutzeroberfläche auf Adobe Campaign zugreifen. Sie können auch APIs verwenden, um Daten zu verwalten und Aufgaben in Ihrer Campaign-Plattform auszuführen.

>[!CAUTION]
>
>Diese Dokumentation konzentriert sich auf die Verwendung der Campaign Client Console. Wenn Sie die Campaign-Webbenutzeroberfläche verwenden, lesen Sie den Abschnitt [diese Dokumentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.

* **Client-Konsole** - Die Campaign-Clientkonsole ist eine native Anwendung, die über Standard-Internetprotokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungsserver kommuniziert. Die Campaign-Clientkonsole zentralisiert alle Funktionen und Einstellungen und erfordert minimale Bandbreite, da sie auf einem lokalen Cache basiert. Die Campaign-Clientkonsole wurde für eine einfache Bereitstellung konzipiert und kann über einen Internetbrowser bereitgestellt werden. Sie wird automatisch aktualisiert und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic generiert. [Weitere Informationen](#ui-access)

  Erfahren Sie, wie Sie die Campaign-Clientkonsole installieren und konfigurieren in [diesem Abschnitt](../start/connect.md).

<!--    ![](assets/home-page.png) -->

* **Web-Benutzeroberfläche** - Als Campaign v8-Benutzer ab Version 8.6.1 haben Sie jetzt Zugriff auf eine Webumgebung, die über die zentrale Benutzeroberfläche von Adobe Experience Cloud verfügbar ist. Sie können dann über einen Webbrowser eine Verbindung zu Adobe Campaign herstellen. Auf dieser neuen Benutzeroberfläche können Sie wichtige Marketing-Aktionen erstellen, verwalten und ausführen. Es sind jedoch nicht alle Campaign-Funktionen verfügbar. [Weitere Informationen](#ac-web-ui).

  Die Webbenutzeroberfläche von Campaign Campaign ist über die Startseite der Clientkonsole verfügbar.

  ![](assets/web-ui.png)

  >[!NOTE]
  >
  >Wenn die neue Zugriffskarte nicht angezeigt wird, stellen Sie sicher, dass die folgenden Felder in Ihrem externen Adobe Experience Cloud-Konto nicht leer gelassen werden: **Server**, **Mandant**, **Callback-Server**, und **Zuordnungsmarke**.

* **Webzugriff** - Mit den Adobe Campaign-Webzugriffsfunktionen können Sie über eine HTML-Benutzeroberfläche mit einem Webbrowser auf eine Untergruppe von Campaign-Funktionen zugreifen. Verwenden Sie diese Web-Benutzeroberfläche, um auf Berichte zuzugreifen, Nachrichten zu steuern und zu validieren, auf Monitoring-Dashboards zuzugreifen und vieles mehr.  Erfahren Sie mehr über den Campaign-Webzugriff [in diesem Abschnitt](../start/connect.md#web-access).

* **APIs** - Um weitere Anwendungsfälle zu beheben, kann das System über die Web-Services-APIs, die über das SOAP-Protokoll verfügbar gemacht werden, aus externen Anwendungen aufgerufen werden. Weitere Informationen zu Campaign-APIs [auf dieser Seite](../dev/api.md).


## Arbeiten mit der Client-Konsole {#ui-access}

Die Campaign-Clientkonsole ist eine native Anwendung, die über Standard-Internetprotokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungsserver kommuniziert. Die Campaign-Clientkonsole zentralisiert alle Funktionen und Einstellungen und erfordert minimale Bandbreite, da sie auf einem lokalen Cache basiert. Die Campaign-Clientkonsole wurde für eine einfache Bereitstellung konzipiert und kann über einen Internetbrowser bereitgestellt werden. Sie wird automatisch aktualisiert und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic generiert.  [Erfahren Sie mehr über die Campaign-Clientkonsole](../start/connect.md).

![](assets/home-page.png)

Sie können auch einen Webbrowser verwenden, um auf Campaign zuzugreifen. In diesem Zusammenhang ist nur ein Teil der Campaign-Funktionen verfügbar. [Weitere Informationen](#web-browser)

### Benutzeroberfläche durchsuchen {#ui-browse}

Sobald Sie mit der Campaign-Clientkonsole verbunden sind, greifen Sie auf die Startseite zu. Durchsuchen Sie die Links, um auf Funktionen zuzugreifen. Die in der Benutzeroberfläche verfügbaren Funktionen hängen von Ihren Optionen und Berechtigungen ab.

Greifen Sie über die Links im mittleren Bereich der Startseite auf die Hilfematerialien von Campaign, die Community und die Support-Website zu. Verwenden Sie die zentralen Karten, um die neue Campaign-Webbenutzeroberfläche und das Campaign Control Panel zu durchsuchen.

Auf den Registerkarten im oberen Abschnitt können Sie auf die wichtigsten Funktionen von Campaign zugreifen:

![](assets/overview-home.png)

>[!NOTE]
>
>Die Liste der Hauptfunktionen, auf die Sie zugreifen können, hängt von Ihren Berechtigungen und Ihrer Implementierung ab.

Im Abschnitt **[!UICONTROL Browsen]** können Sie für jede Funktion auf die wichtigsten Optionen zugreifen. Der Link **[!UICONTROL Mehr]** ermöglicht den Zugriff auf alle anderen Komponenten.

Wenn Sie beispielsweise zur Registerkarte **[!UICONTROL Profile und Zielgruppen]** gehen, können Sie auf die Empfängerlisten, Abonnements, existierende Zielgruppen-Workflows und die Verknüpfungen zur Erstellung dieser Komponenten zugreifen.

![](assets/overview-list.png)

Wenn Sie ein Element auf dem Bildschirm auswählen, wird es in eine neue Registerkarte geladen, sodass Sie Inhalte einfach durchsuchen können.

![](assets/new-tab.png)

### Erstellen eines Elements {#create-an-element}

Verwenden Sie im Abschnitt **[!UICONTROL Erstellen]** auf der linken Bildschirmseite Tastaturbefehle, um neue Elemente hinzufügen. Sie können auch den Button **[!UICONTROL Erstellen]** oberhalb der Liste verwenden, um der aktuellen Liste neue Elemente hinzuzufügen.

Nutzen Sie beispielsweise auf der Seite der Sendungen die Schaltfläche **[!UICONTROL Erstellen]**, um einen neuen Versand anzulegen.

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

![](../assets/do-not-localize/glass.png) [Learn more about Campaign web access](../start/connect.md#web-access).-->

### Zugriff auf Campaign Explorer {#ac-explorer-ui}

Durchsuchen Sie den Campaign Explorer, um auf alle Funktionen und Einstellungen von Adobe Campaign zuzugreifen.

![](assets/explorer.png)

In diesem Arbeitsbereich können Sie auf die Explorer-Baumstruktur zugreifen, um alle Funktionen und Optionen zu durchsuchen.

* Im linken Bereich wird die Baumstruktur des Campaign-Explorers angezeigt. Dort können Sie basierend auf Ihren Berechtigungen alle Komponenten und Einstellungen Ihrer Instanz durchsuchen. Sie können Ordner hinzufügen und anpassen, wie auf [dieser Seite](../audiences/folders-and-views.md) beschrieben.

* Im oberen Bereich wird die Liste der Einträge des aktuellen Ordners angezeigt. Diese Listen können vollständig angepasst werden. [Weitere Informationen](../config/ui-settings.md)

* Im unteren Bereich werden die Details des ausgewählten Eintrags angezeigt.


## Campaign-Webbenutzeroberfläche {#ac-web-ui}

Als Campaign v8-Client-Konsolenbenutzer haben Sie ab Version 8.6.1 Zugriff auf eine Webumgebung, die über die zentrale Benutzeroberfläche von Adobe Experience Cloud verfügbar ist. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen.

![Startseite der Adobe Campaign-Webbenutzeroberfläche](assets/ac-web-home.png)

Erfahren Sie mehr über die neue Campaign-Web-Benutzeroberfläche in [diese Dokumentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.

Zusätzliche und erweiterte Funktionen, Konfigurationen und Einstellungen sind nur in der Clientkonsole verfügbar. Erfahren Sie mehr über die in beiden Benutzeroberflächen verfügbaren Funktionen. [in der Dokumentation der Campaign-Webbenutzeroberfläche](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html){target="_blank"}.


## Unterstützte Sprachen {#languages}

Die unterstützten Sprachen hängen von der Benutzeroberfläche ab.

* Für die Clientkonsole v8 werden folgende Sprachen unterstützt:

   * Englisch (UK)
   * Englisch (US)
   * Französisch
   * Deutsch
   * Japanisch


  >[!CAUTION]
  >
  >Die Sprache wird während der Installation ausgewählt und kann danach nicht mehr geändert werden.

* Für die Campaign-Webbenutzeroberfläche werden folgende Sprachen unterstützt: [auf diese Seite verweisen](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html#language-pref){target="_blank"}.


Die Sprachauswahl beeinflusst Datums- und Uhrzeitformate.

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

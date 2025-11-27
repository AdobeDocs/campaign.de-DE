---
title: Erkunden der Benutzeroberfläche von Campaign
description: Erfahren Sie, wie Sie die Campaign-Benutzeroberfläche durchsuchen und nutzen können
feature: Overview
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: df8ab43d9c7aee96c23240cd6c2775311da1abf2
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 69%

---

# Erkunden der Benutzeroberfläche {#ui-client-console}

Sie können über die Client-Konsole oder die Web-Benutzeroberfläche auf Adobe Campaign zugreifen. Sie können auch APIs verwenden, um Daten zu verwalten und Aufgaben in Ihrer Campaign-Plattform auszuführen.

* **Client-Konsole**: Die Client-Konsole ist eine native Anwendung, die über Standard-Internet-Protokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungs-Server kommuniziert. In der Campaign Client-Konsole sind alle Funktionen und Einstellungen verfügbar. Sie erfordert eine minimale Bandbreite, da sie auf einem lokalen Cache beruht. Die Campaign-Client-Konsole, die für eine einfache Bereitstellung entwickelt wurde, kann über einen Internet-Browser bereitgestellt werden sowie automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic erzeugt. [Weitere Informationen](#ui-access)

  Weitere Informationen dazu, wie Sie die Campaign Client-Konsole installieren und konfigurieren können, finden Sie in [diesem Abschnitt](../start/connect.md).

* **Web-Zugriff**: Mit den Web-basierten Adobe Campaign-Zugriffsfunktionen können Sie über eine HTML-Benutzeroberfläche mit einem Webbrowser auf eine Teilmenge von Campaign-Funktionen zugreifen. Verwenden Sie diese Web-Benutzeroberfläche, um auf Berichte zuzugreifen, Nachrichten zu steuern und zu validieren, auf Monitoring-Dashboards zuzugreifen und vieles mehr. Weitere Informationen zum Web-basierten Zugriff auf Campaign finden Sie [in diesem Abschnitt](../start/connect.md#web-access).

* **APIs**: In bestimmten Fällen kann das System über die via SOAP-Protokoll bereitgestellten Web Services-APIs von einer externen Anwendung aus aufgerufen werden. Weitere Informationen zu Campaign-APIs finden Sie [auf dieser Seite](../dev/api.md).

* **Web-Benutzeroberfläche**: Als Benutzerin oder Benutzer von Campaign v8 haben Sie jetzt ab v8.6.1 Zugriff auf eine Web-Umgebung, die über die zentrale Benutzeroberfläche von Adobe Experience Cloud verfügbar ist. Sie können dann über einen Webbrowser eine Verbindung zu Adobe Campaign herstellen. Auf dieser neuen Benutzeroberfläche können Sie wichtige Marketing-Aktionen erstellen, verwalten und ausführen. Es sind jedoch nicht alle Campaign-Funktionen verfügbar. [Weitere Informationen](#ac-web-ui).

  >[!AVAILABILITY]
  >
  >Die Web-Benutzeroberfläche von Campaign ist nur für Benutzende von Campaign v8 verfügbar, die über ihre Adobe ID eine Verbindung zu Campaign herstellen. Erfahren Sie mehr über das [Identitäts-Management-System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} von Adobe.
  >

>[!CAUTION]
>
>Diese Dokumentation konzentriert sich auf die Verwendung der Campaign-Client-Konsole. Wenn Sie als Campaign v8-Benutzer die Web-Benutzeroberfläche von Campaign verwenden, lesen Sie [diese Dokumentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=de){target="_blank"}.

## Arbeiten mit der Client-Konsole {#ui-access}

Die Campaign-Client-Konsole ist eine native Anwendung, die über Standard-Internet-Protokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungs-Server kommuniziert. In der Campaign Client-Konsole sind alle Funktionen und Einstellungen verfügbar. Sie erfordert eine minimale Bandbreite, da sie auf einem lokalen Cache beruht. Die Campaign-Client-Konsole, die für eine einfache Bereitstellung entwickelt wurde, kann über einen Internet-Browser bereitgestellt werden sowie automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic erzeugt.  [Erfahren Sie mehr über die Campaign-Client-Konsole](../start/connect.md).



>[!BEGINTABS]

>[!TAB Campaign v8]

Sobald Sie mit Campaign verbunden sind, rufen Sie die Startseite von Adobe Campaign auf. Verwenden Sie in Campaign v8 die zentralen Karten, um die neue Campaign Web-Benutzeroberfläche und das Campaign Control Panel zu durchsuchen.

![Startseite der Client-Konsole von Campaign v8](assets/web-ui.png)

>[!NOTE]
>
>Wenn die Karte Web-Benutzeroberfläche nicht angezeigt wird, stellen Sie sicher, dass die folgenden Felder in Ihrem externen A[Adobe Experience Cloud-Konto nicht leer bleiben](../config/external-accounts.md): **Server**, **Mandant**, **Callback-Server** und **Zuordnungszeichen**.

Sie können auch von der Startseite aus auf [Campaign Control Panel](../config/self-service.md) zugreifen.

>[!TAB Campaign Classic v7]

Sobald Sie mit Campaign verbunden sind, gelangen Sie auf die Adobe Campaign-Startseite mit Links und Verknüpfungen, um auf Funktionen, Dokumentation, die Support-Website und die Campaign-Community zuzugreifen.

![Client-Konsole für Campaign Classic v7 - Startseite](assets/v7_user_interface_home.png)


>[!ENDTABS]


Sie können auch einen Webbrowser verwenden, um auf Campaign zuzugreifen. In diesem Zusammenhang ist nur ein Teil der Campaign-Funktionen verfügbar. [Weitere Informationen](#web-browser)

### Durchsuchen der Benutzeroberfläche {#ui-browse}

Sobald Sie mit der Campaign-Client-Konsole verbunden sind, durchsuchen Sie die Registerkarten im oberen Abschnitt, um auf die wichtigsten Funktionen von Campaign zuzugreifen:

![](assets/overview-home.png)

>[!NOTE]
>
>Die Liste der Hauptfunktionen, auf die Sie zugreifen können, hängt von Ihren Berechtigungen und Ihrer Implementierung ab.

Im Abschnitt **[!UICONTROL Browsen]** können Sie für jede Funktion auf die wichtigsten Optionen zugreifen. Der Link **[!UICONTROL Mehr]** ermöglicht den Zugriff auf alle anderen Komponenten.

Wenn Sie beispielsweise zur Registerkarte **[!UICONTROL Profile und Zielgruppen]** gehen, können Sie auf die Empfängerlisten, Abonnements, existierende Zielgruppen-Workflows und die Verknüpfungen zur Erstellung dieser Komponenten zugreifen.

![Benutzeroberfläche der Campaign-Konsole, über die der Zugriff auf die Listen über die Registerkarte Profile und Zielgruppe erfolgt](assets/overview-list.png)

Wenn Sie ein Element auf dem Bildschirm auswählen, wird es in eine neue Registerkarte geladen, sodass Sie Inhalte einfach durchsuchen können.

![Benutzeroberfläche der Campaign-Konsole, in der das Bearbeiten einer Liste auf einer neuen Registerkarte angezeigt wird](assets/new-tab.png)

### Erstellen eines Elements {#create-an-element}

Verwenden Sie im Abschnitt **[!UICONTROL Erstellen]** auf der linken Bildschirmseite Tastaturbefehle, um neue Elemente hinzufügen. Sie können auch den Button **[!UICONTROL Erstellen]** oberhalb der Liste verwenden, um der aktuellen Liste neue Elemente hinzuzufügen.

![Benutzeroberfläche der Campaign-Konsole, die das Erstellen eines Empfängers über den Bildschirm „Profile und Zielgruppe“ anzeigt](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### Zugriff auf Campaign Explorer {#ac-explorer-ui}

Durchsuchen Sie den Campaign Explorer, um auf alle Funktionen und Einstellungen von Adobe Campaign zuzugreifen.

![Benutzeroberfläche der Campaign-Konsole, auf der der Explorer mit Fokus auf dem Menü Kampagnen angezeigt wird](assets/explorer.png)

In diesem Arbeitsbereich können Sie auf die Explorer-Baumstruktur zugreifen, um alle Funktionen und Optionen zu durchsuchen.

* Im linken Bereich wird die Baumstruktur des Campaign-Explorers angezeigt. Dort können Sie basierend auf Ihren Berechtigungen alle Komponenten und Einstellungen Ihrer Instanz durchsuchen. Sie können Ordner hinzufügen und anpassen, wie auf [dieser Seite](../audiences/folders-and-views.md) beschrieben.

* Im oberen Bereich wird die Liste der Einträge des aktuellen Ordners angezeigt. Diese Listen können vollständig angepasst werden. [Weitere Informationen](../config/ui-settings.md)

* Im unteren Bereich werden die Details des ausgewählten Eintrags angezeigt.


## Campaign Web-Benutzeroberfläche {#ac-web-ui}

Als Campaign v8-Benutzer haben Sie ab Version 8.6.1 Zugriff auf eine Web-Umgebung, die über die zentrale Benutzeroberfläche von Adobe Experience Cloud verfügbar ist. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen.

![Startseite der Adobe Campaign Web-Benutzeroberfläche](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>Die Web-Benutzeroberfläche von Campaign ist nur für Benutzende von Campaign v8 verfügbar, die über ihre Adobe ID eine Verbindung zu Campaign herstellen. Erfahren Sie mehr über das [Identitäts-Management-System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} von Adobe.
>

Weitere Informationen über die neue Campaign Web-Benutzeroberfläche finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=de){target="_blank"}. Sie können auch die entsprechende Seite [Häufig gestellte Fragen](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/faq){target="_blank"} in der Dokumentation zur Campaign Web-Benutzeroberfläche besuchen.

Zusätzliche und erweiterte Funktionen, Konfigurationen und Einstellungen sind nur in der Client-Konsole verfügbar. Weitere Informationen über die verfügbaren Funktionen in beiden Benutzeroberflächen finden Sie [in der Dokumentation der Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html?lang=de){target="_blank"}.


## Unterstützte Sprachen {#languages}

Die unterstützten Sprachen hängen von der Benutzeroberfläche ab.

* Für die Benutzeroberfläche der Campaign-Client-Konsole werden folgende Sprachen unterstützt:

   * Englisch (UK)
   * Englisch (US)
   * Französisch
   * Deutsch
   * Japanisch


  >[!CAUTION]
  >
  >Die Sprache wird während des Installationsprozesses ausgewählt und **kann später nicht mehr geändert**.

* Informationen zu den von der Campaign-Web-Benutzeroberfläche unterstützten Sprachen [&#x200B; Sie in der Dokumentation zur Campaign-Web-Benutzeroberfläche](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html?lang=de#language-pref){target="_blank"}.

## Formate

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
   <td> <p>%2M/%2D/%4Y</p><p><strong>z. B.: 09/25/2025</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>z. B.: 25/09/2025</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Kurzform des Datums mit Uhrzeit<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>z. B.: 09/25/2025 :47::25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>z. B.: 25/09/2025 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>


## Zusätzliche Ressourcen

* **[Arbeiten mit Auflistungen](../config/enumerations.md)** - Standardisieren von Feldwerten mit vordefinierten Dropdown-Listen für eine schnellere, konsistentere Dateneingabe.
* **[Filterdaten](../audiences/create-filters.md)** - Entdecken Sie vorhandene integrierte Filter, um auf eine bestimmte Untergruppe von Campaign-Daten zuzugreifen, wie Sie Schnellfilter erstellen oder Ihre eigenen erweiterten Filter entwerfen und freigeben können.
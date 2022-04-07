---
title: Kampagnenprozesse und -komponenten
description: Kampagnenprozesse und -komponenten
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: b54a39ee6d106d68446878815c068571e310aaa3
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 2%

---

# Kampagnenprozesse und -komponenten {#components-and-processes}

Adobe Campaign ist eine kanalübergreifende Marketinglösung, die E-Mail-, Mobile-, Social- und Offline-Kampagnen automatisiert. Adobe Campaign bietet eine zentrale Stelle für den Zugriff auf Ihre Kundendaten und -profile. Verwenden Sie Adobe Campaign, um konsistente Erlebnisse für Ihre Kunden zu orchestrieren, Ihr Marketing kanalübergreifend zu entwerfen, auszuführen und zu personalisieren und gleichzeitig die Kundenerlebnisse auf allen Geräten und Touchpoints zu verbessern. Mit Adobe Campaign können Sie mehrere Datenquellen verwalten, Zielgruppensegmente definieren und mehrstufige, kanalübergreifende Kampagnen über eine Drag &amp; Drop-Benutzeroberfläche für visuelle Workflows planen und ausführen.

Erfahren Sie mehr über die wichtigsten Funktionen von Campaign in [diese Seite](../start/get-started.md).

## Kampagnenkomponenten {#ac-components}

Die Adobe Campaign-Komponenten und die globale Architektur werden nachfolgend beschrieben.

![](assets/ac-components.png)

### Präsentationsschicht{#presentation-layer}

Sie können über einen Rich-Client, einen Thin-Client oder eine API-Integration auf Adobe Campaign zugreifen.

* Rich-Client

   Der Campaign Rich-Client ist eine native Anwendung, die über Standard-Internetprotokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungsserver kommuniziert.

   Die Campaign Client-Konsole zentralisiert alle Funktionen und Einstellungen und erfordert minimale Bandbreite, da sie auf einen lokalen Cache angewiesen ist. Die Campaign Client Console wurde für eine einfache Bereitstellung konzipiert und kann über einen Internetbrowser bereitgestellt werden. Sie wird automatisch aktualisiert und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic generiert.

   ![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über die Campaign-Client-Konsole](../start/connect.md).

* Thin Client

   Mit den Adobe Campaign-Webzugriffsfunktionen können Sie über eine HTML-Benutzeroberfläche mit einem Webbrowser auf eine Untergruppe von Campaign-Funktionen zugreifen. Verwenden Sie diese Webschnittstelle, um auf Berichte zuzugreifen, Nachrichten zu steuern und zu validieren, auf Monitoring-Dashboards zuzugreifen und vieles mehr.

   ![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über den Web-basierten Zugriff auf Campaign](../start/connect.md).

* Externe Anwendungen mit APIs

   In bestimmten Fällen kann das System mithilfe der Web-Services-APIs, die über das SOAP-Protokoll verfügbar gemacht werden, aus externen Anwendungen aufgerufen werden.

   ![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über Campaign-APIs](../dev/api.md).

### Persistenzschicht{#persistance-layer}

Campaign-Datenbanken werden als Persistenzschichten verwendet und enthalten fast alle von Adobe Campaign verwalteten Informationen und Daten. Dazu gehören: Funktionsdaten wie Profile, Abonnements, Inhalte; technische Daten wie Versandaufträge und -logs, Trackinglogs; und Arbeitsdaten (Einkäufe, Leads).

Die Zuverlässigkeit der Datenbank ist von größter Bedeutung, da die meisten Adobe Campaign-Komponenten Zugriff auf die Datenbank benötigen, damit sie ihre Aufgaben ausführen können (mit Ausnahme des Umleitungsmoduls).

### Logische Anwendungsschicht{#logical-app-layer}

Die logische Anwendungsebene von Campaign kann einfach konfiguriert werden, um komplexen geschäftlichen Anforderungen gerecht zu werden. Sie können Campaign als eine Plattform mit verschiedenen Anwendungen verwenden, die zu einer offenen und skalierbaren Architektur kombiniert werden. Jede Campaign-Instanz ist eine Sammlung von Prozessen in der Anwendungsschicht, von denen einige freigegeben und einige dediziert sind.

## Campaign Managed Services{#ac-managed-services}

Adobe Campaign v8 wird as a Managed Service bereitgestellt: Alle Komponenten von Adobe Campaign, einschließlich der Benutzeroberfläche, der Ausführungsverwaltungsmaschine und der Campaign-Datenbanken, werden vollständig von der Adobe gehostet, einschließlich E-Mail-Ausführung, Mirrorseiten, Tracking-Server und extern orientierten Webkomponenten wie Abmelde-Seite/Präferenzcenter und Landingpages.

## Kampagnenprozesse

Der Campaign-Webserver steuert den Zugriff auf Campaign-Webprozesse. JavaScript ist die serverseitige Sprache, die für zentrale Produktfunktionen und die Anpassung verwendet wird. Tomcat ist die Backend-Engine und im Rahmen des Webprozesses in das Campaign-Produkt eingebettet. JavaScript wird beispielsweise auf JSP- oder JSSP-Seiten zum Rendern dynamischer Inhalte verwendet.

![](assets/ac-processes.png)

Die Campaign Client-Konsole stellt eine Verbindung zum Webserver her, indem sie SOAP XML über HTTP verwendet. Der Webserver stellt die Sicherheitsschicht bereit, übergibt die Anforderungen mithilfe von JavaScript an die Anwendungsschicht und die internen Prozesse von Campaign greifen mithilfe von SQL auf die Datenbank zu.

Die allgemeine Kommunikation zwischen Campaign-Prozessen wird im folgenden eigenständigen Bereitstellungsdiagramm beschrieben: alle Campaign-Komponenten auf demselben Computer installiert sind.

![](assets/ac-standalone.png)

Der Benutzer stellt mithilfe von HTTP eine Verbindung zum Campaign-Anwendungsserver her. Alle Daten und Informationen werden in der Campaign-Datenbank verwaltet. Wenn ein Campaign-Entwickler Konfigurationsänderungen durchführt, werden diese in der Datenbank erfasst. Wenn ein Marketing-Experte eine neue Kampagne erstellt, werden alle mit dieser neuen Kampagne verbundenen Informationen und Daten ebenfalls in der Datenbank verwaltet. Wenn ein Marketing-Experte eine Kampagne ausführt, werden E-Mail-Sendungen an Profile vom Campaign-Server über den SMTP-Server gesendet. Da Profile mit E-Mail-Sendungen wie dem Öffnen der E-Mail interagieren, werden Tracking-Daten an den Tracking-Server zurückgesendet.

![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über Campaign-Prozesse](../dev/general-architecture.md#dev-env).

---
title: Prozesse und Komponenten in Campaign
description: Prozesse und Komponenten in Campaign
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 100%

---

# Prozesse und Komponenten in Campaign {#components-and-processes}

Adobe Campaign ist eine Cross-Channel-Marketing-Lösung, die E-Mail-, Mobile-, Social Media- und Offline-Kampagnen automatisiert. Adobe Campaign bietet eine zentrale Stelle für den Zugriff auf Ihre Kundendaten und -profile. Verwenden Sie Adobe Campaign, um konsistente Erlebnisse für Ihre Kunden zu orchestrieren, Ihre Marketing-Maßnahmen kanalübergreifend zu entwickeln, auszuführen und zu personalisieren und gleichzeitig die Kundenerlebnisse auf allen Geräten und an jedem Touchpoint zu verbessern. Mit Adobe Campaign können Sie mehrere Datenquellen verwalten, Zielgruppensegmente definieren und mehrstufige Cross-Channel-Kampagnen über eine visuelle Workflow-Benutzeroberfläche per Drag-and-drop planen und ausführen.

Weitere Informationen zu Campaign finden Sie auf [dieser Seite](../start/get-started.md).

## Komponenten von Campaign {#ac-components}

Nachfolgend werden die Adobe Campaign-Komponenten und die globale Architektur beschrieben.

![](assets/ac-components.png)

### Präsentationsebene{#presentation-layer}

Sie können über einen Rich-Client, einen Thin-Client oder eine API-Integration auf Adobe Campaign zugreifen.

* Rich-Client

   Der Campaign Rich-Client ist eine native Anwendung, die über Standard-Internetprotokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungs-Server kommuniziert.

   In der Campaign Client-Konsole sind alle Funktionen und Einstellungen verfügbar. Sie erfordert minimale Bandbreite, da sie auf einem lokalen Cache beruht. Diese Konsole, die im Hinblick auf eine einfache Implementierung entwickelt wurde, kann über einen Internet-Browser implementiert werden, kann automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic erzeugt.

   ![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über die Campaign-Client-Konsole](../start/connect.md).

* Thin-Client

   Mit den Web-basierten Adobe Campaign-Zugriffsfunktionen können Sie über eine HTML-Benutzeroberfläche mit einem Webbrowser auf eine Untergruppe von Campaign-Funktionen zugreifen. Verwenden Sie diese Web-Benutzeroberfläche, um auf Berichte zuzugreifen, Nachrichten zu steuern und zu validieren, auf Monitoring-Dashboards zuzugreifen und vieles mehr.

   ![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über den Web-basierten Zugriff auf Campaign](../start/connect.md).

* Externe Anwendungen mit APIs

   In bestimmten Fällen kann das System über die via SOAP-Protokoll bereitgestellten Web Services-APIs von einem externen Programm aus aufgerufen werden.

   ![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über Campaign-APIs](../dev/api.md).

### Persistenzebene{#persistance-layer}

Campaign-Datenbanken werden als Persistenzebenen verwendet und enthalten fast alle von Adobe Campaign verwalteten Informationen und Daten. Dazu gehören: Funktionsdaten wie Profile, Abonnements, Inhalte, technische Daten wie Versandvorgänge und -Logs, Trackinglogs; und Arbeitsdaten (Bestellungen, Leads).

Die Zuverlässigkeit der Datenbank ist von größter Bedeutung, da die meisten Adobe Campaign-Komponenten Zugriff auf die Datenbank benötigen, damit sie ihre Aufgaben ausführen können (mit Ausnahme des Umleitungsmoduls).

### Logische Anwendungsebene{#logical-app-layer}

Die logische Anwendungsebene von Campaign kann einfach konfiguriert werden, um komplexen geschäftlichen Anforderungen gerecht zu werden. Sie können Campaign als zentrale Plattform mit verschiedenen Anwendungen verwenden, die zu einer offenen und skalierbaren Architektur kombiniert werden. Jede Campaign-Instanz ist eine Sammlung von Prozessen in der Anwendungsebene, von denen einige freigegeben und einige dediziert sind.

## Campaign Managed Services{#ac-managed-services}

Adobe Campaign v8 wird als Managed Service bereitgestellt: Alle Komponenten von Adobe Campaign, einschließlich der Benutzeroberfläche, der Ausführungsverwaltungs-Engine und der Campaign-Datenbanken, werden vollständig von Adobe gehostet, einschließlich E-Mail-Ausführung, Mirror-Seiten, Tracking-Server und nach außen gerichtete Web-Komponenten wie die Abmelde-Seite bzw. das Präferenzcenter und Landingpages.

## Prozesse in Campaign

Der Campaign-Webserver steuert den Zugriff auf Campaign-Web-Prozesse. JavaScript ist die Server-seitige Sprache, die für zentrale Produktfunktionen und die Anpassung verwendet wird. Tomcat ist die Back-End-Engine und im Rahmen des Web-Prozesses in das Campaign-Produkt eingebettet. JavaScript wird beispielsweise auf JSP- oder JSSP-Seiten zum Rendern dynamischer Inhalte verwendet.

![](assets/ac-processes.png)

Die Campaign Client-Konsole stellt eine Verbindung zum Webserver her, indem sie SOAP XML über HTTP verwendet. Der Webserver stellt die Sicherheitsebene bereit, übergibt die Anfragen mithilfe von JavaScript an die Anwendungsebene und die internen Prozesse von Campaign greifen mithilfe von SQL auf die Datenbank zu.

Die allgemeine Kommunikation zwischen Campaign-Prozessen wird im folgenden Diagramm einer Standalone-Implementierung beschrieben: Alle Campaign-Komponenten sind auf demselben Computer installiert.

![](assets/ac-standalone.png)

Der Benutzer stellt mithilfe von HTTP eine Verbindung zum Campaign-Anwendungs-Server her. Alle Daten und Informationen werden in der Campaign-Datenbank verwaltet. Wenn ein Campaign-Entwickler Änderungen an der Konfiguration durchführt, werden diese in der Datenbank erfasst. Wenn ein Marketer eine neue Kampagne erstellt, werden alle mit dieser neuen Kampagne verbundenen Informationen und Daten ebenfalls in der Datenbank verwaltet. Wenn ein Marketer eine Kampagne ausführt, werden vom Campaign-Server über den SMTP-Server E-Mail-Sendungen an Profile durchgeführt. Wenn Profile mit E-Mail-Sendungen interagieren, wie etwa beim Öffnen einer E-Mail, werden Tracking-Daten an den Tracking-Server zurückgesendet.

![](../assets/do-not-localize/glass.png) [Erfahren Sie mehr über die Prozesse in Campaign](../architecture/general-architecture.md#dev-env).

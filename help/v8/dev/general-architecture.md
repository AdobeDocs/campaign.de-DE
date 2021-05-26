---
solution: Campaign v8
product: Adobe Campaign
title: Allgemeine Architektur
description: Allgemeine Architektur von Campaign v8
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 0%

---

# Allgemeine Architektur{#general-architecture}

Die typische Adobe Campaign-Lösungsimplementierung besteht aus den folgenden Komponenten:

* **Personalisierte Client-Umgebung**

   Intuitive grafische Benutzeroberfläche, über die Benutzer Marketingangebote kommunizieren und verfolgen, Kampagnen erstellen, alle Marketing-Aktivitäten, Programme und Pläne - einschließlich E-Mails, Workflows und Landingpages - überprüfen und verwalten, Kundenprofile erstellen und verwalten sowie Zielgruppen erstellen können.

* **Entwicklungsumgebung**

   Serverseitige Software, die die Marketingkampagnen über ausgewählte Kommunikationskanäle ausführt, einschließlich E-Mails, SMS, Push-Benachrichtigungen, Briefpost, Web oder Social, basierend auf den in der Benutzeroberfläche definierten Regeln und Workflows.

* **Datenbank-Container**

   Basierend auf der relationalen Datenbanktechnologie speichert die Adobe Campaign Cloud-Datenbank alle Kundeninformationen, Kampagnenkomponenten, Angebote und Workflows sowie Kampagnenergebnisse in Container der Kundendatenbank.

## Personalisierte Client-Umgebung {#client-env}

Der Zugriff auf die Anwendung erfolgt auf unterschiedliche Weise: Rich-Client-, Thin-Client- oder API-Integration.

* **Client Console**: Die Hauptbenutzeroberfläche des Programms ist ein natives Programm (unter Windows), das mit dem Adobe Campaign-Anwendungsserver mit Standardinternetprotokollen (SOAP, HTTP usw.) kommuniziert. Die Adobe Campaign Client Console bietet eine hervorragende Benutzerfreundlichkeit für die Produktivität, verwendet sehr wenig Bandbreite (durch Verwendung eines lokalen Caches) und ist für eine einfache Implementierung ausgelegt. Diese Konsole kann über einen Internetbrowser bereitgestellt werden, kann automatisch aktualisiert werden und erfordert keine spezifische Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic generiert.

   [!DNL :bulb:] [Erfahren Sie mehr über die Campaign Client Console](../start/connect.md).

* **Webzugriff**: auf Teile der Anwendung kann über einen einfachen Webbrowser über eine HTML-Benutzeroberfläche zugegriffen werden, einschließlich Berichterstellungsmodul, Versandvalidierungsphasen, Instanzüberwachung usw.

   [!DNL :bulb:] [Erfahren Sie mehr über den Campaign-Webzugriff](../start/connect.md).

* **Campaign-APIs**: In bestimmten Fällen kann das System mithilfe der Web-Services-APIs, die über das SOAP-Protokoll verfügbar gemacht werden, aus einer externen Anwendung aufgerufen werden.

   [!DNL :bulb:] [Erfahren Sie mehr über Campaign-APIs](../dev/api.md).

## Entwicklungsumgebung {#dev-env}

Adobe Campaign ist eine Plattform mit verschiedenen Anwendungen, um eine offene und skalierbare Architektur zu erstellen. Die Adobe Campaign-Plattform ist auf einer flexiblen Anwendungsebene konzipiert und lässt sich einfach an Ihre geschäftlichen Anforderungen anpassen. Die verteilte Architektur stellt eine lineare Skalierbarkeit der Systeme sicher, die von Tausenden von Nachrichten auf Millionen von Nachrichten skaliert wird.

Einige Campaign-Module funktionieren kontinuierlich, während andere gelegentlich gestartet werden, um administrative Aufgaben auszuführen (z. B. zur Konfiguration der Datenbankverbindung) oder um eine wiederkehrende Aufgabe auszuführen (z. B. Konsolidierung von Tracking-Informationen).

Es gibt drei Typen von Adobe Campaign-Modulen:

* **Module mit mehreren Instanzen**: für alle Instanzen wird ein einzelner Prozess ausgeführt. Dies gilt für die folgenden Module: Web, syslogd, trackinglogd und watchdog.
* **Mono-Instanzmodule**: Pro Instanz wird ein Prozess ausgeführt. Dies gilt für die folgenden Module: mta, wfserver, inMail, sms und stat.
* **Dienstprogrammmodule**: Hierbei handelt es sich um Module, die gelegentlich ausgeführt werden, um gelegentliche oder wiederkehrende Vorgänge durchzuführen (Bereinigung, Konfiguration, Herunterladen von Trackinglogs usw.).

Die wichtigsten Prozesse sind:

**Anwendungsserver**  (nlserver web)

Dadurch wird die gesamte Bandbreite der Adobe Campaign-Funktionen über Web-Services-APIs (SOAP/HTTP + XML) verfügbar. Darüber hinaus kann es dynamisch die Webseiten generieren, die für den HTML-basierten Zugriff verwendet werden (Berichte, Webformulare usw.). Dazu umfasst dieser Prozess einen Apache Tomcat JSP-Server. Dies ist der Prozess, mit dem die Konsole eine Verbindung herstellt.

**Workflow-Engine**  (nlserver wfserver)

Er führt die in der Anwendung definierten Workflow-Prozesse aus.

Außerdem werden regelmäßig ausgeführte technische Workflows verarbeitet, darunter:

* **Tracking**: Wiederherstellen und Konsolidieren von Trackinglogs. Dadurch können Sie die Protokolle vom Weiterleitungsserver abrufen und die vom Berichtsmodul verwendeten Aggregat-Indikatoren erstellen.
* **Bereinigung**: Bereinigung der Datenbank. Wird verwendet, um alte Datensätze zu löschen und zu vermeiden, dass die Datenbank exponentiell wächst.
* **Rechnungsstellung**: Automatisches Senden eines Aktivitätsberichts für die Plattform (Datenbankgröße, Anzahl der Marketing-Aktionen usw.).

**Versandserver**  (nlserver mta)

Adobe Campaign verfügt über native E-Mail-Broadcast-Funktionen. Dieser Prozess fungiert als SMTP-Mail Transfer Agent (MTA). Es führt eine &quot;Eins-zu-Eins&quot;-Personalisierung von Nachrichten durch und verarbeitet deren physischen Versand. Sie wird mit Bereitstellungsaufträgen ausgeführt und verarbeitet automatische Neuversuche. Wenn die Verfolgung aktiviert ist, ersetzt sie außerdem automatisch die URLs, sodass sie auf den Weiterleitungsserver verweisen.

Dieser Prozess kann die Anpassung und den automatischen Versand von SMS, Fax und Briefpost an einen Drittanbieter-Router durchführen.

**Weiterleitungsserver**  (nlserver webmdl)

Bei E-Mails verarbeitet Adobe Campaign automatisch das Öffnungs- und Klick-Tracking (das Transaktions-Tracking auf Website-Ebene ist eine weitere Möglichkeit). Zu diesem Zweck werden die in die E-Mail-Nachrichten integrierten URLs umgeschrieben, um auf dieses Modul zu verweisen, das die Übergabe des Internetbenutzers registriert, bevor er sie an die gewünschte URL weiterleitet.

Um eine optimale Verfügbarkeit zu gewährleisten, ist dieser Prozess vollständig unabhängig von der Datenbank: die anderen Serverprozesse kommunizieren nur mit SOAP-Aufrufen (HTTP, HTTP(S) und XML) mit ihr. Technisch gesehen ist diese Funktion in einem Erweiterungsmodul eines HTTP-Servers (ISAPI-Erweiterung in IIS, DSO-Apache-Modul usw.) implementiert. und ist nur unter Windows verfügbar.

Weitere technische Prozesse sind ebenfalls verfügbar:

**Bounce Messages verwalten**  (nlserver inMail)

Auf diese Weise können Sie E-Mails aus Postfächern automatisch abrufen, die für den Empfang von nicht zugestellten Nachrichten konfiguriert sind, die im Falle eines fehlgeschlagenen Versands zurückgegeben werden. Diese Nachrichten werden dann regelbasiert verarbeitet, um die Gründe für die Nichtbereitstellung zu ermitteln (unbekannter Empfänger, Überschreitung der Quote usw.). und um den Versandstatus in der Datenbank zu aktualisieren.

Alle diese Vorgänge sind vollständig automatisch und vorkonfiguriert.

**SMS-Versandstatus**  (nlserver sms)

Dieser Prozess fragt den SMS-Router ab, um den Fortschrittsstatus zu erfassen und die Datenbank zu aktualisieren.

**Schreiben von Protokollmeldungen**  (nlserver syslogd)

Dieser technische Prozess erfasst Protokollmeldungen und von anderen Prozessen erzeugte Traces und schreibt sie auf die Festplatte. Dadurch werden bei Problemen umfangreiche Informationen zur Diagnose bereitgestellt.

**Schreiben von Trackinglogs**  (nlserver trackinglogd)

Dieser Prozess speichert die Trackinglogs, die durch den Weiterleitungsprozess generiert wurden.

**Schreiben eingehender Ereignisse**  (nlserver interaction)

Dieser Prozess stellt sicher, dass eingehende Ereignisse im Rahmen von Interaction auf der Festplatte aufgezeichnet werden.

**Überwachungsmodule**  (nlserver watchdog)

Dieser technische Prozess dient als primärer Prozess, der die anderen hervorbringt. Außerdem werden sie überwacht und bei Vorfällen automatisch neu gestartet, sodass die maximale Systembetriebsdauer beibehalten wird.

**Statistikserver**  (nlserver stat)

Dieser Prozess enthält Statistiken über die Anzahl der Verbindungen, die gesendeten Nachrichten für jeden E-Mail-Server, an den Nachrichten gesendet werden, sowie deren Einschränkungen (die höchste Anzahl gleichzeitiger Verbindungen, Nachrichten pro Stunde/ und Verbindung). Außerdem können Sie mehrere Instanzen oder Computer verbinden, wenn sie dieselben öffentlichen IP-Adressen verwenden.

## Datenbankcontainer {#db-containers}

Die Adobe Campaign Cloud-Datenbank basiert auf [!DNL Snowflake], die die funktionalen Daten (Profile, Abonnements, Inhalte usw.), die technischen Daten (Versandaufträge und Protokolle, Trackinglogs usw.) enthält. und die Arbeitsdaten (Käufe, Leads) für die Lösung sowie alle Adobe Campaign-Komponenten kommunizieren mit der Datenbank, um ihre spezifischen Aufgaben auszuführen.

Kunden können Adobe Campaign mithilfe der vordefinierten Datenbank und Schemata bereitstellen. Bei Bedarf kann diese vordefinierte Umgebung erweitert werden. Auf alle Daten im Datamart kann Adobe Campaign über SQL-Aufrufe zugreifen. Adobe Campaign bietet außerdem ein vollständiges Komplement der Tools zum Extract Transform and Load (ETL), mit denen Daten in das und aus dem System importiert und exportiert werden können.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Mit **Campaign Managed Cloud Services** wurden Ihre Umgebung und die Erstkonfiguration gemäß Ihren Lizenzbestimmungen von Adobe festgelegt. Sie dürfen keine installierten integrierten Packages, integrierten Schemata oder Berichte ändern.
>
>Wenn Sie ein Campaign-Add-on oder eine spezifische Funktion verwenden müssen, die Ihnen nicht zur Verfügung gestellt wurde, wenden Sie sich an die **Adobe-Kundenunterstützung**.
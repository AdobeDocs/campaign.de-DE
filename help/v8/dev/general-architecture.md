---
solution: Campaign v8
product: Adobe Campaign
title: Allgemeine Architektur
description: Campaign v8 – allgemeine Architektur
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 77%

---

# Allgemeine Architektur{#general-architecture}

Die typische Implementierung einer Adobe Campaign-Lösung setzt sich aus folgenden Komponenten zusammen:

* **Personalisierte Client-Umgebung**

   Eine intuitive grafische Benutzeroberfläche, über die neben der Kommunikation zu und dem Tracking von Marketing-Angeboten die Erstellung von Kampagnen möglich ist, sämtliche Marketing-Aktivitäten, -Programme und Pläne (einschließlich E-Mails, Workflows und Landingpages) geprüft und verwaltet werden können und zudem die Erstellung und Verwaltung von Kundenprofilen und Audiences durchgeführt werden kann.

* **Entwicklungsumgebung**

   Eine Server-seitige Software, die Marketing-Kampagnen über benutzerseitig ausgewählte Kommunikationskanäle ausführt, die von E-Mail, SMS und Push-Benachrichtigungen über Briefpost bis zu Web- und Social-Media-Kanälen reichen. In der Benutzeroberfläche werden dabei zugehörige Regeln und Workflows festgelegt.

* **Datenbank-Container**

   Basierend auf relationaler Datenbanktechnologie speichert die Adobe Campaign Cloud-Datenbank alle Kundeninformationen, Kampagnen, Angebote und Workflows sowie die Kampagne in Containern der Kundendatenbank.

## Personalisierte Client-Umgebung {#client-env}

Der Zugriff auf das Programm erfolgt auf unterschiedliche Weise: Richclient-, Thinclient- oder API-Integration.

* **Client Console**: Die Hauptbenutzeroberfläche des Programms ist ein natives Programm (unter Windows), das mit dem Adobe Campaign-Anwendungsserver mit Standardinternetprotokollen (SOAP, HTTP usw.) kommuniziert. Die Adobe Campaign-Client-Konsole bietet hohe Benutzerfreundlichkeit für hohe Produktivität, verbraucht sehr wenig Bandbreite (durch die Verwendung eines lokalen Cache) und wurde für eine einfache Implementierung entwickelt. Diese Konsole kann über einen Internetbrowser bereitgestellt werden, kann automatisch aktualisiert werden und erfordert keine spezifische Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic generiert.

   [!DNL :bulb:] [Erfahren Sie mehr über die Campaign-Client-Konsole](../start/connect.md).

* **Webzugriff**: auf Teile der Anwendung kann über einen einfachen Webbrowser über eine HTML-Benutzeroberfläche zugegriffen werden, einschließlich Berichterstellungsmodul, Versandvalidierungsphasen, Instanzüberwachung usw.

   [!DNL :bulb:] [Erfahren Sie mehr über den Web-basierten Zugriff auf Campaign](../start/connect.md).

* **Campaign-APIs**: In bestimmten Fällen kann das System über die via SOAP-Protokoll bereitgestellten Web-Services-API von einem externen Programm aus aufgerufen werden.

   [!DNL :bulb:] [Erfahren Sie mehr über Campaign-APIs](../dev/api.md).

## Entwicklungsumgebung {#dev-env}

Adobe Campaign ist eine Plattform mit verschiedenen Anwendungen, um eine offene und skalierbare Architektur zu erstellen. Die Adobe Campaign-Plattform basiert auf einer flexiblen Anwendungsebene, wodurch sie sich mühelos an verschiedenste Geschäftsanforderungen anpassen lässt. Dank der verteilten Architektur ist das System linear von mehreren Tausend auf mehrere Millionen Nachrichten skalierbar.

Einige Campaign-Module werden durchgängig ausgeführt, andere wiederum werden nur für bestimmte Aufgaben etwa administrativer Art (z. B. zum Konfigurieren der Datenbankverbindung) oder zur Ausführung wiederkehrender Operationen wie der Konsolidierung von Tracking-Informationen gestartet.

Es gibt drei Typen von Adobe Campaign-Modulen:

* **Module mit mehreren Instanzen**: für alle Instanzen wird ein einzelner Prozess ausgeführt. Dies gilt für die folgenden Module: web, syslogd, trackinglogd und watchdog.
* **Mono-Instanzmodule**: Pro Instanz wird ein Prozess ausgeführt. Dies gilt für die folgenden Module: mta, wfserver, inMail, sms und stat.
* **Dienstprogrammmodule**: Hierbei handelt es sich um Module, die gelegentlich ausgeführt werden, um gelegentliche oder wiederkehrende Vorgänge durchzuführen (Bereinigung, Konfiguration, Herunterladen von Trackinglogs usw.).

Dies sind die wichtigsten Prozesse:

**Anwendungs-Server** (nlserver web)

Dadurch wird die gesamte Bandbreite der Adobe Campaign-Funktionen über Web-Services-APIs (SOAP/HTTP + XML) verfügbar. Darüber hinaus kann er dynamisch die Web-Seiten generieren, die für den HTML-basierten Zugriff verwendet werden (Berichte, Web-Formulare usw.). Um dies zu ermöglichen, umfasst der Prozess einen Apache Tomcat JSP-Server. Dies ist der Prozess, an den die Konsole angebunden ist.

**Workflow-Engine** (nlserver wfserver)

Diese führt die im Programm definierten Workflow-Prozesse aus.

Außerdem verarbeitet sie zeitweise ausgeführte technische Workflows, darunter:

* **Tracking**: Wiederherstellen und Konsolidieren von Trackinglogs. Dadurch können Protokolle vom Weiterleitungs-Server abgerufen und die vom Reporting-Modul verwendeten aggregierten Indikatoren erstellt werden.
* **Bereinigung**: Bereinigung der Datenbank. Dabei wird die Datenbank von alten Datensätzen bereinigt, um zu vermeiden, dass sie übermäßig wächst.
* **Rechnungsstellung**: Automatisches Senden eines Aktivitätsberichts für die Plattform (Datenbankgröße, Anzahl der Marketing-Aktionen usw.).

**Versand-Server** (nlserver mta)

Adobe Campaign umfasst eine native Funktion zum Senden von E-Mails. Dieser Prozess fungiert als SMTP Mail Transfer Agent (MTA). Er personalisiert Nachrichten individuell für den jeweiligen Empfänger und verarbeitet deren physischen Versand. Sie wird mit Bereitstellungsaufträgen ausgeführt und verarbeitet automatische Neuversuche. Ist zusätzlich noch Tracking aktiviert, werden die URLs automatisch ersetzt, sodass sie auf den Weiterleitungs-Server verweisen.

Über diesen Prozess ist die Anpassung sowie der automatische Versand an einen Dritt-Router für SMS, Fax und Briefpost möglich.

**Weiterleitungs-Server** (nlserver webmdl)

Bei E-Mails übernimmt Adobe Campaign automatisch das Öffnungs- und Klick-Tracking (wobei das Tracking von Transaktionen auf Website-Ebene ebenfalls möglich ist). Hierfür werden die in den E-Mail-Nachrichten enthaltenen URLs so umgeschrieben, dass sie auf dieses Modul verweisen. Dieses wiederum registriert Internet-Benutzer, während diese an die Ziel-URL weitergeleitet werden.

Zur Sicherstellung maximaler Verfügbarkeit ist dieser Prozess vollkommen unabhängig von der Datenbank: Die anderen Server-Prozesse kommunizieren mit ihm nur über SOAP-Aufrufe (HTTP, HTTPS und XML). Aus technischer Sicht ist diese Funktion in einem Erweiterungsmodul (ISAPI-Erweiterung in IIS, DSO Apache-Modul usw.) eines HTTP-Servers implementiert und nur unter Windows verfügbar.

Daneben sind auch noch weitere technische Prozesse verfügbar:

**Handhabung von Bounce-E-Mails** (nlserver inMail)

Dieser Prozess ermöglicht den automatischen Abruf von E-Mails aus Postfächern, die für den Empfang von Nachrichten konfiguriert sind, die bei fehlgeschlagenem Versand als unzustellbar zurückgesendet werden. Diese Nachrichten werden dann regelbasiert verarbeitet, um die Gründe für die Unzustellbarkeit (z. B. Empfänger unbekannt, Nachrichtenkontingente ausgeschöpft) zu ermitteln und den Versandstatus in der Datenbank zu aktualisieren.

Alle diese Operationen laufen vollkommen automatisch und sind vorkonfiguriert.

**Status des SMS-Versands** (nlserver sms)

Dieser Prozess fragt beim SMS-Router den Status des Versandfortschritts ab und aktualisiert diesen in der Datenbank.

**Schreiben von Log-Nachrichten** (nlserver-syslogd)

Dieser technische Prozess erfasst von anderen Prozessen generierte Log-Nachrichten und -Traces und speichert sie auf der Festplatte. Dadurch stehen im Falle von Problemen umfangreiche Informationen zur Diagnose zur Verfügung.

**Schreiben von Trackinglogs** (nlserver trackinglogd)

Dieser Prozess speichert die Trackinglogs, die durch vom Weiterleitungsprozess generiert werden.

**Schreiben eingehender Ereignisse** (nlserver interactiond)

Dieser Vorgang gewährleistet die Aufzeichnung von im Rahmen der Interaktion eingehenden Ereignisse auf der Festplatte

**Überwachungsmodule** (nlserver watchdog)

Hierbei handelt es sich um einen technischen Primärprozess, der zur Erzeugung der anderen Prozesse dient. Zugleich überwacht er diese aber auch startet sie beim Auftreten von Vorfällen automatisch neu, sodass maximale Systemverfügbarkeit gewährleistet bleibt.

**Statistik-Server** (nlserver stat)

Dieser Prozess erstellt Statistiken zur Anzahl von Verbindungen, zu an die einzelnen Mailserver gesendeten Nachrichten und zu deren Einschränkungen (z. B. Maximalzahl gleichzeitiger Verbindungen, Nachrichten pro Stunde und/oder Verbindung usw.). Ebenfalls lassen sich über diesen Prozess Instanzen oder Computer zusammenführen, sofern diese dieselben öffentlichen IP-Adressen verwenden.

## Datenbank-Container {#db-containers}

Die Cloud-Datenbank von Adobe Campaign nutzt [!DNL Snowflake], wo die funktionellen Daten (Profile, Abonnements, Inhalte usw.), die technischen Daten (Versand, Aufträge und Protokolle, Trackinglogs usw.) und die Arbeitsdaten (Bestellungen, Interessenten) für die Lösung abgelegt sind. Alle Komponenten von Adobe Campaign kommunizieren mit der Datenbank, um ihre spezifischen Aufgaben auszuführen.

Kunden können Adobe Campaign mithilfe der vordefinierten Datenbank und Schemata bereitstellen. Bei Bedarf kann diese vordefinierte Umgebung erweitert werden. Der Zugriff auf alle Daten im Datamart durch Adobe Campaign erfolgt über SQL-Aufrufe. Adobe Campaign bietet außerdem eine vollständige Ergänzung der ETL-Tools (Extract, Transform, Load – Extrahieren, Umwandeln, Laden), mittels derer Daten in das und aus dem System importiert und exportiert werden können.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Mit **Campaign Managed Cloud Services** wurden Ihre Umgebung und die Erstkonfiguration gemäß Ihren Lizenzbestimmungen von Adobe festgelegt. Sie dürfen keine installierten integrierten Packages, integrierten Schemata oder Berichte ändern.
>
>Wenn Sie ein Campaign-Add-on oder eine spezifische Funktion verwenden müssen, die Ihnen nicht zur Verfügung gestellt wurde, wenden Sie sich an die **Adobe-Kundenunterstützung**.
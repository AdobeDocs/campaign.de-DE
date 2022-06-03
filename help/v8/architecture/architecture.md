---
title: Erste Schritte mit der Campaign-Architektur
description: Grundlagen zu Umgebungen und zur Bereitstellung
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: ht
source-wordcount: '606'
ht-degree: 100%

---

# Erste Schritte mit der Campaign-Architektur{#gs-ac-archi}

## Umgebungen {#environments}

Campaign wird in Form einzelner Instanzen bereitgestellt, wobei jede Instanz eine komplette Campaign-Umgebung darstellt.

Mit Campaign Cloud Service stehen zwei Umgebungstypen zur Verfügung:

* **Produktionsumgebung**: hostet die Programme für die diversen Fachleute.

* **Staging-Umgebung**: wird für verschiedene Leistungs- und Qualitätstests verwendet, bevor Änderungen am Programm in die Produktionsumgebung übertragen werden.

Sie können Packages von einer Umgebung in eine andere exportieren und importieren.

![](../assets/do-not-localize/book.png) Weitere Informationen über Packages in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=de)

## Implementierungsmodell{#ac-deployment}

In seiner [Enterprise (FFDA)-Implementierung](enterprise-deployment.md) kann [!DNL Adobe Campaign] v8 mit zwei Datenbanken verwendet werden: einer lokalen [!DNL Campaign]-Datenbank für Echtzeit-Messaging und Einzelabfragen und das Schreiben über APIs sowie einer Cloud-[!DNL Snowflake]-Datenbank für die Kampagnenausführung, für Batch-Abfragen und die Workflow-Ausführung.

Campaign v8 Enterprise bietet das Konzept des **Full Federated Data Access** (FFDA): Alle Daten befinden sich nun entfernt in der Cloud-Datenbank. Mit dieser neuen Architektur vereinfacht die Campaign v8 Enterprise (FFDA)-Implementierung die Datenverwaltung: Es wird kein Index in der Cloud-Datenbank benötigt. Sie müssen nur die Tabellen erstellen, die Daten kopieren und schon können Sie loslegen. Die Cloud-Datenbanktechnologie erfordert keine spezielle Wartung, um das Leistungsniveau zu gewährleisten.



<!--Two deployment models are available:

* **Campaign FDA [!DNL Snowflake] deployment**

In its [[!DNL Snowflake] FDA deployment](fda-deployment.md), [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through Federated Data Access capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

* **Campaign Enterprise (FFDA) deployment**

-->

## Message Center-Architektur{#transac-msg-archi}

Das Campaign-Modul &quot;Transaktionsnachricht (Message Center)&quot; wurde zum Verwalten von Trigger-Nachrichten entwickelt.

![](../assets/do-not-localize/glass.png) In [diesem Abschnitt](../send/transactional.md) erfahren Sie, wie Sie Transaktionsnachrichten senden können.

Als Reaktion auf eine Kundenaktion auf einer Website wird ein Ereignis über eine REST-API gesendet. Die Nachrichtenvorlage wird mit den Informationen oder Daten gefüllt, die über den API-Aufruf bereitgestellt werden, und eine Transaktionsnachricht wird in Echtzeit an den Kunden gesendet. Diese Nachrichten können einzeln oder in Batches per E-Mail, SMS oder Push-Benachrichtigungen gesendet werden.

In der hier angewendeten Architektur sind Ausführungszelle und Kontrollinstanz voneinander getrennt, was höhere Verfügbarkeit und besseres Last-Management gewährleistet.

* Die **Kontrollinstanz** (oder die Marketing-Instanz) wird von Marketing-Experten und IT-Teams zum Erstellen, Konfigurieren und Veröffentlichen von Nachrichtenvorlagen verwendet. Diese Instanz zentralisiert auch die Überwachung und den Verlauf von Ereignissen.

   ![](../assets/do-not-localize/glass.png) Erfahren Sie in [diesem Abschnitt](../send/transactional.md), wie Sie Nachrichtenvorlagen erstellen und veröffentlichen.

* Die **Ausführungsinstanz** ruft eingehende Ereignisse (z. B. Passwortrücksetzung oder Bestellungen von einer Website) ab und versendet personalisierte Nachrichten. Es kann mehr als eine Ausführungsinstanz geben, um Nachrichten über den Load-Balancer zu verarbeiten und die Anzahl der zu verarbeitenden Ereignisse zwecks maximaler Verfügbarkeit zu skalieren.

>[!CAUTION]
>
>Die Kontroll- und die Ausführungsinstanz(en) müssen auf unterschiedlichen Computern installiert werden. Sie können aber nicht auf derselben Campaign-Instanz ausgeführt werden.

![](assets/messagecenter_diagram.png)

### Authentifizierung

Um diese Funktionen zu nutzen, können Benutzer von Adobe Campaign in der Kontrollinstanz Vorlagen für Transaktionsnachrichten erstellen, eine Nachrichtenvorschau mithilfe einer Testadresse erzeugen, Berichte anzeigen und Ausführungsinstanzen überwachen.

* Einzelne Ausführungsinstanz
Bei der Interaktion mit einer gehosteten Message Center-Ausführungsinstanz kann ein externes System zunächst ein Sitzungs-Token abrufen (das standardmäßig nach 24 Stunden abläuft), indem ein API-Aufruf an die Sitzungs-Anmeldemethode unter Verwendung eines bereitgestellten Kontoanmeldenamens und eines Passworts erfolgt.
Dann kann die externe Anwendung mit dem von der Ausführungsinstanz als Antwort auf den obigen Aufruf bereitgestellten Sitzungs-Token SOAP-API-Aufrufe (rtEvents oder batchEvents) ausführen, um Nachrichten zu senden, ohne dass in jedem SOAP-Aufruf der Kontoanmeldename und das Passwort enthalten sein müssen.

* Mehrere Ausführungsinstanzen
In einer mehrzelligen Ausführungsarchitektur mit mehreren Ausführungsinstanzen hinter einem Load-Balancer durchläuft die vom externen Programm aufgerufene Anmeldemethode den Load-Balancer: Aus diesem Grund kann keine Token-basierte Authentifizierung verwendet werden. Eine Benutzer-/Passwortbasierte Authentifizierung ist erforderlich.

![](../assets/do-not-localize/book.png) Weitere Informationen über Transaktionsnachrichten-Ereignisse in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html?lang=de#about-transactional-messaging-datamodel)

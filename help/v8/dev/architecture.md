---
product: Adobe Campaign
title: Erste Schritte mit der Campaign-Architektur
description: Erste Schritte mit der Campaign-Architektur
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 83%

---

# Erste Schritte mit der Campaign-Architektur{#gs-ac-archi}

## Umgebungen

Campaign wird in Form einzelner Instanzen bereitgestellt, wobei jede Instanz eine komplette Campaign-Umgebung darstellt.

Mit Campaign Cloud Service stehen drei Umgebungstypen zur Verfügung:

* **Produktionsumgebung**: hostet die Anwendungen für Geschäftsleute.

* **Staging-Umgebung**: wird für verschiedene Leistungs- und Qualitätstests verwendet, bevor Änderungen an der Anwendung in die Produktionsumgebung übertragen werden.

* **Entwicklungsumgebung**: ermöglicht es Entwicklern, Campaign unter denselben Laufzeitbedingungen wie die Staging- und Produktionsumgebungen zu implementieren.

Sie können Packages von einer Umgebung in eine andere exportieren und importieren.

[!DNL :arrow_upper_right:] Weitere Informationen zu Paketen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Mid-Sourcing-Implementierung{#mid-sourcing-deployment}

Die allgemeine Kommunikation zwischen Servern und Prozessen erfolgt gemäß dem folgenden Schema:

![](assets/architecture.png)

* Die Ausführungs- und Bounce-Management-Module sind in der Instanz deaktiviert.

* Das Programm ist so konfiguriert, dass Nachrichten auf einem entfernten &quot;Mid-Sourced&quot;-Server ausgeführt werden, der über SOAP-Aufrufe (über HTTP oder HTTPS) gesteuert wird.

>[!NOTE]
>
> Campaign v8 basiert auf einer Hybridarchitektur. Wenn Sie von Campaign Classic v7 wechseln, beachten Sie, dass alle Sendungen den Mid-Sourcing-Server durchlaufen.
> Infolgedessen ist internes Routing in Campaign v8 **nicht möglich** und das externe Konto wurde entsprechend deaktiviert.

## Message Center-Architektur{#transac-msg-archi}

Transaktionsnachricht (Message Center) ist das Campaign-Modul, das zum Verwalten von Trigger-Nachrichten entwickelt wurde.

[!DNL :bulb:] In [diesem Abschnitt](../send/transactional.md) erfahren Sie, wie Sie Transaktionsnachrichten senden können.

Als Reaktion auf eine Kundenaktion auf einer Website wird ein Ereignis über eine REST-API gesendet. Die Nachrichtenvorlage wird mit den Informationen oder Daten gefüllt, die über den API-Aufruf bereitgestellt werden, und eine Transaktionsnachricht wird in Echtzeit an den Kunden gesendet. Diese Nachrichten können einzeln oder in Batches per E-Mail, SMS oder Push-Benachrichtigungen gesendet werden.

In der hier angewendeten Architektur sind Ausführungszelle und Kontrollinstanz voneinander getrennt, was höhere Verfügbarkeit und besseres Last-Management gewährleistet.

* Die **Kontrollinstanz** (oder die Marketing-Instanz) wird von Marketing-Experten und IT-Teams zum Erstellen, Konfigurieren und Veröffentlichen von Nachrichtenvorlagen verwendet. Diese Instanz zentralisiert auch die Überwachung und den Verlauf von Ereignissen.

   [!DNL :bulb:] In  [diesem Abschnitt](../send/transactional.md) erfahren Sie, wie Sie Nachrichtenvorlagen erstellen und veröffentlichen.

* Die **Ausführungsinstanz** ruft eingehende Ereignisse (z. B. Passwortrücksetzung oder Bestellungen von einer Website) ab und versendet personalisierte Nachrichten. Es kann mehr als eine Ausführungsinstanz geben, um Nachrichten über den Load-Balancer zu verarbeiten und die Anzahl der zu verarbeitenden Ereignisse zwecks maximaler Verfügbarkeit zu skalieren.

>[!CAUTION]
>
>Die Kontroll- und die Ausführungsinstanz(en) müssen auf unterschiedlichen Computern installiert werden. Sie können aber nicht auf derselben Campaign-Instanz ausgeführt werden.

![](assets/messagecenter_diagram.png)

[!DNL :arrow_upper_right:] Die Message-Center-Architektur wird in der Dokumentation zu  [Campaign Classic v7 beschrieben.](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=de#transactional-messaging)

### Authentifizierung

Um diese Funktionen zu nutzen, können Benutzer von Adobe Campaign in der Kontrollinstanz Vorlagen für Transaktionsnachrichten erstellen, eine Nachrichtenvorschau mithilfe einer Testadresse erzeugen, Berichte anzeigen und Ausführungsinstanzen überwachen.

* Einzelne Ausführungsinstanz
Bei der Interaktion mit einer gehosteten Message Center-Ausführungsinstanz kann ein externes System zunächst ein Sitzungs-Token abrufen (das standardmäßig nach 24 Stunden abläuft), indem ein API-Aufruf an die Sitzungs-Anmeldemethode unter Verwendung eines bereitgestellten Kontoanmeldenamens und eines Passworts erfolgt.
Dann kann die externe Anwendung mit dem von der Ausführungsinstanz als Antwort auf den obigen Aufruf bereitgestellten Sitzungs-Token SOAP-API-Aufrufe (rtEvents oder batchEvents) ausführen, um Nachrichten zu senden, ohne dass in jedem SOAP-Aufruf der Kontoanmeldename und das Passwort enthalten sein müssen.

* Mehrere Ausführungsinstanzen
In einer mehrzelligen Ausführungsarchitektur mit mehreren Ausführungsinstanzen hinter einem Load-Balancer durchläuft die vom externen Programm aufgerufene Anmeldemethode den Load-Balancer: Aus diesem Grund kann keine Token-basierte Authentifizierung verwendet werden. Eine Benutzer-/Passwortbasierte Authentifizierung ist erforderlich.

[!DNL :arrow_upper_right:] Weitere Informationen zu Transaktionsnachrichten-Ereignissen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)
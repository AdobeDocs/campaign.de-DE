---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit der Kampagne
description: Erste Schritte mit der Kampagne
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 3%

---

# Erste Schritte mit Kampagne{#gs-ac-archi}

## Umgebung

Kampagne wird als einzelne Instanzen bereitgestellt, wobei jede Instanz eine vollständige Kampagne-Umgebung darstellt.

Für Kampagne Cloud Service stehen drei Typen von Umgebung zur Verfügung:

* Umgebung der Produktion: die Anwendungen für die Geschäftspraktiker.

* Umgebung der Stufe: für verschiedene Leistungs- und Qualitätstests verwendet werden, bevor Änderungen an der Umgebung an die Produktion gesendet werden.

* Umgebung der Entwicklung: ermöglicht Entwicklern die Implementierung von Kampagne unter denselben Laufzeitbedingungen wie die Umgebung für die Phase und Produktion.

Sie können Pakete von einer Umgebung in eine andere exportieren und importieren.

:arrow_upper_right: Weitere Informationen zu Paketen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=en#about-data-packages)

## Mid-Sourcing-Bereitstellung{#mid-sourcing-deployment}

Die allgemeine Kommunikation zwischen Servern und Prozessen erfolgt gemäß dem folgenden Schema:

![](assets/architecture.png)

* Die Management-Module für Ausführung und Absprung sind in der Instanz deaktiviert.

* Die Anwendung ist so konfiguriert, dass eine Nachrichtenausführung auf einem Remote-Server mit mittlerer Quelle durchgeführt wird, der mit SOAP-Aufrufen (über HTTP oder HTTPS) angetrieben wird.

>[!NOTE]
>
> Kampagne v8 basiert auf einer Hybridarchitektur. Wenn Sie von Campaign Classic v7 wechseln, beachten Sie, dass alle Versand den Mid-Sourcing-Server durchlaufen.
> Infolgedessen ist internes Routing in Kampagne v8 **nicht möglich** und das Externe Konto wurde entsprechend deaktiviert.


## Message Center-Architektur{#transac-msg-archi}

Transactional Messaging (Message Center) ist das Kampagne-Modul, das zum Verwalten von Trigger-Nachrichten entwickelt wurde.

:bulb: Erfahren Sie, wie Sie Transaktionsnachrichten senden können, unter [dieser Abschnitt](../send/transactional.md).

Als Reaktion auf eine Kundenaktion auf einer Website wird ein Ereignis über eine REST-API gesendet. Die Nachrichtenvorlage wird mit den Informationen oder Daten gefüllt, die über den API-Aufruf bereitgestellt werden, und eine Transaktionsnachricht wird in Echtzeit an den Kunden gesendet. Diese Nachrichten können einzeln oder in Stapeln per E-Mail, SMS oder Push-Benachrichtigungen gesendet werden.

In dieser speziellen Architektur wird die Ausführungszelle von der Kontrollinstanz getrennt, um eine hohe Verfügbarkeit und ein hohes Lastmanagement sicherzustellen.

* Die **Kontrollinstanz** (oder die Marketing-Instanz) wird von Marketingexperten und IT-Teams zum Erstellen, Konfigurieren und Veröffentlichen von Nachrichtenvorlagen verwendet. Diese Instanz zentralisiert auch die Überwachung und den Verlauf von Ereignissen.

   :arrow_upper_right: Informationen zum Erstellen und Veröffentlichen von Nachrichtenvorlagen in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/introduction.html?lang=en#transactional-messaging)

* Die **Ausführungsinstanz** ruft eingehende Ereignis zurück (z. B. Passwortzurücksetzung oder Bestellungen von einer Website) und sendet personalisierte Nachrichten. Es kann mehr als eine Ausführungsinstanz geben, Nachrichten über den Lastenausgleich zu verarbeiten und die Anzahl der Ereignis zu skalieren, die für eine maximale Verfügbarkeit ausgeführt werden.

>[!CAUTION]
>
>Die Kontroll- und die Ausführungsinstanz(en) müssen auf unterschiedlichen Computern installiert werden. Sie können aber nicht auf derselben Campaign-Instanz ausgeführt werden.

![](assets/messagecenter_diagram.png)

:arrow_upper_right: Die Message Center-Architektur wird in [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging) beschrieben.


### Authentifizierung

Um diese Funktionen zu nutzen, melden sich Adobe Campaign-Benutzer bei der Kontrollinstanz an, um Transaktionsnachrichtenvorlagen zu erstellen, die Vorschau mit einer Seed-Liste zu erstellen, Berichte anzuzeigen und Ausführungsinstanzen zu überwachen.

* Einzelne Ausführungsinstanz
Bei der Interaktion mit einer gehosteten Message Center-Ausführungsinstanz kann ein externes System zunächst ein Sitzungs-Token abrufen (das standardmäßig nach 24 Stunden abläuft), indem ein API-Aufruf an die Sitzungs-Anmeldemethode unter Verwendung einer angegebenen Kontoanmeldung und eines Kennworts erfolgt.
Wenn die externe Anwendung dann das sessionToken bereitstellt, das von der Ausführungsinstanz als Antwort auf den oben genannten Aufruf bereitgestellt wird, kann sie SOAP-API-Aufrufe (rtEvents oder batchEvents) zum Senden von Nachrichten durchführen, ohne dass die Kontoanmeldung und das Kennwort in jedem SOAP-Aufruf einbezogen werden müssen.

* Mehrere Ausführungsinstanzen
In einer Mehrzellenausführungsarchitektur mit mehreren Ausführungsinstanzen hinter einem Lastenausgleich durchläuft die von der externen Anwendung aufgerufene Anmeldemethode den Lastenausgleich: Aus diesem Grund kann keine Token-basierte Authentifizierung verwendet werden. Eine Benutzer-/Kennwortbasierte Authentifizierung ist erforderlich.

:arrow_upper_right: Weitere Informationen zu Transaktionsnachrichten-Ereignissen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)
---
title: Erste Schritte mit Nachrichten
description: Erste Schritte mit Nachrichten
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: fb0b7dbeae1d083935da91bbe50a711ce5f47b7e
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 66%

---

# Erste Schritte mit Nachrichten{#gs-ac-audiences}

Mit Adobe Campaign können Sie Cross-Channel-Kampagnen wie E-Mails, SMS, Push-Benachrichtigungen und Briefpost senden und deren Effektivität mithilfe verschiedener dedizierter Berichte messen. Diese Nachrichten werden mittels Sendungen entworfen und gesendet und können für jeden Empfänger personalisiert werden.

Zu den Kernfunktionen zählen Zielgruppenbestimmung, Definition und Personalisierung von Nachrichten, Ausführung der Kommunikation und die damit verbundenen operativen Berichte. Der wichtigste funktionale Zugangspunkt ist der Versandassistent. Dieser Zugriffspunkt führt zu mehreren Funktionen, die von Adobe Campaign abgedeckt werden.

Adobe Campaign v8 enthält die folgenden Versandkanäle:

* **E-Mail-Kanal**: Ein E-Mail-Versand richtet personalisierte elektronische Nachrichten an eine zuvor bestimmte Zielpopulation. [Weitere Informationen](#gs-channel-email)

* **Mobile Kanäle**: Ein Versand über Mobile-Kanäle ermöglicht den Versand personalisierter Nachrichten auf Mobilgeräten an die Zielpopulation. [Weitere Informationen](#gs-channel-sms)

* **Mobile-App-Kanal**: Mit Mobile-App-Sendungen können Sie Benachrichtigungen an iOS- und Android-Geräte senden. [Weitere Informationen](#gs-channel-push)

* **Briefpost-Kanal**: Ein Briefpost-Versand erzeugt eine Ausgabedatei, die die Daten der Zielpopulation enthält. [Weitere Informationen](#gs-channel-direct)


  Weitere Kanäle werden beschrieben unter [diesem Abschnitt](#other-channels).

  >[!NOTE]
  >
  >Die Anzahl der verfügbaren Kanäle hängt von Ihrem Vertrag ab. Prüfen Sie diesbezüglich Ihren Lizenzvertrag.

## Kanal auswählen{#gs-channel}

### E-Mail-Kanal {#gs-channel-email}

Der [E-Mail-Kanal](../send/direct-mail.md) ist einer der wichtigsten Kanäle in Adobe Campaign. Damit können Sie den Versand von personalisierten E-Mails an bestimmte Zielgruppen planen und durchführen.

Verschiedene Typen von E-Mails können gesendet werden:

* Einmalige E-Mails: E-Mails, die ein einziges Mal an eine definierte Zielgruppe gesendet werden. Sie werden zur Verbreitung spezifischer Inhalte verwendet, die nur ein einziges Mal vorbereitet und gesendet werden (Newsletter, Werbe-E-Mails etc.).
* Wiederkehrende E-Mails: In einer Kampagne wird regelmäßig dieselbe E-Mail gesendet und jeder Versand und seine Berichte werden regelmäßig aggregiert. Dieselbe E-Mail wird gesendet, in der Regel aber an eine andere Zielgruppe, basierend auf der für den Versandtag infrage kommenden Zielgruppe. Ein häufiges Beispiel ist eine Geburtstags-E-Mail. Weitere Informationen hierzu finden Sie unter [Wiederkehrende Sendungen](../../automation/workflow/recurring-delivery.md).
* Transaktions-E-Mails: einzelne E-Mails, die auf der Basis des Kundenverhaltens ausgelöst werden. Siehe auch [Transaktionsnachrichten](../send/transactional.md).

Weitere Informationen zur Verwendung von Sendungen und Empfehlungen finden Sie unter Adobe Campaign Classic . [Best Practices beim Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=de#sending-messages){target="_blank"}

Weiterführende Informationen zu den unterschiedlichen Versandarten finden Sie in [diesem Abschnitt](#types-of-deliveries).

### Mobile-Kanal {#gs-channel-sms}

Adobe Campaign ermöglicht den Versand von Nachrichten per [SMS](../send/sms.md) und [LINE](../send/line.md) auf Mobiltelefone.

Die Inhalt-Kachel von SMS bietet ebenfalls die Möglichkeit der Erstellung, Anpassung und Personalisierung von Nachrichteninhalten, jedoch ausschließlich im Textformat. Es ist außerdem möglich, vor dem Versand eine Vorschau der SMS zu erzeugen.

LINE-Nachrichten können Text, Bilder und Links enthalten.

Folgende Voraussetzungen müssen gegeben sein, um SMS- oder LINE-Nachrichten an Mobiltelefone zu senden:

* Ein externes Konto, das für den Kanal **[!UICONTROL Mobiltelefon (SMS)]** oder **[!UICONTROL LINE]** konfiguriert wurde.
* Eine SMS- oder LINE-Versandvorlage, die auf das externe Konto Bezug nimmt.


### Push-Benachrichtigungs-Kanal {#gs-channel-push}

Mit Adobe Campaign können Sie personalisierte und segmentierte Nachrichten senden [Push-Benachrichtigungen](../send/push.md) auf mobilen iOS- und Android-Geräten über dedizierte Apps. Nachdem die Konfigurations- und Integrationsschritte ausgeführt wurden, können iOS- und Android-Sendungen erstellt und mit Adobe Campaign gesendet werden. Sie können auch Rich-Benachrichtigungen mit Bildern oder Videos erstellen und an Android-Geräte senden.

### Briefpost-Kanal {#gs-channel-direct}

[Briefpost](../send/direct-mail.md) ist ein Offline-Kanal, mit dem Sie eine externe Datei erstellen, personalisieren und generieren können, die für Ihre Briefpost-Dienstleister freigegeben werden kann. Verwenden Sie diesen Kanal, um Online- und Offline-Kanäle in Ihren Journey zu orchestrieren.

Wenn Sie einen Briefpost-Versand vorbereiten, erzeugt Adobe Campaign eine Datei, die alle Zielgruppenprofile und die ausgewählte Kontaktinformationen enthält (z. B. Postanschrift). Sie können diese Datei dann an Ihren Briefpost-Dienstleister senden, der sich um den tatsächlichen Versand kümmert.


### Sonstige Kanäle {#other-channels}

Adobe Campaign verfügt außerdem über eine Vorlage für den Telefonversand, mit der externe Sendungen erstellt werden können. Die Verwendung dieses Kanals setzt voraus, dass Sie dedizierte Methoden zur Verarbeitung von Ausgabedateien implementieren. Die Konfigurationsschritte sind mit denen des [Brief-Kanals](../send/direct-mail.md) identisch.

>[!NOTE]
>
>Der Telefonkanal ist kein integrierter Kanal. Seine Implementierung erfordert die Einbindung von Adobe Consulting oder einem Adobe-Partner. Wenden Sie sich für weitere Informationen an Ihren Adobe-Support-Mitarbeiter.

Sendungen vom Typ &quot;Sonstige&quot; verwenden eine spezifische technische Vorlage, die keinen Vorgang ausführt. Auf diese Weise können außerhalb der Adobe Campaign-Plattform ausgeführte Marketing-Aktionen verwaltet werden.

Dieser Kanal besitzt keinen bestimmten Mechanismus. Es handelt sich dabei um einen generischen Kanal mit einer eigenen externen Konto-Routing-Option, einem Versandvorlagentyp und einer Kampagnen-Workflow-Aktivität, genau wie bei jedem anderen Kommunikationskanal, der in Adobe Campaign verfügbar ist. Dieser Kanal ist nur für informative Zwecke konzipiert, wie etwa um Zielgruppeninformationen zu mit externen Tools durchgeführten Kampagnen zu speichern.

## Versandtyp auswählen {#types-of-deliveries}

In Campaign gibt es drei Typen von Versandobjekten:

### Einzelversand {#single-delivery}

Ein **Versand** ist ein unabhängiges Versandobjekt, das ein einziges Mal ausgeführt wird. Es kann dupliziert und nochmals vorbereitet werden, doch sobald es in seinem finalen Zustand ist (abgebrochen, gestoppt, fertiggestellt), kann es nicht wiederverwendet werden.

Sendungen können entweder in der Versandliste oder innerhalb eines Workflows über die Aktivität [Versand](../../automation/workflow/delivery.md) erstellt werden.

Workflows bieten abhängig vom zu verwendeten Kanal auch spezifische Versandaktivitäten. Weiterführende Informationen zu diesen Aktivitäten erhalten Sie in [diesem Abschnitt](../../automation/workflow/cross-channel-deliveries.md).

### Wiederkehrender Versand {#recurring-delivery}

A **Wiederkehrender Versand** ist im Kontext eines Workflows verfügbar. Damit können Sie bei jeder Ausführung der Aktivität einen neuen Versand erstellen. Auf diese Weise wird vermieden, dass Sie einen neuen Versand für wiederkehrende Aufgaben erstellen müssen. Wenn Sie diese Aktivität beispielsweise einmal im Monat ausführen, ergibt das im Jahr 12 Sendungen.

Wiederkehrende Sendungen werden über Workflows mit der Aktivität [](../../automation/workflow/recurring-delivery.md)Wiederkehrender Versand erstellt. Ein Beispiel für diese Aktivität finden Sie in diesem Abschnitt: [Erstellen eines wiederkehrenden Versands in einem Zielgruppen-Workflow](../../automation/workflow/send-a-birthday-email.md).

### Versand (fortlaufend) {#continuous-delivery}

A **kontinuierliche Bereitstellung** ist im Kontext eines Workflows verfügbar. Damit können Sie einem bestehenden Versand neue Empfänger hinzufügen, sodass Sie nicht jedes Mal einen neuen Versand erstellen müssen.

Wenn sich Daten im Versand ändern (Inhalt, Name etc.), wird bei der Ausführung des Versands ein neues Versandobjekt erstellt. Wenn keine Daten geändert wurden, wird dasselbe Versandobjekt erneut verwendet und die Versand- und Trackinglogs werden im selben Objekt hinzugefügt.

Wenn Sie diese Aktivität beispielsweise einmal im Monat ausführen, ergibt das eine einzige Sendung im Jahr (vorausgesetzt Sie haben am Versand keine Änderung vorgenommen).

Fortlaufende Sendungen werden in Workflows über die Aktivität [Versand (fortlaufend)](../../automation/workflow/continuous-delivery.md) erstellt.


## Auswahl der Versandart für Ihre Nachrichten{#gs-send-msg}

Sobald Ihre Nachricht erstellt und ihr Inhalt entworfen und getestet wurde, können Sie wählen, wie Sie sie versenden möchten. Campaign bietet eine Reihe von Funktionen, um:

* Manuelles Senden von Nachrichten an die Hauptzielgruppe

  ![](assets/send-email.png)

  In [diesem Abschnitt](../send/send.md) erfahren Sie, wie Sie Nachrichten senden können

* Senden von Nachrichten, die einer [Marketing-Kampagne](campaigns.md) zugeordnet sind

  ![](assets/deliveries-in-a-campaign.png)

  In [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=de){target="_blank"} erfahren Sie, wie Sie Nachrichten im Rahmen einer Kampagne versenden.

* Senden von Nachrichten über einen [Workflow](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

   Auf [dieser Seite](../../automation/workflow/delivery.md) erfahren Sie, wie Sie einen E-Mail-Versand automatisieren können

* [Auslösen von Nachrichten](../send/transactional.md) durch ein Ereignis

  Das Campaign-Modul &quot;Transaktionsnachricht (Message Center)&quot; wurde zum Verwalten von Trigger-Nachrichten entwickelt.

  Weitere Informationen zur Funktion für Transaktionsnachrichten finden Sie in [diesem Abschnitt](../architecture/architecture.md#transac-msg-archi).

  Die Schritte zum Konfigurieren und Senden von Transaktionsnachrichten werden auf [dieser Seite](../send/transactional.md) ausführlich beschrieben.

* Planen von Nachrichten

  ![](assets/schedule-send.png)

  Informationen zum Planen des Versands Ihrer Sendungen finden Sie unter [diese Seite](../send/configure-and-send.md)

  Siehe auch [Anwendungsfall: Erfahren Sie, wie Sie eine Geburtstags-E-Mail planen und senden.](../../automation/workflow/send-a-birthday-email.md)


## Hinzufügen von Personalisierung{#personalization}

Nachrichten, die von Adobe Campaign versendet werden, können auf verschiedene Weise personalisiert werden. [Weitere Informationen zu Personalisierungsfunktionen](../send/personalize.md)

Sie haben folgende Möglichkeiten:

* Dynamische Personalisierungsfelder einfügen. [Weitere Informationen](../send/personalization-fields.md)
* Vordefinierte Gestaltungsbausteine einfügen. [Weitere Informationen](../send/personalization-blocks.md)
* Bedingte Inhalte erstellen. [Weitere Informationen](../send/conditions.md)


## Versand- und Trackinglogs{#gs-tracking-logs}

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Sie können nach dem Versand überwachen sowie nachvollziehen, wie Zustellungsfehler und Quarantänen gehandhabt werden.

Informationen zum Überwachen Ihrer Sendungen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de#sending-messages){target="_blank"}.


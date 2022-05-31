---
title: E-Mails senden und überwachen
description: Erfahren Sie mehr über den Umfang und die Besonderheiten des Versands von E-Mails mit Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 57%

---


# E-Mails senden und überwachen

Wenn der Versand konfiguriert wurde und versandbereit ist, stellen Sie sicher, dass Sie die Versandanalyse ausgeführt haben.

![](../assets/do-not-localize/book.png)[ Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#confirming-delivery){target=&quot;_blank&quot;}.

Bestätigen Sie danach den Versand, um den Versand der Nachrichten zu starten.

Außerdem können Sie:

* den Versand zu einem späteren Zeitpunkt planen, indem Sie [die Option Versand verschieben](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#scheduling-the-delivery-sending){target=&quot;_blank&quot;},
* in mehrere Batches mit [mehrere Schübe](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target=&quot;_blank&quot;}.

Verfolgen Sie die Ausführung des Versands über die **Versand** -Tab, der über die Details dieses Versands oder die Versandliste zugänglich ist.

## E-Mails überwachen

Nach dem Versand können Sie im Versand-Dashboard den Versandstatus überprüfen und auf Versandprotokolle und Berichte zugreifen, die bestätigen, dass die Nachrichten korrekt versendet wurden.

![](../assets/do-not-localize/book.png) [Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=de).{target=&quot;_blank&quot;}


## Campaign MTA {#mta}

Der Campaign v8 Mail Transfer Agent (MTA) bietet eine erstklassige Versandinfrastruktur, die eine optimale Zustellbarkeit, Reputation, Durchsatz, Berichterstellung, Bounce-Handhabung, IP-Ramp-up und Verwaltung von Verbindungseinstellungen ermöglicht.

Sie ist für alle Campaign v8-Kunden verfügbar und garantiert Skalierbarkeit, einen hohen Versanddurchsatz und ermöglicht den schnelleren Versand von E-Mails. Erreicht wird dies durch neue adaptive Versandtechniken, die die Einstellungen für den E-Mail-Versand in Echtzeit auf der Grundlage von Rückmeldungen von ISPs (Internetanbietern) ändern.

### Vorteile

Adobe Campaign verwendet einen Mail Transfer Agent (MTA), der den kommerziellen E-Mail-MTA von SparkPost mit dem Namen ausführt. **Momentum**.

Momentum steht für eine innovative, hochleistungsfähige MTA-Technologie, die eine intelligentere Behandlung von Bounce-E-Mails und eine automatische Zustellbarkeitsoptimierung beinhaltet, die den Absendern hilft, optimale Zustellraten im Posteingang zu erreichen und zu erhalten.

* Der MTA ermöglicht einen massiven Anstieg der Gesamtdurchsatzgeschwindigkeit und eine deutliche Verringerung der Softbounces.
* Es verwendet die neueste MTA-Technologie, um Ihnen die optimale Durchsatzgeschwindigkeit für Ihren E-Mail-Versand zu bieten.
* Durch die sofortige und automatische Anpassung an die Rückmeldungen, die er erhält, sorgt er außerdem für einen genaueren und intelligenteren E-Mail-Versand mit Versanddaten in Echtzeit.

### Bounce-Qualifizierung

Für **synchron** Fehlermeldungen bei fehlgeschlagenen Sendungen, bestimmt der MTA den Bounce-Typ und die Qualifizierung und sendet diese Informationen an Campaign zurück.

Der MTA qualifiziert den SMTP-Bounce und sendet diese Qualifizierung zurück an Campaign in Form eines Bouncecodes, der in Campaign einem Bounce-Grund und einer Bounce-Qualifikation zugeordnet ist.

>[!NOTE]
>
>Aktuell **asynchron** Bounces werden vom inMail-Prozess durch das **[!UICONTROL Eingehende E-Mail]** Regeln. Weitere Informationen hierzu finden Sie unter [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Erfahren Sie mehr über fehlgeschlagene Sendungen in [diesem Abschnitt](delivery-failures.md).


### Spezifische MX-Regeln

MX-Regeln (Mail eXchanger) dienen zur Verwaltung der Kommunikation zwischen einem Sender- und einem Empfangs-Server.

Der MTA hat seine eigenen MX-Regeln. Mit diesen kann Ihr Durchsatz anhand Ihrer historischen E-Mail-Reputation und dem Echtzeit-Feedback, das von den Domains stammt, von denen Sie E-Mails senden, angepasst werden.

### DKIM-Signierung

Domain Keys Identified Mail (DKIM) ist eine Authentifizierungsmethode, mit der gefälschte Absenderadressen (häufig als &quot;Spoofing&quot;bezeichnet) erkannt werden.

In Adobe Campaign wird die DKIM-E-Mail-Authentifizierungssignatur vom MTA ausgeführt.

Erfahren Sie mehr über DKIM im [Best Practices für die Zustellbarkeit von Adoben](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=de#authentication){target=&quot;_blank&quot;}.

## E-Mail-Feedback-Service {#email-feedback-service}

Mit der Funktion &quot;E-Mail-Feedback-Service&quot;(EFS) wird der Status jeder E-Mail genau gemeldet, da Feedback direkt aus dem MTA erfasst wird.

Nachdem der Versand gestartet wurde, ändert sich der **[!UICONTROL Erfolgsprozentsatz]** nicht, wenn die Nachricht erfolgreich von Campaign an den MTA weitergeleitet wurde.

Die Versandlogs zeigen den Status **[!UICONTROL Vom Dienstleister berücksichtigt]** für jede Zieladresse an.

Wenn die Nachricht tatsächlich den Zielgruppenprofilen zugestellt wird und diese Informationen in Echtzeit vom MTA gemeldet werden, zeigen die Versandlogs für jede Adresse, die die Nachricht erfolgreich erhalten hat, den Status **[!UICONTROL Gesendet]** an. Der **[!UICONTROL Erfolgsprozentsatz]** wird mit jedem erfolgreichen Versand entsprechend erhöht.

Wenn Hardbounces vom MTA zurückgemeldet werden, ändert sich ihr Log-Status von **[!UICONTROL Vom Dienstleister berücksichtigt]** in **[!UICONTROL Fehlgeschlagen]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Wenn Softbounces vom MTA zurückgemeldet werden, bleibt ihr Log-Status unverändert (**[!UICONTROL Vom Dienstleister berücksichtigt]**): Nur der [Fehlergrund](delivery-failures.md#delivery-failure-reasons) wird aktualisiert<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Der **[!UICONTROL Erfolgsprozentsatz]** bleibt unverändert. Soft-Bounce-Nachrichten werden dann im gesamten Versand wiederholt. [Gültigkeitszeitraum](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

* Wenn ein erneuter Versuch vor Ende der Gültigkeitszeitraums erfolgreich ist, ändert sich der Nachrichtenstatus in **[!UICONTROL Gesendet]** und der **[!UICONTROL Erfolgsprozentsatz]** wird entsprechend erhöht.

* Andernfalls ändert sich der Status in **[!UICONTROL Fehlgeschlagen]**. Der **[!UICONTROL Erfolgsprozentsatz]** <!--and **[!UICONTROL Bounces + errors]** -->bleibt unverändert.

>[!NOTE]
>
>Weitere Informationen zu Hard- und Softbounces finden Sie in [diesem Abschnitt](delivery-failures.md#delivery-failure-reasons).
>
>Weitere Informationen zu zusätzlichen Zustellversuchen nach einem vorübergehend fehlgeschlagenen Versand finden Sie in [diesem Abschnitt](delivery-failures.md#retries).

Die nachstehende Tabelle zeigt, wie die Status der KPIs und Versandlogs bei jedem Schritt des Versandvorgangs mit der EFS-Funktion aktualisiert werden.

| Schritt im Versandprozess | KPI-Zusammenfassung | Versandlogstatus |
|--- |--- |--- |
| Nachricht wird erfolgreich von Campaign an den MTA weitergeleitet | **[!UICONTROL Erfolgsprozentsatz]** wird nicht angezeigt (beginnt bei 0 %) | Vom Dienstleister berücksichtigt |
| Hardbounces werden vom MTA zurückgemeldet. | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Fehlgeschlagen |
| Softbounce-Nachrichten werden aus dem MTA gemeldet | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Vom Dienstleister berücksichtigt |
| Weitere Zustellversuche von Nachrichten, bei denen ein Softbounce aufgetreten ist, sind erfolgreich | **[!UICONTROL Erfolgsprozentsatz]** wird entsprechend erhöht | Gesendet |
| Weitere Zustellversuche von Nachrichten, bei denen ein Softbounce aufgetreten ist, schlagen fehl | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Fehlgeschlagen |

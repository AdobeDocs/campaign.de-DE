---
title: Versand mit dem erweiterten MTA in Adobe Campaign
description: Erfahren Sie mehr über den Umfang und die Besonderheiten des E-Mail-Versands mit dem Enhanced MTA in Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
source-git-commit: 448436d56d14dca2d18088ebfc94f9e21ebb58c4
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 70%

---

# Mit Enhanced MTA senden {#sending-with-enhanced-mta}

Die **Adobe Campaign Enhanced MTA** (Mail Transfer Agent) bietet eine aktualisierte Versandinfrastruktur, die eine optimale Zustellbarkeit, Reputation, Durchsatz, Berichterstellung, Bounce-Handhabung, IP-Ramp-up und Verwaltung der Verbindungseinstellungen ermöglicht.

Er wurde implementiert, um die Skalierbarkeit zu verbessern, den Versanddurchsatz zu erhöhen und mehr E-Mails schneller zu senden. Erreicht wird dies durch neue adaptive Versandtechniken, die die Einstellungen für den E-Mail-Versand in Echtzeit auf der Grundlage von Rückmeldungen von ISPs (Internetanbietern) ändern.

## Nutzung und Vorteile

**Was ist der Enhanced MTA?**

Adobe Campaign verwendet einen Mail Transfer Agent (MTA), der den kommerziellen E-Mail-MTA von SparkPost mit dem Namen ausführt. **Momentum**.

Momentum steht für eine innovative, hochleistungsfähige MTA-Technologie, die eine intelligentere Behandlung von Bounce-E-Mails und eine automatische Zustellbarkeitsoptimierung beinhaltet, die den Absendern hilft, optimale Zustellraten im Posteingang zu erreichen und zu erhalten.

**Was sind die Vorteile?**

* Der Enhanced MTA ermöglicht eine massive Steigerung der Gesamtdurchsatzgeschwindigkeit und eine deutliche Verringerung der Softbounces.
* Es verwendet die neueste MTA-Technologie, um Ihnen die optimale Durchsatzgeschwindigkeit für Ihren E-Mail-Versand zu bieten.
* Durch die sofortige und automatische Anpassung an die Rückmeldungen, die er erhält, sorgt er außerdem für einen genaueren und intelligenteren E-Mail-Versand mit Versanddaten in Echtzeit.

## Besonderheiten des Enhanced MTA {#enhanced-mta-impacts}

### Bounce-Qualifizierung

Für **synchron** Fehlermeldungen von fehlgeschlagenen Sendungen, der erweiterte MTA bestimmt den Bounce-Typ und die Qualifizierung und sendet diese Informationen an Campaign zurück.

Der Enhanced MTA qualifiziert den SMTP-Bounce und sendet diese Qualifizierung zurück an Campaign in Form eines Bouncecodes, der in Campaign einem Bounce-Grund und einer Bounce-Qualifikation zugeordnet ist.

>[!NOTE]
>
>Aktuell **asynchron** Bounces werden vom inMail-Prozess durch das **[!UICONTROL Eingehende E-Mail]** Regeln. Weitere Informationen hierzu finden Sie unter [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Erfahren Sie mehr über fehlgeschlagene Sendungen in [diesem Abschnitt](delivery-failures.md).

### Gültigkeitszeitraum

Die Einstellung für den Gültigkeitszeitraum in Ihren Campaign-Sendungen wird vom Enhanced MTA nur verwendet, wenn sie auf **3,5 Tage oder weniger** eingestellt ist. Wenn Sie in Campaign einen Wert von mehr als 3,5 Tagen definieren, wird dieser nicht berücksichtigt.

Wenn der Gültigkeitszeitraum in Campaign beispielsweise auf den Standardwert von 5 Tagen eingestellt ist, werden Softbounce-Nachrichten in die Warteschlange für Wiederholungsversuche des Enhanced MTA aufgenommen und nur bis zu 3,5 Tage ab dem Zeitpunkt, an dem die Nachricht den Enhanced MTA erreicht hat, erneut versucht. In diesem Fall wird der in Campaign eingestellte Wert nicht verwendet.

Sobald eine Nachricht 3,5 Tage lang in der Warteschlange des Enhanced MTA war und nicht gesendet werden konnte, wird sie mit einem Timeout beendet; ihr Status wird von **[!UICONTROL Gesendet]** in **[!UICONTROL Fehlgeschlagen]** geändert (in den Versandlogs).

Weitere Informationen zum Gültigkeitszeitraum finden Sie im Abschnitt [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.

### Weitere Zustellversuche

Weitere Versuche aufgrund von Softbounces und die Zeitdauer zwischen ihnen werden durch den Enhanced MTA bestimmt, basierend auf Typ und Prioritätsstufe der Bounce-Antworten, die von der E-Mail-Domain der Nachricht zurückgegeben werden.

>[!NOTE]
>
>Die Einstellungen für den erneuten Versuch in den Versandeigenschaften werden von Campaign nicht verwendet.

Erfahren Sie mehr über weitere Zustellversuche in [diesem Abschnitt](delivery-failures.md#retries).

### Spezifische MX-Regeln

MX-Regeln (Mail eXchanger) dienen zur Verwaltung der Kommunikation zwischen einem Sender- und einem Empfangs-Server.

Der Enhanced MTA hat seine eigenen MX-Regeln. Mit diesen kann Ihr Durchsatz anhand Ihrer historischen E-Mail-Reputation und dem Echtzeit-Feedback, das von den Domains stammt, von denen Sie E-Mails senden, angepasst werden.

### DKIM-Signierung

Domain Keys Identified Mail (DKIM) ist eine Authentifizierungsmethode, mit der gefälschte Absenderadressen (häufig als &quot;Spoofing&quot;bezeichnet) erkannt werden.

In Adobe Campaign wird die DKIM-E-Mail-Authentifizierungssignatur vom erweiterten MTA durchgeführt.

Erfahren Sie mehr über DKIM im [Best Practices für die Zustellbarkeit von Adoben](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=de#authentication){target=&quot;_blank&quot;}.

## E-Mail-Feedback-Service {#email-feedback-service}

Mit der EFS-Funktion (E-Mail-Feedback-Service) wird der Status jeder E-Mail genau gemeldet, da Feedback direkt vom erweiterten MTA (Message Transfer Agent) erfasst wird.

Nachdem der Versand gestartet wurde, ändert sich der **[!UICONTROL Erfolgsprozentsatz]** nicht, wenn die Nachricht erfolgreich von Campaign an den Enhanced MTA weitergeleitet wurde.

Die Versandlogs zeigen den Status **[!UICONTROL Vom Dienstleister berücksichtigt]** für jede Zieladresse an.

Wenn die Nachricht tatsächlich den Zielgruppenprofilen zugestellt wird und diese Informationen in Echtzeit vom Enhanced MTA gemeldet werden, zeigen die Versandlogs für jede Adresse, die die Nachricht erfolgreich erhalten hat, den Status **[!UICONTROL Gesendet]** an. Der **[!UICONTROL Erfolgsprozentsatz]** wird mit jedem erfolgreichen Versand entsprechend erhöht.

Wenn Hardbounces vom Enhanced MTA zurückgemeldet werden, ändert sich ihr Log-Status von **[!UICONTROL Vom Dienstleister berücksichtigt]** in **[!UICONTROL Fehlgeschlagen]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Wenn Softbounces vom Enhanced MTA zurückgemeldet werden, bleibt ihr Log-Status unverändert (**[!UICONTROL Vom Dienstleister berücksichtigt]**): Nur der [Fehlergrund](delivery-failures.md#delivery-failure-reasons) wird aktualisiert<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Der **[!UICONTROL Erfolgsprozentsatz]** bleibt unverändert. Soft-Bounce-Nachrichten werden dann im gesamten Versand wiederholt. [Gültigkeitszeitraum](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

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
| Nachricht wird erfolgreich von Campaign an den Enhanced MTA weitergeleitet | **[!UICONTROL Erfolgsprozentsatz]** wird nicht angezeigt (beginnt bei 0 %) | Vom Dienstleister berücksichtigt |
| Hardbounces werden vom Enhanced MTA zurückgemeldet. | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Fehlgeschlagen |
| Softbounces werden vom erweiterten MTA zurückgemeldet. | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Vom Dienstleister berücksichtigt |
| Weitere Zustellversuche von Nachrichten, bei denen ein Softbounce aufgetreten ist, sind erfolgreich | **[!UICONTROL Erfolgsprozentsatz]** wird entsprechend erhöht | Gesendet |
| Weitere Zustellversuche von Nachrichten, bei denen ein Softbounce aufgetreten ist, schlagen fehl | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Fehlgeschlagen |


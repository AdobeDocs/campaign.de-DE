---
title: Senden und Überwachen Ihrer E-Mails
description: Erfahren Sie mehr über den Umfang und die Besonderheiten des E-Mail-Versands mit Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: ht
source-wordcount: '845'
ht-degree: 100%

---


# Senden und Überwachen Ihrer E-Mails  {#send-and-monitor-emails}

Stellen Sie sicher, dass Sie nach der Konfiguration des Versands die Versandanalyse ausgeführt haben, bevor Sie den Versand durchführen. [Weitere Informationen](delivery-analysis.md)

Bestätigen Sie anschließend den Versand, um den Versand der Nachrichten zu starten.

Sie können die Ausführung des Versands über die Registerkarte **Versand** verfolgen, die über die Details dieses Versands oder über die Versandliste zugänglich ist.

## Überwachen Ihrer E-Mails {#email-monitoring}

Nach dem Versand können Sie im **Versand-Dashboard** den Versandstatus überprüfen und auf Versandprotokolle und Berichte zugreifen, die bestätigen, dass die Nachrichten korrekt versendet wurden.

Im Versand-Dashboard können Sie außerdem die verarbeiteten Nachrichten und Versand-Auditlogs überprüfen. In den Versandlogs können Sie den Status der Nachrichten feststellen.

>[!NOTE]
>
>Der Versandstatus wird nicht in Echtzeit angezeigt. Weitere Informationen zum E-Mail-Feedback-Service finden Sie [in diesem Abschnitt](#email-feedback-service).


[Weitere Informationen zum Versand-Monitoring finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=de){target="_blank"}.

## Campaign MTA {#mta}

Der Mail Transfer Agent (MTA) von Campaign v8 bietet eine marktführende Versandinfrastruktur, die eine Verbesserungen bei Zustellbarkeit, Reputation, Durchsatz, Reporting, Handhabung von Bounces, IP-Anwärmphase und Verwaltung der Verbindungsparameter bietet.

Er ist für alle Campaign v8-Kunden verfügbar und garantiert Skalierbarkeit und einen hohen Versanddurchsatz, was einen schnelleren Versand von mehr E-Mails ermöglicht. Erreicht wird dies durch neue adaptive Versandtechniken, die die Einstellungen für den E-Mail-Versand in Echtzeit auf der Grundlage von Rückmeldungen von ISPs (Internetanbietern) anpassen.

### Vorteile

Adobe Campaign verwendet einen Mail Transfer Agent (MTA), der den kommerziellen E-Mail-MTA von SparkPost namens **Momentum** ausführt.

Momentum steht für eine innovative, hochleistungsfähige MTA-Technologie, die eine intelligentere Handhabung von Bounce-E-Mails und eine automatische Zustellbarkeitsoptimierung beinhaltet, die den Absenderinnen und Absendern hilft, optimale Versandraten im Posteingang zu erreichen und beizubehalten.

* Der MTA ermöglicht eine beachtliche Steigerung der Gesamtdurchsatzgeschwindigkeit und eine deutliche Verringerung der Softbounces.
* Er nutzt die neueste MTA-Technologie, um Ihnen optimale Durchsatzgeschwindigkeiten für Ihren E-Mail-Versand zu bieten.
* Durch die sofortige und automatische Anpassung an die Rückmeldungen, die er erhält, sorgt er außerdem für einen genaueren und intelligenteren E-Mail-Versand mit Versanddaten in Echtzeit.

### Bounce-Qualifizierung

Bei Fehlermeldungen zu **synchronen** Versandfehlern bestimmt der MTA den Bounce-Typ und die Qualifizierung und sendet diese Informationen an Campaign zurück.

Der MTA qualifiziert den SMTP-Bounce und sendet diese Qualifizierung zurück an Campaign in Form eines Bouncecodes, der in Campaign einer Bounce-Ursache und einer Bounce-Qualifikation zugeordnet ist.

>[!NOTE]
>
>Derzeit werden **asynchrone** Bounces durch den inMail-Prozess über die Regeln für **[!UICONTROL eingehende E-Mails]** als solche qualifiziert.

In [diesem Abschnitt](delivery-failures.md) erfahren Sie mehr über fehlgeschlagene Sendungen.


### Spezifische MX-Regeln

MX-Regeln (Mail eXchanger) dienen zur Verwaltung der Kommunikation zwischen einem Sende- und einem Empfangs-Server.

Der MTA hat seine eigenen MX-Regeln. Mit diesen kann Ihr Durchsatz anhand Ihrer historischen E-Mail-Reputation und des Echtzeit-Feedbacks, das von den Domains stammt, von denen Sie E-Mails senden, angepasst werden.

### DKIM-Signierung

Domain Keys Identified Mail (DKIM) ist eine Authentifizierungsmethode, mit der gefälschte Absenderadressen (häufig als &quot;Spoofing&quot; bezeichnet) erkannt werden.

In Adobe Campaign wird die DKIM-E-Mail-Authentifizierungssignatur vom MTA durchgeführt.

Im [Handbuch von Adobe zu Best Practices für die Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=de#authentication){target="_blank"} erfahren Sie mehr über DKIM.

## E-Mail-Feedback-Service {#email-feedback-service}

Der E-Mail-Feedback-Service (EFS) von Campaign meldet den Status jedes mit Adobe Campaign gesendeten E-Mail-Versands.

Nachdem der Versand gestartet wurde, ändert sich der **[!UICONTROL Erfolgsprozentsatz]** nicht, wenn die Nachricht erfolgreich von Campaign an den MTA weitergeleitet wurde. Die Versandlogs zeigen für jede Zieladresse den Status **[!UICONTROL Vom Dienstleister berücksichtigt]** an.

Wenn die Nachricht den Zielgruppenprofilen zugestellt wird und diese Information vom MTA in Echtzeit zurückgemeldet wird, zeigen die Versandlogs für jede Adresse, die die Nachricht erfolgreich erhalten hat, den Status **[!UICONTROL Gesendet]** an. Der **[!UICONTROL Erfolgsprozentsatz]** wird mit jedem erfolgreichen Versand erhöht.

Wenn Hardbounces vom MTA zurückgemeldet werden, ändert sich ihr Log-Status von **[!UICONTROL Vom Dienstleister berücksichtigt]** in **[!UICONTROL Fehlgeschlagen]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Wenn Softbounces vom MTA zurückgemeldet werden, bleibt ihr Log-Status unverändert (**[!UICONTROL Vom Dienstleister berücksichtigt]**). Nur die [Fehlerursache](delivery-failures.md#delivery-failure-reasons) wird aktualisiert<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Der **[!UICONTROL Erfolgsprozentsatz]** bleibt unverändert. Nachrichten, bei denen ein Softbounce aufgetreten ist, erhalten dann während des [Gültigkeitszeitraums](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=de#defining-validity-period){target="_blank"} des Versands einen erneuten Zustellversuch:

* Wenn ein erneuter Versuch vor Ende der Gültigkeitszeitraums erfolgreich ist, ändert sich der Nachrichtenstatus in **[!UICONTROL Gesendet]** und der **[!UICONTROL Erfolgsprozentsatz]** wird entsprechend erhöht.

* Andernfalls ändert sich der Status in **[!UICONTROL Fehlgeschlagen]**. Der **[!UICONTROL Erfolgsprozentsatz]** <!--and **[!UICONTROL Bounces + errors]** -->bleibt unverändert.

>[!NOTE]
>
>Weitere Informationen zu Hard- und Softbounces finden Sie in [diesem Abschnitt](delivery-failures.md#delivery-failure-reasons).
>
>Weitere Informationen zu zusätzlichen Zustellversuchen nach einem vorübergehend fehlgeschlagenen Versand finden Sie in [diesem Abschnitt](delivery-failures.md#retries).

Die nachstehende Tabelle zeigt, wie die Status der KPIs und Versandlogs bei jedem Schritt des Versandvorgangs aktualisiert werden.

| Schritt im Versandprozess | KPI-Zusammenfassung | Versandlogstatus |
|--- |--- |--- |
| Nachricht wird erfolgreich von Campaign an den MTA weitergeleitet | **[!UICONTROL Erfolgsprozentsatz]** wird nicht angezeigt (beginnt bei 0 %) | Vom Dienstleister berücksichtigt |
| Hardbounces werden vom MTA zurückgemeldet. | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Fehlgeschlagen |
| Softbounces werden vom MTA zurückgemeldet. | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Vom Dienstleister berücksichtigt |
| Weitere Zustellversuche von Nachrichten, bei denen ein Softbounce aufgetreten ist, sind erfolgreich | **[!UICONTROL Erfolgsprozentsatz]** wird entsprechend erhöht | Gesendet |
| Weitere Zustellversuche von Nachrichten, bei denen ein Softbounce aufgetreten ist, schlagen fehl | Keine Änderung des **[!UICONTROL Erfolgsprozentsatzes]** | Fehlgeschlagen |

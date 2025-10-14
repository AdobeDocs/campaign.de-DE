---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d31368428fc7d5b982bb5fc67d0369bb17ea0b2c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 24%

---

# Neueste Versionen {#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **neuesten Campaign v8-Versionen** (Konsole) aufgelistet. Weitere Informationen zu Campaign-Versionen und -Upgrades finden Sie auf [dieser Seite](upgrades.md). Weitere Versionen sind im Abschnitt „Frühere Versionen“ dieser Dokumentation aufgeführt.

## Version 8.8.2 {#release-8-8-2}

_9. Oktober 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. 

### Neue Funktionen {#features-8-8-2}

Der **neue SMS-**-Connector) ist jetzt für [Campaign FFDA-Bereitstellungen](../architecture/enterprise-deployment.md) verfügbar. Weiterführende Informationen finden Sie im [entsprechenden Handbuch](../send/sms/sms.md).

Diese Version enthält auch eine Reihe von Funktionen, die in der Web-Benutzeroberfläche von Campaign verfügbar sind:

* [Profilanreicherung in Transaktionsnachrichten](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=de){target="_blank"}
* [Mehrsprachige Funktionen für Transaktionsnachrichten, Push-Benachrichtigungen und SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=de){target="_blank"}

Weitere Informationen finden Sie in den Versionshinweisen zur [&#x200B; Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=de){target="_blank"}

### Fehlerbehebungen {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Fehlerkorrektur - Der Datenbankbereinigungs-Workflow schlägt jetzt nicht mehr fehl. (NEO-87949)
* Fehlerkorrektur - Im verteilten Marketing werden jetzt Tracking-Daten für den Versand über partizipative Kampagnen erfasst. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Fehlerkorrektur - Die Personalisierung in Fragmenten funktioniert jetzt einwandfrei. (NEO-88161)
* Fehlerkorrektur - Nach der Migration zum neuen Redshift ODBC-Connector schlägt die Workflow-Aktivität Aufspaltung jetzt nicht mehr mit SQL-Fehlern fehl. (NEO-87466)
* Fehlerkorrektur - Die Anzahl der Ausschlüsse in Workflows ist jetzt korrekt. (NEO-89207)
* Fehlerkorrektur - Die Klickindikatoren für Push-Benachrichtigungen sind jetzt korrekt. (NEO-89503)
* Fehlerkorrektur - Die SMS-Versandlogs werden jetzt korrekt aktualisiert, was die Statusberichterstattung in Adobe Campaign verhindert. (NEO-88479)
* Es wurde ein Problem behoben, bei dem französische Anführungszeichen im Versandinhalt fälschlicherweise in englische Anführungszeichen konvertiert wurden. (NEO-89631)
* Es wurde ein Problem behoben, bei dem der Echtzeit-Server stattdessen einen falschen Antwort-Code für ungültige IMS-Token zurückgab. (NEO-87428)
* Fehlerkorrektur - Die Versandstatistiken für E-Mail und SMS werden jetzt vollständig neu berechnet, was zu ungenauen Erfolgsindikatoren führt. (NEO-88106)
* Fehlerkorrektur - Beim neuen SMS-Versand-Connector wird Versandlogs jetzt für eine kleine Teilmenge von Nachrichten kein Versandstatus mehr zugewiesen. (NEO-89581)
* Fehlerkorrektur - Beim neuen SMS-Versand-Connector werden die Erfolgsmetriken und Sendungen auf Marketing- und Mid-Server jetzt korrekt aktualisiert. (NEO-89850)
* Fehlerkorrektur - Es wurde ein Synchronisierungsproblem zwischen der Echtzeit- und der Marketing-Instanz behoben, das zu fehlenden Trackinglogs und falschen Berichten führte. (NEO-90247)
* Fehlerkorrektur: Es wurde ein Workflow-Anreicherungsproblem behoben, das zu Fehlern bei der Auswahl von Feldern über zwei aufeinander folgende 1-N-Links in benutzerdefinierten Schemata führen konnte. (NEO-87682)


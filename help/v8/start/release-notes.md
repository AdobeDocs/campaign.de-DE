---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 21%

---

# Neueste Versionen {#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **neuesten Campaign v8-Versionen** (Konsole) aufgelistet. Weitere Informationen zu Campaign-Versionen und -Upgrades finden Sie auf [dieser Seite](upgrades.md). Weitere Versionen sind im Abschnitt „Frühere Versionen“ dieser Dokumentation aufgeführt.

## Version 8.9.1 {#release-8-9-1}

_27. Januar 2026_

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

### Neue Funktionen {#new-8-9-1}

Der **neue SMS-**-Connector) ist jetzt für alle Kunden (GA) verfügbar. Weiterführende Informationen finden Sie im [entsprechenden Handbuch](../send/sms/sms.md).

Diese Version enthält eine Reihe von Funktionen, die in der Web-Benutzeroberfläche von Campaign verfügbar sind:

* [Mehrsprachige Bereitstellungsfunktionen (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Profilanreicherung in Transaktionsnachrichten (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager Live Copies und Sprachkopien](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Inhaltsexperimente - A/B-Tests](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [Kontinuierliche Versandaktivität](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [Validierungsverwaltung für Kampagnen](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Weitere Informationen finden Sie in den Versionshinweisen zur [ Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=de){target="_blank"}

### Verbesserungen bezüglich der Sicherheit {#security-8-9-1}

* Externe Snowflake-Konten unterstützen jetzt die OAuth2-Authentifizierung und bieten moderne und sichere Authentifizierungsmethoden für Federated Data Access-Verbindungen. (NEO-87013)
* Fehlerkorrektur - Der Zugriff auf Workflow-Dateien erfolgt jetzt fehlerfrei, indem Vorgänge auf autorisierte Verzeichnisse beschränkt werden. Dadurch wird ein nicht autorisierter Zugriff und eine potenzielle Ausführung von Remote-Code verhindert. (NEO-88460)
* Es wurden Steuerelemente zur FTP-URL-Zulassungsauflistung zu Workflow-JavaScript-Code-Aktivitäten hinzugefügt, wodurch ausgehende FTP-Verbindungen auf autorisierte Adressen beschränkt werden. (NEO-89083)

### Sonstige Änderungen  {#changes-8-9-1}

* Verbessertes Container-Speichermanagement durch Implementierung automatischer Workflow-Einschränkungen unter Bedingungen mit hohem Arbeitsspeicher sowie intelligente Workflow-Neustart-Funktionen und Speicher-Leitplanken für unkritische Prozesse. (NEO-89041)
* Unterstützung für asymmetrische Verschlüsselungs- und Entschlüsselungsfunktionen in Campaign-Workflows hinzugefügt. (NEO-80257)
* Verbesserte Leistung des Replikationsagenten und verbesserte Speicherresilienz für große Datenuploads in FFDA-Bereitstellungen. (NEO-88430)


### Fehlerbehebungen {#fixes-8-9-1}

* Es wurde ein Problem behoben, bei dem dynamische Berichte bei der Gruppierung nach bestimmten Spalten falsche Zählungen anzeigten. (NEO-86898)
* Es wurden Datendiskrepanzen zwischen dynamischen Berichten und tatsächlichen Kampagnendaten behoben. (NEO-88068)
* Es wurden Verkettungsprobleme mit PostgreSQL „char“-Feldtypen behoben, die zu unerwarteten Ergebnissen in Abfragen führten. (NEO-87769)
* Fehlerkorrektur - Der JavaScript-Befehl logInfo verarbeitet bestimmte Parameter nicht ordnungsgemäß. (NEO-88263)
* Behobene Synchronisierungsprobleme bei der Echtzeit-Ereignisverarbeitung in Message Center. (NEO-88330)
* Es wurde ein Problem behoben, bei dem der Visual Editor HTML-Inhalte automatisch neu formatierte, was zu Layout-Änderungen führte. (NEO-88409)
* Es wurde ein Problem behoben, bei dem die Aktivität Deduplizierung nicht ordnungsgemäß mit temporären Schemata funktionierte. (NEO-88577)
* Fehlerkorrektur - Testadressen werden jetzt beim Senden von Testsendungen generiert. (NEO-88720)
* Verbesserte PostgreSQL-Abfrageleistung durch Optimierung der Behandlung von Partitionsspalten. (NEO-88771)
* Es wurde ein Problem behoben, bei dem Dateiübertragungsaktivitäten Zeilenfortsetzungszeichen nicht ordnungsgemäß verarbeiten konnten. (NEO-88812)
* Verbesserte PostgreSQL-Abfrageoptimierung für eine bessere Leistung in großen Datensätzen. (NEO-88885)
* Es wurde ein Fehler „Berechtigung verweigert“ behoben, der das Öffnen von Hybrid-Kampagnen verhinderte. (NEO-88955)
* Erweiterte Barcode-Funktionsunterstützung für die Verarbeitung längerer Textzeichenfolgen. (NEO-88958)
* Fehlerkorrektur - In den Kampagnenprotokollen tritt jetzt kein Fehler mehr auf, wenn Testsendungen mit wiederkehrenden Sendungen verwendet werden. (NEO-88976)
* Fehlerkorrektur - E-Mail-Versandvorgänge werden jetzt in bestimmten Szenarien zuverlässig ausgeführt. (NEO-89019)
* Es wurde ein Problem behoben, bei dem der Workflow-Startmodus unerwartet von Sofort in Normal geändert wurde. (NEO-89025)
* Es wurden Fehler behoben, die bei der Ausführung der Aktivität Daten-Update unter bestimmten Bedingungen auftraten. (NEO-89031)
* Es wurde ein Problem behoben, bei dem die Aktivität Daten-Update benutzerdefinierte Schemadateien verlor. (NEO-89056)
* Fehlerkorrektur - Bei der Versandvorbereitung tritt jetzt kein Validierungsfehler mehr auf. (NEO-89063)
* Die ungültige SQL-Generierung wurde behoben, wenn Abfragen Filter für 1:1-Link-Beziehungen enthielten. (NEO-89065)
* Es wurde ein Problem behoben, bei dem die Aktivität Inkrementelle Abfrage die konfigurierte Größenbeschränkung nicht beachtete. (NEO-89066)
* Verbesserte Workflow-Leistung in FFDA-Bereitstellungen für groß angelegte Vorgänge. (NEO-89098)
* Verbesserte Speicherverwaltung und Stabilität für Workflow-Prozesse. (NEO-89105)
* Strenge Spaltenvalidierung für Web-Formulare wurde aktiviert, um Dateninkonsistenzen zu vermeiden. (NEO-89111)
* Es wurden Synchronisationsprobleme des Message Centers behoben, die zu Verarbeitungsverzögerungen führten. (NEO-89138)
* Fehlerkorrektur - Der Workflow Zustellbarkeit funktioniert jetzt fehlerfrei. (NEO-89160)
* Fehler, die beim Ausführen von JavaScript-Code-Aktivitäten in Workflows aufgetreten sind, wurden korrigiert. (NEO-89169)
* Hartcodierte Snowflake Warehouse-Konfigurationen wurden entfernt, um ordnungsgemäße Einstellungen für externe Konten zu ermöglichen. (NEO-89201)
* Behebung von 403 Fehlern, die bei Workflow-Dateiübertragungsvorgängen auftraten und die nicht zulässig waren. (NEO-89226)
* Optimierte langsame Abfragen der Empfängertabelle in FFDA-Bereitstellungen. (NEO-89268)
* Es wurde ein Problem behoben, bei dem inkrementelle Abfrageaktivitäten konfigurierte Zeitpläne ignorierten. (NEO-89317)
* Behobene Zugriffsfehler beim Öffnen von Kampagnen in Hybridumgebungen. (NEO-89320)
* Es wurden Diskrepanzen in den Berichten der Web-Benutzeroberfläche von Campaign behoben, bei denen Tracking-Statistiken im Vergleich zur Konsole andere Werte angezeigt haben. Die Berichte Tracking-Indikatoren, Versandzusammenfassung und URL-Clickstreams zeigen jetzt über beide Schnittstellen hinweg konsistente Metriken an. (NEO-82339)
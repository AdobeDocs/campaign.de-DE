---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
TQID: https://experienceleague.adobe.com/Zdo52RLQFbxlRNgE54yLDn3yAMmmOqxKyRhnCJa0Xwg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ffeb9430b382b598af412555b1b0a6ff42bc68d0
workflow-type: tm+mt
source-wordcount: 1754
ht-degree: 6%

---

# Neueste Versionen {#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **neuesten Campaign v8-Versionen** (Konsole) aufgelistet. Weitere Informationen zu Campaign-Versionen und -Upgrades finden Sie auf [dieser Seite](upgrades.md). Weitere Versionen sind im Abschnitt „Frühere Versionen“ dieser Dokumentation aufgeführt.

## Version 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

_3. Mai 2026_

### Verbesserungen bezüglich der Sicherheit {#security-8-9-2}

* Um optimale Sicherheit, Stabilität und Compliance zu gewährleisten, wurden alle Instanzen auf Debian 13 und PostgreSQL 17 aktualisiert.

### Fehlerbehebungen {#fixes-8-9-2}

>[!NOTE]
>
> Die unten aufgeführten Fehlerbehebungen wurden schrittweise in allen aufeinander folgenden 8.9.2-Builds implementiert. Navigieren Sie zu **[!UICONTROL Hilfe > Über…]** [Menü](upgrades.md#version), um zu überprüfen, ob Sie den neuesten 8.9.2 (11d1c68)-Build haben. Weitere Informationen erhalten Sie vom Adobe-Support.

* Es wurde ein Problem behoben, bei dem Ereignisdaten in Transaktionsereignissen aufgrund eines Datentypkonvertierungsproblems falsch festgelegt wurden, was zu falschen Datumsangaben in dynamischen Berichten führte. (NEO-93923)
* Fehlerkorrektur - Stille Push-Benachrichtigungen in Android und iOS funktionieren jetzt während der Versandvorbereitung, wenn die Titel- und Textfelder leer sind. (NEO-93739)
* Fehlerkorrektur - Das Sprachfeld wird jetzt für Android-App-Registrierungs-Token erfasst, da die Abstimmschlüssel falsch sind. (NEO-93100)
* Fehlerkorrektur - Die Versandvorbereitung schlägt jetzt nicht mehr fehl, wenn benutzerdefinierte Typologieregeln mit Druckregeln angewendet werden. (NEO-94457)
* Es wurde ein Problem behoben, bei dem in der Client-Konsole Fehler bei der Verarbeitung von HTTP-Anfragen auftreten konnten. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* Die FDA-Überwachung ist jetzt standardmäßig deaktiviert, um Fehler beim Einfügen des Verbindungsprotokolls zu vermeiden. (NEO-94841)
* Es wurde ein Problem behoben, bei dem Interaction SOAP-Aufrufe, die für die Angebotseinlösung verwendet werden, mit einem Namespace-Auflösungsfehler fehlschlagen konnten. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* Es wurde ein Problem behoben, bei dem Zeichenfolgenfelder mit der Länge 1 zu SQL-Fehlern in temporären Workflow-Tabellen in PostgreSQL 17 führen konnten. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* Es wurde ein Problem behoben, bei **die Option „Mirrorseite anzeigen** in der Client-Konsole und der Web-Benutzeroberfläche den Fehler „Fehlerhafte Mirrorseite“ zurückgeben konnte. (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* Fehlerkorrektur - Der vorkonfigurierte technische Workflow **Tracking** schlägt nach der Installation eines Multivarianz-Pakets in FFDA-Bereitstellungen nicht mehr fehl. (NEO-94972)
* Fehlerkorrektur - Bei der Versandvorbereitung können keine Empfänger zur Zielgruppe hinzugefügt werden, wenn die Versandvorlage eine Gewichtungsformel verwendet, die auf den aktuellen Versand verweist. (NEO-94892)
<!-- hotfix -->
* Fehlerkorrektur - Workflow-Anreicherungen mit Joins über zwei aufeinander folgende 1-N-Links hinweg schlagen nach einem Upgrade nicht mehr mit SQL-Fehlern fehl. (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* Fehlerkorrektur - In der E-Mail-Pipeline wird jetzt nicht mehr viel Arbeitsspeicher belegt. (NEO-95088)
* Es wurde ein Problem behoben, bei dem die E-Mail-Typologieregel in Konflikt stehende Empfänger fälschlicherweise von einer Versandzielgruppe ausschließen konnte, wenn Seed- oder Testversand-Adressen verwendet wurden. (NEO-95026)
* Es wurde ein Problem behoben, bei dem der standardmäßige technische Workflow **Angebotsbenachrichtigung** nach einem Upgrade fehlschlug. (NEO-95064)
* Der Multivarianz-Paketinstallationsprozess wurde verbessert, um Tracking-Workflow-Fehler während Build-Upgrades zu verhindern. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* Fehlerkorrektur - Der Server stürzt jetzt nicht mehr wiederholt ab, was zu Instanzausfällen führen kann. (NEO-95304)
* Es wurde ein Problem behoben, bei dem Tracking- und Mirrorseiten-Links Sendungen nicht laden konnten. (NEO-95239)
* Fehlerkorrektur - Beim Anmelden bei Campaign-Web-Anwendungen, die durch das einmalige Anmelden von IMS geschützt sind, kommt es jetzt nicht mehr zu einer Umleitungsschleife. (NEO-95188)
* Fehlerkorrektur - Nach dem Speichern des Versands fehlt jetzt das Erstellungsdatum des Versands in den Extraktionsdateien des Versands. (NEO-95010)
* Es wurde ein Problem behoben, bei dem untergeordnete Workflows, die in großen Mengen erzeugt wurden, im Status **In Bearbeitung** bleiben konnten, wodurch die Kapazität des Transaktions-Workflows reduziert wurde. (NEO-95131)
* Es wurde ein Problem behoben, bei dem die **Liste lesen**-Aktivität vordefinierte Listenvorlagen mit Workflow-generierten Listenstrukturen überschreiben konnte, was zu Fehlern in nachgelagerten Workflows führte. (NEO-95103)
* Es wurde ein Problem behoben, bei dem die Verarbeitung von Feedback zu Push-Benachrichtigungen dazu führen konnte, dass der Server bei der Verarbeitung von Sendungen mit hohem Volumen abstürzte. (NEO-95150)
* Es wurde ein Problem behoben, bei dem beim Öffnen **Registerkarte** Daten“ im `xtk:workflow` im Schema-Explorer eine Fehlermeldung Trigger werden konnte. (NEO-94923)
<!-- hotfixes -->
* Fehlerkorrektur - Die Aktivität **Anreicherung** kann jetzt keine Ausgabeattribute mehr aus Upstream-Aktivitäten **Unter-Workflows** abrufen, was dazu führt, dass Workflows fehlschlagen. (NEO-95151)
* Fehlerkorrektur - Die Aufnahme von Tracking-Daten funktioniert jetzt problemlos, wenn der Versandstatus nicht mehr aktualisiert werden kann und die nachgelagerte Nachrichtenverarbeitung blockiert wird. (NEO-94666)
* Es wurde ein Problem behoben, bei dem durch bestimmte Aktionen der Client-Konsole im Zusammenhang mit Angebotsvorschlägen lange laufende Abfragen in Snowflake-Datenbanken Trigger wurden, was zu Sperren und Langsamkeit führte. (NEO-92936)
* Es wurde ein Problem behoben, bei dem benutzerdefinierte Optionen zum Speichern verschlüsselter Schlüssel nicht für externe Snowflake-Konten konfiguriert werden konnten. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## Version 8.9.1 {#release-8-9-1}

_27. Januar 2026_

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

### Neue Funktionen {#new-8-9-1}

Der **neue SMS-**-Connector) ist jetzt für alle Kunden (GA) verfügbar. Weiterführende Informationen finden Sie im [entsprechenden Handbuch](../send/sms/sms.md).

Diese Version enthält eine Reihe von Funktionen, die in der Web-Benutzeroberfläche von Campaign verfügbar sind:

* [Mehrsprachige Versandfunktionen (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=de){target="_blank"}
* [Profilanreicherung in Transaktionsnachrichten (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=de){target="_blank"}
* [Adobe Experience Manager Live Copies und Sprachkopien](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=de){target="_blank"}
* [Inhaltsexperimente - A/B-Tests](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=de){target="_blank"}
* [Kontinuierliche Versandaktivität](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=de){target="_blank"}
* [Validierungsverwaltung für Kampagnen](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=de){target="_blank"}

Weitere Informationen finden Sie in den Versionshinweisen zur [&#x200B; Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=de){target="_blank"}

### Verbesserungen bezüglich der Sicherheit {#security-8-9-1}

* Externe Snowflake-Konten unterstützen jetzt die OAuth2-Authentifizierung und bieten moderne und sichere Authentifizierungsmethoden für Federated Data Access-Verbindungen. (NEO-87013) [Mehr dazu](../config/external-accounts.md#snowflake-external-accounts)
* Externe Databricks-Konten unterstützen jetzt die OAuth2-Authentifizierung über den Service-Prinzipal (nicht interaktiver Fluss der Client-Anmeldeinformationen) und bieten sichere Authentifizierungsmethoden für Federated Data Access-Verbindungen. Die interaktive OAuth2-Authentifizierung wird in einer zukünftigen Version verfügbar sein. (NEO-87422) [Mehr dazu](../config/external-accounts.md#databricks-external-accounts)
* Fehlerkorrektur - Der Zugriff auf Workflow-Dateien erfolgt jetzt fehlerfrei, indem Vorgänge auf autorisierte Verzeichnisse beschränkt werden. Dadurch wird ein nicht autorisierter Zugriff und eine potenzielle Ausführung von Remote-Code verhindert. (NEO-88460)
* Es wurden Steuerelemente zur FTP-URL-Zulassungsauflistung zu Workflow-JavaScript-Code-Aktivitäten hinzugefügt, wodurch ausgehende FTP-Verbindungen auf autorisierte Adressen beschränkt werden. (NEO-89083)

### Sonstige Änderungen {#changes-8-9-1}

* Verbessertes Container-Speichermanagement durch Implementierung automatischer Workflow-Einschränkungen unter Bedingungen mit hohem Arbeitsspeicher sowie intelligente Workflow-Neustart-Funktionen und Speicher-Leitplanken für unkritische Prozesse. (NEO-89041)
* Unterstützung für asymmetrische Verschlüsselungs- und Entschlüsselungsfunktionen in Campaign-Workflows hinzugefügt. (NEO-80257)
* Verbesserte Leistung des Replikationsagenten und verbesserte Speicherresilienz für große Datenuploads in FFDA-Bereitstellungen. (NEO-88430)
* Die Workflow-Aktivitäten **[!UICONTROL SQL-Code]** und **[!UICONTROL SQL-Daten-Management]** wurden verbessert, um PostgreSQL-Datenbanken besser zu schützen und dafür zu sorgen, dass Ihre Workflows reibungslos ausgeführt werden, wenn benutzerdefinierte SQL von Campaign aus ausgeführt wird. Weitere Informationen und Best Practices finden Sie unter [SQL](../../automation/workflow/sql-data-management.md#important-notes)Daten-Management und [SQL](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)Code). (NEO-86540)


### Fehlerbehebungen {#fixes-8-9-1}

* Es wurde ein Problem behoben, bei dem die Datenbankstruktur nach sysFilter-Änderungen nicht aktualisiert werden konnte. (NEO-93306)
* Es wurde ein Problem behoben, bei dem dynamische Berichtsdaten nach der Migration fehlten. (NEO-92962)
* Fehlerkorrektur - Der Versandstatus wird jetzt korrekt aktualisiert. (NEO-92908)
* Es wurde ein Problem im Zusammenhang mit der Databricks-FDA-Nutzungskatalogbeschränkung behoben. (NEO-92900)
* Fehlerkorrektur - HTML-Layout-Fehler auf dem Windows-Desktop von Outlook treten jetzt nicht mehr auf. (NEO-92611)
* Fehlerkorrektur - Die Datenintegrität funktioniert jetzt einwandfrei, wenn nach einem Upgrade Bereitstellungs-Primärschlüssel auf der Mid-Instanz dupliziert werden. (NEO-92424)
* Fehlerkorrektur - Links können jetzt im Dialogfeld Tracking &amp; Bilder in einem Versand deaktiviert werden. (NEO-92381)
* Es wurde ein Problem behoben, bei dem die Funktion nms.subscription.RecipientSubscribe() bei Massenabonnements nicht funktionierte. (NEO-92308)
* Fehlerkorrektur - Versandfehler treten jetzt nicht mehr auf, wenn Versandteile nach einem Upgrade fehlen. (NEO-92278)
* Fehlerkorrektur - Im Tracking-Workflow werden Tracking-Indikatoren jetzt zuverlässig aktualisiert, wenn doppelte Statusfehler und SQL-Syntaxfehler vorhanden sind. (NEO-92239)
* Es wurde ein Problem behoben, bei dem Auflistungsfeldbeschriftungen in über einen Workflow erstellten Listen fehlten oder falsch angezeigt wurden, wenn dbEnum-Felder verwendet wurden. (NEO-91158)
* Es wurde ein Problem behoben, bei dem das Dialogfeld zum Veröffentlichen/Rückgängigmachen der Veröffentlichung nicht geschlossen und eingefroren wurde. (NEO-91038)
* Fehlerkorrektur - Empfänger mit dem Status „Vom Dienstleister berücksichtigt“ haben jetzt keine Probleme mehr. (NEO-90927)
* Es wurde ein Problem behoben, bei dem die (Abmelde-)Herkunft für Opt-out-Links fehlte. (NEO-90714)
* Fehlerkorrektur - Beim Hinzufügen von Coupons ist die Versandvorbereitung nicht mehr fehlgeschlagen. (NEO-90547)
* Es wurde ein Problem behoben, bei dem die Anzahl der Einfüge-Zurückweisungen nicht korrekt auf der Registerkarte Audit angezeigt wurde. (NEO-90318)
* Es wurde ein Sicherheitsproblem behoben, das zu einer Diensteverweigerung führen konnte. (NEO-89984)
* Es wurde ein Problem behoben, bei dem die heruntergeladene PDF des Hotclick-Berichts fehlerhaft war. (NEO-89954)
* Es wurde ein SSL-Fehler behoben, der nach einem Upgrade auftrat und beim Lesen von Fehlern zu einem unerwarteten ENOF führte. (NEO-89108)
* Es wurde ein Problem behoben, bei dem nach einem Upgrade keine Daten in einem Datenschema abgefragt werden konnten. (NEO-88663)
* Fehlerkorrektur - Beim Verketten eines „char“-Felds in PostgreSQL 15 tritt jetzt kein Fehler mehr auf. (NEO-88028)
* Fehlerkorrektur - Beim Speichern oder Duplizieren der Vorlage ändert sich jetzt nicht mehr die Reihenfolge der Versandvorlagenvariablen. (NEO-87845)
* Es wurde ein Problem behoben, bei dem das Erstellen eines neuen Datenbibliotheksschemas zum Absturz der Web-Schnittstelle führte. (NEO-87816)
* Es wurde ein Problem behoben, bei dem in der Deduplizierungsaktivität mit Komplementsätzen verwendet wurde. (NEO-87711)
* Es wurde eine Anfrage für ein Installationspaket ohne X11-Abhängigkeit behoben. (NEO-87471)
* Es wurde ein Problem behoben, bei dem Segment-Codes nicht in dynamischen Berichten verwendet werden konnten. (NEO-87276)
* Es wurde ein Problem behoben, bei dem Workflows in der Aktivität Daten-Update hängen blieben. (NEO-87252)
* Es wurde ein Problem behoben, bei dem BigQuery eine falsche Zeitzone verwendete. (NEO-86622)
* Fehlerkorrektur - Bei der Auswertung des Skripts „mcSynch_mcExec1/jsReplicateUrl“ tritt jetzt kein JavaScript-Fehler mehr auf. (NEO-86553)
* Es wurde ein Problem behoben, bei dem aufgrund einer falschen Kennungsberechnungsmethode doppelte Ereignisse in der eventHistory-Tabelle auftraten. (NEO-86544)
* Es wurde ein Problem behoben, bei dem die Registerkarte Erweitert beim Kopieren für iOS Push nicht angezeigt wurde. (NEO-86231)
* Es wurde ein Problem behoben, bei dem der Workflow Referenztabellen replizieren beim Replizieren des nms:delivery-Schemas fehlschlug. (NEO-85884)
* Fehlerkorrektur - Beim Senden von Sendungen treten jetzt keine Domain-Fehler mehr auf, die den MXIP-Adressen entsprechen. (NEO-85238)
* Es wurde ein Problem behoben, bei dem technische Versandvorlagen nach Änderungen an Optionen nicht aktualisiert wurden. (NEO-84149)
* Fehlerkorrektur - Im vordefinierten Workflow Abrechnung tritt jetzt kein Fehler mehr auf. (NEO-83624)
* Es wurde ein Problem behoben, bei dem Duplikate nur anhand des Primärschlüssels der Zieldatensätze ausgeschlossen wurden. (NEO-82910)
* Es wurden Diskrepanzen in den Berichten der Web-Benutzeroberfläche von Campaign behoben, bei denen Tracking-Statistiken im Vergleich zur Konsole andere Werte angezeigt haben. (NEO-82339)
* Es wurde ein Problem behoben, bei dem sich das Datum der letzten Änderung auch dann änderte, wenn der Datensatz in der Aktivität Daten-Update nicht aktualisiert werden sollte. (NEO-82002)
* Es wurde ein Problem behoben, bei dem das Hinzufügen neuer Attribute zu einer Liste dazu führte, dass Workflows, die die Liste lesen, fehlschlugen. (NEO-80258)
* Es wurde ein Problem behoben, bei dem der Bericht Tracking-Indikatoren falsche Werte für einzelne Öffnungen anzeigte. (NEO-79466)
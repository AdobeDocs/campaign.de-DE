---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4fe8b8eaf88f763e796dbe06ef3c1477de12bad6
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 18%

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

Weitere Informationen finden Sie in den Versionshinweisen zur [&#x200B; Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=de){target="_blank"}

### Verbesserungen bezüglich der Sicherheit {#security-8-9-1}

* Externe Snowflake-Konten unterstützen jetzt die OAuth2-Authentifizierung und bieten moderne und sichere Authentifizierungsmethoden für Federated Data Access-Verbindungen. (NEO-87013)
* Fehlerkorrektur - Der Zugriff auf Workflow-Dateien erfolgt jetzt fehlerfrei, indem Vorgänge auf autorisierte Verzeichnisse beschränkt werden. Dadurch wird ein nicht autorisierter Zugriff und eine potenzielle Ausführung von Remote-Code verhindert. (NEO-88460)
* Es wurden Steuerelemente zur FTP-URL-Zulassungsauflistung zu Workflow-JavaScript-Code-Aktivitäten hinzugefügt, wodurch ausgehende FTP-Verbindungen auf autorisierte Adressen beschränkt werden. (NEO-89083)

### Sonstige Änderungen  {#changes-8-9-1}

* Verbessertes Container-Speichermanagement durch Implementierung automatischer Workflow-Einschränkungen unter Bedingungen mit hohem Arbeitsspeicher sowie intelligente Workflow-Neustart-Funktionen und Speicher-Leitplanken für unkritische Prozesse. (NEO-89041)
* Unterstützung für asymmetrische Verschlüsselungs- und Entschlüsselungsfunktionen in Campaign-Workflows hinzugefügt. (NEO-80257)
* Verbesserte Leistung des Replikationsagenten und verbesserte Speicherresilienz für große Datenuploads in FFDA-Bereitstellungen. (NEO-88430)


### Fehlerbehebungen {#fixes-8-9-1}

* Es wurde ein Problem behoben, bei dem die Datenbankstruktur nach sysFilter-Änderungen nicht aktualisiert werden konnte. (NEO-93306)
* Es wurde ein Problem behoben, bei dem dynamische Berichtsdaten nach der Migration fehlten. (NEO-92962)
* Fehlerkorrektur - Der Versandstatus wird jetzt korrekt aktualisiert. (NEO-92908)
* Es wurde eine Problemumgehung für Datenblöcke hinzugefügt, die die Katalogeinschränkung FDA-Verwendung verwenden. (NEO-92900)
* Es wurde ein Problem behoben, bei dem das HTML-Layout auf dem Windows Outlook-Desktop durch den Visual Editor beschädigt wurde. (NEO-92611)
* Es wurde ein kritisches Problem mit der Datenintegrität behoben, bei dem Bereitstellungs-Primärschlüssel auf der Mid-Instanz nach dem Upgrade dupliziert wurden. (NEO-92424)
* Fehlerkorrektur - Links können jetzt im Dialogfeld Tracking und Bilder in einem Versand deaktiviert werden. (NEO-92381)
* Fehlerkorrektur - Die Funktion nms.subscription.RecipientSubscribe() funktioniert jetzt auch bei Massenabonnements. (NEO-92308)
* Fehlerkorrektur - Versandfehler treten jetzt nicht mehr auf, wenn Versandteile nach dem Upgrade fehlen. (NEO-92278)
* Fehlerkorrektur - Der Tracking-Workflow funktioniert jetzt einwandfrei. (NEO-92239)
* Es wurde ein Problem behoben, bei dem nach der Erstellung einer Liste mithilfe eines Workflows temporäre Aufzählungsreferenzen in der XML-Liste fehlten. (NEO-91158)
* Es wurde ein Problem behoben, bei dem das Dialogfeld Veröffentlichen/Veröffentlichung rückgängig machen nicht geschlossen und eingefroren wurde. (NEO-91038)
* Es wurde ein Problem behoben, bei dem Empfängerinnen und Empfänger, die den Status „Vom Dienstleister berücksichtigt“ nicht erreichten, Momentum nicht erreichten. (NEO-90927)
* Es wurde ein Problem behoben, bei dem in v8 für Opt-out-Links der Ursprung (Abmeldung) fehlte. (NEO-90714)
* Fehlerkorrektur - Das Hinzufügen von Coupons schlägt bei der Versandvorbereitung fehl. (NEO-90547)
* Es wurde ein Problem behoben, bei dem die Anzahl der Einfüge-Zurückweisungen nicht korrekt auf der Registerkarte Audit angezeigt wurde. (NEO-90318)
* Es wurde ein Sicherheitsproblem behoben, das zu einem Denial of Service der Anwendung führen konnte. (NEO-89984)
* Es wurde ein Problem behoben, bei dem die heruntergeladene PDF des Hotclick-Berichts fehlerhaft war. (NEO-89954)
* Es wurde ein SSL-Fehler behoben, der nach dem Upgrade auftrat und beim Lesen von Fehlern zu einem unerwarteten ENOF führte. (NEO-89108)
* Es wurde ein Problem behoben, bei dem Daten nach einem Upgrade nicht im Datenschema abgefragt werden konnten. (NEO-88663)
* Fehlerkorrektur - Beim Verketten eines „char“-Felds in PostgreSQL 15 tritt jetzt kein Fehler mehr auf. (NEO-88028)
* Fehlerkorrektur - Beim Speichern oder Duplizieren der Vorlage ändert sich jetzt nicht mehr die Reihenfolge der Versandvorlagenvariablen. (NEO-87845)
* Es wurde ein Problem behoben, bei dem das Erstellen eines neuen Datenbibliotheksschemas zum Absturz der Web-Schnittstelle führte. (NEO-87816)
* Es wurde ein Problem behoben, bei dem der Komplement-Set-Segment-Code der Deduplizierungsaktivität nicht funktionierte. (NEO-87711)
* Es wurde eine Anfrage für ein Installationspaket ohne X11-Abhängigkeit behoben. (NEO-87471)
* Es wurde ein Problem behoben, bei dem Segment-Codes nicht in dynamischen Berichten verwendet werden konnten. (NEO-87276)
* Es wurde ein Problem behoben, bei dem Workflows in der Aktivität Daten-Update hängen blieben. (NEO-87252)
* Es wurde ein Problem behoben, bei dem BigQuery eine falsche Zeitzone verwendete. (NEO-86622)
* Es wurde ein JavaScript-Fehler bei der Auswertung des Skripts „mcSynch_mcExec1/jsReplicateUrl“ korrigiert. (NEO-86553)
* Es wurde ein Problem behoben, bei dem aufgrund einer Kennungsberechnungsmethode doppelte Ereignisse in der eventHistory-Tabelle angezeigt wurden. (NEO-86544)
* Es wurde ein Problem behoben, bei dem die Registerkarte Erweitert beim Kopieren für iOS Push nicht angezeigt wurde. (NEO-86231)
* Es wurde ein Problem behoben, bei dem der Workflow Referenztabellen replizieren beim Replizieren des nms:delivery-Schemas fehlgeschlagen ist. (NEO-85884)
* Fehlerkorrektur - Beim Senden von Sendungen treten jetzt keine Domain-Fehler mehr auf, die den MXIP-Adressen entsprechen. (NEO-85238)
* Es wurde eine Möglichkeit hinzugefügt, technische Versandvorlagen nach allen Änderungen zu aktualisieren, die an Optionen vorgenommen wurden. (NEO-84149)
* Fehlerkorrektur - Im vordefinierten Workflow Abrechnung tritt jetzt kein Fehler mehr auf. (NEO-83624)
* Es wurde ein Problem behoben, bei dem Duplikate nur anhand des Primärschlüssels der Zieldatensätze ausgeschlossen wurden. (NEO-82910)
* Es wurden Diskrepanzen in den Berichten der Web-Benutzeroberfläche von Campaign behoben, bei denen Tracking-Statistiken im Vergleich zur Konsole andere Werte angezeigt haben. Die Berichte Tracking-Indikatoren, Versandzusammenfassung und URL-Clickstreams zeigen jetzt über beide Schnittstellen hinweg konsistente Metriken an. (NEO-82339)
* Es wurde ein Problem behoben, bei dem sich das Datum der letzten Änderung auch dann änderte, wenn der Datensatz in der Aktivität Daten-Update nicht aktualisiert werden sollte. (NEO-82002)
* Es wurde ein Problem behoben, bei dem das Hinzufügen neuer Attribute in einer Liste dazu führte, dass Workflows, die die Liste lesen, fehlschlugen. (NEO-80258)
* Anomalie im Bericht „Tracking-Indikatoren“ behoben. (NEO-79466)
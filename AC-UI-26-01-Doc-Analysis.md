---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 Dokumentationsanalyse

## Inhalt der nächsten Version

In diesem Dokument werden Produkt-JIRAs für die monatlichen Versionen AC-UI-26-01 und AC-UI-25-11 analysiert, um Dokumentationsaktionen zu planen.

### JIRA-Filter

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Hauptveröffentlichungen
2. **[NEO-92400 Verbesserungen](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - Versionsverbesserungen Verknüpfte Probleme
3. **[AC-UI-25-11-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Übertrag der vorherigen Version
4. **[AC-UI-25-11 mit Ausnahme von 8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** - Gefilterte vorherige Version

&#x200B;---

## 🟢 DOCAC erstellen

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - Unterstützung für Personalisierungsfelder hinzufügen (erweiterte AEM-Integration)**Status:** aufgelöst\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** None\**Aktion:** DOCAC erstellen

**Anwendungsbereich:**
- Dokumentenunterstützung für Personalisierungsfelder in der erweiterten AEM-Integration
- Workflow- und Konfigurationsschritte der Benutzeroberfläche
- Mehrsprachige AEM-Integrationsfunktionen

**Funktionsbeschreibung:**
Unterstützung für das Hinzufügen von Personalisierungsfeldern in Sendungen mithilfe der erweiterten AEM-Integration, die das Einfügen dynamischer Inhalte aus Campaign-Daten in von AEM erstellte E-Mail-Vorlagen ermöglicht.

**Kontext:** ACS zu ACC-Parität, MSFT-spezifische Anforderung

**Verweise:** [Mehrsprachiges AEM-Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - Berechnungsprozess für die Versandplanung (ACS-Parität)**status:** Neu\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** None\**Aktion:** DOCAC erstellen

**Anwendungsbereich:**
- Prozess zur Berechnung der Versandplanung für Push-Benachrichtigungen
- Zeitzonenbasierte Zeitplanformeln
- Datei-Upload für Targeting mit mehreren Zeitzonen

**Funktionsbeschreibung:**
Aktivieren Sie die vorkonfigurierte dateibasierte Versandplanung mit berechneten Versandzeiten basierend auf der Zeitzone des Empfängers, sodass ein Versand über mehrere Zeitzonen hinweg mit optimierten Versandzeiten pro Region durchgeführt werden kann.

**Kontext:** Kundengesteuert (H&amp;M), ACS zu ACC-Paritätsanforderung

**Verweise:** [ACS-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## 🔄 DOCAC aktualisieren

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) - Verfügbarkeit von dynamischen Berichten für alle Benutzer der Web-Benutzeroberfläche&#x200B;**Status:** in Bearbeitung\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) (geschlossen), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) (aufgelöst)\**Aktion:** DOCAC überprüfen

**Anwendungsbereich:**
- Informationen zur Verfügbarkeit aktualisieren (jetzt für alle Benutzer der Web-Benutzeroberfläche, nicht nur für 8.7)
- Einschränkungen bei Dokumentsprachen
- Klärung der Anzeige von Konfliktmetriken mit veralteten Berichten

**Funktionsbeschreibung:**
Die dynamische Berichterstellung ist jetzt für alle Benutzenden der Campaign Web-Benutzeroberfläche verfügbar (zuvor auf 8.7 ACS für ACC-Kunden beschränkt) und bietet erweiterte Analyse- und benutzerdefinierte Berichtsfunktionen mit einer ACS-ähnlichen Oberfläche.

**Kontext:** Funktionserweiterung, Backend-Build-Abhängigkeit (8.8.1)

**Verweise:** [Wiki - Vergleich von Berichten](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - A/B-Tests&#x200B;**Status:** in Bearbeitung\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) (neu)\**Aktion:** DOCAC aktualisieren

**Anwendungsbereich:**
- Vollständige Dokumentation zum Workflow für A/B-Tests
- Einrichtung und Konfiguration von Inhaltsexperimenten
- Definition des Stichprobenanteils und Auswahlkriterien für den Gewinner
- Erhebung und Auswertung von Statistiken

**Funktionsbeschreibung:**
Inhaltsexperimente und A/B-Tests für E-Mail-Sendungen ermöglichen es Marketing-Experten, verschiedene Inhaltsvarianten zu testen, Stichprobengrößen zu definieren, Leistungsstatistiken zu sammeln und die erfolgreichste Variante automatisch an die verbleibenden Empfangenden zu senden.

**Kontext:** Europa-Projekt, Microsoft-Anforderung, Feature Flag aktiviert

**Referenzen:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [Figma mocks](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) - Erstellung von Schemata (neue Tabelle erstellen, Schemata erweitern, auf externe DB zugreifen)**Status:** in Bearbeitung\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) (neu)\**Aktion:** DOCAC aktualisieren

**Anwendungsbereich:**
- Workflow zum Erstellen von Dokumentschemata (nur 3 Optionen: Tabelle erstellen, Schema erweitern, Zugriff auf externe DB)
- Formulardefinition für benutzerdefinierte Entitäten
- Navigieren und CRUD-Vorgänge für benutzerdefinierte Schemata
- Funktionen der Phasen 2 und 3

**Funktionsbeschreibung:**
Funktionen zum Erstellen von Schemata in der Web-Benutzeroberfläche, mit denen Admins neue Datenbanktabellen erstellen, vorhandene Schemata mit benutzerdefinierten Feldern erweitern und eine Verbindung zu externen Datenbanken herstellen können - wichtig für die Anpassung von Datenmodellen.

**Kontext:** Microsoft-Anforderung, Europa-Projekt, schrittweise Bereitstellung (Phase 2 aktiv, Phase 3, Ende Februar)

**Verweise:** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - Web-Analyse&#x200B;**status:** Neu\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** None\**Aktion:** DOCAC erstellen

**Anwendungsbereich:**
- Konfiguration des externen Web-Analytics-Kontos
- Einrichtung und Authentifizierung der Integration
- Analytics-Datennutzung in Kampagnen

**Funktionsbeschreibung:**
Web Analytics-Integration, die die Verbindung zu Web-Analyseplattformen ermöglicht, um die Kampagnenleistung und das Verhalten der Website-Besucher zu verfolgen und darüber zu berichten.

**Kontext:** Kundenanfrage (P2E-RSC), Verfügbarkeit der Umgebung ausstehend

**Verweise:** nicht angegeben

&#x200B;---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) - AEM-Integration für Live Copies/Sprachkopien&#x200B;**status:** Neu\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) (aufgelöst)\**Aktion:** DOCAC überprüfen

**Anwendungsbereich:**
- Durchsuchen von AEM-Versandvorlagen
- Erstellen von Live Copies und Sprachkopien mit einem Klick
- Workflow zur Erstellung mehrsprachiger Inhaltsvarianten

**Funktionsbeschreibung:**
Die optimierte AEM-Integration ermöglicht die Erstellung von Live Copies und Sprachkopien aus AEM-Versandvorlagen mit einem Klick und vereinfacht die Erstellung mehrsprachiger Kampagnen für AEM-Benutzende.

**Kontext:** Anforderung an Microsoft, Arbeit an Himanshus Team übertragen

**Verweise:** [ACS-Dokumentation](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

&#x200B;---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - Inhaltseditor: Verwenden von Design-Variablen in Fragmenten&#x200B;**status:** Neu\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) (neu)\**Aktion:** DOCAC aktualisieren

**Anwendungsbereich:**
- Designvariablen in Email Designer (Beta)
- Verwenden von Designs in Fragmenten
- Aktive Funktionsaktivierung

**Funktionsbeschreibung:**
Unterstützung für die Verwendung von Design-Variablen in Inhaltsfragmenten, um konsistentes Branding und Design von Systemanwendungen für E-Mail-Komponenten mit zentralisiertem Design-Management zu ermöglichen.

**Kontext:** Halten, die Acrite-Funktion soll erneut aufgerufen werden

**Verweise:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕ Erstellen von DOCAC (Verbesserungen)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - Vordefinierte Filter - Option „Freigegeben“**Status:** aufgelöst\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) (Code-Überprüfung), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) (geschlossen - Helper)\**Aktion:** DOCAC überprüfen

**Anwendungsbereich:**
- Freigegebene Option für vordefinierte Filter
- Sichtbarkeit mit anderen Benutzern filtern (ACC vs. Brand Journey-Verhalten)
- Benutzerverwaltung freigegebener Filter

**Funktionsbeschreibung:**
Vordefinierte Filter können jetzt als „freigegeben“ markiert werden, um sie für andere Benutzende sichtbar zu machen, wobei sich das Verhalten für ACC (Standard) und Brand Journey (benutzerspezifische Filterung) unterscheidet.

**Kontext:** Verbesserung des Regel-Builders, Feature Flag: enable-query-filter-shared

**Verweise:** mit Bezug zu [NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)

&#x200B;---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - Kontinuierliche Versandaktivität&#x200B;**status:** closed\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) (Neu), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) (Geschlossen - Kontextuelle Hilfe)\**Aktion:** DOCAC aktualisieren

**Anwendungsbereich:**
- Workflow-Aktivität „Fortlaufender Versand“
- Konfiguration der Auswahl von Versandvorlagen
- Automatische Erzeugung ausgehender Transitionen
- Zielgruppenbestimmungsoptionen (kein Inhaltszugriff)

**Funktionsbeschreibung:**
Die Aktivität „Kontinuierlicher Versand“ für Workflows ermöglicht die wiederholte Ausführung von Sendungen aus Vorlagen und generiert automatisch ausgehende Transitionen für die Workflow-Orchestrierung ohne Inhaltsänderung.

**Kontext:** Feature Flag: enable-continuous-delivery

**Verweise:** Verwandtes Epos [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) - OOTB-Datei-Upload für mehrsprachige Push-Benachrichtigungen aktivieren&#x200B;**status:** closed\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) (neu)\**Aktion:** DOCAC aktualisieren

**Anwendungsbereich:**
- Datei-Upload für mehrsprachige Push-Benachrichtigungen (iOS und Android)
- CSV-Format und Feldzuordnung
- Rich-Push-Unterstützung mit mehrsprachigen Funktionen

**Funktionsbeschreibung:**
OOTB-Datei-Upload-Funktion zur Erstellung von mehrsprachigen Push-Benachrichtigungs-Sendungen über CSV-Import, Abgleich der ACS-Funktionen und Ermöglichung einer effizienten mehrsprachigen Kampagnenkonfiguration.

**Kontext:** Kundengesteuert (H&amp;M), Parität von ACS zu ACC, wichtig für die Migration

**Verweise:** [ACS-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌ storniert/nicht mehr anwendbar

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) - Unterstützung für CTA-Tracking in der Web-Benutzeroberfläche&#x200B;**status:** Geschlossen (gilt nicht mehr)\**Dokument erforderlich:** Nein\**Vorhandenes DOCAC:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) (neu)\**Aktion:** Schließen DOCAC

**Grund:** neue ACS-Funktion zur Unterstützung von MSFT - nicht gestartet, ausstehende Informationen von MSFT, keine Arbeit in der Benutzeroberfläche erwartet

**Kontext:** Microsoft-spezifisch, CTA-Tracking-Anforderung

&#x200B;---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - Unterstützung der mehrsprachigen Benutzeroberfläche von AEM&#x200B;**status:** Geschlossen (gilt nicht mehr)\**Dokument erforderlich:** Nein\**Vorhandenes DOCAC:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) (neu)\**Aktion:** Schließen DOCAC

**Grund:** von Himanshus Team verwaltete UI-Arbeit (andere Story)

**Kontext:** Microsoft-Anforderung, übertragene Arbeit

&#x200B;---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - Unterstützung für NRT-Funktion hinzufügen&#x200B;**Status:** aufgelöst (gilt nicht mehr)\**Dokument erforderlich:** Nein\**Vorhandenes DOCAC:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) (neu)\**Aktion:** Schließen DOCAC

**Grund:** neue ACS-spezifische Funktion für MSFT - Spezifikation verfügbar, aber keine Auswirkung auf die Web-Benutzeroberfläche

**Kontext:** Microsoft-Anforderung, Transaktionsnachrichten

&#x200B;---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) - Transaktions-REST-API für profilbasierte Anreicherung&#x200B;**Status:** aufgelöst (gilt nicht mehr)\**Dokument erforderlich:** Nein\**Vorhandenes DOCAC:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) (neu)\**Aktion:** Schließen DOCAC

**Grund:** Web-Benutzeroberfläche funktioniert nicht, Instanz-Upgrade steht aus, Build-Upgrade für Veröffentlichung obligatorisch

**Kontext:** REST-API-Endpunktfunktion

&#x200B;---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - Profilbasierte Anreicherung - Transaktionsnachrichten Phase 2&#x200B;**Status:** aufgelöst (gilt nicht mehr)\**Dokument erforderlich:** Nein\**Vorhandenes DOCAC:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) (neu)\**Aktion:** Schließen DOCAC

**Grund:** Story hat keine Aufgaben, markiert als „gilt nicht mehr“

**Kontext:** Microsoft-Anforderung, Projekt Europa

&#x200B;---

## 🟢 Dokumentation bereit (von AC-UI-25-11)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - Mehrsprachiger Rich-Push - Benutzeroberfläche&#x200B;**status:** closed\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) (neu)\**Aktion:** DOCAC überprüfen

**Anwendungsbereich:**
- Rich-Push-Felder für mehrsprachige Sendungen
- Plattformunterstützung für iOS und Android
- Vorlagen- und Inhaltskonfiguration

**Funktionsbeschreibung:**
Rich-Push-Benachrichtigung unterstützt mehrsprachige Funktionen, mit denen Marketing-Experten erweiterte Push-Benachrichtigungen mit Bildern, Schaltflächen und Rich-Media für iOS und Android in mehreren Sprachen erstellen können.

**Kontext:** Kundengesteuert (H&amp;M), bereitgestellt in 25-11, Backend-Arbeit abgeschlossen

**Verweise:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) - Einrichten und Verwalten des Genehmigungsprozesses&#x200B;**Status:** aufgelöst\**Dokument erforderlich:** Ja\**Vorhandenes DOCAC:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) (neu)\**Aktion:** DOCAC aktualisieren

**Anwendungsbereich:**
- Konfigurieren von Validierungsoperatoren in Versand/Kampagne
- Einrichtung des Validierungs-Workflows
- Genehmigungsprozess für Inhalte und Zielgruppen
- Multi-Channel-Support (E-Mail, SMS, Push, Briefpost, Callcenter, benutzerdefiniert)

**Funktionsbeschreibung:**
Validierungsprozess-Management ermöglicht Validierungs-Workflows für Versandinhalt und Zielgruppenbestimmung mit Benutzerzuweisung und Validierungs-Tracking über alle Versandkanäle hinweg.

**Kontext:** Kundengesteuert (Pierre Fabre), Microsoft-Anforderung, Entwicklung abgeschlossen und im Testmodus

**Referenzen:** [Klassische Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [Figma mocks](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## Zusammenfassung nach Aktion 📊

| Aktion | Count |
|--------|-------|
| 🟢 DOCAC erstellen | 3 |
| 🔄 DOCAC aktualisieren | 6 |
| ✅ DOCAC | 3 |
| ❌ DOCAC schließen | 5 |
| **Insgesamt** | **17** |

&#x200B;---

## Offene Fragen ⚠️

1. NEO-93487 - H&amp;M-Eskalation - Erfordert dringende Aufmerksamkeit für die Planung von Rechenprozessen
2. NEO-92668 - Web Analytics - Warten auf Umgebungsverfügbarkeit, bevor die Dokumentation abgeschlossen werden kann
3. NEO-76126 - Schemas Phase 3 - Ende ETA Februar, separate Dokumentations-Story erforderlich
4. NEO-88838 - Design-Variablen - Ausstehende Acrite-Funktionsrevision wird zurückgestellt
5. Dynamische Berichterstellung - Klärung der Anleitung zur Anzeige von Konfliktmetriken mit veralteten Berichten

&#x200B;---

## 🔗-bezogene Epen

- NEO-85263 - ACS zu ACC (EUROPA) Elternepos
- NEO-67972 - Workflow-Verbesserungen
- NEO-87980 - Erweiterte AEM-Integration
- NEO-90199 - Bereitschaft für Dynamic Reporting-Versionen
- NEO-63067 - Inhaltsexperimentierung (UX/UI)
- NEO-67726 - A/B-Tests und Inhaltsexperimente
- NEO-85274 - Schema und Formular (Phase 2)
- NEO-87993 - Schema und Formular (Phase 3)

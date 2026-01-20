---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 3%

---
# AC-UI Jira-Ticketanalyse - Arbeitszusammenfassung
**Datum:** 12. Januar 2026
**Dokumenttyp:** Arbeitsdokument/Interne Analyse

---

## Zusammenfassung

In diesem Dokument werden Produkt-Jira-Tickets aus mehreren Abfragen im Zusammenhang mit AC-UI-Versionen (Januar 2026 und November 2025) analysiert. Die Analyse konzentriert sich auf die Identifizierung von Dokumentationsanforderungen, die Vorlage von DOCAC-Tickets und die Hervorhebung offener Fragen.

**Eindeutige Tickets insgesamt analysiert:** 19
**Tickets, für die Unterlagen erforderlich sind:** 14
**Tickets bereits dokumentiert:** 5
**Tickets ohne Dokumentbedarf:** 5

---

## &#x200B;1. Liste der analysierten Tickets

### 1.1 AC-UI-26-01-Monthly Release (Januar 2026)

| Ticket-ID | Title | Status | Priorität | Komponenten |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [Web-Benutzeroberfläche] Unterstützung für Personalisierungsfelder hinzufügen (Erweiterte AEM-Integration) | Aufgelöst | Normal | ACS zu ACC, PIX UI/UX |
| NEO-80973 | Verfügbarkeit von dynamischen Berichten für alle Benutzer der Web-Benutzeroberfläche | Bearbeitung läuft | Normal | ACS zu ACC, PIX UI/UX |
| NEO-86754 | [UX/UI] A/B-Tests | Bearbeitung läuft | Blocker | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-76126 | Erstellen von Schemata : Erstellen einer neuen Tabelle, Erweitern von Schemata und Zugreifen auf externe Datenbanken | Bearbeitung läuft | Kritisch | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-93487 | [Web-Benutzeroberfläche] Berechnungsprozess für die Versandplanung ähnlich dem in ACS | Neu | Kritisch | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-92400 | Versionsverbesserungen - 26. Januar | Neu | Normal | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-88838 | Inhaltseditor: Verwenden von Design-Variablen in Fragmenten | Neu | Normal | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-92668 | [UX/UI] Web Analytics | Neu | Normal | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-86753 | [UX/UI] AEM-Integration für Live Copies/Sprachkopien | Neu | Blocker | ACS zu ACC, PIX UI/UX |

### 1.2 Versionsverbesserungen Verknüpfte Tickets (NEO-92400)

| Ticket-ID | Title | Status | Priorität | Komponenten |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [Rule Builder] Vordefinierte Filter - Option „Freigegeben“ | Aufgelöst | Normal | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-91299 | Web-Benutzeroberfläche - Aktivität „Fortlaufender Versand“ | Geschlossen | Wesentlich | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-90130 | OOTB-Datei-Upload für mehrsprachigen Push-Benachrichtigungs-Versand aktivieren | Geschlossen | Kritisch | ACS zu ACC, PIX UI/UX |

### 1.3 AC-UI-25-11-Monthly Release (November 2025)

| Ticket-ID | Title | Status | Priorität | Komponenten |
|-----------|-------|--------|----------|------------|
| NEO-91566 | [Web-Benutzeroberfläche] Unterstützung für CTA-Tracking in der Web-Benutzeroberfläche | Geschlossen | Normal | ACS zu ACC, PIX UI/UX |
| NEO-91564 | [Web-Benutzeroberfläche] [Mehrsprachige AEM in ACC]-Benutzeroberfläche Unterstützung für mehrsprachige AEM | Geschlossen | Normal | ACS zu ACC, PIX UI/UX |
| NEO-90183 | [UX/UI] Mehrsprachiger Rich-Push - Benutzeroberfläche | Geschlossen | Blocker | PIX-BENUTZEROBERFLÄCHE/UX |
| NEO-91567 | [Web-Benutzeroberfläche] Unterstützung für NRT-Funktion hinzufügen | Aufgelöst | Normal | ACS zu ACC, PIX UI/UX |
| NEO-91563 | Transaktions-REST-API für profilbasierte Anreicherung - Web-Benutzeroberfläche | Aufgelöst | Normal | ACS zu ACC, PIX UI/UX |
| NEO-92151 | [UI/UX] Profilbasierte Anreicherung Transaktionsnachrichten - Phase 2 | Aufgelöst | Wesentlich | ACS zu ACC, PIX UI/UX |
| NEO-84916 | [UX/UI] Einrichten und Verwalten des Genehmigungsprozesses | Aufgelöst | Kritisch | PIX-BENUTZEROBERFLÄCHE/UX |

---

## &#x200B;2. Tickets, für die Unterlagen erforderlich sind

### 2.1 HOHE PRIORITÄT - Aktive Entwicklung (AC-UI-26-01)

#### **NEO-86754: A/B-Tests**
- **Status:** läuft (auf Kurs)
- **Bedarf an Dokumentation:** Wichtige neue Funktion für E-Mail-Inhaltsexperimente mit A/B-Testfunktionen
- **Vorhandenes DOCAC:** DOCAC-13104 (neuer Status)
- **Dokumentationsumfang:**
   - Erstellen von A/B-Testexperimenten in Sendungen
   - Definieren von Inhalts-/Bereitstellungsvarianten
   - Festlegen der Stichprobenanteile und Senden von Testvarianten
   - Auswertungskriterien definieren
   - Analyse der Experimentergebnisse und Auswahl der Gewinner
   - Best Practices und Einschränkungen
- **Zielgruppe:** Marketing-Benutzer, Kampagnen-Manager
- **Version:** 8.9.1, AC-UI-26-01-Monthly
- **Offene Fragen:**
   - Endgültiger UI/UX-Validierungsstatus?
   - Gibt es Einschränkungen für Transaktionsnachrichten?
   - Integration mit der Acrobat-Inhaltsvorschau?

#### **NEO-80973: Verfügbarkeit von dynamischen Berichten**
- **Status:** in Bearbeitung (Bereit für Überprüfung)
- **Bedarf an Dokumentation:** Erweiterung des dynamischen Reportings auf alle Benutzer der Web-Benutzeroberfläche (nicht nur 8.7 ACS für ACC-Kunden)
- **Vorhandenes DOCAC:** DOCAC-11070 (geschlossen), DOCAC-13432 (Gelöst - Sprachbeschränkungen)
- **Dokumentationsumfang:**
   - Verfügbarkeits- und Zugriffsanforderungen
   - Dokumentation zu unterstützten Sprachen
   - Bekannte Einschränkungen vs. veraltete Berichterstellung
   - Anzeige widersprüchlicher Metriken mit veralteten Berichten
   - Einrichtung der Demo-Umgebung
- **Target-Zielgruppe** Alle Benutzer, Analysten und Benutzer der Web-Benutzeroberfläche
- **Version:** 8.8.1, AC-UI-26-01-Monthly
- **Offene Fragen:**
   - Verfügbarkeitsstatus der Demo-Umgebung?
   - Vollständige Liste der widersprüchlichen Metriken mit veralteten Berichten?
   - Sprachunterstützungsmatrix?

#### **NEO-76126: Schemata werden erstellt**
- **Status:** läuft (auf Kurs)
- **Bedarf an Dokumentation:** wichtige Administratorfunktion für die Verwaltung von Datenmodellen
- **Vorhandenes DOCAC:** DOCAC-13826 (neuer Status)
- **Dokumentationsumfang:**
   - Erstellen neuer Tabellen
   - Erweitern vorhandener Schemata
   - Zugriff auf externe Datenbanken
   - Formulardefinition für benutzerdefinierte Entitäten
   - Navigation und CRUD-Vorgänge
   - Phase 3-Funktionen (Erstellen und Erweitern von Schemata) - ETA Februar
- **Target-Zielgruppe:** Admin-Benutzer, technische Administratoren
- **Version:** AC-UI-26-01-Monthly
- **Fälligkeitsdatum:** 28. Februar 2026
- **Offene Fragen:**
   - Wann wird Phase 2 für die FF-Aktivierung abgeschlossen sein?
   - Versandzeitplan der Phase 3 bestätigen?
   - Einrichten der Umgebung - Anforderungen?

#### **NEO-93487: Versandplanungs-Berechnungsprozess (H&amp;M)**
- **status:** Neu
- **Bedarf an Dokumentation:** kritische Kundeneskalation - Zeitzonenbasierte Versandplanung
- **Vorhandenes DOCAC:** Keine identifiziert
- **Dokumentationsumfang:**
   - Versandplanung basierend auf der Zeitzone des Benutzers
   - Verwenden berechneter Formeln für Regionen mit mehreren Zeitzonen
   - Konfigurationsbeispiele (z. B. USA mit mehreren Zeitzonen)
   - Best Practices für globale Kampagnen
   - Funktionsvergleich mit ACS
- **Zielgruppe:** Kampagnen-Manager, Marketing-Benutzer
- **Kundenwirkung:** H&amp;M (über 50 Märkte)
- **Version:** 8.9.1, AC-UI-26-01-Monthly, 8.8.2.NEO-90300
- **Offene Fragen:**
   - Funktionsdemo mit PM geplant?
   - Vollständige Funktionsspezifikationen verfügbar?
   - UI-Mockups abgeschlossen?

#### **NEO-86753: AEM-Integration für Live Copies/Sprachkopien**
- **status:** Neu
- **Bedarf an Dokumentation:** Microsoft-spezifische Funktion für mehrsprachiges Inhaltsmanagement
- **Vorhandenes DOCAC:** DOCAC-13829 (aufgelöst)
- **Dokumentationsumfang:**
   - Durchsuchen von AEM-Versandvorlagen
   - Erstellen von Live Copies
   - Erstellen von Sprachkopien und Inhaltsvarianten
   - Workflow und Best Practices
   - Voraussetzungen für die Einrichtung der Integration
- **Target-Zielgruppe:** Marketing-Benutzer, die mit AEM- und Microsoft-Teams arbeiten
- **Version:** AC-UI-26-01-Monthly
- **priority:** Blocker
- **Offene Fragen:**
   - Arbeit in das Team von Himanshu übertragen - aktueller Status?
   - Zeitplan für den Abschluss?

#### **NEO-92668: Web-Analyse**
- **status:** Neu (auf Kurs)
- **Gründe für die Dokumentationsanforderung:** Konfiguration externer Konten für die Web-Analytics-Integration
- **Vorhandenes DOCAC:** Keine identifiziert
- **Dokumentationsumfang:**
   - Erstellung eines externen Web Analytics-Kontos
   - Konfigurationsparameter
   - Integration mit Versandverfolgung
   - Reporting-Funktionen
- **Target-Zielgruppe:** Admin-Benutzer, Marketing-Analysten
- **Version:** AC-UI-26-01-Monthly
- **Offene Fragen:**
   - Status der Umgebungsverfügbarkeit?
   - Erforderliche Einrichtungsschritte?

### 2.2 MEDIUM PRIORITY - Zuletzt bereitgestellt (AC-UI-25-11)

#### **NEO-90183: Mehrsprachiger Rich-Push**
- **status:** closed
- **Bedarf an Dokumentation:** neue Funktion für iOS/Android Rich Push mit mehrsprachiger Unterstützung
- **Vorhandenes DOCAC:** DOCAC-13565 (neuer Status)
- **Dokumentationsumfang:**
   - Rich-Push-Benachrichtigungskonfiguration für iOS und Android
   - Mehrsprachige Inhaltsvarianten
   - Vorlagenauswahl
   - Zusätzliche Felder für Rich-Content
   - Funktionen zum Hochladen von Dateien
   - Best Practices und Einschränkungen
- **Zielgruppe:** Marketing-Benutzer, Manager mobiler Kanäle
- **Version:** AC-UI-25-11-Monthly, 8.8.2
- **Kunde:** H&amp;M

#### **NEO-84916: Verwaltung von Genehmigungsprozessen**
- **Status:** aufgelöst
- **Bedarf an Dokumentation:** wichtige Workflow-Funktion für die Versandvalidierung
- **Vorhandenes DOCAC:** DOCAC-13827 (neuer Status)
- **Dokumentationsumfang:**
   - Einrichten von Validierungsverantwortlichen in Sendungen/Kampagnen
   - Konfigurieren der Inhaltsvalidierung
   - Zielgruppenvalidierung konfigurieren
   - Validierungs-Workflows kanalübergreifend verwalten (E-Mail, SMS, Push-iOS/Android, Briefpost, Callcenter)
   - Akzeptieren/Ablehnen von Prozessen
   - Reporting und Tracking von Genehmigungen
- **Zielgruppe:** Kampagnenmanager, Admin-Benutzer
- **Version:** AC-UI-25-11-Monthly
- **Priorität:** kritisch
- **Kunde:** Pierre Fabre

#### **NEO-91299: Kontinuierliche Versandaktivität**
- **status:** closed
- **Bedarf an Dokumentation:** neue Workflow-Aktivität für wiederkehrende Versandszenarien
- **Vorhandenes DOCAC:** DOCAC-13586 (neuer Status), DOCAC-13808 (geschlossen - kontextuelle Hilfe)
- **Dokumentationsumfang:**
   - Konfiguration der Aktivität „Fortlaufender Versand“
   - Anforderungen an die Auswahl von Versandvorlagen
   - Umgang mit Prozessfehlern
   - Workflow-Integration
   - Anwendungsfälle und Beispiele
- **Zielgruppe:** Technische Benutzer, Workflow-Designer
- **Version:** AC-UI-26.01.06

#### **NEO-90130: Mehrsprachiger Upload von Push-Dateien (H&amp;M)**
- **status:** closed
- **Bedarf an Dokumentation:** Parität der OOTB-Funktionen mit ACS für dateibasierte mehrsprachige Push-Benachrichtigungen
- **Vorhandenes DOCAC:** DOCAC-13606 (neuer Status)
- **Dokumentationsumfang:**
   - CSV-Datei zum Hochladen für mehrsprachige Push-Benachrichtigungen
   - Spezifikationen für Dateiformate
   - Feld-Mapping
   - Spezifische Konfigurationen für iOS und Android
   - Umgang mit Datennachrichten
   - Fehlerbehebung und bekannte Probleme
- **Zielgruppe:** Marketing-Benutzer, Kampagnen-Manager
- **Version:** AC-UI-25-10-Monthly, AC-UI-25.11.03
- **Priorität:** kritisch
- **Kunde:** H&amp;M (Migration von ACS zu ACC)

#### **NEO-92942: Vordefinierte Filter - Option „Freigegeben“**
- **Status:** aufgelöst
- **Bedarf an Dokumentation:** der Rule Builder-Funktionalität
- **Vorhandenes DOCAC:** DOCAC-13697 (Code-Prüfungsstatus), DOCAC-13522 (Geschlossen - Helper)
- **Dokumentationsumfang:**
   - Freigegebene Option für vordefinierte Filter
   - Verwalten der Filtersichtbarkeit mit anderen Benutzern
   - ACC vs. Brand Journey-Verhalten
   - Verwaltung von Filterlisten
- **Target-Zielgruppe** Alle Benutzer, Abfrage-Designer
- **release:** Hauptversion
- **FF:** enable-query-filter-shared

### 2.3 NIEDRIGE PRIORITÄT - Verbesserung des Inhaltseditors

#### **NEO-88838: Design-Variablen in Fragmenten**
- **status:** Neu (zurückgestellt)
- **Gründe für die Dokumentationsanforderung:** Funktion E-Mail an Designer-Design senden
- **Vorhandenes DOCAC:** DOCAC-12941 (neuer Status)
- **Dokumentationsumfang:**
   - Verwenden von Design-Variablen in E-Mail-Fragmenten
   - Design-Konfiguration
   - Variablenverwaltung
   - Best Practices
- **Zielgruppe:** E-Mail-Designer, Marketing-Benutzer
- **Version:** AC-UI-26-01-Monthly
- **Hinweis:** Funktion ist bis zum akriteseitigen erneuten Besuch zurückgestellt.

---

## &#x200B;3. Tickets, für die KEINE Dokumentation erforderlich ist

### 3.1 Storniert/Nicht mehr anwendbar

| Ticket-ID | Title | Grund |
|-----------|-------|--------|
| NEO-91566 | CTA-Tracking in der Web-Benutzeroberfläche | Keine UI-Arbeit erwartet; ausstehende Informationen von MSFT |
| NEO-91564 | Unterstützung der mehrsprachigen Benutzeroberfläche von AEM | Benutzeroberflächenarbeit wird von verschiedenen Teams verwaltet |
| NEO-91567 | NRT-Funktionsunterstützung | Keine Auswirkung auf die Web-Benutzeroberfläche; Spezifikation verfügbar |
| NEO-91563 | Transaktions-REST-API | Keine Funktion der Web-Benutzeroberfläche; Instanz-Upgrade steht aus |
| NEO-92151 | Profilanreicherung Phase 2 | Story hat keine Aufgaben; als nicht mehr zutreffend markiert |

### 3.2 Platzhalter/Tracking-Tickets

| Ticket-ID | Title | Grund |
|-----------|-------|--------|
| NEO-92400 | Versionsverbesserungen - 26. Januar | Platzhalter zum Nachverfolgen des Abschlusses von Verbesserungen |

---

## &#x200B;4. Vorgeschlagene DOCAC-Tickets

### 4.1 NEUE DOCAC-Tickets erforderlich

#### **DOCAC-XXXX: Versandplanung mit Zeitzonen-Unterstützung**
**Übergeordnetes Ticket:** NEO-93487
**Priorität:** kritisch
**Target-Version:** AC-UI-26-01-Monthly
**Beschreibung:**
Dokumentieren Sie den neuen Versandplanungs-Berechnungsprozess, der eine zeitzonenbasierte Versandplanung ermöglicht, ähnlich wie die ACS-Funktion. Mit dieser Funktion können Marketing-Fachleute mithilfe berechneter Formeln Nachrichten senden, die auf Zeitzonen der Empfänger basieren. Dies ist besonders für Märkte mit mehreren Zeitzonen wie die USA wichtig.

**Anwendungsbereich:**
- Konfigurationshandbuch für die Zeitzonen-basierte Planung
- Beispiele für berechnete Formeln
- Marktszenarien für mehrere Zeitzonen
- Migrationshandbuch von ACS
- Best Practices und Einschränkungen

**Kunde:** H&amp;M (Kritisch für Migration von ACS zu ACC)

#### **DOCAC-XXXX: Konfiguration des externen Web-Analytics-Kontos**
**Übergeordnetes Ticket:** NEO-92668
**Priorität:** normal
**Target-Version:** AC-UI-26-01-Monthly
**Beschreibung:**
Dokumentieren Sie die Konfiguration und Verwendung des externen Web-Analytics-Kontotyps in der Web-Benutzeroberfläche.

**Anwendungsbereich:**
- Schritte zur Erstellung externer Konten
- Konfigurationsparameter
- Integration mit Versandverfolgung
- Reporting-Funktionen
- Fehlerbehebung

---

### 4.2 VORHANDENE DOCAC-Tickets zur Aktualisierung

#### **DOCAC-13104: A/B-Tests**
**status:** Neu
**Übergeordnetes Ticket:** NEO-86754
**Erforderliche Aktion:**-Dokumentation - Funktion in aktiver Entwicklung
**Voraussichtliche Lieferung:** Februar 2026 (Abschluss der Entwicklung ausstehend)

#### **DOCAC-11070 &amp; DOCAC-13432: Dynamische Berichterstellung**
**Status:** Geschlossen/Gelöst
**Übergeordnetes Ticket:** NEO-80973
**Erforderliche Aktion:**
- Update für allgemeine Verfügbarkeit (nicht nur 8.7)
- Dokumentation widersprüchlicher Metriken mit veralteten Berichten
- Überprüfen der Dokumentation zur Sprachunterstützung

#### **DOCAC-13826: Schemas-Authoring**
**status:** Neu
**Übergeordnetes Ticket:** NEO-76126
**Erforderliche Aktion:**
- Dokumentation für Phase 2 (Navigation + CRUD + Formulardefinition)
- Vorbereiten für Phase 3 (Erstellen/Erweitern von Schemata) - Ende von ETA Feb

#### **DOCAC-13829: AEM Live Copies/Sprachkopien**
**Status:** aufgelöst
**Übergeordnetes Ticket:** NEO-86753
**Aktion erforderlich:** Überprüfen Sie den aktuellen Status und aktualisieren Sie ihn nach Bedarf

#### **DOCAC-13565: Mehrsprachiger Rich-Push**
**status:** Neu
**Übergeordnetes Ticket:** NEO-90183
**Aktion erforderlich:** Vollständige Dokumentation - Funktion bereitgestellt im November 2025

#### **DOCAC-13827: Genehmigungsprozess**
**status:** Neu
**Übergeordnetes Ticket:** NEO-84916
**Aktion erforderlich:** Vollständige Dokumentation - Funktion bereitgestellt im November 2025

#### **DOCAC-13586 &amp; DOCAC-13808: Kontinuierliche Lieferung**
**status:** Neu/Geschlossen
**Übergeordnetes Ticket:** NEO-91299
**Aktion erforderlich:** Hauptdokumentation (13586) - Funktion bereitgestellt

#### **DOCAC-13606: Mehrsprachiger Upload von Push-Dateien**
**status:** Neu
**Übergeordnetes Ticket:** NEO-90130
**Aktion erforderlich:** Dokumentation - Funktion bereitgestellt

#### **DOCAC-13697 &amp; DOCAC-13522: Vordefinierte Filter freigegeben**
**status:** Überprüfung/Abgeschlossen des Codes
**Übergeordnetes Ticket:** NEO-92942
**Aktion erforderlich:** Dokumentation abschließen (13697)

#### **DOCAC-12941: Designs in E-Mail Designer**
**status:** Neu
**Übergeordnetes Ticket:** NEO-88838
**Aktion erforderlich:** ausstehende Funktionswiederholungen zurückstellen

---

## &#x200B;5. Offene Fragen und fehlende Informationen

### 5.1 nach Funktion

#### **A/B-Tests (NEO-86754)**
- [ ] Was ist der endgültige UI/UX-Validierungsstatus?
- [ ] Gibt es bestimmte Einschränkungen für Transaktionsnachrichten?
- [ ] Wie lässt sich dies in die Acrite-Inhaltsvorschau integrieren (NEO-92516-Blockierung)?
- [ ] Welche Simulations-/Vorschaufunktionen gibt es in den einzelnen Varianten?

#### **Dynamisches Reporting (NEO-80973)**
- [ ] Was ist der Status der Demo-Umgebung-Reaktivierung?
- [ ] vollständige Liste der widersprüchlichen Metriken mit veralteten Berichten?
- [ ] detaillierte Matrix zur Sprachunterstützung?
- [ ] Leistungsvergleich mit veralteten Berichten?

#### **Erstellen von Schemata (NEO-76126)**
- [ ] Wann wird Phase 2 FF aktiviert?
- [ ] bestätigte ETA für Phase 3 (Schemata erstellen/erweitern)?
- [ ] Welche Anforderungen gelten für die Einrichtung der Umgebung?
- [ ] Einschränkungen im Vergleich zur Funktionalität der Client-Konsole?

#### **Versandplanung (NEO-93487)**
- [ ] Ist die Funktionsdemo mit PM geplant?
- [ ] Sind vollständige Funktionsspezifikationen verfügbar?
- [ ] UI-Mockups fertig gestellt und überprüft?
- [ ] Was ist die genaue Syntax/Struktur der Formel?

#### **AEM Live Copies/Sprachkopien (NEO-86753)**
- [ ] Was ist der aktuelle Stand in Himanshus Team?
- [ ] die Versandzeitleiste aktualisiert?
- [ ] Abhängigkeiten von der AEM-Version?

#### **Web-Analyse (NEO-92668)**
- [ ] Was ist der Verfügbarkeitsstatus der Umgebung?
- [ ] vollständige Setup-Anforderungen?
- [ ] Unterstützte Analyseplattformen?

#### **Designvariablen in Fragmenten (NEO-88838)**
- [ ] Wann wird Acrite die Funktion erneut aufrufen?
- [ ] Ist dies noch für AC-UI-26-01 geplant?

### 5.2 Nach Version

#### **AC-UI-26-01-Monthly (Januar 2026)**
- [ ] offizielle Bestätigung des Veröffentlichungsdatums?
- [ ] Datum für das Einfrieren von Funktionen?
- [ ] die Zeitleiste für den Abschluss von Tests?
- [ Lieferfrist für Dokumentation ]?

#### **Von November 2025 bereitgestellte Funktionen**
- [ ] Welche Funktionen sind bereits in der Produktion aktiviert?
- [ ] Gibt es bekannte Probleme oder Einschränkungen, die nach der Veröffentlichung entdeckt wurden?
- [ ] Kundenfeedback eingegangen?

### 5.3 Dokumentationsprozess

- [ ] Wer sind die SMEs für jede Funktion?
- [ ] Was ist der Prozess der Dokumentationsüberprüfung?
- [ ] Target-Dokumentationssprache (nur EN oder mehrsprachig)?
- [ ] Anforderungen an Dokumentationsplattform/Format?
- [ ] Screenshots und die Verfügbarkeit der Demo-Umgebung?

---

## &#x200B;6. Auswirkungen und Eskalationen auf den Kunden

### 6.1 Kritische Kunden-Tickets

| Kundin bzw. Kunde | Eintrittskarte | Funktion | Auswirkung |
|----------|--------|---------|--------|
| **H&amp;M** | NEO-93487 | Versandauslösung | Mehr als 50 Märkte; Anforderungen an die Bereitstellung in mehreren Zeitzonen; ACS zu ACC-Migrationsblocker |
| **H&amp;M** | NEO-90130 | Mehrsprachiger Push-Datei-Upload | Kritisch für die Migration von ACS zu ACC; reduziert Betriebskosten |
| **Pierre Fabre** | NEO-84916 | Genehmigungsprozess | Vorschriften und Workflow-Anforderungen |

### 6.2 Microsoft-spezifische Funktionen

| Eintrittskarte | Funktion | Status | Anmerkungen |
|--------|---------|--------|-------|
| NEO-86753 | AEM Live Copies/Sprachkopien | Neu | Starke Verwendung durch Microsoft |
| NEO-91566 | CTA-Tracking | Geschlossen/Nicht mehr anwendbar | Ausstehende Informationen von MSFT |
| NEO-91567 | NRT-Funktion | Aufgelöste/Keine Auswirkung auf die Benutzeroberfläche | Neue ACS-Funktion für MSFT |

---

## &#x200B;7. Dokumentationsprioritäten und Zeitplan

### 7.1 Sofortiges Handeln erforderlich (Januar 2026)

**HOHE PRIORITÄT - Bereitgestellt, aber nicht dokumentiert:**
1. **NEO-90183** - Mehrsprachiger Rich-Push (DOCAC-13565)
2. **NEO-84916** - Genehmigungsprozess (DOCAC-13827)
3. **NEO-91299** - Versand (DOCAC-13586)
4. **NEO-90130** - Mehrsprachiger Upload von Push-Dateien (DOCAC-13606)

### 7.2 In Bearbeitung - Entwicklung läuft (Februar-März 2026)

**KRITISCHE PRIORITÄT:**
1. **NEO-86754** - A/B-Tests (DOCAC-13104) - Fällig: Feb 2026
2. **NEO-76126** - Schemabearbeitung (DOCAC-13826) - Phase 2: Februar, Phase 3: Ende Februar
3. **NEO-93487** - Versandplanung (NEUES DOCAC) - Kritische Kundeneskalation

**NORMALE PRIORITÄT:**
1. **NEO-80973** - Dynamische Berichte (Aktualisieren von DOCAC-11070)
2. **NEO-92668** - Web-Analyse (NEUES DOCAC)
3. **NEO-86753** - AEM Live Copies/Sprachkopien (DOCAC-13829)

### 7.3 Zurückgestellt/Zukunft

1. **NEO-88838** - Design-Variablen (DOCAC-12941) - Wiederholungsbesuch für Acrite ausstehend

---

## &#x200B;8. Nächste Schritte

### 8.1 Dokumentations-Team-Aktionen
1. **Bereitgestellte Funktionen priorisieren** ohne Dokumentation (Abschnitt 7.1)
2. **Neue DOCAC-Tickets erstellen** für NEO-93487 und NEO-92668
3. **Aktualisieren vorhandener DOCAC**-Tickets mit detailliertem Umfang (Abschnitt 4.2)
4. **Planen von SME** Interviews für A/B-Tests, Schemata und Versandzeitplanung
5. **Sammeln von Screenshots** und Vorbereiten von Demo-Umgebungen
6. **Überprüfen und Abschließen** Sprachbeschränkungen für Dynamic Reporting

### 8.2 Informationssammlung
1. **Kontaktieren Sie die Engineering Leads**, um Statusaktualisierungen zu erhalten über:
   - Endgültige Validierung von A/B-Tests
   - Schemas Phase 2/3-Zeitleiste
   - Spezifikationen für die Versandplanung
2. **Planen von Funktionsdemos** mit Produktverwaltung
3. **Kundenfeedback einholen** von H&amp;M und Pierre Fabre
4. **Überprüfen der Umgebungsverfügbarkeit** für Web Analytics und Dynamic Reporting

### 8.3 Koordinierung
1. **Synchronisieren mit dem Team von Himanshu** auf AEM Live/Language Copies
2. **Koordinieren mit dem Acrite-Team** über den Status von Themenvariablen
3. **Follow-up zu Microsoft-spezifischen** mit dem Account-Team

---

## Dokumentenverlauf

| Datum | Autor | Version | Änderungen |
|------|--------|---------|---------|
| 12.01.2026 | KI-Assistent | 1,0 | Erste Analyse der Jira-Abfragen |

---

## Anhang: Jira-Abfragen analysiert

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Gesamtergebnisse:** 19 Einzeltickets analysiert


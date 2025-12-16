---
title: Häufig gestellte Fragen zu Campaign v8
description: Erhalten Sie Antworten auf häufig gestellte Fragen zu Adobe Campaign v8 hinsichtlich Einrichtung, Konfiguration, Messaging, Workflows und mehr
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, Fragen, Antworten, Hilfe, Support, Fehlerbehebung
version: Campaign v8
source-git-commit: 9c751429ac3da2a583990ba0d891744353bd65c8
workflow-type: tm+mt
source-wordcount: '10219'
ht-degree: 13%

---

# Häufig gestellte Fragen {#faq}

Erhalten Sie schnelle Antworten auf die häufigsten Fragen zu Adobe Campaign v8. Unabhängig davon, ob Sie gerade erst anfangen oder nach Hilfe zur erweiterten Konfiguration suchen, finden Sie Antworten, die nach Themen geordnet unten sind.

**Neu bei Campaign?** Erste Schritte mit [Erste Schritte](#getting-started) um das Wesentliche zu lernen.\
**Benötigen Sie Hilfe zu Versionen?** Informationen zur Version [&#x200B; Upgrades &#x200B;](#upgrades) Sie auf Upgrades.\
**Migration von v7 oder Standard?** Informationen zu Unterschieden [&#x200B; Übergangsanleitungen finden Sie unter &#x200B;](#v7-differences)Campaign v8 und frühere Versionen“.\
**Benötigen Sie technische Hilfe?** Überprüfen Sie [Entwickler](#developers) und [Kampagneneinstellungen](#settings).\
**Finden Sie keine Antwort?** Besuchen Sie unsere [Community-Foren](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"} oder [Support kontaktieren](#get-help).

**Tipp** Verwenden Sie Strg+F (Befehl+F auf Mac), um auf dieser Seite nach bestimmten Keywords zu suchen. Klicken Sie auf eine Frage, um die Antwort zu erweitern.


## Erste Schritte {#getting-started}

Lernen Sie die Grundlagen zur Arbeit mit Adobe Campaign v8 kennen, von der Installation und Verbindung bis zur Erstellung Ihrer ersten Kampagnen.

+++ Was ist Adobe Campaign v8?

Adobe Campaign v8 ist eine leistungsstarke kanalübergreifende Marketing-Automatisierungsplattform, mit der Sie personalisierte Kampagnen erstellen, koordinieren und auf E-Mail-, Mobile-, Social- und Offline-Kanälen bereitstellen können. Es kombiniert eine robuste Marketing-Datenbank, eine Orchestrierungs-Engine für Kampagnen und Echtzeit-Interaktionsfunktionen, um Kunden während ihres gesamten Journey anzusprechen.

**Schlüsselfunktionen:** Multi-Channel-Kampagnen-Management, Audience-Segmentierung und -Zielgruppenbestimmung, Workflow-Automatisierung, skalierbare Personalisierung, Echtzeit- und Batch-Messaging, Reporting und Analysen, Integration mit Adobe Experience Cloud.

**Was v8 einzigartig macht:** Cloud-native Architektur (nur Managed Cloud Services), Performance auf Unternehmensniveau basierend auf Snowflake-Datenbank, automatische Upgrades, verbesserte Sicherheit und bidirektionale Integration mit Adobe Experience Platform.

**Ideal für:** Marketing-Teams für Unternehmen, die komplexe Kampagnen mit hohem Volumen über mehrere Kanäle und Kunden-Touchpoints verwalten.

**Verwandte Themen:**

[Produktbeschreibung von Campaign v8](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [Neue Funktionen in v8](whats-new.md) | [Erste Schritte](get-started.md)

+++

+++ Wie kann ich Campaign herunterladen?

Sie können das Installationsprogramm und die Client-Konsole vom Adobe Download Center abrufen.

Greifen Sie als Admin-Benutzerin bzw. -Benutzer auf Adobe [Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html){target="_blank"} zu, um Adobe Campaign herunterzuladen.

Weitere Informationen zum Verteilungs-Center [&#x200B; Sie auf dieser Seite](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=de){target="_blank"}.

+++

+++ Wie kann ich eine Verbindung zu Campaign v8 herstellen?

Sie müssen die Campaign-Client-Konsole herunterladen und installieren, um eine Verbindung zu Adobe Campaign herzustellen. [Weitere Informationen](connect.md).

Ab Campaign v8.6 haben Sie Zugriff auf die **Campaign Web-Benutzeroberfläche**, die über die zentrale Adobe Experience Cloud-Umgebung verfügbar ist. Experience Cloud ist Adobes integrierte Produktfamilie von Programmen, Produkten und Services für das digitale Marketing.

Erfahren Sie auf dieser Seite , wie Sie eine Verbindung zu Adobe Experience Cloud herstellen und auf [&#x200B; Adobe Campaign-Web-Oberfläche &#x200B;](campaign-ui.md#ac-web-ui). Weitere Informationen finden Sie in der [Dokumentation zur Adobe Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Verwandte Themen:**

[Installieren Sie die Client-Konsole](connect.md) | [Campaign-Benutzeroberfläche](campaign-ui.md) | [Benutzerberechtigungen](gs-permissions.md)

+++

+++ Kann ich mit Adobe ID eine Verbindung zu Campaign v8 herstellen?

Ja! Dank der Integration mit dem IMS (Adobe Identity Management System) können Benutzende über ihre Adobe ID eine Verbindung zur Adobe Campaign-Konsole herstellen. Diese Integration bietet die folgenden Vorteile:

* Verwendung ein und derselben ID für alle Adobe Experience Cloud-Lösungen;
* Speicherung der Verbindung bei der Verwendung von Adobe Campaign mit den verschiedenen Integrationen;
* Optimierte Sicherheitsrichtlinien für die Kennwortverwaltung;
* Verwendung von Konten des Typs Federated ID (externer Identity Provider).

[Weitere Informationen](connect.md) zum Zugriff auf Campaign v8 mit einer Adobe ID.

+++

+++ Über welche Benutzeroberflächen-Konzepte von Campaign sollte ich Bescheid wissen?

Adobe Campaign Weitere Informationen [&#x200B; Grundlagen zur Benutzeroberfläche von &#x200B;](campaign-ui.md) finden Sie in diesem Abschnitt.

Ab Campaign v8.6 haben Sie auch Zugriff auf die neue **Campaign Web-Benutzeroberfläche**, die über die zentrale Adobe Experience Cloud-Umgebung verfügbar ist.

[Weitere Informationen finden Sie in der Dokumentation zur Web-Benutzeroberfläche von Adobe Campaign](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Wie kann ich Benutzerberechtigungen erteilen?

Campaign-Administratoren können Berechtigungen für Benutzer im Unternehmen vergeben.

Die damit einhergehenden Rechte und Einschränkungen ermöglichen dem Benutzer Folgendes:

* Zugriff auf bestimmte Funktionen
* Zugriff auf bestimmte Daten
* Erstellen, Ändern und/oder Löschen von Daten

**Verwandte Themen:**

[Erste Schritte mit Berechtigungen](gs-permissions.md) | [Verwalten von Benutzerberechtigungen](manage-permissions.md) | [Berechtigungen für Ordner hinzufügen](folder-permissions.md)

+++

+++ Wie kann ich die Zielgruppe für meine Nachrichten auswählen?

Campaign bietet mehrere Zielgruppenbestimmungsmethoden, um die richtige Audience für Ihre Nachrichten auszuwählen:

**Targeting-Methoden:**

* **Abfrage-Editor** - Erstellen von Zielgruppen mithilfe visueller Filter für Empfängerattribute, Verhaltensweisen oder Demografie
* **Listen** - Vordefinierte statische oder dynamische Empfängerlisten verwenden
* **Dateiimport** - Hochladen externer Empfängerdateien für einmalige Kampagnen
* **Workflows** - Erstellen einer komplexen Zielgruppenbestimmungslogik mit Abfrage-, Aufspaltungs- und Anreicherungsaktivitäten
* **Vordefinierte Filter** - Anwenden von einsatzbereiten Filtern (aktive Kunden, Abonnenten, VIPs)
* **Segmente aus Adobe Experience Platform** - Nutzen Sie einheitliche Profile und Echtzeit-Segmente

Sie können mehrere Kriterien (Standort, Kaufverlauf, Interaktion) kombinieren und Ausschlüsse, Schnittmengen oder Vereinigungen verwenden, um Ihre Audience zu verfeinern.

**Verwandte Themen:**

[Definieren von Audiences in Campaign v8](../audiences/gs-audiences.md) | [Abfrage-Editor](query-editor.md) | [Zielgruppen-Mappings](../audiences/target-mappings.md)

+++

+++ Wie erstelle und sende ich die erste E-Mail?

Die Erstellung Ihrer ersten E-Mail in Campaign v8 ist unkompliziert. Sie beginnen mit einer Vorlage, wählen Ihre Zielgruppe aus, entwerfen Ihre Inhalte mit Personalisierung, testen sie mit Testsendungen und senden dann die Nachrichten. Campaign bietet zwei Schnittstellen zur E-Mail-Erstellung: die voll ausgestattete **Client-Konsole** für erfahrene Benutzer und die moderne **Campaign Web-Benutzeroberfläche** für eine schnellere, intuitivere E-Mail-Erstellung.

**5 wichtige Schritte:**

1. **Versand erstellen** - Von einer E-Mail-Vorlage starten oder von Grund auf neu erstellen
2. **Audience definieren** - Auswahl von Empfängern mithilfe von Abfragen, Listen oder Workflows
3. **Inhalt gestalten** - Verwenden Sie den E-Mail-Designer, um Ihre Nachricht mit Personalisierungsfeldern zu erstellen
4. **Testsendungen durchführen** - Validieren des Renderings und der Inhalte auf allen Geräten und E-Mail-Clients
5. **Analysieren und senden** - Versandanalyse durchführen, um Fehler zu finden, und dann E-Mail senden

**Verwandte Themen:**

[E-Mail-Design und -Validierung](../send/email.md) | [Erstellen des ersten Versands](create-message.md) | [Versandvorlagen](../send/create-templates.md) | [Inhalt personalisieren](../send/personalize.md)

+++

+++ Wie übersetze ich eine Fehlermeldung?

Eine Fehlermeldung wird in einer Fremdsprache angezeigt? Alle Fehlermeldungen und deren Übersetzung werden auf [dieser Seite](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=de){target="_blank"} aufgelistet.

+++

+++ Wie kann ich ein Problem protokollieren?

Um den Adobe-Support zu kontaktieren, verbinden Sie sich mit [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}, um einen Fall zu erstellen oder eine Chat-Sitzung zu starten.

Erfordert individuelle Konten mit korrekten Berechtigungen. Wenn Sie sich nicht anmelden können, fordern Sie den Zugriff über Experience League an. [Weitere Informationen](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Alternativ können Sie der [Campaign-Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"} beitreten, um nach Antworten zu suchen oder Experten zu fragen.

+++

+++ Mit welchen Systemen und Komponenten ist Campaign v8 kompatibel?

Eine Liste mit allen Systemen und Komponenten, die vom aktuellen Build von Campaign unterstützt werden, finden Sie in der [Kompatibilitätsmatrix von Adobe Campaign &#x200B;](compatibility-matrix.md).

+++

+++ Kann ich Campaign v8 mit anderen Adobe-Lösungen verwenden?

Ja. Campaign v8 lässt sich nahtlos in Adobe Experience Cloud-Lösungen integrieren, um ein einheitliches Marketing-Ökosystem zu schaffen.

**Wichtige Integrationen:** Adobe Experience Platform (einheitliche Profile, Echtzeitdaten), Adobe Analytics (Leistungsmessung), Adobe Target (Personalisierung), Adobe Experience Manager (Content-Management), Adobe Audience Manager (Zielgruppensegmente).

**Setup:** Erfordert die Adobe IMS-Authentifizierung, die automatisch für Campaign v8 Managed Cloud Services konfiguriert wird.

**Verwandte Themen:**

[Adobe Campaign-Integrationen](../connect/integration.md) | [Verbinden mit Adobe ID](connect.md)

+++

+++ Welche Einschränkungen gibt es in Campaign v8?

Campaign v8 bietet erhebliche Leistungsverbesserungen, weist jedoch einige architektonische Unterschiede zu Campaign Classic v7 auf, insbesondere bei FFDA-Bereitstellungen.

**Wichtige Aspekte:**

* **FFDA-**: Verwendet eine Cloud-Datenbank (Snowflake) mit unterschiedlichen Datenzugriffsmustern
* **Datenaktualisierungen** - sollte in Workflows und nicht über direkten Datenbankzugriff erfolgen
* **Batch-optimiert** - Optimiert für Batch-Vorgänge anstelle von hochfrequenten individuellen Aktualisierungen
* **In FFDA nicht verfügbar** - Umfragen, Marketing Resource Management (MRM), einige spezifische Connectoren

**Auswirkungen der Migration:** Benutzerdefinierter Code, der direkte Datenbankschreibvorgänge verwendet, muss umgestaltet werden. API-Integrationen müssen möglicherweise für die Batch-Verarbeitung angepasst werden.

Diese Einschränkungen ändern sich mit der Erweiterung von Adobe v8. Den aktuellen Status finden Sie in der aktuellen Dokumentation.

**Verwandte Themen:**

[Migration von Campaign v7 zu v8](../start/v7-to-v8.md#limitations) | [FFDA-Architektur](../architecture/enterprise-deployment.md)

+++

+++ Kann ich als Campaign Classic v7-Anwender zu Campaign v8 migrieren?

Die automatische Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht verfügbar.

Campaign v8 ist derzeit **nur** als Managed Cloud Service verfügbar und kann nicht in On-Premise- oder Hybrid-Umgebungen bereitgestellt werden.

Weitere Informationen zum Migrationsprozess erhalten Sie von Ihrer Adobe-Support-Kontaktperson.

Weitere Informationen finden Sie im Abschnitt [Campaign v8 im Vergleich zu früheren &#x200B;](#v7-differences)).

+++


## Aktualisierungen {#upgrades}

Erfahren Sie, wie Sie Ihre Campaign-Version überprüfen, den Upgrade-Prozess verstehen und über neue Versionen auf dem Laufenden bleiben. Campaign v8 Managed Cloud Services verarbeitet Upgrades automatisch mit minimaler Unterbrechung.

+++ Welche Version von Campaign habe ich?

Ihre [Version und Build-Nummer](upgrades.md#version) können Sie in der Client-Konsole von Campaign über das Menü **Hilfe > Versionsinformationen...** abrufen.

+++

+++ Wie kann ich Campaign auf die neuste Version aktualisieren?

Adobe Campaign wird regelmäßig aktualisiert. Jedes Jahr werden kleinere Versionen mit neuen Funktionen, Verbesserungen und Fehlerbehebungen veröffentlicht. Darüber hinaus veröffentlichen wir regelmäßig Builds nur mit kumulativen Fehlerbehebungen.

Dieser regelmäßige Aktualisierungsrhythmus zielt darauf ab, Ihnen die neuesten und besten Funktionen bereitzustellen, Ihre Umgebung sicher zu halten und Ihr Produkterlebnis zu verbessern. Deshalb erachten wir es für wichtig, dass Sie die aktuelle Version von Adobe Campaign verwenden.

**Hinweis:** Als Managed Cloud Services-Anwender wird Ihre Instanz von Adobe mit neuen Versionen aktualisiert.

Weitere Informationen zu [Campaign-Versionen und -Upgrades](upgrades.md).

+++

+++ So erhalten Sie Informationen zu Veröffentlichungen neuer Versionen

Bleiben Sie über diese Kanäle über neue Campaign-Versionen auf dem Laufenden:

* **Adobe-Support** - Kontaktiert Sie direkt, wenn eine neue Version verfügbar ist
* **Versionshinweise** - Alle Versionen und Änderungen, die in den [Versionshinweisen zu Campaign dokumentiert sind](release-notes.md)
* **Adobe Priority Product Updates** - [Abonnieren](https://www.adobe.com/de/subscription/priority-product-update.html){target="_blank"} für E-Mail-Benachrichtigungen
* **Campaign-Community** - Nehmen Sie an [Diskussionen](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"} teil, um frühzeitig Updates zu erhalten

Als Managed Cloud Services-Anwender erledigt Adobe Upgrades und koordiniert die zeitliche Abstimmung mit Ihnen.

**Verwandte Themen:**

[Versionshinweise](release-notes.md) | [Neue Funktionen](whats-new.md) | [Campaign-Versionen und -Upgrades](upgrades.md)

+++

+++ Warum benötigt meine Organisation ein Upgrade?

Die Aktualisierung auf die neueste Campaign-Version ist für die Sicherheit, Leistung und Support-Qualität von entscheidender Bedeutung.

**Wichtigste Vorteile:**

* **Verbesserte Sicherheit** - Schutz vor Sicherheitslücken, neueste Patches, verbesserter Datenschutz
* **Besserer Support** - Schnellere Problembehebung, Zugriff auf Fehlerbehebungen, vorrangiger Support für aktuelle Versionen
* **Verbesserte Leistung** - Datenbank- und Workflow-Optimierungen, bessere Skalierbarkeit, zuverlässigerer Betrieb
* **Neue Funktionen** - Neueste Funktionen, verbesserte Adobe Experience Cloud-Integrationen, moderne Verbesserungen der Benutzeroberfläche

Adobe empfiehlt dringend, die neueste Version auszuführen. Als Kunde von Managed Cloud Services werden Upgrades von Adobe mit minimaler Unterbrechung durchgeführt.

**Verwandte Themen:**

[Campaign-Versionen und -Upgrades](upgrades.md) | [Neue Funktionen](whats-new.md) | [Kompatibilitätsmatrix](compatibility-matrix.md)

+++

+++ Wie sieht das Verfahren und der Zeitplan für ein Upgrade aus?

Als Kunde von Managed Cloud Services verwaltet Adobe den gesamten Upgrade-Prozess mit minimalen Auswirkungen auf Ihren Betrieb.

**process:**

1. **Benachrichtigung** - Adobe benachrichtigt Sie Wochen im Voraus
2. **Planung** - Planen Sie das Upgrade zum optimalen Zeitpunkt mit Ihrem Adobe-Support-Mitarbeiter
3. **Vorbereitung** - Adobe bereitet Umgebung vor und validiert
4. **Ausführung** - Adobe aktualisiert Infrastruktur mit minimaler Ausfallzeit
5. **Validierung** - Testen nach einem Upgrade durch Adobe
6. **Client-Konsolen-Upgrade** - Sie müssen Ihre Client-Konsolen aktualisieren, damit sie mit der Server-Version übereinstimmen.

**Ihre Zuständigkeiten:**

* Koordinieren der internen Stakeholder für die Zeitplanung
* [Aktualisieren von Client-](connect.md#upgrade-ac-console) auf die neue Version
* Testen von Kampagnen und Workflows nach einem Upgrade
* Probleme dem Adobe-Support melden

Adobe führt das Infrastruktur-Upgrade durch. Sie müssen keine technischen Aktionen auf Servern durchführen.

**Verwandte Themen:**

[Campaign-Versionen und -Upgrades](upgrades.md) | [Aktualisieren der Client-Konsole](connect.md#upgrade-ac-console) | [Versionshinweise](release-notes.md)

+++


## Campaign v8 im Vergleich zu vorherigen Versionen {#v7-differences}

Machen Sie sich mit den wichtigsten Unterschieden zwischen Campaign v8 und früheren Versionen (Classic v7 und Standard) vertraut, einschließlich Architektur, Bereitstellung, Migrationspfade und Funktionsänderungen. Erfahren Sie, was neu ist und wie Sie den Übergang reibungslos gestalten können, unabhängig davon, ob Sie von Campaign Classic v7 oder Campaign Standard kommen.


+++ Was sind die Hauptunterschiede zwischen Campaign v8 und früheren Versionen?

Campaign v8 basiert auf einer modernen Cloud-nativen Architektur mit erheblichen Verbesserungen:

* **Nur Managed Cloud Services** - Vollständig von Adobe gehostet (keine On-Premise-/Hybrid-Optionen)
* **Überlegene Leistung** - Bis zu 20 Millionen Vorgänge/Stunde mit FFDA-Architektur (Full Federated Data Access)
* **Neue Web-Benutzeroberfläche von Campaign** - Moderne, intuitive Benutzeroberfläche neben der klassischen Konsole
* **Automatische Upgrades** - Immer die neueste Version ohne Ausfallzeiten
* **Erweiterte Funktionen** - KI-Assistent, Rich-Push-Benachrichtigungen, aktualisierte SMS, verbesserte Integrationen mit Adobe Experience Cloud

**Für Campaign Classic v7-Benutzer:** Erfahren Sie mehr über den [Wechsel von v7 zu v8](v7-to-v8.md) einschließlich Änderungen an der Architektur, nicht verfügbaren Funktionen und Überlegungen zur Migration.

**Für Campaign Standard-Benutzer:** Entdecken Sie den [Umstellungspfad zu v8](acs-to-v8.md) und das [Migrationshandbuch zu Campaign Standard](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Verwandte Themen:**

[Wichtigste Funktionen von Campaign v8](whats-new.md) | [Architektur von Campaign v8](../architecture/architecture.md) | [Funktionsmatrix](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Leitplanken und Einschränkungen](ac-guardrails.md)

+++

+++ Sollte ich von Campaign Classic v7 oder Campaign Standard zu v8 migrieren?

Campaign v8 ist die Adobe-Plattform, die sich ideal für Unternehmen eignet, die Kampagnen mit hohem Volumen (20 Millionen Vorgänge/Stunde), eine moderne Web-Benutzeroberfläche, Cloud-native Vorteile und langfristigen Support benötigen.

**Wichtigste Vorteile:**

* **Für Campaign Standard-**: Vertraute Web-Benutzeroberfläche, Funktionsparität (dynamisches Reporting, REST-APIs, Landingpages), reibungslose Datenmigration
* **Für Campaign Classic v7-**: Zwei Schnittstellen (Konsole + Web-Benutzeroberfläche), bessere Leistung, automatische Upgrades, verbesserte FFDA-Architektur

**Ziehen Sie eine Migration in Betracht, wenn Sie:**

* Sie verarbeiten große Datenmengen oder es treten Leistungsprobleme auf
* Geringerer IT-Overhead und weniger Infrastrukturverwaltung
* Integration von Adobe Experience Cloud/Platform erforderlich
* Sie möchten zukunftssichere Technologie mit automatischen Updates

**Nächste Schritte:** Wenden Sie sich an den Adobe-Support, um die Migrationsbereitschaft zu bewerten und auf die Migrationswerkzeuge zuzugreifen.

**Verwandte Themen:**

[Von Campaign Classic v7 zu v8](v7-to-v8.md) | [Campaign Standard-Umstellungshandbuch](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Funktionsmatrix](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

+++ Kann Campaign v8 in einer On-Premise- oder Hybridumgebung installiert werden?

Nein. Campaign v8 ist ausschließlich als **Managed Cloud Service** verfügbar und wird vollständig von Adobe gehostet.

**Die wichtigsten Vorteile von Managed Cloud Services:**

* Überlegene Leistung und Skalierbarkeit
* Automatische Upgrades - immer auf der neuesten Version
* Verbesserte Sicherheit durch kontinuierliche Überwachung
* Kein Infrastruktur-Management oder IT-Overhead
* Integrierte Hochverfügbarkeit und Notfallwiederherstellung

Erfahren Sie mehr über [&#x200B; Architektur von Campaign v8 &#x200B;](../architecture/architecture.md) die [Unterschiede zwischen Campaign v8 und Classic v7](../start/v7-to-v8.md).

+++

+++ Wie migriere ich meine On-Premise- oder Hybridumgebung von Campaign Classic v7 zu Adobe Managed Services?

Die Migration zu Adobe Managed Services bietet einen strategischen Weg von On-Premise/Hybrid v7 zur Cloud und bietet mehr Skalierbarkeit, Sicherheit und einen geringeren IT-Overhead. Häufig ist dies ein Sprungbrett vor der Umstellung auf Campaign v8.

**Wichtigste Punkte:**

* Kein automatisiertes Migrationswerkzeug verfügbar, manuelle Planung und Ausführung erforderlich
* Adobe Professional Services-Support wird dringend empfohlen
* Zu den Vorteilen gehören Cloud-Infrastruktur, automatische Sicherheits-Patches, Experten-Support und der einfachere Pfad zu v8
* Die Migration erfordert die gebührende Sorgfalt, Umgebungsprüfung, Datenbereinigung, Staging-Migration und Produktionsumstellung

**Erste Schritte:** Wenden Sie sich an Ihre Adobe-Support-Fachkraft, die Ihre Umgebung bewertet und einen detaillierten Migrationsplan mit Adobe Professional Services erstellt.

Erfahren Sie mehr über [Migration zu Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605?profile.language=de){target="_blank"} einschließlich Herausforderungen, Best Practices und einer detaillierten Migrationsstrategie.

+++

+++ Worin bestehen die wichtigsten terminologischen und funktionalen Unterschiede in Campaign v8?

Campaign v8 bietet die meisten v7/Standard-Funktionen mit Verbesserungen, wobei einige Begriffe und Funktionen jedoch unterschiedlich sind. Nachfolgend finden Sie eine Zusammenfassung der wichtigsten Änderungen.

**Wichtige terminologische Änderungen (Campaign Standard → v8):**

* Benutzerdefinierte Ressourcen → **Schemata** | Nachrichten → **Sendungen** | Produktbenutzer → **Benutzer**
* Sicherheitsgruppen → **Benutzergruppen** | Organisationseinheiten → **Ordnerberechtigungen**

**Aktualisierungen der Web-Benutzeroberfläche von Campaign:**

* Empfänger → **Profile** | Testadressen → **Testprofile** | Versandanalyse → **Versandvorbereitung**
* Listen → **Zielgruppen** | E-Mail-Vorschau → **Inhalt simulieren**

**In v8 nicht verfügbar:**

* On-Premise-/Hybrid-Bereitstellungen (nur Managed Cloud Services)
* Direkter Datenbankzugriff (APIs verwenden)
* Manuelle Infrastrukturverwaltung (Adobe-verwaltet)

**Neue Funktionen für Campaign Standard-Benutzer:**

* Dynamic Reporting, zentralisiertes Branding, REST-APIs, Verbesserungen bei Landingpages, visuelle Fragmente

**Verwandte Themen:**

[Funktionsmatrix](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [v7 zu v8 - Übergangshandbuch](v7-to-v8.md) | [Wechsel von Campaign Standard zu v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Profile und Zielgruppen {#audiences}

Hier finden Sie Antworten auf Fragen zur Verwaltung von Profilen, zur Erstellung von Audiences, zum Datenimport und zur Zielgruppenbestimmung von Empfängern für Ihre Kampagnen.

+++ Wie erstelle ich Empfänger?

Manuelles Erstellen von Empfängern für einzelne Profile, Import aus Dateien (CSV/TXT) für Massenhinzufügungen, Verwendung von Web-Formularen zur Selbstregistrierung oder Integration über APIs von externen Systemen. Verwenden Sie Import-Workflows für wiederkehrende Datenladevorgänge.

**Verwandte Themen:**

[Manuelles Erstellen von Profilen](../audiences/create-profiles.md) | [Importieren von Profilen aus einer Datei](../audiences/import-profiles.md) | [Erfassen von Profilen mit Web-Formularen](../audiences/collect-profiles.md)

+++

+++ Wie importiere ich Profile?

Campaign bietet mehrere Importmethoden: einen einfachen Dateiimport mit dem Importassistenten, einen Workflow-basierten Import für komplexe Umwandlungen, wiederkehrende Importe mit geplanten Workflows aus SFTP und einen API-Import für die programmgesteuerte Integration.

Bereiten Sie Ihre Datendatei (CSV/TXT, UTF-8-Kodierung) für den Dateiimport vor, verwenden Sie den Importassistenten oder -Workflow, ordnen Sie Spalten Campaign-Feldern zu, definieren Sie Regeln zum Aktualisieren/Einfügen und testen Sie sie zuerst mit einem kleinen Muster. Verwenden Sie Workflows für wiederkehrende Importe und wenden Sie Deduplizierungsregeln an.

**Verwandte Themen:**

[Datenimport-Handbuch](../start/import.md) | [Workflow für wiederkehrenden Import](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=de){target="_blank"} | [Aktivität „Laden“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=de){target="_blank"}

+++

+++ Wie erstelle ich Testprofile für meine Sendungen?

Mit Testprofilen (Testadressen) können Sie Empfänger ansprechen, die nicht den definierten Zielgruppenkriterien entsprechen. So können Sie Ihren Versand testen, bevor Sie ihn an Ihre Hauptzielgruppe senden. Fügen Sie diese über **[!UICONTROL Testadressen]** in den Versandeigenschaften hinzu oder verwenden Sie den Ordner **[!UICONTROL Testadressen]**.

Weitere Informationen zu [Testprofilen](../audiences/test-profiles.md).

+++

+++ Wie kann ich die Zielpopulation für meine Marketing-Kampagne definieren?

Campaign bietet mehrere Zielgruppenbestimmungsmethoden: Abfragen mit visuellen Kriterien erstellen, vorhandene Listen oder Segmente ansprechen, Empfänger aus externen Dateien (CSV, TXT) importieren oder vordefinierte Filter anwenden. Sie können Kriterien mit UND/ODER-Logik kombinieren, bestimmte Populationen ausschließen, Kontrollgruppen verwenden und für A/B-Tests aufteilen. Zeigen Sie vor dem Versand immer die Größe Ihrer Zielpopulation in der Vorschau an.

**Verwandte Themen:**

[Definieren von Kampagnenzielen](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=de){target="_blank"} | [Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"} | [Zielgruppen erstellen](../audiences/create-audiences.md)

+++

+++ Wie kann ich eine Profilliste erstellen?

Eine Liste ist eine statische Gruppe von Empfängern, die Sie in Sendungen auswählen und kampagnenübergreifend wiederverwenden können.

**Drei Erstellungsmethoden:**

* **Manuelle Erstellung:** Navigieren Sie zu **[!UICONTROL Profile und Zielgruppen >]** und klicken Sie auf **[!UICONTROL Erstellen]**. Hinzufügen von Empfängern aus einer Abfrage, einer individuellen Auswahl oder einem Ordner.

* **Workflow-Automatisierung:** Verwenden Sie die Aktivität **[!UICONTROL Listen-Update]**, um Listen automatisch aus Abfrageergebnissen oder importierten Daten zu erstellen und zu pflegen.

* **Beim Import:** beim Importieren von Profilen eine Liste, um sie als wiederverwendbare Gruppe zu speichern.

**Tipp** Verwenden Sie Workflows für Listen, die regelmäßige Aktualisierungen erfordern, und für die manuelle Erstellung einer einmaligen Segmentierung.

**Verwandte Themen:**

[Zielgruppen erstellen](../audiences/create-audiences.md) | [Aktivität „Listen-Update“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=de){target="_blank"}

+++

+++ Wie kann ich eine Population vor dem Nachrichtenversand deduplizieren?

Verwenden Sie die **[!UICONTROL Deduplizierung]** in einem Workflow, um doppelte Empfänger vor dem Versand zu entfernen. Platzieren Sie sie zwischen Ihren **[!UICONTROL Abfrage]**- und **[!UICONTROL Versand]**-Aktivitäten und wählen Sie dann Ihre Deduplizierungskriterien (normalerweise E-Mail-Adresse oder Empfänger-ID) und den beizubehaltenden Datensatz aus.

**Tipp:** Sie vor dem Versand immer deduplizieren, damit jede Person Ihre Nachricht nur einmal erhält.

Weitere Informationen zur Aktivität [Deduplizierung](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=de){target="_blank"}

+++

+++ Wie kann ich Abonnenten meines Newsletters identifizieren und ansprechen?

Campaign verfolgt Newsletter-Abonnements automatisch über Informations-Services. An Abonnenten richten:

* Verwenden Sie eine **[!UICONTROL Abfrage]**-Aktivität und filtern Sie nach **[!UICONTROL Abonnements]** > wählen Sie Ihren Newsletter-Service aus.
* Sprechen Sie Abonnentinnen und Abonnenten direkt aus Ihrem Versand an, indem Sie **[!UICONTROL An > Abonnentinnen und Abonnenten eines Informationsdienstes auswählen]**
* Erstellen von Abonnentenlisten mit der Workflow **[!UICONTROL Aktivität „Abonnement]**

Campaign verfolgt den Verlauf von An-/Abmeldungen und verwaltet die An-/Abmeldung automatisch.

**Verwandte Themen:**

[Abonnements verwalten](../start/subscriptions.md) | [Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"}

+++

+++ Was sind die Best Practices beim Ausschließen von Profilen aus einer Zielpopulation?

Verwenden Sie die **[!UICONTROL Ausschluss]**-Aktivität in einem Workflow, um unerwünschte Profile aus Ihrer Zielgruppe zu entfernen. Platzieren Sie sie nach Ihren Zielgruppenbestimmungsaktivitäten und definieren Sie, welche Population ausgeschlossen werden soll.

Weitere Informationen zur [Ausschlussaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=de){target="_blank"}

+++


## Nachrichtendesign {#design}

Erfahren Sie, wie Sie in Campaign v8 effektive Marketing-Nachrichten entwerfen, einschließlich E-Mail-Vorlagen, Personalisierungstechniken und mehrsprachiger Inhalte. Gestalten Sie Ihre Nachrichten in der Client-Konsole oder verwenden Sie den modernen **E-Mail-Designer** in der Web-Benutzeroberfläche von Campaign, um die visuelle Bearbeitung zu verbessern.

+++ Was sind die Best Practices für die Gestaltung von E-Mails in Campaign?

Wichtige Richtlinien: Sicherstellen eines responsiven Designs für Mobilgeräte, Verwenden von HTML 4.0/XHTML-kompatiblem Code mit Inline-CSS, Optimieren von Bildern (unter 100 KB) mit Alt-Text, Verwenden von Personalisierungszusammenführungsfeldern, Testen über E-Mail-Clients hinweg vor dem Versand und Einschließen einer Nur-Text-Version. Für optimale Zustellbarkeit wird eine E-Mail-Gesamtgröße von unter 500 KB angestrebt.

**Verwandte Themen:**

[E-Mail-Design-Handbuch](../send/email.md) | [Best Practices beim Versand](delivery-best-practices.md)

+++

+++ Was ist eine Versandvorlage?

Eine Versandvorlage ist ein vorkonfigurierter Versand, der alle Einstellungen und Parameter speichert, um sie in mehreren Kampagnen wiederzuverwenden. Zu den Vorlagen gehören Zielgruppenregeln, Inhaltsdesign, Personalisierung, technische Einstellungen (Absender, Antwortadresse) und Typologieregeln. Einmal erstellen und wiederverwenden, um Konsistenz zu wahren und die Kampagnenerstellung zu beschleunigen.

Erfahren Sie, wie Sie [Versandvorlagen erstellen](../send/create-templates.md)

+++

+++ Kann ich eine vorhandene HTML-Datei einfach importieren, um eine E-Mail in Campaign zu erstellen?

Ja. Importieren Sie HTML-Inhalte per Direktkopie/Einfügen in den Inhaltseditor, über Ihren Computer hochgeladene Dateien oder über eine URL. Stellen Sie sicher, dass Ihre HTML E-Mail-kompatiblen Code (HTML 4.0/XHTML) mit Inline-CSS verwendet und Bilder auf einem öffentlichen Server hosten. Campaign fügt importierten HTML automatisch Personalisierung und Tracking hinzu.

**Tipp:** Um das Design von E-Mails zu optimieren, verwenden Sie die **E-Mail-Designer** in der Web-Benutzeroberfläche von Campaign. Diese bietet moderne Drag-and-Drop-Funktionen und integrierte responsive Vorlagen, anstatt unbearbeitetes HTML zu importieren.

Erfahren Sie, wie [HTML-Inhalte importieren](../send/defining-the-email-content.md)

+++

+++ Wie kann ich in Campaign einen Newsletter zum Abonnieren erstellen?

Ja. Verwenden Sie die Informations-Services von Campaign, um Newsletter-Abonnements zu verwalten. Zu den wichtigsten Funktionen gehören die automatische Handhabung von Opt-in/Opt-out, Abonnement-Tracking, Compliance-Management (DSGVO, CAN-SPAM), Unterstützung für mehrere Newsletter, Web-Integration für Anmeldeformulare und zielgerichteter Versand an Abonnenten.

Erfahren Sie, wie [Abonnements verwalten](../start/subscriptions.md)

+++

+++ Wie kann ich Nachrichten personalisieren?

Campaign bietet Personalisierungsfunktionen, mit denen basierend auf Empfängerdaten, Verhalten und Voreinstellungen relevante, zielgerichtete Nachrichten erstellt werden können.

**Personalization-Optionen:**

* **Personalisierungsfelder** - Empfängerdaten einfügen (z. B. `"Hello {{firstName}}")`
* **Gestaltungsbausteine** - Verwenden vordefinierter oder benutzerdefinierter Inhaltsbausteine
* **Bedingter Inhalt** - Unterschiedlicher Inhalt wird basierend auf Empfängerkriterien angezeigt
* **Verhaltensdaten** - Nutzen Sie den Browser-Verlauf, Kaufmuster oder Interaktionsmetriken

Testen Sie die Personalisierung vor dem Senden, um zu überprüfen, ob Zusammenführungsfelder und die bedingte Logik ordnungsgemäß funktionieren.

**Verwandte Themen:**

[Handbuch zu Personalization](../send/personalize.md) | [Personalisierungsfelder](../send/personalization-fields.md) | [Bedingter Inhalt](../send/conditions.md)

+++

+++ Wie kann ich die Betreffzeilen von E-Mails personalisieren?

Personalisierte Betreffzeilen erhöhen die Öffnungsraten erheblich. Mit Campaign können Sie Empfängerdaten dynamisch einfügen, bedingte Logik anwenden und Varianten testen, um die Interaktion zu optimieren.

**Personalization-Verfahren:**

* **Standardfelder** - Vornamen, Nachnamen, Speicherort einfügen: `"<%@ firstName %>, exclusive offer for you"`
* **Bedingter Inhalt** - Unterschiedliche Themen nach Segment: `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **Dynamische Daten** - Schließen Sie Kaufverlauf, Treuepunkte oder Kontoinformationen ein
* **Emojis** - Optisch ansprechend (zuerst über E-Mail-Clients hinweg testen)

**Best Practices:** Sie weniger als 50 Zeichen ein, testen Sie Personalisierungs-Token vor dem Versand, verwenden Sie A/B-Tests zur Optimierung, vermeiden Sie Spam-Trigger-Wörter, schließen Sie ein Wertversprechen oder eine Dringlichkeit ein.

**Verwandte Themen:**

[Personalisierungsfelder](../send/personalization-fields.md) | [Bedingter Inhalt](../send/conditions.md)

+++

+++ Kann ich mehrsprachige Nachrichten senden?

Ja. Campaign v8 bietet mehrsprachige Funktionen, wobei die **Campaign Web-Benutzeroberfläche** den einfachsten Ansatz bietet. Die Web-Benutzeroberfläche bietet einen nativen mehrsprachigen Versand mit Sprachvarianten. Fügen Sie Ihrem Versand Sprachvarianten hinzu, und Campaign sendet automatisch die entsprechende Version basierend auf der bevorzugten Sprache des Empfängers. Verfügbar für E-Mail, Push-Benachrichtigungen, SMS und Transaktionsnachrichten.

Hauptfunktionen: automatische Inhaltsduplizierung, automatisches sprachbasiertes Senden, standardmäßiges Sprachfallback und einfache Variantenverwaltung.

Die Client-Konsole unterstützt auch mehrsprachige Inhalte mit bedingten Inhalten und Workflows, erfordert jedoch eine manuellere Konfiguration.

**Verwandte Themen:**

[Mehrsprachige Sendungen (Web-Benutzeroberfläche)](https://experienceleague.adobe.com/de/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Bedingter Inhalt (Client-Konsole)](../send/conditions.md)

+++

+++ Kann ich ein Web-Formular lokalisieren?

Ja. Web-Anwendungen von Campaign unterstützen die Lokalisierung in mehreren Sprachen. Definieren Sie Übersetzungen für alle Formularelemente (Beschriftungen, Schaltflächen, Meldungen, Fehlertext), mit automatischer Spracherkennung basierend auf Empfängerprofil- oder Browser-Einstellungen. Innerhalb einer einzelnen Webanwendung werden mehrere Sprachversionen unterstützt, wobei bei Bedarf auf eine Standardsprache zurückgegriffen wird.

Weitere Informationen über [Lokalisierung von Web-Anwendungen](../dev/webapps.md)

+++

+++ Kann ich KI-gestützte Inhalte in meinen E-Mails verwenden?

Ja, aber **nur über die Campaign Web-Benutzeroberfläche**. Der KI-Assistent unterstützt Microsoft Azure OpenAI und Adobe Firefly und hilft beim Erstellen professioneller, markenkonsistenter Inhalte für E-Mail, SMS und Push-Benachrichtigungen.

**Schlüsselfunktionen:**

* Generieren von Text (E-Mail-Kopie, Betreffzeilen, SMS-/Push-Inhalt) und markenorientierten Bildern
* Erstellen von Inhaltsvarianten, die für verschiedene Zielgruppen optimiert sind
* Inhalte verfeinern (ausarbeiten, zusammenfassen, umformulieren, vereinfachen)
* Hochladen von Marken-Assets und Abrufen der Bewertung bei der Markenausrichtung
* Vorhandenen Inhalt als Referenz verwenden und Stilreferenzbilder hochladen

**Hinweis:** KI-Assistent ist ausschließlich in der Web-Benutzeroberfläche von Campaign verfügbar und unterstützt derzeit nur Englisch. Benutzer benötigen entsprechende Berechtigungen und müssen einer Benutzervereinbarung zustimmen.

**Verwandte Themen:**

[Überblick über den KI-Assistenten](https://experienceleague.adobe.com/de/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Anwendungsfälle des KI-Assistenten](https://experienceleague.adobe.com/de/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Markenausrichtung](https://experienceleague.adobe.com/de/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Testen und Senden von Nachrichten {#send}

Erfahren Sie mehr über Best Practices zum Testen, Validieren, Senden und Tracking Ihrer Marketing-Nachrichten, um den erfolgreichen Versand einer Kampagne sicherzustellen.

+++ Wie kann ich den E-Mail-Versand optimieren?

Die Zustellbarkeit von E-Mails, ein wichtiger Faktor für den Erfolg jedes Marketing-Programms, unterliegt ständig wechselnden Kriterien und Regeln. Eine effektive Navigation in dieser digitalen Welt erfordert eine regelmäßige Abstimmung Ihrer E-Mail-Strategie unter Berücksichtigung der wichtigsten Trends mit Blick auf die Zustellbarkeit, um Ihre Zielgruppen optimal zu erreichen.

Lesen Sie dieses Handbuch, um mehr über [Best Practices für die Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"} zu erfahren

In [diesem Handbuch](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=de){target="_blank"} erfahren Sie, wie Sie in Campaign eine hohe Zustellbarkeit gewährleisten.

**Verwandte Themen:**

[Erste Schritte mit der Zustellbarkeit](../send/about-deliverability.md) | [Kontrollieren des Nachrichteninhalts](../send/control-message-content.md) | [Zustellbarkeit überwachen](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ Wie weiß ich, dass mein Versand fehlerfrei durchgeführt wird?

**Vor dem Versand** Versandanalyse durchführen, Testsendungen durchführen, Warnungen überprüfen, Zielgruppenanzahl überprüfen.

**Während/nach dem Versand:** Überwachen des Versand-Dashboards (gesendet, zugestellt, Bounces, Fehler), Überprüfen der Versandlogs, Verfolgen der Erfolgs-/Bounce-Raten, Überprüfen der Quarantäneadressen.

**Best Practices:** Richten Sie Warnhinweise ein, verwenden Sie Schübe für große Volumina, testen Sie zuerst mit kleinen Volumina, bereinigen Sie die Empfängerdatenbank regelmäßig, überwachen Sie die Reputation des Absenders.

**Verwandte Themen:**

[Verfolgen und Überwachen von Sendungen](../send/tracking.md) | [Best Practices beim Versand](delivery-best-practices.md)

+++

+++ Was ist die Versandanalyse?

Die Versandanalyse ist eine Validierungsphase, die Campaign vor dem Versand durchführt. Es berechnet die Zielpopulation, validiert den Inhalt, sucht nach Fehlern, wendet Typologieregeln an und schätzt das Versandvolumen.

Campaign generiert Protokolle mit Warnungen und Fehlern. Fehler blockieren den Versand und müssen behoben werden. Warnungen sind empfehlenswert. Überprüfen Sie vor dem Versand immer die Analyseprotokolle.

Weitere Informationen finden Sie im [Handbuch zur Versandanalyse](../send/delivery-analysis.md)

+++

+++ Warum sollte ich Testsendungen durchführen?

Testsendungen sind Testnachrichten, die Ihren Versand validieren, bevor Sie ihn an Ihre Hauptzielgruppe senden. Testsendungen verwenden, um die Personalisierung zu überprüfen, das Rendering von Inhalten für E-Mail-Clients zu testen, Links und Tracking-Arbeit zu bestätigen, Bilder und Anhänge zu überprüfen und die Reaktionsfähigkeit auf Mobilgeräten zu validieren.

Testsendungen helfen dabei, Fehler zu erkennen, bevor sie Tausende von Empfängern erreichen, ermöglichen die Genehmigung durch Stakeholder und testen die Posteingangsplatzierung. Führen Sie Testsendungen an mehrere E-Mail-Clients und -Geräte durch und holen Sie sich immer die Genehmigung ein, bevor die Produktion gesendet wird.

Weitere Informationen finden Sie im [Korrekturabzüge und Vorschau-Handbuch](../send/preview-and-proof.md)

+++

+++ Wie werden Testadressen in Adobe Campaign verwendet?

Testadressen sind spezielle Empfängerinnen und Empfänger, die automatisch zu jedem Versand hinzugefügt werden, um ihn zu testen, zu prüfen und zu überwachen - ohne dass sie Ihren Zielgruppenkriterien entsprechen. Nützlich für die laufende Überwachung, Tests der Posteingangsplatzierung, Direkt-Mail-Validierung und die Sichtbarkeit für Stakeholder.

**Die wichtigsten Unterschiede zu Testsendungen:**

* **Testadressen**: Die Testadressen werden automatisch zum Versandvolumen in der Produktion hinzugefügt.
* **Testsendungen** - Testsendungen vor der Produktion, werden nicht zum Volumen gezählt, sondern zur Validierung verwendet

Testadressen verwalten in **[!UICONTROL Ressourcen > Kampagnen-Management > Testadressen]**. Halten Sie Listen klein, um eine Beeinträchtigung der Versandmetriken zu vermeiden.

Weitere Informationen finden Sie im [Handbuch zu Testadressen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=de){target="_blank"}

+++

+++ Wie kann ich vor dem Versand einen Validierungsprozess einrichten?

Campaign bietet Validierungs-Workflows, um sicherzustellen, dass Nachrichten vor dem Versand den Qualitätsstandards entsprechen. Konfigurieren von Validierungen für Inhalt, Zielgruppe, Extraktion (Briefpost) und Budget auf Kampagnen- oder Versandebene.

**Setup:**

Erstellen Sie Benutzergruppen unter **[!UICONTROL Administration > Zugriffsverwaltung > Benutzergruppen]** und weisen Sie dann in den Kampagnen- oder Versandeigenschaften Validierungsgruppen zu. Campaign sendet Benachrichtigungs-E-Mails an Validierungsverantwortliche, die Änderungen genehmigen, ablehnen oder anfordern können.

**Für eigenständige Sendungen (nicht in einer Kampagne):**

Verwenden **Testsendungen als Genehmigungsprozess**. Führen Sie Testsendungen zur Validierung an Ihre Genehmigungsgruppe durch und senden Sie nach der Vornahme von Änderungen immer einen neuen Testversand, um sicherzustellen, dass die Verantwortlichen die neueste Version überprüfen.

**Verwandte Themen:**

[Versandvalidierung](../send/preview-and-proof.md) | [Kampagnengenehmigungen](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=de){target="_blank"}

+++

+++ Kann ich A/B-Tests für meine Sendungen durchführen?

Ja! Mit Campaign können Sie A/B-Tests (auch als Split-Tests bezeichnet) durchführen, um Betreffzeilen, Inhalte, Absendernamen, Sendezeiten und mehr zu optimieren, indem Sie die Leistung über verschiedene Varianten hinweg vergleichen.

**Was Sie testen können:**

* **Betreffzeilen** - Vergleichen Sie Öffnungsraten in verschiedenen Themen
* **Inhaltsvarianten** - Testen verschiedener Layouts, Aktionsaufrufe oder Bilder
* **Absenderinformationen** - Absendername oder Absenderadresse prüfen
* **Versandzeit** - Ermitteln der optimalen Versandfenster
* **Personalization-Strategien** - Vergleich von personalisierten und allgemeinen Inhalten

**Funktionsweise:**

1. Versand erstellen und Testvarianten definieren (bis zu 3)
2. Aufspaltung der Zielgruppe (normalerweise 10-20 % für Testsegmente)
3. Campaign sendet Varianten, um Segmente zu testen, und verfolgt die Leistung
4. Die erfolgreichste Variante wird automatisch an die verbleibende Zielgruppe gesendet (oder Sie wählen den Gewinner manuell aus).

**Verfügbar in:** Sowohl die Campaign Web-Benutzeroberfläche als auch die Client-Konsole. Die Web-Benutzeroberfläche bietet eine einfachere Einrichtung mit visuellem Vergleich.

**Verwandte Themen:**

[Versandanalyse](../send/delivery-analysis.md) | [Sendungen durchführen und verfolgen](../send/send.md)

+++

+++ Was ist eine Typologieregel?

Typologieregeln sind automatisierte Geschäftslogiken, die während der Versandanalyse angewendet werden, um den Nachrichtenversand zu validieren und zu optimieren. Sie gewährleisten die Einhaltung von Marketing-Richtlinien, schützen die Zustellbarkeit und verhindern Kundenmüdigkeit.

**Hauptregeltypen:**

* **Filterregeln** - Empfänger ausschließen (auf die Blockierungsliste gesetzt, abgemeldet, unter Quarantäne gestellt)
* **Druckregeln** - Kontrollieren Sie die Häufigkeit von Nachrichten, um zu vermeiden, dass Empfänger überfordert werden
* **Kapazitätsregeln** - Nachrichtenvolumen für Verarbeitungskapazität oder ISP-Beschränkungen begrenzen
* **Kontrollregeln** - Gültigkeit der Nachricht überprüfen (Betreffzeile, Abmelde-Link, Absenderformat)

Regeln werden in Typologien gruppiert und bei der Versandanalyse angewendet. Campaign kann Empfänger anhand der Regeln ausschließen, den Versand blockieren oder Warnungen generieren.

Weitere Informationen finden Sie im [Handbuch zu Typologieregeln](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=de){target="_blank"}

+++

+++ Wie kann ich E-Mails in mehreren Schüben senden?

Ja. Der Wellenversand unterteilt Ihren Versand in mehrere Batches, die in terminierten Intervallen gesendet werden. Dies ist für Kampagnen mit großem Volumen unerlässlich, um die Server-Last auszugleichen, ISP-Drosselungen zu verhindern, die Reputation der Absender mit neuen IPs aufzubauen und Opt-outs/Bounces zwischen Schüben zu verwalten.

**Konfiguration:**

Aktivieren Sie in den Versandeigenschaften das Senden von Wellen und definieren Sie die Anzahl der Wellen (oder die Batch-Größe), das Intervall zwischen den Wellen und die Wellenverteilung (lineare oder benutzerdefinierte Prozentsätze). Campaign teilt Ihre Zielpopulation automatisch auf und sendet jede Welle planmäßig.

Verwenden Sie Wellen für große Kampagnen, überwachen Sie die Leistung der ersten Welle, bevor Sie fortfahren, und lassen Sie ausreichend Zeit zwischen den Wellen, um Bounces und Opt-outs zu verarbeiten.

Erfahren Sie, wie [Wellenversand konfigurieren](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Wie wird ein Versand terminiert?

Mit Campaign können Sie Sendungen für den zukünftigen Versand planen, um Versandzeiten zu optimieren und Kampagnen zu koordinieren.

**Planungsoptionen:**

* **Versandeigenschaften** - Sofort senden, für ein bestimmtes Datum/eine bestimmte Uhrzeit planen oder nach Stunden/Tagen verschieben
* **Kampagnenebene** - Koordinieren aller Sendungen innerhalb einer Kampagne
* **Workflow-Planungsaktivität** - Für wiederkehrende Sendungen, komplexe Muster und ereignisausgelöste Kampagnen

Campaign unterstützt auch die Optimierung des Kontaktdatums (beste Versandzeit pro Empfänger) und die Anpassung der Zeitzone (gleiche lokale Zeit für alle Empfänger).

Erfahren Sie, wie Sie [den Versand planen](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Kann ich zu E-Mails einen Anhang hinzufügen?

Ja. Campaign unterstützt statische Anhänge (dieselbe Datei für alle Empfänger) und personalisierte Anhänge (je nach Empfänger unterschiedliche Dateien basierend auf Profildaten). Fügen Sie Anlagen im **[!UICONTROL Anlagen]** Ihrer Versandeigenschaften hinzu.

**Wichtige Überlegungen:**

* Anhänge für eine optimale Zustellbarkeit unter 1 MB speichern
* Anhänge können Spam-Filter zum Trigger bringen. Vor dem Versand gründlich testen
* Vermeiden Sie Dateitypen, die häufig von E-Mail-Clients (.exe, .zip, .js) blockiert werden
* Bei großen Dateien sollten Sie stattdessen getrackte Download-Links verwenden

Sichere Dateiformate verwenden (PDF, JPEG, PNG, DOCX) und Testadressen testen, bevor die Produktion gesendet wird.

Weitere Informationen finden Sie im [Handbuch zu E-Mail-Anhängen](../send/email.md#attachments)

+++

+++ Wie kann ich getrackte Links in einem E-Mail-Versand konfigurieren?

Campaign konvertiert automatisch alle URLs in Ihrer E-Mail in getrackte Links, um die Empfängerinteraktion zu überwachen. Rufen Sie den **[!UICONTROL Tracking]** in Ihrem Versand auf, um die Tracking-Einstellungen für jeden Link zu konfigurieren.

**Konfigurationsoptionen:**

* **Tracking aktivieren/deaktivieren** - Tracking pro Link steuern
* **Link-Kennzeichnungen** - Fügen Sie beschreibende Namen für das Reporting hinzu (z. B. „Jetzt CTA kaufen„)
* **Link-Kategorien** - Gruppieren von Links nach Typ für die aggregierte Analyse
* **Tracking-Typ** - Klicks, Öffnungen oder beides verfolgen

Campaign verfolgt Inhalts-Links, Mirrorseiten-Links und Abmelde-Links und kann ein optionales Tracking-Pixel für E-Mail-Öffnungen enthalten. Verwenden Sie aussagekräftige Bezeichnungen und Kategorien, um das Reporting zu vereinfachen und leistungsstarke Inhalte schnell zu identifizieren.

**Verwandte Themen:**

[Linktracking-Handbuch](../send/tracking.md) | [Best Practices für das Tracking](../send/send.md)

+++

+++ Wo kann ich auf Versand- und Trackinglogs zugreifen?

Zugreifen auf Versand- und Trackinglogs direkt über jedes Versand-Dashboard. Klicken Sie in der Client-Konsole **[!UICONTROL unten auf]** Registerkarte „Versand“. Navigieren Sie in der Web-Benutzeroberfläche von Campaign zum Abschnitt **[!UICONTROL Protokolle]** .

**Verfügbare Protokolle:**

* **Versandlogs** - Gesendete Nachrichten mit Empfängerdetails und Status (gesendet, ausstehend, fehlgeschlagen)
* **Trackinglogs** - Empfängerinteraktionen (Öffnungen, Klicks) mit Zeitstempeln
* **Ausschlusslogs** - Ausgeschlossene Empfänger mit Gründen (Quarantäne, Typologieregeln, Duplikate)
* **Broadcast-Protokolle** - Vollständiger Versandverlauf einschließlich weiterer Versuche und Fehler

Verwenden Sie diese Protokolle, um Versandprobleme zu beheben, die Interaktion zu analysieren und die Listenhygiene aufrechtzuerhalten.

**Verwandte Themen:**

[Versand-Monitoring](../send/send.md) | [Tracking-Anleitung](../send/tracking.md)

+++

+++ Wo finde ich Versandberichte?

Campaign bietet umfassende integrierte Berichte, um die Versandleistung, die Interaktion mit Empfängern und die Effektivität der Kampagne zu analysieren. Greifen Sie auf Berichte über die **[!UICONTROL Berichte]** in jedem Versand, über das Kampagnen-Dashboard oder über das globale Menü **[!UICONTROL Berichte]** für die kampagnenübergreifende Analyse zu.

**Zu den wichtigsten Berichten gehören:**

* **Versandzusammenfassung** - Versandstatistiken, Öffnungen, Klicks, Bounces und Abmeldungen
* **Klicks** - Visuelle Heatmap der Link-Performance
* **Tracking-Indikatoren** - Klickraten und Interaktionsmetriken
* **Fehler** - Bounce-Analyse mit Fehlerursachen

Berichte sind sowohl in der Client-Konsole als auch in der Campaign Web-Benutzeroberfläche mit modernen Visualisierungen verfügbar.

**Verwandte Themen:**

[Integrierte Versandberichte](../reporting/delivery-reports.md) | [Kampagnenberichte](../reporting/gs-reporting.md)

+++

+++ Wie qualifiziert und handhabt Adobe Campaign in Quarantäne befindliche Adressen?

Campaign verwaltet automatisch eine Quarantäneliste, um die Reputation Ihrer Absender zu schützen und die Zustellbarkeit zu verbessern. Quarantäneadressen werden automatisch von zukünftigen Sendungen ausgeschlossen, bis sie validiert oder aus der Quarantäne entfernt werden.

**Warum Adressen unter Quarantäne gestellt werden:**

* **Hardbounces** - Ständige Versandfehler (ungültige E-Mail-Adresse, Domain existiert nicht, Postfach gelöscht)
* **Schwellenwert für Softbounces** - Wiederholte temporäre Fehler (Postfach voll, Server vorübergehend nicht verfügbar), die den Fehlerschwellenwert überschreiten
* **Spam-Beschwerden** - Empfänger, die Ihre E-Mails als Spam markieren
* **Ungültige Adressen** - Adressen mit Syntaxfehlern oder fehlgeschlagener Validierung
* **Auf die Blockierungsliste gesetzt** - Empfänger, die sich per Opt-out abgemeldet haben oder einen Ausschluss beantragt haben

**Funktionsweise der Quarantäne:**

Campaign verfolgt Versandfehler für jede Adresse. Wenn eine Adresse den konfigurierten Fehlerschwellenwert erreicht, wird sie während der Analyse automatisch unter Quarantäne gestellt und von allen zukünftigen Sendungen ausgeschlossen. Hardbounces (dauerhafte Fehler) werden sofort unter Quarantäne gestellt, während Softbounces mehrere Fehler erfordern, bevor sie unter Quarantäne gestellt werden.

**Quarantäneadressen verwalten:**

Greifen Sie auf die Quarantäneverwaltung in **[!UICONTROL Administration > Kampagnenverwaltung > Unzustellbarkeitsverwaltung]** zu. Sie können unter Quarantäne gestellte Adressen anzeigen, validierte Adressen manuell aus der Quarantäne entfernen oder automatische Bereinigungsregeln konfigurieren.

**Tipp:** Überwachen Sie Ihre Quarantäneliste regelmäßig. Steigende Quarantäneraten deuten häufig auf Datenqualitätsprobleme hin, die beachtet werden müssen, bevor sie sich auf die Reputation des Absenders auswirken.

**Verwandte Themen:**

[Handbuch zur Quarantäneverwaltung](../send/quarantines.md) | [Bounce-Verwaltung](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Erfahren Sie, wie Sie mithilfe von Workflows Prozesse automatisieren, Daten verwalten und komplexe Marketing-Kampagnen in Adobe Campaign koordinieren können.

+++ Was ist ein Workflow?

Mit Adobe Campaign verfügen Sie über ein integriertes Workflow-Management-System, welches die zentrale Steuerung aller Prozesse und Vorgänge der Anwendung ermöglicht. Die Workflow-Engine dient der Modellierung und Automatisierung der verschiedenen Aufgaben der Anwendungs-Server-Module. Mithilfe der grafischen Oberfläche lassen sich vollständige Arbeitsabläufe zur Segmentierung von Zielgruppen, zur Ausführung von Kampagnen, zum Umgang mit Dateien etc. gestalten.

So bieten Workflows beispielsweise die Möglichkeit, Dateien von einem Server herunterladen, sie zu entkomprimieren und die Datensätze in die Adobe Campaign-Datenbank zu importieren.

Ein Workflow kann auch einen oder mehrere Benutzende einbinden, die benachrichtigt werden oder Entscheidungen treffen und Prozesse genehmigen können. Auf diese Weise können Versandaktionen erstellt und einem oder mehreren Benutzenden die Bearbeitung von Inhalten, die Bestimmung der Zielgruppen und die Validierung von Testsendungen vor dem Versandbeginn zugewiesen werden.

[Weitere Informationen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=de){target="_blank"} über Workflows. Informationen über [Best Practices bei Workflows finden Sie hier](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"}.

**Verwandte Themen:**

[Erste Schritte mit Workflows](../config/workflows.md) | [Erstellen des ersten Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"} | [Workflow-Anwendungsfälle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Überwachen der Workflow-Ausführung](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

+++

+++ Kann ich die Ausführung von Workflows überwachen?

Ja. Campaign bietet mehrere Überwachungs-Tools: Workflow-Dashboard (Echtzeitstatus und -fehler), Workflow-Protokolle (detaillierte Ausführungsprotokolle), Heatmap (visualisiert Aktivitäten und Engpässe), Audit-Protokoll (verfolgt Änderungen) und Warnhinweise (Benachrichtigungen bei Fehlern).

Öffnen Sie zum Überwachen den Workflow und klicken Sie auf die Registerkarte **Protokolle**. Fehlgeschlagene Aktivitäten werden rot angezeigt.

**Verwandte Themen:**

[Überwachen der Workflow-Ausführung](https://experienceleague.adobe.com/de/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [Best Practices für Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"}

+++

+++ Was sind die wichtigsten Schritte bei der Erstellung eines Workflows?

Erstellen von Workflows zur Automatisierung von Marketing-Prozessen in Campaign:

1. **Neuen Workflow erstellen** - Navigieren Sie zu **[!UICONTROL Profile und Zielgruppen > Vorgänge > Zielgruppen-Workflows]** oder **[!UICONTROL Administration > Produktion > Technische Workflows]** und klicken Sie auf **[!UICONTROL Erstellen]**
1. **Aktivitäten hinzufügen** - Ziehen und Ablegen von Aktivitäten aus der Palette (Zielgruppenbestimmung, Flusskontrolle, Aktionsaktivitäten)
1. **Aktivitäten konfigurieren** - Doppelklicken Sie auf jede Aktivität, um Parameter festzulegen und die Logik zu definieren
1. **Aktivitäten verbinden** - Verknüpfen von Aktivitäten mit Transitionen, um den Ausführungsfluss zu definieren
1. **Testen und Validieren** - Verwenden Sie das Workflow-Diagramm, um die Logik zu überprüfen, und testen Sie dann mit einem kleinen Datensatz.
1. **Ausführen** - Startet den Workflow manuell oder plant ihn für die automatische Ausführung

Häufige Workflow-Muster: Datenimport, Zielgruppensegmentierung, Versand, Datenanreicherung und kanalübergreifende Orchestrierung.

**Verwandte Themen:**

[Workflow erstellen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"} | [Workflow-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [Best Practices für Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"} | [Workflow-Anwendungsfälle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Wie kann ich wiederkehrende Kampagnen automatisieren?

Verwenden Sie Workflows mit der Aktivität **Planung**, um Kampagnen zu automatisieren, die nach einem regulären Zeitplan ausgeführt werden - täglich, wöchentlich, monatlich oder in benutzerdefinierten Intervallen. Ideal für Begrüßungs-E-Mails, Geburtstagsnachrichten, Newsletter-Sendungen, Erinnerungen an Transaktionsabbrüche und regelmäßige Berichte.

**Setup-Muster:**

1. **Planung** - Definieren der Häufigkeit (z. B. „Jeden Montag um 9 Uhr„)
2. **Abfrage** - Zielgruppe mit dynamischen Kriterien auswählen
3. **Anreicherung** (optional) - Personalisierungsdaten hinzufügen
4. **Versand**: Konfigurieren Ihrer Nachricht (E-Mail, SMS, Push)
5. **Ende** - Workflow wird abgeschlossen und wartet auf die nächste geplante Ausführung

**Häufige automatisierte Kampagnen:**

* **Willkommensreihe** - Täglicher Workflow zum Senden von Onboarding-E-Mails an neue Abonnenten
* **Geburtstags-E** - Täglicher Check für Empfänger mit Geburtstagen, Senden personalisierter Nachricht
* **Rückgewinnung** - Wöchentliches Targeting inaktiver Benutzer mit Win-Back-Angeboten
* **Newsletter** - Geplante wöchentliche oder monatliche Inhaltsverteilung
* **Warenkorbabbruch** - Stündlicher Workflow zur Identifizierung und Meldung von Warenkorbabbrüchen

**Tipp:** Verwenden Sie den **wiederkehrender Versand**-Typ in Workflows, um jede Ausführung separat zu verfolgen und historische Berichte zu verwalten.

**Verwandte Themen:**

[Planungsaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html?lang=de){target="_blank"} | [Wiederkehrende Sendungen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [Kampagnenautomatisierung](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=de){target="_blank"}

+++

+++ Wie kann ich Daten in Campaign importieren?

**Methoden:**-Importassistent (einmalige CSV/TXT), Workflow-basierter Import (**[!UICONTROL Laden (Datei)]** Aktivität für komplexe/wiederkehrende Importe mit Umwandlungen), REST-APIs (programmgesteuerte/Echtzeit-Synchronisierung).

**Best Practices:** Testen Sie mit kleinen Beispielen, verwenden Sie UTF-8-Kodierung, ordnen Sie Felder korrekt zu, wenden Sie Deduplizierung an, planen Sie große Importe außerhalb der Spitzenzeiten.

**Verwandte Themen:**

[Best Practices beim Import](../start/import.md) | [Aktivität „Laden“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=de){target="_blank"} | [Workflow für wiederkehrenden Import](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=de){target="_blank"}

+++

+++ Wie kann ich die Datenqualität während des Imports sicherstellen?

Die Datenqualität ist für eine erfolgreiche Kampagnenausführung von entscheidender Bedeutung. Schlechte Daten führen zu Versandfehlern, verschwendeten Ressourcen und Compliance-Risiken. Campaign bietet Tools zum Validieren, Bereinigen und Anreichern von Daten während des Importvorgangs.

**Schritte zur Datenvalidierung:**

1. **Validierung vor dem Import** - Überprüfen des Dateiformats, der Codierung (UTF-8), der Spaltenzuordnung und des Vorhandenseins erforderlicher Felder
2. **Deduplizierung** - Verwenden Sie **[!UICONTROL Deduplizierung]** Aktivität, um Duplikate per E-Mail, ID oder benutzerdefinierter Schlüssel zu identifizieren und zu verarbeiten
3. **Datenanreicherung** - Verwenden der Aktivität **[!UICONTROL Anreicherung]** um fehlende Daten aus bestehenden Campaign-Tabellen hinzuzufügen
4. **Formatstandardisierung** - Normalisieren von Telefonnummern, E-Mail-Adressen, Datumsangaben, Ländercodes mithilfe von JavaScript oder Anreicherung
5. **Validierungsregeln** - Anwenden von Einschränkungen (gültiges E-Mail-Format, Pflichtfelder, Wertebereiche)

**Häufige Probleme und Fehlerbehebungen:**

* **Zeichenkodierungsfehler** → Verwenden Sie immer UTF-8-Kodierung
* **Datumsformat stimmt nicht überein** → Standardisieren im Format JJJJ-MM-TT
* **Ungültige E-**-Adressen→ Verwenden Sie Validierungsregeln oder JavaScript zum Filtern
* **Datensätze duplizieren** Deduplizierungsaktivität → vor Aktualisierungen immer einschließen
* **Erforderliche Felder fehlen** → Standardwerte festlegen oder unvollständige Datensätze ablehnen

**Best Practice:** Erstellen Sie eine wiederverwendbare Workflow-Vorlage „Datenqualität“ mit standardmäßigen Validierungs- und Bereinigungsaktivitäten, die Sie auf alle Importe anwenden können.

**Verwandte Themen:**

[Datenqualitätshandbuch](../start/import.md) | [Aktivität „Deduplizierung“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=de){target="_blank"} | [Anreicherungsaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=de){target="_blank"}

+++

+++ Was sind in Campaign häufige Anwendungsfälle für Workflows?

Workflows automatisieren Marketing-Prozesse, darunter:

**Daten-Management:** Importieren/Laden von Daten, Bereinigung, Anreicherung, Listenverwaltung\
**Kampagnenautomatisierung:** Begrüßungsserie, Geburtstagskampagnen, Rückgewinnung, Warenkorbabbruch\
**Erweitertes Targeting** A/B-Tests, dynamische Segmentierung, Lead-Scoring, kanalübergreifende Orchestrierung\
**Überwachung:** Workflow-/Versandüberwachung, Warnhinweise, Datenbankwartung\
**Integration:** CRM-Synchronisierung, API-Integrationen, ereignisgesteuerte Workflows

**Verwandte Themen:**

[Anwendungsfallbibliothek für Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Workflow erstellen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"} | [Best Practices für Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"}

+++

+++ Wie kann ich Daten in Campaign mit einem Workflow aktualisieren?

Verwenden **[!UICONTROL Aktivität „Daten aktualisieren]** für Massendatenbankvorgänge: Einfügen (neue Datensätze hinzufügen), Aktualisieren (vorhandenes ändern), Einfügen oder Aktualisieren (upsert), Löschen (übereinstimmende Datensätze entfernen).

**Häufige Verwendungszwecke** Aktualisieren von Profilattributen, Synchronisieren mit externen Systemen, Verwalten von Listenmitgliedschaften, Bereinigen/Deduplizieren von Daten, Anwenden von Massenstatusänderungen.

Konfigurieren Sie Abstimmschlüssel für eine genaue Übereinstimmung und wählen Sie Aktualisierungsoptionen aus.

**Verwandte Themen:**

[Aktivität „Daten aktualisieren“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=de){target="_blank"} | [Datenverwaltungsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Wie kann ich Daten-Management-Funktionen verwenden?

Datenverwaltungsaktivitäten ermöglichen komplexe Operationen: Anreicherung (Hinzufügen von Daten aus verwandten Tabellen), Aufspaltung (Segmentpopulationen), Deduplizierung (Entfernen von Duplikaten), Datenaktualisierung (Massenvorgänge), Dimensionsänderung (Wechsel der Zielgruppendimensionen), Schnittmenge/Vereinigung/Ausschluss (Kombinieren/Filtern von Populationen).

**Häufige Verwendungszwecke** Anreicherung mit Kauf-/Verhaltensdaten, Segmentierung von Zielgruppen, Entfernen von Duplikaten, Integrieren externer Datenbanken (FDA), Erstellen komplexer Abfragen für mehrere Tabellen.

**Verwandte Themen:**

[Datenverwaltungsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Anreicherungsaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=de){target="_blank"}

+++

+++ Kann ich den Versand personalisierter Nachrichten automatisieren?

Ja. Automatisierte Workflows erstellen: Abfrage (Zielgruppe) → Anreicherung (Personalisierungsdaten hinzufügen) → Aufspaltung (optionale Segmente) → Versand (personalisierte Nachrichten) → Planung (wiederkehrende Ausführung).

**Personalization:** Verwenden von Profildaten, Verhaltensdaten, bedingten Inhalten und dynamischen Werten. Häufige Szenarien: Geburtstagskampagnen, Warenkorbabbruch, Treueprogramme, Win-Back-Nachrichten, Nachrichten, die durch ein Ereignis ausgelöst werden.

**Verwandte Themen:**

[Handbuch zu Personalization](../send/personalize.md) | [Workflow-Anwendungsfälle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=de){target="_blank"}

+++

+++ Wie kann ich eine Zielgruppe mit einem Workflow in Teilmengen unterteilen?

Verwenden Sie **[!UICONTROL Split]**-Aktivität, um Populationen aufzuteilen: Filterbedingungen (Alter, Standort, VIP-Status), prozentuale Verteilung (A/B-Tests), Limitdatensätze (erste N, oberste X %), Datengruppierung (eine Untergruppe pro Wert).

**Häufig verwendet:** A/B-Tests, Routing mit Kanalvoreinstellungen, progressiver Rollout, segmentspezifisches Messaging, Lastenausgleich. Jede Teilmenge fließt zu separaten Transitionen für unterschiedliche Verarbeitungsvorgänge.

**Verwandte Themen:**

[Aufspaltungsaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=de){target="_blank"} | [A/B-Test-Handbuch](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Wie kann ich Empfängerdaten durch eine externe Datei aktualisieren?

Ja. Workflow: Laden (Datei) → Anreicherung (optional) → Abstimmung (Übereinstimmungsschlüssel wie E-Mail/ID) → Daten aktualisieren (übereinstimmende Datensätze aktualisieren, neue einfügen, wenn keine Übereinstimmung vorliegt).

**Häufige Verwendungszwecke** Aktualisieren von Profilattributen aus dem CRM, Aktualisieren des Abonnementstatus, Synchronisieren von Treuepunkten, Aktualisieren der Opt-in-/Opt-out-Voreinstellungen.

**Best Practices:** Verwenden eindeutiger Kennungen, Validieren der Daten zuerst, Testen mit Beispielen, Planen regelmäßiger Aktualisierungen.

**Verwandte Themen:**

[Datenimport-Handbuch](../start/import.md) | [Aktivität „Laden“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=de){target="_blank"} | [Aktivität „Daten aktualisieren“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=de){target="_blank"}

+++

+++ Wie kann ich neue Empfänger identifizieren und ansprechen?

Abfrage **[!UICONTROL Erstellungsdatum]**, um innerhalb eines bestimmten Zeitraums hinzugefügte Empfänger auszuwählen.

**Automatisierter Begrüßungs-Workflow:** Planung (täglich ausgeführt) → Abfrage (neue Empfänger auswählen) → Deduplizierung (optional) → Versand (Willkommensnachricht) → Daten aktualisieren (als „willkommen“ markieren).

**Erweitert:** Verwenden Sie Aggregatfunktionen, um kürzlich hinzugefügte Komponenten dynamisch zu identifizieren.

**Verwandte Themen:**

[Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"} | [Verwenden von Aggregaten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=de){target="_blank"}

+++

+++ Wie verwende ich Workflow-Aktivitäten?

Vier Aktivitätskategorien:

**Zielgruppenbestimmung:** Abfrage, Aufspaltung, Deduplizierung, Anreicherung, Schnittmenge, Vereinigung, Ausschluss (Zielgruppe definieren/verfeinern)\
**Flusssteuerung:**, Warten, Testen, Verzweigung, UND-Verknüpfung, ODER-Verknüpfung, Springen (Logik/Timing verwalten)\
**Aktion:** Versand, Daten-Update, Laden/Extrahieren von Daten, JavaScript-Code (Vorgänge ausführen)\
**Ereignis:** Externes Signal, Datei-Wächter, HTTP-Übertragung (Reaktion auf Trigger)

Ziehen Sie aus der Palette, doppelklicken Sie zum Konfigurieren, verbinden Sie sich mit Übergängen.

**Verwandte Themen:**

[Zielgruppenbestimmungsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=de){target="_blank"} | [Flusskontrolle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=de){target="_blank"} | [Aktionsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=de){target="_blank"}

+++

+++ Was sind die Best Practices für Workflows?

**Design:** Namen löschen, Beschriftungen/Beschreibungen hinzufügen, verwandte Aktivitäten gruppieren, komplexe Prozesse in kleinere Workflows aufteilen\
**Leistung:** Begrenzung der Abfragegrößen, Verwendung temporärer Tabellen, Planung von Nebenzeiten, Vermeidung übermäßiger Schleifen\
**Fehlerbehandlung:** Fehlerpfade hinzufügen, Warnhinweise konfigurieren, mit Beispielen testen, Protokolle überprüfen\
**Wartung:** Archivieren veralteter Workflows, Versionskontrolle, Begrenzung der Komplexität (&lt;20 Aktivitäten), Verwenden von Vorlagen\
**Sicherheit:** Berechtigungen anwenden, temporäre Daten bereinigen, Variablen ohne hartcodierte Werte verwenden

**Verwandte Themen:**

[Handbuch mit Best Practices für Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"} | [Überwachen von Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

+++

## Kampagneneinstellungen {#settings}

Konfigurieren Sie Ihre Campaign-Instanz mit den richtigen Einstellungen, Integrationen und Konfigurationen, um Ihre Marketing-Vorgänge zu optimieren.

+++ Kann ich die Sprache der Benutzeroberfläche von Campaign ändern?

Es hängt davon ab, welche Benutzeroberfläche Sie verwenden. Die Sprache **Client-**) ist fest, aber die **Campaign Web-Benutzeroberfläche** ermöglicht es einzelnen Benutzern, ihre Spracheinstellungen zu ändern.

**Client-Konsole (Desktop-Programm):**

* Die Sprache wird beim Erstellen der Instanz festgelegt und kann nicht geändert werden
* Client-Konsole und Server müssen dieselbe Sprache verwenden
* Jede Campaign-Instanz wird in einer einzigen Sprache ausgeführt
* Bei englischen Installationen können Sie zwischen Englisch (USA) oder Englisch (Großbritannien) wählen (sie unterscheiden sich in Datums- und Uhrzeitformaten)

**Campaign Web-Benutzeroberfläche:**

* Benutzer können die Sprache ihrer Benutzeroberfläche über ihre Profilvoreinstellungen selbstständig ändern
* Mehrere Sprachen werden mit gebietsschemaspezifischer Formatierung für Daten, Uhrzeiten und Zahlen unterstützt
* Die Spracheinstellung der Web-Benutzeroberfläche ist unabhängig von der Sprache Ihres Campaign-Servers und Ihrer Client-Konsole


**Verwandte Themen:**

[Ändern der Sprache in der Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Erste Schritte mit der Campaign-Client-Konsole](connect.md)

+++

+++ Was ist das Campaign Control Panel und wie greife ich darauf zu?

Das Campaign Control Panel ist eine Web-basierte Verwaltungsoberfläche, mit der Campaign-Administratoren die Effizienz steigern können, indem sie die Einstellungen und die Nutzung in allen Campaign-Instanzen verwalten. Es bietet Self-Service-Funktionen zum Verwalten kritischer Instanzkonfigurationen, ohne sich an den Adobe-Support wenden zu müssen.

**Schlüsselfunktionen:**

* **Subdomain-Verwaltung** - Subdomains delegieren und verwalten, SSL-Zertifikate überwachen
* **Speicherüberwachung** - Verfolgen Sie die Datenbanknutzung und vermeiden Sie Speicherprobleme.
* **SFTP-**: Überwachen des SFTP-Speichers, Verwalten von IP-Zulassungslisten und SSH-Schlüsseln
* **Instanzeinstellungen** - IP-Zulassungslisten konfigurieren, URL-Berechtigungen verwalten, Instanzdetails überprüfen
* **Überwachung aktiver Profile** - Verfolgen der aktiven Profilnutzung anhand von Berechtigungen
* **Leistungsüberwachung** - Überwachen der Datenbank- und Workflow-Leistung
* **E-Mail** Zustellbarkeit: Konfigurieren von DMARC-, BIMI- und anderen Authentifizierungsdatensätzen

**Zugriffsanforderungen:**

* **Nur Admin-Benutzer** - Das Control Panel ist auf Benutzer mit Administratorrechten beschränkt
* **Adobe IMS-Authentifizierung** - Zugriff über Adobe Experience Cloud mit Ihrer Adobe ID
* **Campaign v8 Managed Cloud Services** - Nur für gehostete Instanzen verfügbar

**Zusätzliche Ressourcen:**

[Control Panel-Dokumentation](https://experienceleague.adobe.com/de/docs/control-panel/using/control-panel-home){target="_blank"} | [Anleitungsvideos zum Control Panel](https://experienceleague.adobe.com/de/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ Wie funktioniert das Verfahren der Domain-Delegation?

Sie können Ihre Domain in Subdomains unterteilen, um Ihre Marken oder unterschiedlichen Textsorten (Transaktionsnachrichten, Marketing-Informationen usw.) voreinander zu trennen.

>[!NOTE]
>
>Wenn Sie Managed Cloud Services nutzen, kontaktieren Sie Adobe, um Ihre Subdomains an Adobe zu delegieren.

+++

+++ Wie kann ich Tracking-Funktionen in meiner Campaign-Instanz einrichten?

Campaign v8 bietet ein umfassendes Tracking zur Überwachung der Empfängerinteraktionen mit Ihren Nachrichten. Für das Tracking ist eine ordnungsgemäße Konfiguration Ihrer Instanz und der Nachrichteneinstellungen erforderlich.

**Was Sie verfolgen können:**

* **E-Mail wird geöffnet** - Über Tracking-Pixel (1 x 1 transparentes Bild)
* **Link-Klicks** - Alle URLs werden automatisch in getrackte Links konvertiert
* **Abmeldungen** - Opt-out-Linktracking
* **Mirrorseitenansichten** - Wenn Empfänger die Web-Version anzeigen
* **Benutzerdefinierte Parameter** - Hinzufügen von Tracking-Daten zu URLs für erweiterte Analysen

**Wichtige Konfigurationsschritte:**

1. Konfigurieren der Tracking-Server-URL in Ihren Instanzeinstellungen (von Adobe für v8 verwaltet)
2. Aktivieren des Trackings in den Versandeigenschaften
3. Automatisches Einrichten des Trackings für einzelne Links oder alle Links
4. Definieren des Tracking-Gültigkeitszeitraums und der Protokollaufbewahrung

**Best Practice:** Testen Sie Tracking immer mit Testsendungen, bevor Sie es an Ihre Hauptzielgruppe senden. So stellen Sie sicher, dass Links ordnungsgemäß funktionieren und Daten erfasst werden.

**Verwandte Themen:**

[Verfolgen und Überwachen von Sendungen](../send/tracking.md) | [Konfigurieren getrackter Links](../send/tracked-links.md) | [Tracking testen](../send/testing-tracking.md)

+++

+++ Wie kann ich den E-Mail-Versand konfigurieren?

Die Zustellbarkeit der E-Mails hängt von der technischen Konfiguration, der Qualität der Inhalte und der Reputation des Absenders ab. Campaign v8 bietet Tools und Einstellungen zur Optimierung der Platzierung im Posteingang.

**Wesentliche Konfigurationsschritte:**

* **Domain-Authentifizierung** - Richten Sie SPF-, DKIM- und DMARC-Einträge ein, um Ihre Versand-Domain zu überprüfen
* **IP-Warming** - Erhöhen Sie das Versandvolumen bei neuen IPs schrittweise, um die Reputation zu verbessern
* **Absenderkonfiguration** - Verwenden Sie konsistente, erkennbare Absenderadressen und -namen
* **Bounce-Verwaltung** - Konfigurieren von Quarantäneregeln zur automatischen Verarbeitung von Hard- und Softbounces
* **Feedback Loops** - Richten Sie die Behandlung von Beschwerden ein, um Spam-Berichte zu verwalten

**Best Practices für Inhalte:**

* Testen von E-Mails mit SpamAssassin zur Überprüfung der Spam-Punktzahl
* Beibehaltung des korrekten Text-Bild-Verhältnisses
* Nur-Text-Version neben HTML einschließen
* Abmelde-Link immer angeben
* Vermeiden Sie Spam-Trigger und übermäßige Großschreibung

**Monitoring** Verwenden Sie die Zustellbarkeitsberichte von Campaign, um Bounce-Raten, Beschwerderaten und die Platzierung im Posteingang zu verfolgen. Für Campaign v8 bietet Adobe eine Zustellbarkeitsoptimierung auf Infrastrukturebene.

**Verwandte Themen:**

[Über die Zustellbarkeit in Campaign](../send/about-deliverability.md) | [Best Practice-Handbuch zur Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"}

+++

+++ Welche externen Datenbanken kann ich mit Campaign verknüpfen?

Campaign v8 unterstützt Federated Data Access (FDA)-Verbindungen zu wichtigen Unternehmensdatenbanksystemen (Cloud-Datenbanken, Unternehmensdatenbanken, Data Warehouses, Big-Data-Plattformen).

Unterstützte Datenbankversionen und Verbindungsanforderungen variieren. Überprüfen Sie die [Kompatibilitätsmatrix](compatibility-matrix.md) für Ihre Campaign v8-Version, um die Unterstützung für bestimmte Datenbanken zu bestätigen und eine ordnungsgemäße Lizenzierung für FDA-Connectoren sicherzustellen.

Siehe [Konfigurieren von FDA-Verbindungen](../connect/fda.md)

+++

+++ Kann Adobe Campaign in CRM-Systeme integriert werden?

Ja. Campaign bietet native CRM-Connectoren für die bidirektionale Synchronisation mit wichtigen CRM-Systemen. Synchronisiert Kontaktdaten, Leads, Konten, Versandlogs, Tracking-Daten und Interaktionsmetriken. Unterstützt geplante, manuelle und Echtzeit-Synchronisierungsmodi (über API).

Verwenden Sie den CRM-Connector-Assistenten von Campaign, um Felder zuzuordnen, Tabellen auszuwählen und die Synchronisierung zu planen. Überprüfen Sie [Kompatibilitätsmatrix](compatibility-matrix.md) auf unterstützte CRM-Versionen.

**Verwandte Themen:**

[CRM-Connector-Konfiguration](../connect/crm.md) | [Workflow-CRM-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=de){target="_blank"}

+++

+++ Wie leere ich den Cache der Client-Konsole?

Durch Löschen des Caches der Client-Konsole werden viele gängige Anzeige- und Funktionsprobleme behoben. Der Cache speichert lokale Konfigurationsdateien, die gelegentlich beschädigt oder veraltet sein können.

**In folgenden Fällen sollte der Cache geleert werden:**

* Neue Branding-Elemente (Logos, Farben) werden nicht korrekt angezeigt
* Export-/Importfunktionen schlagen unerwartet fehl
* Elemente der Benutzeroberfläche werden nach Konfigurationsänderungen nicht aktualisiert
* Leistungsprobleme oder langsame Konsolenreaktion
* Nach dem Upgrade auf eine neue Version der Client-Konsole

**Schritte zum Löschen des Cache:**

1. Öffnen Sie die Campaign-Client-Konsole
2. Öffnen Sie das Menü **[!UICONTROL Datei]**
3. Wählen Sie **[!UICONTROL Lokalen Cache leeren…]** aus
4. Bestätigen Sie die Aktion bei Aufforderung
5. Starten Sie die Client-Konsole neu

Weitere Informationen finden Sie unter [Installieren und Konfigurieren der Client-Konsole](connect.md)

+++

+++ Kann ich Einstellungen für die Benutzeroberfläche konfigurieren?

Ja. Campaign-Admins können die Benutzeroberfläche an das Branding ihrer Organisation anpassen und das Benutzererlebnis optimieren. Konfigurieren Sie Einstellungen auf Instanz- oder Benutzerebene.

**Was Sie anpassen können:**

* **Branding** - Logo, Farben und visuelle Identitätselemente
* **Standardansichten** - Startseiten-Layout, Sichtbarkeit der Ordnerstruktur
* **Listenkonfigurationen** - Standardspalten, Sortierreihenfolge, Filter in Datenlisten
* **Navigation** - Verfügbare Menüelemente und Tastaturbefehle
* **Regionale Einstellungen** - Datums-/Zeitformate, Zahlenformate, Zeitzonen
* **Benachrichtigungen** - E-Mail-Warnungen, In-App-Benachrichtigungen, Workflow-Warnungen

**Konfigurationsebenen:**

* **Instanzweit** - Auf alle Benutzer anwenden (Administratorrechte erforderlich)
* **Benutzerspezifisch** - Individuelle Voreinstellungen und persönliche Einstellungen

**Verwandte Themen:**

[Konfigurieren von Benutzeroberflächeneinstellungen](../config/ui-settings.md) | [Benutzerberechtigungen](gs-permissions.md)

+++

+++ Kann ich benutzerdefinierte Felder und Tabellen erstellen?

Ja. Das flexible Datenmodell von Campaign ermöglicht es Ihnen, integrierte Schemata mit benutzerdefinierten Feldern zu erweitern und völlig neue Tabellen zu erstellen, um Ihre spezifischen Geschäftsanforderungen zu erfüllen.

**Was Sie anpassen können:**

* **Felder zu vorhandenen Tabellen hinzufügen** - Empfängertabelle um Treuepunkte, benutzerdefinierte Voreinstellungen und externe IDs erweitern
* **Neue benutzerdefinierte Tabellen erstellen** - Produkte, Transaktionen, Treuestufen, benutzerdefinierte Entitäten speichern
* **Definieren von Beziehungen** - Verknüpfen benutzerdefinierter Tabellen mit vorhandenen Campaign-Tabellen
* **Formulare erweitern** - Aktualisieren der Benutzeroberfläche zum Anzeigen und Bearbeiten benutzerdefinierter Felder

**Häufige Anwendungsfälle:**

* Speichern zusätzlicher Profilattribute (Kundenlebenszeitwert, bevorzugter Store, VIP-Status)
* Verwalten von Produktkatalogen mit benutzerdefinierten Attributen
* Benutzerdefinierte Ereignisse und Interaktionen verfolgen
* Integrieren externer System-IDs für die Datensynchronisation
* Erstellen branchenspezifischer Datenmodelle (Einzelhandel, Finanzen, Reisen)

**Verwandte Themen:**

[Datenmodell erweitern](../dev/extend-schema.md) | [Schemastruktur](../dev/schemas.md) | [Best Practices für Datenmodelle](../dev/datamodel-best-practices.md)

+++

## Reporting {#reporting}

Erhalten Sie Einblicke in die Reporting-Funktionen von Campaign, einschließlich integrierter Berichte, benutzerdefinierter Berichte und Datenanalysetools wie Cubes.

+++ Wie kann ich neue Berichte erstellen?

Campaign bietet je nach Bedarf und technischem Know-how verschiedene Reporting-Optionen: integrierte Berichte, deskriptive Analysen, benutzerdefinierte Berichte in der Client-Konsole und Cubes.

**Berichtsoptionen:**

* **Integrierte Berichte** - Einsatzbereite Versand-, Kampagnen- und Tracking-Berichte, die über die Registerkarte **[!UICONTROL Berichte]** zugänglich sind
* **Deskriptive Analyse** - Schnelle statistische Berichte zu beliebigen Daten mit einer assistentengesteuerten Oberfläche
* **Benutzerspezifische Berichte** - Erweiterte Berichte, die von technischen Anwendern mit dem Reporting-Editor erstellt wurden
* **Cubes** - Mehrdimensionale Datenexploration und Pivot-Tabellenanalyse

**Wichtig:** Campaign wurde für die Berichterstellung zu Marketing-Vorgängen entwickelt, nicht als spezielles Business Intelligence-Tool. Bei komplexen Analyseanforderungen sollten Sie die Integration mit Adobe Analytics oder dedizierten BI-Plattformen in Betracht ziehen.

**Verwandte Themen:**

[Erste Schritte mit Reporting](../reporting/gs-reporting.md) | [Berichte der Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ Wie kann ich Statistikberichte zu Populationen erstellen und teilen?

Mit dem deskriptiven Analyse-Tool von Campaign können Sie schnell statistische Berichte zu Populationsdaten erstellen. Mit dieser assistentengesteuerten Funktion können Sie Verteilungen, Trends und Muster ohne technisches Know-how analysieren.

**Was Sie analysieren können:**

* Aufschlüsselung der Empfängerdemografie und Segmentierung
* Leistungsmetriken und Reaktionsraten von Campaign
* Verteilung von Profilattributen (Alter, Standort, Voreinstellungen)
* Versandstatistiken und Interaktionsmuster
* Benutzerdefinierte Feldwerte und Metriken zur Datenqualität

**Erstellen:** Wählen Sie eine Liste oder ein Abfrageergebnis aus → klicken Sie mit der rechten Maustaste auf → **[!UICONTROL Aktionen > Analysieren]** → wählen Sie den Analysetyp (qualitativ oder quantitativ) → konfigurieren Sie Anzeigeoptionen → Bericht erstellen.

**Freigabe** Exportieren Sie Berichte nach Excel/PDF oder speichern Sie sie im Ordner **[!UICONTROL Berichte]**, um Team-Zugriff mit entsprechenden Berechtigungen zu erhalten.

Weitere Informationen über [deskriptive Analyse](../reporting/built-in-reports.md)

+++

+++ Wie kann ich erweiterte Berichte zu meinen Daten erstellen?

Verwenden Sie die Client-Konsole, um erweiterte benutzerdefinierte Berichte mit komplexen Analysefunktionen zu erstellen.

In der Client-Konsole haben Sie folgende Möglichkeiten:

* Erstellen komplexer Berichte mithilfe von SQL-Abfragen und benutzerdefinierten Berechnungen
* Erstellen mehrseitiger Berichte mit Diagrammen, Tabellen und Pivot-Tabellen
* Entwerfen bedingter Formatierung und dynamischer Inhalte
* Zugriff auf das vollständige Campaign-Datenmodell und externe Datenbanken (FDA)

Erfahren Sie, wie [&#x200B; benutzerdefinierte Berichte erstellen (Client-Konsole)](../reporting/custom-reports.md)

+++

+++ Was ist ein Cube und wie kann ich ihn für das Reporting verwenden?

Cubes sind mehrdimensionale Datenstrukturen, mit denen Business-Anwender Campaign-Daten ohne technische Kenntnisse mithilfe von Pivot-Tabellen untersuchen und analysieren können. Stellen Sie sie sich als vorkonfigurierte Datenmodelle vor, die komplexe Berichte vereinfachen. Dieses Reporting-Tool ist sowohl in der Client-Konsole als auch in der Campaign Web-Benutzeroberfläche verfügbar.

* Technische Benutzende erstellen und konfigurieren Cubes, die Dimensionen (Zeit, Geografie, Kanäle) und Kennzahlen (Öffnungen, Klicks, Umsatz) definieren
* Business-Anwender wählen beim Erstellen von Berichten und Drag-and-Drop von Dimensionen einen Cube aus, um Daten zu untersuchen
* Die Daten werden automatisch aggregiert und basierend auf der Cube-Konfiguration berechnet
* Ergebnisse können als Pivot-Tabellen, Diagramme oder nach Excel exportiert werden

Erfahren Sie, wie [Daten mit Cubes erkunden](../reporting/gs-cubes.md)

+++

+++ Kann ich einen Bericht aus Antworten auf eine Online-Umfrage erstellen?

Ja! Campaign enthält ein Umfragemodul, mit dem Sie Online-Fragebögen erstellen und integrierte Berichte zu Umfrageantworten generieren können.

**Wichtig:** Die Umfrageverwaltung ist in Campaign v8 Enterprise (FFDA)-Bereitstellungen nicht verfügbar. [Weitere Informationen](../architecture/enterprise-deployment.md).

**Umfragefunktionen:**

* Erstellen von Online-Fragebögen mit mehreren Seiten und Fragetypen
* Sammeln von Antworten in der Datenbank oder lokalen Variablen
* Echtzeit-Tracking der Umfrageantworten anzeigen
* Erstellung spezieller Berichte zu Umfrageantworten (Aufschlüsselung nach Fragen, allgemeine Statistiken)
* Exportieren von Umfrageantworten nach Excel, PDF oder CSV für weitere Analysen
* Verwenden von Umfragedaten in Zielgruppen-Workflows zur Personalisierung von Kampagnen

**Erweiterte Analyse:**

* Greifen Sie über die Registerkarte **[!UICONTROL Antworten“ auf]** Umfrageantworten zu und exportieren Sie Daten
* Verwenden **[!UICONTROL Aktivität „Umfrageantworten]** in Workflows, um Empfänger anhand ihrer Antworten anzusprechen
* Kombinieren von Umfragedaten mit anderen Campaign-Daten zur Segmentierung und Personalisierung
* Erstellen benutzerdefinierter Berichte und Cubes für die mehrdimensionale Umfrageanalyse

**Verwandte Themen:**

[Erste Schritte mit Umfragen](https://experienceleague.adobe.com/de/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Umfrageberichte](https://experienceleague.adobe.com/de/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Wie kann ich den Zugriff auf meine Berichte freigeben?

Kontrollieren Sie die Sichtbarkeit von Berichten über Ordnerberechtigungen und spezifische Berechtigungen in Campaign.

**Zugriffssteuerungsmethoden:**

* **Ordnerberechtigungen** - Platzieren von Berichten in Ordnern mit geeignetem Zugriff für Benutzergruppen
* **Spezifische Berechtigungen** - Zuweisen von Rechten zum Anzeigen, Erstellen oder Ändern von Berichten
* **Anzeigekontext** - Festlegen, wo Berichte angezeigt werden (Berichtsordner, Kampagnen-Registerkarten, Versandbildschirme)

**Setup** Bericht in einem bestimmten Ordner speichern → Ordnerzugriff für Benutzergruppen konfigurieren → Berichteigenschaften und Anzeigekontext definieren.

**Verwandte Themen:**

[Benutzerdefinierte Berichte](../reporting/custom-reports.md) | [Benutzerberechtigungen](gs-permissions.md)

+++

+++ Kann ich Berichte in verschiedenen Formaten exportieren?

Ja, Campaign unterstützt mehrere Exportformate für Berichte sowohl der Client-Konsole als auch der Web-Benutzeroberfläche und ermöglicht so eine einfache Freigabe für Stakeholder und Integration mit anderen Tools.

**Verfügbare Exportformate:**

* **Excel (.xlsx)** - Am besten geeignet für Datenmanipulationen, weitere Analysen und Pivot-Tabellen
* **PDF** - Ideal für Präsentationen, Zusammenfassungen für Führungskräfte und gedruckte Berichte
* **CSV** - Ideal für Datenimporte in andere Systeme und BI-Tools
* **OpenDocument (.ods)** - Open-Source-Tabellenformat
* **XML** - Für Systemintegrationen und automatisierte Verarbeitung

**So exportieren Sie:**

* **Client-Konsole:** Bericht öffnen → auf die Schaltfläche **[!UICONTROL Exportieren]** klicken → Format auswählen → Datei speichern
* **Web-Benutzeroberfläche:** Dashboard öffnen → auf das Exportsymbol klicken → Format auswählen → Herunterladen
* **Automatisierte Exporte:** Planen Sie regelmäßige Exporte mithilfe von Workflows mit Exportaktivitäten

**Best Practices:**

* Excel für Berichte verwenden, die eine Analyse der Stakeholder und Anmerkungen erfordern
* Verwenden Sie PDF für statische Berichte, die an Führungskräfte gesendet oder zur Einhaltung archiviert werden
* Verwenden von CSV für Integrationen mit Data Warehouses oder externen Analyse-Tools
* Testen exportierter Berichte zur Sicherstellung der Formatierung und Datengenauigkeit

**Verwandte Themen:**

[Benutzerdefinierte Berichte](../reporting/custom-reports.md) | [Berichte der Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Entwickler {#developers}

Zugreifen auf technische Informationen für Entwickler, einschließlich Datenmodelldetails, Schemata, APIs und Anpassungsfunktionen.

+++ Was ist das Campaign-Datenmodell?

Das Datenmodell von Campaign ist eine schemabasierte relationale Datenbankstruktur, die aus integrierten Tabellen (Empfängerinnen und Empfänger, Sendungen, Kampagnen) besteht, die für Ihre Geschäftsanforderungen erweitert werden können.

**Schlüsselkonzepte:** (XML-Definitionen), integrierte Tabellen, Links (Beziehungen), Auflistungen (Wertelisten), Erweiterungen (benutzerdefinierte Felder/Tabellen).

**Hauptschemata:** Empfänger (`nms:recipient`), Versand (`nms:delivery`), Workflow (`xtk:workflow`), Kampagne (`nms:operation`), Trackinglogs.

Das Verständnis des Datenmodells ist für Workflows, Abfragen, Schemaerweiterungen und Integrationen von entscheidender Bedeutung.

**Verwandte Themen:**

[Campaign-Datenmodell](../dev/datamodel.md) | [Best Practices für Datenmodelle](../dev/datamodel-best-practices.md)

+++

+++ Wie funktionieren Schemata in Campaign?

Schemata definieren die Datenstruktur von Campaign im XML-Format und geben die Tabellenstruktur, die Feldeigenschaften, Beziehungen, Indizes und die Zugriffssteuerung an.

**Arbeiten mit Schemata:**

* **Anzeigen:** Zugriff über **[!UICONTROL Administration > Konfiguration > Datenschemata]**
* **Erweitern:** Erstellen Sie Erweiterungsschemata (z. B. `cus:recipient`), um benutzerdefinierte Felder hinzuzufügen, ohne die Kernschemata zu ändern
* **Erstellen** Erstellen neuer Tabellen für geschäftsspezifische Daten
* **Aktualisieren** Änderungen über &quot;**[!UICONTROL &quot; > „Erweitert“ > „Datenbankstruktur aktualisieren“]**

**Häufige Verwendungszwecke** Hinzufügen benutzerdefinierter Felder zur Empfängertabelle, Erstellen benutzerdefinierter Tabellen, Definieren von Beziehungen und Implementieren geschäftsspezifischer Modelle.

**Wichtig:** Nie integrierte Schemata direkt ändern. Verwenden Sie immer Erweiterungsschemata, um die Upgrade-Kompatibilität zu gewährleisten.

**Verwandte Themen:**

[Erste Schritte mit Schemata](../dev/schemas.md) | [Schema erweitern](../dev/extend-schema.md)

+++

+++ Wie wird eine benutzerdefinierte Empfängertabelle verwendet?

Verwenden Sie beim Targeting von B2B-Konten, separaten Abonnentendaten, externen Systemen oder Mehrmarkenarchitekturen eine benutzerdefinierte Empfängertabelle anstelle der standardmäßigen Empfängertabelle.

**Implementierung:** Sie ein benutzerdefiniertes Schema mit Pflichtfeldern (E-Mail, Primärschlüssel, Ausschlüsse) → konfigurieren Sie Zielgruppen-Mappings → aktualisieren Sie Versandvorlagen → passen Sie Workflows/Abfragen an.

**Wichtige Überlegungen:** müssen die erforderlichen Versandfelder enthalten, Workflows/Formulare müssen angepasst und vor der Produktionsmigration getestet werden.

**Best Practice:** Erweitern Sie zuerst die standardmäßige Empfängertabelle. Verwenden Sie benutzerdefinierte Tabellen nur, wenn dies aufgrund der zusätzlichen Komplexität wirklich erforderlich ist.

**Verwandte Themen:**

[Benutzerdefinierte Empfängertabelle](../dev/custom-recipient.md) | [Zielgruppen-Mappings](../audiences/target-mappings.md)

+++

+++ Was sind die Best Practices zum Definieren von Abfragen in Campaign?

Der Abfrage-Editor von Campaign erstellt Datenbankabfragen visuell ohne SQL, die in Workflow-Aktivitäten, Versand-Targeting, Listen, Berichten und Filtern verwendet werden.

**Best Practices:**

* Einfach starten - Schritt für Schritt inkrementell erstellen und testen
* Filterdimensionen verwenden - Tabellenbeziehungen nutzen
* Leistung optimieren - Indizieren Sie abgefragte Felder, vermeiden Sie komplexe Berechnungen
* Wiederverwenden vordefinierter Filter für Konsistenz
* Zuerst mit kleinen Proben testen
* Komplexe Dokumentabfragen

**Häufige Muster:** Versandöffner ansprechen, inaktive Kontakte suchen, nach Verhalten segmentieren, frühere Empfänger ausschließen.

**Zugriff:** **[!UICONTROL Tools > Generischer Abfrage-Editor]** für die Ad-hoc-Untersuchung.

**Verwandte Themen:**

[Abfrage-Editor](../start/query-editor.md) | [Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"}

+++

+++ Wie kann ich Daten-Packages importieren?

Package-Import über **[!UICONTROL Tools > Erweitert > Package-Import]** in der Client-Konsole. Pakete enthalten Campaign-Konfigurationen (Schemata, Workflows, Typologien) und Daten für die Bereitstellung zwischen Instanzen.

**Pakettypen:** Benutzerpaket (benutzerdefinierte Konfigurationen), Plattformpaket (von Adobe bereitgestellt), Datenpaket (tatsächliche Daten).

**Best Practices:** Testen Sie zuerst in der Entwicklungsumgebung, sichern Sie sie vor dem Import, exportieren Sie aus derselben/älteren Version.

Weitere Informationen finden Sie unter [Arbeiten mit Datenpaketen](../dev/packages.md)

+++

+++ Wo finde ich die Liste der Campaign v8-APIs?

Campaign v8 stellt SOAP-APIs (Client-Konsolenvorgänge), REST-APIs (moderne Integrationen) und JavaScript-APIs (Workflow-Skripterstellung) bereit.

**Häufige Verwendungszwecke:** Integration mit CRM/ERP, Automatisierung von Kampagnen, Datensynchronisation, Erstellen von Überwachungslösungen, Erstellen externer Schnittstellen.

**Zugriff:** [API-Dokumentation zu Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=de){target="_blank"}

+++


+++ Wie kann ich Workflows über die API überwachen?

Mit Campaign-APIs können Sie Workflows programmgesteuert steuern: Starten, Pausieren/Fortsetzen, Stoppen, Abfragestatus, Protokolle abrufen, den Aktivitätsfortschritt überwachen.

**API-Endpunkt:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Befehle:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**Anwendungsfälle:** Erstellen von Überwachungs-Dashboards, Implementieren automatisierter Warnhinweise, Orchestrierung aus externen Zeitplänen, Erstellen von Abhängigkeiten über Instanzen hinweg, Generieren benutzerdefinierter Berichte.

**Best Practice:** Kombinieren Sie API-Überwachung mit Audit-Protokoll für eine umfassende Governance.

Siehe [Steuern von Workflows über API](../dev/api/controlling-a-workflow.md)

+++

+++ Wie kann ich die Datenbankstruktur aktualisieren?

Nach dem Ändern von Schemata (Hinzufügen von Feldern, Erstellen von Tabellen, Ändern von Datentypen), aktualisieren Sie die physische Datenbankstruktur über **[!UICONTROL Tools > Erweitert > Datenbankstruktur aktualisieren]** um Änderungen anzuwenden.

**Bei Bedarf:** Hinzufügen von Feldern, Erstellen/Erweitern von Tabellen, Ändern von Feldeigenschaften, Hinzufügen/Entfernen von Links, Erstellen von Indizes.

**Wichtig:** Sie zuerst die Sicherung, testen Sie sie in der Entwicklungsumgebung, planen Sie Ausfallzeiten für große Änderungen, stimmen Sie sich mit der Adobe-Unterstützung (Managed Cloud Services) ab und beachten Sie, dass einige Änderungen Datenverlust verursachen können.


**Verwandte Themen:**

[Datenbankstruktur aktualisieren](../dev/update-database-structure.md) | [Schema erweitern](../dev/extend-schema.md)

+++

## Datenschutz {#privacy}

Erfahren Sie, wie Sie mit Adobe Campaign Datenschutzbestimmungen wie die DSGVO und den CCPA einhalten und Anfragen von betroffenen Personen verwalten können.

+++ Was sind die wichtigsten Datenschutzkonzepte in Campaign?

Campaign unterstützt Sie bei der Einhaltung von Datenschutzbestimmungen (DSGVO, CCPA, PDPA, LGPD) durch Tools zur Verwaltung der Rechte betroffener Personen, der Einwilligung und der Datenspeicherung. Zu den wichtigsten Konzepten gehören Datenschutzbestimmungen, die Identifizierung personenbezogener Daten, die Rechte betroffener Personen (Zugriff, Löschung, Übertragbarkeit), Einverständnisverwaltung und Richtlinien zur Datenspeicherung.

Als Datenverantwortlicher sind Sie dafür verantwortlich, Anfragen von betroffenen Personen zu bearbeiten, Einverständnisdatensätze aufzubewahren und eine transparente Datennutzung sicherzustellen.

Weitere Informationen zu [Datenschutzverwaltung](../start/privacy.md)

+++

+++ Wie stelle ich die Einhaltung von Datenschutzbestimmungen in Campaign sicher?

Campaign bietet Tools für die Einhaltung von Datenschutzbestimmungen, aber die rechtliche Verantwortung liegt bei Ihnen. Arbeiten Sie mit einem Rechtsbeistand für Ihr Datenschutzprogramm zusammen.

**Grundlegende Maßnahmen:**

* Einrichten von Prozessen für die Bearbeitung von Anfragen betroffener Personen (Zugriff, Löschung)
* Implementieren der Einverständnisverwaltung mit Zeitstempeln und Umfangsverfolgung
* Abmelde-Links in alle Marketing-E-Mails einschließen
* Datenquellen überprüfen und nicht verwendete Daten entfernen
* Anwenden von Zugriffssteuerungen mit geringsten Berechtigungen

Campaign bietet Privacy Core Service-Integration, Einverständnisverfolgung, automatisierte Löschungs-Workflows und Audit-Trails für die Einhaltung der Vorschriften.

Weitere Informationen zu [Datenschutzverwaltung](../start/privacy.md)

+++

+++ Wie erhebe und verwalte ich das Benutzereinverständnis in Campaign?

Eine gültige Einwilligung erfordert eine aktive, spezifische, informierte und widerrufliche Zustimmung. Benutzende müssen explizit handeln - keine vorab markierten Kästchen oder Schweigen als Zustimmung. Getrennte Einverständnisse für verschiedene Zwecke (entbündelt), klare Erläuterungen geben und Datensätze mit Zeitstempeln verwalten.

**Best Practices:** Bereitstellung granularer Opt-in-Optionen, regelmäßige Aktualisierung des Einverständnisses, Erleichterung des Zugriffs auf Präferenzzentren und Einverständniserklärung als Grundlage für Vertrauen.

**Technische Implementierung in Campaign:**

Campaign bietet Abonnement-Services, Präferenzzentren, Opt-out-Kennzeichnungen und benutzerdefinierte Einverständnisfelder zur Verfolgung des Einverständnisses.

* Empfängerschema für Einverständnisfelder erweitern (Datum, Typ, Quelle)
* Erstellen von Abonnement-Services für jeden Einwilligungstyp
* Erstellen von Web-Formularen für das Präferenzzentrum
* Verwenden von Workflows zur Durchsetzung des Einverständnisses beim Targeting
* Audit-Trails verwalten

Konsultieren Sie den Rechtsbeistand, um sicherzustellen, dass Ihre Implementierung die gesetzlichen Anforderungen erfüllt.

**Verwandte Themen:**

[Anmeldedienste](../start/subscriptions.md) | [Datenschutz und Einverständnis](../start/privacy.md#consent-retention-roles) | [Datenschutzverwaltung](../start/privacy.md)

+++

+++ Welche Daten werden bei der Bearbeitung einer Löschanfrage gelöscht?

Campaign löscht automatisch alle mit einer betroffenen Person verknüpften Daten: Empfängerprofil, Versand- und Trackinglogs, benutzerdefinierte Daten mit Eigentümerbeziehungen und Abonnementverlauf.

**Funktionsweise:** Campaign löscht alle Daten, bei denen die Relation zum Empfänger in der Schemadefinition `integrity="own"` ist, und stellt so eine kaskadierende Löschung über verwandte Tabellen hinweg sicher.

Sie können den Löschbereich anpassen, indem Sie die Link-Integrität in Schemata ändern, aber zuerst einen Rechtsbeistand konsultieren. Das Löschen ist dauerhaft und kann nicht rückgängig gemacht werden.

**Verwandte Themen:**

[Datenschutzverwaltung](../start/privacy.md) | [Schema-Links](../dev/schemas.md)

+++

+++ Wirken sich Löschungen von Daten auf meine Versandberichte aus?

Nein. Kampagnenberichte basieren auf vorab berechneten aggregierten Metriken (insgesamt gesendet, Öffnungen, Klicks) und nicht auf Live-Abfragen einzelner Protokolle. Durch das Löschen einzelner Empfängerdaten werden historische Aggregatstatistiken nicht geändert.

Insgesamt bleiben Versandstatistiken und Leistungsmetriken intakt, während einzelne Trackinglogs und persönliche Details entfernt werden. Auf diese Weise können Sie Marketing-Analysen verwalten und gleichzeitig die Rechte der betroffenen Person respektieren.

**Verwandte Themen:**

[Datenschutzverwaltung](../start/privacy.md) | [Berichte](../reporting/gs-reporting.md)

+++

+++ Wie kann ich verhindern, dass gelöschte Daten erneut importiert werden?

Sie müssen Daten aus allen Quellsystemen löschen, nicht nur aus Campaign. Daten fließen häufig aus externen Systemen (CRM, E-Commerce, Data Warehouses).

**Erforderliche Aktionen** Identifizieren aller Datenquellen, Löschen aus Quellsystemen, Hinzufügen zu Ausschluss-/Unterdrückungslisten, Aktualisieren von Import-Workflows unter Berücksichtigung von Löschkennzeichnungen und Dokumentieren des Prozesses.

Als Datenverantwortlicher sind Sie für die vollständige Entfernung von Daten in Ihrem gesamten Technologie-Ökosystem verantwortlich.

**Verwandte Themen:**

[Datenschutzverwaltung](../start/privacy.md) | [Workflows importieren](../config/workflows.md)

+++

+++ Können sich gelöschte Benutzer erneut anmelden?

Ja. Betroffene Personen können sich nach der Löschung erneut anmelden. Campaign erstellt einen völlig neuen Empfängerdatensatz ohne Verknüpfung mit zuvor gelöschten Daten. Das Profil beginnt mit einem Neuanfang.

Das Audit-Protokoll von Campaign zeichnet sowohl das Löschereignis als auch die Erstellung eines neuen Profils auf. Es zeigt die Einhaltung der Vorschriften und dass das neue Opt-in nach dem Löschen frei erteilt wurde.

**Verwandte Themen:**

[Datenschutzverwaltung](../start/privacy.md) | [Abonnements](../start/subscriptions.md)

+++

## Brauchen Sie noch Hilfe? {#get-help}

Du findest nicht, was du suchst? Im Folgenden finden Sie zusätzliche Ressourcen, die Ihnen bei der erfolgreichen Verwendung von Adobe Campaign v8 helfen.

### Unterstützung durch die Gemeinschaft

Tauschen Sie sich mit anderen Campaign-Benutzern und Adobe-Experten aus, um Informationen auszutauschen und Antworten zu erhalten.

* **[Adobe Campaign-Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"}** - Stellen Sie Fragen, teilen Sie Lösungen mit anderen und treten Sie in die Campaign-Community ein
* **[Experience League-](https://experienceleaguecommunities.adobe.com/?profile.language=de){target="_blank"}**: Durchsuchen Sie Diskussionen über alle Adobe-Produkte hinweg.
* **[Campaign Community Office Hours](https://experienceleague.adobe.com/de){target="_blank"}** - Nehmen Sie an Live-Sessions mit Adobe-Experten teil.

### Dokumentation und Lernen

Zugriff auf umfassende Handbücher, Tutorials und Schulungsmaterialien.

* **[Campaign-Tutorials](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=de){target="_blank"}** - Schrittweise Videoanleitungen und praktische Tutorials
* **[Neue Funktionen](whats-new.md)** - Neueste Funktionen
* **[Versionshinweise](release-notes.md)** - Aktuelle und vorherige Versionsinformationen
* **[Versionen und Upgrades](upgrades.md)** - Erfahren Sie mehr über Campaign-Versionen, Upgrades und die Überprüfung Ihrer Version

### Technische Ressourcen

Hier finden Sie ausführliche technische Dokumentationen und Entwicklerressourcen.

* **[Campaign-](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=de){target="_blank"}**: Vollständige API-Referenzdokumentation
* **[Kompatibilitätsmatrix](compatibility-matrix.md)** - Unterstützte Systeme und Versionen
* **[Häufig gestellte Fragen zu Versionen und Upgrades](upgrades.md)** - Überprüfen Sie Ihre Version und erfahren Sie mehr über Upgrades

### Support und Services

Erhalten Sie Hilfe vom Support-Team von Adobe und verwalten Sie Ihre Instanz.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Support-Fälle protokollieren und Benutzer verwalten
* **[Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Kontaktieren Sie das Support-Team
* **[Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de){target="_blank"}** - Einstellungen der Campaign-Instanz verwalten
* **[Systemstatus](https://status.adobe.com/){target="_blank"}** - Überprüfen des Adobe Services-Status

### Schulung und Zertifizierung

Erweitern Sie Ihre Kenntnisse mit offiziellen Adobe-Schulungs- und Zertifizierungsprogrammen.

* **[Experience League-Hilfe](https://experienceleague.adobe.com/de/browse/campaign/campaign-v8){target="_blank"}** - Hilferessourcen für Campaign v8 (Web-Benutzeroberfläche und Client-Konsole)
* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Offizielle, von Kursleitern geführte Kurse und Kurse zum Selbststudium
* **[Adobe Campaign-Zertifizierung](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=de){target="_blank"}** - Validieren Sie Ihr Fachwissen mit einer professionellen Zertifizierung.
* **[Experience League-Lernpfade](https://experienceleague.adobe.com/de?lang=de#dashboard/learning){target="_blank"}** - Geführte Journey

### Weitere hilfreiche Ressourcen

* **[Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=de){target="_blank"}** - Referenz für Benutzer von Classic v7
* **[Dokumentation zur Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Handbuch für die neue Web-Benutzeroberfläche
* **[Best Practices für die Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"}** - Optimieren des E-Mail-Versands


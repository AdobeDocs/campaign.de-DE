---
title: Häufig gestellte Fragen zu Campaign v8
description: Erhalten Sie Antworten auf häufig gestellte Fragen zu Adobe Campaign v8 hinsichtlich Einrichtung, Konfiguration, Messaging, Workflows und mehr
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, Fragen, Antworten, Hilfe, Support, Fehlerbehebung
hide: true
hidefromtoc: true
source-git-commit: 15e52d3c7d990bd1a1a5c9d1a2d83d8fee9aaaed
workflow-type: tm+mt
source-wordcount: '10867'
ht-degree: 23%

---

# Häufig gestellte Fragen {#faq}

Erhalten Sie schnelle Antworten auf die häufigsten Fragen zu Adobe Campaign v8. Unabhängig davon, ob Sie gerade erst anfangen oder nach Hilfe zur erweiterten Konfiguration suchen, finden Sie Antworten, die nach Themen geordnet unten sind.

**Neu bei Campaign?** beginnen mit [allgemeinen &#x200B;](#general) und [Schlüsselkonzepten](#key-concepts).\
**Benötigen Sie technische Hilfe?** Überprüfen Sie [Entwickler](#developers) und [Kampagneneinstellungen](#settings).\
**Finden Sie keine Antwort?** Besuchen Sie unsere [Community-Foren](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"} oder [Support kontaktieren](#get-help).

>[!TIP]
>
>Verwenden Sie Strg+F (Befehl+F auf Mac), um auf dieser Seite nach bestimmten Keywords zu suchen. Klicken Sie auf eine Frage, um die Antwort zu erweitern.


## Allgemeine Fragen {#general}

Hier erhalten Sie Antworten auf die häufigsten Fragen zu Adobe Campaign v8, einschließlich Informationen zur Verbindung, zum Upgrade und zum Support.

+++ Wie kann ich eine Verbindung zu Campaign v8 herstellen?

Sie müssen die Campaign-Client-Konsole herunterladen und installieren, um eine Verbindung zu Adobe Campaign herzustellen.

[Hier erfahren Sie mehr darüber](connect.md).

Ab Campaign v8.6 haben Sie Zugriff auf die **Campaign Web-Benutzeroberfläche**, die über die zentrale Adobe Experience Cloud-Umgebung verfügbar ist. Experience Cloud ist Adobes integrierte Produktfamilie von Programmen, Produkten und Services für das digitale Marketing.

[Auf dieser Seite](campaign-ui.md#ac-web-ui) erfahren Sie, wie Sie eine Verbindung mit Adobe Experience Cloud herstellen und auf die Benutzeroberfläche von Adobe Campaign Web zugreifen.

Weitere Informationen finden Sie in der [Dokumentation zur Adobe Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

>[!TIP]
>
>**Beheben von Verbindungsproblemen:**
>
>* Überprüfen Sie, ob Ihre Adobe ID-Anmeldedaten korrekt sind
>* Stellen Sie sicher, dass Ihre Client-Konsolenversion mit der Server-Version übereinstimmt.
>* Netzwerkkonnektivität und Firewall-Einstellungen überprüfen
>* Den Cache der Client-Konsole löschen, wenn Probleme auftreten
>* Admin kontaktieren, um Benutzerberechtigungen zu überprüfen

**Verwandte Themen:**

* [Installieren der Client-Konsole](connect.md)
* [Campaign-Benutzeroberfläche](campaign-ui.md)
* [Benutzerberechtigungen](gs-permissions.md)

+++

+++ Kann Campaign v8 in einer On-Premise- oder Hybridumgebung installiert werden?

Campaign v8 ist nur in Managed Cloud Services verfügbar, die vollständig von Adobe gehostet werden.

+++

+++ Wie kann ich Campaign auf die neuste Version aktualisieren?

Adobe Campaign wird regelmäßig aktualisiert. Jedes Jahr werden kleinere Versionen mit neuen Funktionen, Verbesserungen und Fehlerbehebungen veröffentlicht. Darüber hinaus veröffentlichen wir regelmäßig Builds nur mit kumulativen Fehlerbehebungen.

Dieser regelmäßige Aktualisierungsrhythmus zielt darauf ab, Ihnen die neuesten und besten Funktionen bereitzustellen, Ihre Umgebung sicher zu halten und Ihr Produkterlebnis zu verbessern. Deshalb erachten wir es für wichtig, dass Sie die aktuelle Version von Adobe Campaign verwenden.

>[!NOTE]
>
>Als Managed Cloud Services-Anwender wird Ihre Instanz von Adobe mit neuen Versionen aktualisiert.

+++

+++ Wie kann ich den E-Mail-Versand optimieren?

Die Zustellbarkeit von E-Mails, ein wichtiger Faktor für den Erfolg jedes Marketing-Programms, unterliegt ständig wechselnden Kriterien und Regeln. Eine effektive Navigation in dieser digitalen Welt erfordert eine regelmäßige Abstimmung Ihrer E-Mail-Strategie unter Berücksichtigung der wichtigsten Trends mit Blick auf die Zustellbarkeit, um Ihre Zielgruppen optimal zu erreichen.

Lesen Sie dieses Handbuch, um mehr über [Best Practices für die Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"} zu erfahren

In [diesem Handbuch](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=de){target="_blank"} erfahren Sie, wie Sie in Campaign eine hohe Zustellbarkeit gewährleisten.

>[!TIP]
>
>**Wichtige Tipps zur Zustellbarkeit:**
>
>* Pflegen Sie eine saubere E-Mail-Liste und entfernen Sie regelmäßig inaktive Abonnenten
>* Verwenden Sie Double-Opt-in, um interaktive Empfänger sicherzustellen.
>* Überwachen der Reputation des Absenders und der IP-Reputation
>* E-Mails mit SPF, DKIM und DMARC authentifizieren
>* Sofortiges Befolgen von Abmeldeanfragen
>* Testen Sie Ihre E-Mails, bevor Sie sie an große Zielgruppen senden.

**Verwandte Themen:**

* [Über die Zustellbarkeit](../send/about-deliverability.md)
* [Steuern des Nachrichteninhalts](../send/control-message-content.md)
* [Überwachen der Zustellbarkeit](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ Wie weiß ich, dass mein Versand fehlerfrei durchgeführt wird?

Adobe Campaign ist mit einer Reihe von Dashboards und Tools zur Überwachung des E-Mail-Versands ausgestattet.

[Lesen Sie die Dokumentation zu Campaign Classic v7, um zu erfahren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de){target="_blank"}, wie Sie dafür sorgen, dass Ihre Nachrichten gesendet werden, und die Ausführung überwachen sowie Fehler beheben können.

+++

+++ Kann ich die Ausführung von Workflows überwachen?

Informationen zur Überwachung der Workflow-Ausführung von Campaign [finden Sie auf dieser Seite](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}.

+++

+++ Mit welchen Systemen und Komponenten ist Campaign v8 kompatibel?

Eine Liste mit allen Systemen und Komponenten, die vom aktuellen Build von Campaign unterstützt werden, finden Sie in der [Kompatibilitätsmatrix von Adobe Campaign &#x200B;](compatibility-matrix.md).

+++

+++ Wie kann ich Campaign herunterladen?

Sie können das Installationsprogramm und die Client-Konsole vom Adobe Download Center abrufen.

Greifen Sie als Admin-Benutzerin bzw. -Benutzer auf Adobe [Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html){target="_blank"} zu, um Adobe Campaign herunterzuladen.

Weitere Informationen zum Verteilungs-Center [&#x200B; Sie auf dieser Seite](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=de){target="_blank"}.

+++

+++ Wie kann ich ein Problem protokollieren?

Durch das Erstellen eines Tickets können Sie sich an das Adobe-Supportteam wenden, wenn Probleme mit Ihren Adobe-Produkten auftreten. Sie können in der Adobe Admin Console mit dem Adobe-Support chatten, um Ihre Probleme zu lösen.

Um in diesem neuen System ein Ticket zu erstellen oder eine Chat-Sitzung zu starten, müssen Sie sich mit [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"} verbinden.

Das System erfordert für jeden Benutzer ein individuelles Konto mit den entsprechenden Berechtigungen. Wenn Sie sich nicht mit Ihrer Adobe ID anmelden können, beantragen Sie den Zugang über die Experience League, und das Kundenunterstützungs-Team wird ihn so schnell wie möglich einrichten. [Weitere Informationen](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Der Campaign-Community beitreten: Suchen Sie nach Antworten in bereits gestellten Fragen oder fragen Sie die Experten. [Reden Sie mit](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"}

+++


## Schlüsselkonzepte {#key-concepts}

Erfahren Sie mehr über die grundlegenden Konzepte von Campaign, einschließlich Authentifizierung, Benutzeroberfläche, Workflows und Kernfunktionen, um effektiv zu beginnen.

+++ Kann ich mit Adobe ID eine Verbindung zu Campaign v8 herstellen?

Ja! Dank der Integration mit dem IMS (Adobe Identity Management System) können Benutzende über ihre Adobe ID eine Verbindung zur Adobe Campaign-Konsole herstellen. Diese Integration bietet die folgenden Vorteile:

* Verwendung ein und derselben ID für alle Adobe Experience Cloud-Lösungen;
* Speicherung der Verbindung bei der Verwendung von Adobe Campaign mit den verschiedenen Integrationen;
* Optimierte Sicherheitsrichtlinien für die Kennwortverwaltung;
* Verwendung von Konten des Typs Federated ID (externer Identity Provider).

[Weitere Informationen](connect.md) zum Zugriff auf Campaign v8 mit einer Adobe ID.

+++

+++ Welche Version von Campaign habe ich?

Ihre [Version und Build-Nummer](connect.md#ac-version) können Sie in der Client-Konsole von Campaign über das Menü **Hilfe > Versionsinformationen...** abrufen.

+++

+++ Was sind die Unterschiede zwischen Campaign Classic v7 und Campaign v8?

Campaign v8 ist die Campaign-Version der nächsten Generation, die für Managed Cloud Services entwickelt wurde. Er bietet deutliche Verbesserungen in den Bereichen Infrastruktur, Sicherheit, Zustellbarkeit und Überwachung.

Adobe Campaign v8 ist ausschließlich als **Managed Cloud Service** verfügbar und kann nicht in einer On-Premise- oder Hybridumgebung bereitgestellt werden.

[&#x200B; Erfahren Sie mehr über den Wechsel von Campaign Classic v7 zu v8](v7-to-v8.md).

+++

+++ Wie kann ich Benutzerberechtigungen erteilen?

Campaign-Administratoren können Berechtigungen für Benutzer im Unternehmen vergeben.

Die damit einhergehenden Rechte und Einschränkungen ermöglichen dem Benutzer Folgendes:

* Zugriff auf bestimmte Funktionen
* Zugriff auf bestimmte Daten
* Erstellen, Ändern und/oder Löschen von Daten

[Weitere &#x200B;](../start/gs-permissions.md) zu Benutzerberechtigungen in Campaign v8.

**Verwandte Themen:**

* [Erste Schritte mit Berechtigungen](gs-permissions.md)
* [Verwalten von Benutzerberechtigungen](manage-permissions.md)
* [Berechtigungen für Ordner hinzufügen](folder-permissions.md)

+++

+++ Wie kann ich mit Campaign Datenschutzbestimmungen einhalten?

Adobe Campaign bietet eine Reihe von Tools, die Sie bei der Einhaltung von Datenschutzbestimmungen in Bezug auf die DSGVO, den CCPA und andere Datenschutzbestimmungen unterstützen.

[&#x200B; Erfahren Sie &#x200B;](../start/privacy.md) über die Datenschutzverwaltung und die Tools und Funktionen, die Adobe Campaign Ihnen zur Einhaltung Ihrer Datenschutzbestimmungen bietet.

+++

+++ Über welche Benutzeroberflächen-Konzepte von Campaign sollte ich Bescheid wissen?

Adobe Campaign Weitere Informationen [&#x200B; Grundlagen zur Benutzeroberfläche von &#x200B;](campaign-ui.md) finden Sie in diesem Abschnitt.

Ab Campaign v8.6 haben Sie auch Zugriff auf die neue **Campaign Web-Benutzeroberfläche**, die über die zentrale Adobe Experience Cloud-Umgebung verfügbar ist.

[Weitere Informationen finden Sie in der Dokumentation zur Web-Benutzeroberfläche von Adobe Campaign](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Wie kann ich die Zielgruppe für meine Nachrichten auswählen?

Bei Adobe Campaign stehen Ihnen für die Erstellung von Zielgruppen und die Auswahl von Empfangenden unterschiedliche Strategien zur Verfügung.

[Weitere Informationen](../audiences/gs-audiences.md) wie Sie Audiences in Campaign v8 definieren.

+++

+++ Was ist ein Workflow?

Mit Adobe Campaign verfügen Sie über ein integriertes Workflow-Management-System, welches die zentrale Steuerung aller Prozesse und Vorgänge der Anwendung ermöglicht. Die Workflow-Engine dient der Modellierung und Automatisierung der verschiedenen Aufgaben der Anwendungs-Server-Module. Mithilfe der grafischen Oberfläche lassen sich vollständige Arbeitsabläufe zur Segmentierung von Zielgruppen, zur Ausführung von Kampagnen, zum Umgang mit Dateien etc. gestalten.

So bieten Workflows beispielsweise die Möglichkeit, Dateien von einem Server herunterladen, sie zu entkomprimieren und die Datensätze in die Adobe Campaign-Datenbank zu importieren.

Ein Workflow kann auch einen oder mehrere Benutzende einbinden, die benachrichtigt werden oder Entscheidungen treffen und Prozesse genehmigen können. Auf diese Weise können Versandaktionen erstellt und einem oder mehreren Benutzenden die Bearbeitung von Inhalten, die Bestimmung der Zielgruppen und die Validierung von Testsendungen vor dem Versandbeginn zugewiesen werden.

[Weitere Informationen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=de){target="_blank"} über Workflows. Informationen über [Best Practices bei Workflows finden Sie hier](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"}.

**Verwandte Themen:**

* [Erste Schritte mit Workflows](../config/workflows.md)
* [Erstellen des ersten Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"}
* [Workflow-Anwendungsfälle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [Überwachen der Workflow-Ausführung](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

+++

+++ Wie erstelle und sende ich die erste E-Mail?

Die Erstellung Ihrer ersten E-Mail in Campaign v8 umfasst mehrere wichtige Schritte:

1. **Versand erstellen** - Erstellen Sie zunächst einen neuen E-Mail-Versand aus einer Vorlage oder von Grund auf
1. **Audience definieren** - Zielgruppenempfänger mithilfe von Abfragen, Listen oder Workflows auswählen
1. **Inhalt gestalten** - Verwenden Sie den E-Mail-Designer, um Ihre Nachricht mit Personalisierung zu erstellen
1. **Mit Testsendungen testen** - Senden von Test-E-Mails zur Validierung von Inhalten und Personalisierung
1. **Analysieren und senden** - Versandanalyse durchführen, um Fehler zu finden, und dann E-Mail senden

Campaign v8 bietet zwei Schnittstellen zur E-Mail-Erstellung:

* **Client-Konsole** - Desktop-Programm mit vollem Funktionsumfang und erweiterten Funktionen
* **Campaign Web UI** - Moderne, intuitive Web-Oberfläche für eine schnellere E-Mail-Erstellung

[Erfahren Sie mehr über das Entwerfen und Validieren von E-Mails](../send/email.md) in Campaign v8.

**Verwandte Themen:**

* [Erstellen des ersten Versands](create-message.md) - Schritt-für-Schritt-Anleitung
* [Arbeiten mit Versandvorlagen](../send/create-templates.md) - Zeit sparen mit Vorlagen
* [Best Practices für den Versand](delivery-best-practices.md) - Empfehlungen für den Erfolg
* [Definieren des E-Mail-](../send/defining-the-email-content.md) - Optionen zur Inhaltserstellung
* [Vorschau und Testsendungen](../send/preview-and-proof.md) - Testen vor dem Senden
* [Konfigurieren und Senden](../send/configure-and-send.md) - Abschließende Schritte zum Senden
* [Inhalt personalisieren](../send/personalize.md) - Dynamische Personalisierung hinzufügen

+++

+++ Wie kann ich SMS-Nachrichten senden?

Das Senden von SMS-Nachrichten mit Campaign v8 erfordert eine Erstkonfiguration und folgt dann einem einfachen Versandprozess:

**Ersteinrichtung (einmalige Konfiguration):**

1. **SMS-Kanal konfigurieren** - Einrichten der SMS-Versandeinstellungen und des externen Kontos
1. **SMPP-Verbindung konfigurieren** - Herstellen einer Verbindung zu Ihrem SMS-Dienstleister über das SMPP-Protokoll
1. **Verbindung testen** - Validieren der Verbindung mit Ihrem SMS-Anbieter
1. **Routing einrichten** - Definieren, wie SMS-Nachrichten über Ihren Provider geleitet werden

**SMS erstellen und senden:**

1. **SMS-Versand erstellen** - Einen neuen SMS-Versand aus einer Vorlage starten
1. **Empfänger definieren** - Wählen Sie Ihre mobile Zielgruppe mithilfe von Telefonnummernfeldern aus.
1. **SMS-Inhalt schreiben** - Erstellen Sie Ihre Nachricht (standardmäßig 160 Zeichen oder länger mit Verkettung).
1. **Personalisierung hinzufügen** - Dynamische Felder für jeden Empfänger einbeziehen
1. **Testversand durchführen** - Testen des SMS-Versands zur Validierung von Inhalt und Versand
1. **Analysieren und senden** - Führen Sie eine Analyse durch und senden Sie sie an Ihre Audience.

**Wichtige SMS-Funktionen:**

* **Mehrere SMPP-Connectoren** - Unterstützung für verschiedene SMS-Anbieter und Protokolle
* **Versandberichte** - Verfolgen gesendeter, zugestellter und fehlgeschlagener Nachrichten
* **Zeichenkodierung** - Unterstützung für GSM7, Unicode und Sonderzeichen
* **Lange SMS-Unterstützung** - Automatische Nachrichtenverkettung für längere Texte
* **Zwei-Wege-SMS** - Verarbeiten eingehender SMS-Antworten mit Workflows

[Erfahren Sie mehr über die Konfiguration und den Versand von SMS](../send/sms/sms.md) in Campaign v8.

**Verwandte Themen:**

* [Erste Schritte mit SMS](../send/sms/sms.md) - Vollständiges SMS-Handbuch
* [SMS-Versandeinstellungen](../send/sms/sms-delivery-settings.md) - Konfigurationsoptionen
* [Einstellungen für externes SMPP-Konto](../send/sms/smpp-external-account.md) - Provider-Setup
* [Erstellen eines SMS-Versands](../send/sms/create-sms.md) - Schrittweise Erstellung
* [SMS-Inhalt](../send/sms/sms-content.md) - Richtlinien für die Inhaltserstellung
* [SMS-Testsendungen durchführen](../send/sms/sms-proofs.md) - SMS testen
* [SMS überwachen](../send/sms/sms-monitor.md) - Versand verfolgen und analysieren

+++

+++ Wie kann ich Push-Benachrichtigungen senden?

Das Senden von Push-Benachrichtigungen mit Campaign v8 umfasst die Konfiguration der Mobile-App-Integration und die Erstellung ansprechender Benachrichtigungen:

**Ersteinrichtung (einmalige Konfiguration):**

1. **Push-Kanal konfigurieren** - Einrichten der Kanaleinstellungen für Push-Benachrichtigungen in Campaign
1. **Campaign SDK integrieren** - Adobe Campaign SDK zu Ihrer Mobile App hinzufügen (oder die Datenerfassung verwenden)
1. **Mobile App konfigurieren** - Registrieren Ihrer iOS- und Android-Apps in Campaign
1. **Zertifikate einrichten** - APNs-Zertifikat (iOS) und FCM-Schlüssel (Android) konfigurieren
1. **Testregistrierung** - Überprüfen, ob Geräte Token registrieren und empfangen können

**Push-Benachrichtigungen erstellen und senden:**

1. **Push-Versand erstellen** - Neue Push-Benachrichtigung von einer Vorlage aus starten
1. **Plattform auswählen** - iOS, Android oder beide Plattformen auswählen
1. **Zielgruppe definieren** - App-Abonnenten ansprechen, die Mobile-App-Abonnementdaten verwenden
1. **Design-Benachrichtigung** - Erstellen von Titeln, Nachrichten und Rich-Media-Inhalten
1. **Verhalten konfigurieren** - Festlegen von Klickaktionen, Deep-Links und benutzerdefinierten Daten
1. **Testbenachrichtigungen senden** - Vor dem Senden auf echten Geräten validieren
1. **Analysieren und senden** - Überprüfen des Targeting und Senden an Ihre mobile Zielgruppe

**Funktionen für Push-Benachrichtigungen:**

* **Rich-Push-**: Bilder, Videos und interaktive Schaltflächen (iOS und Android) enthalten
* **Personalization** - Dynamische Inhalte basierend auf Benutzerprofil und Verhalten
* **Deep-Linking** - Leitet Benutzer zu bestimmten Bildschirmen oder Inhalten der App weiter.
* **Planung** - Senden zu optimalen Zeiten basierend auf der Zeitzone des Benutzers
* **A/B-Tests** - Testen verschiedener Nachrichten und Optimieren der Interaktion
* **Tracking** - Öffnungen, Klicks und Konversionen überwachen

**Plattformspezifische Funktionen:**

* **iOS** - Stille Benachrichtigungen, Benachrichtigungskategorien, Tonanpassung
* **Android** - Rich-Push-Vorlagen, Benachrichtigungskanäle, benutzerdefinierte Layouts

[Erfahren Sie mehr über die Konfiguration von Push](../send/push-settings.md)Benachrichtigungen in Campaign v8.

**Verwandte Themen:**

* [Push-Benachrichtigungen erstellen und senden](../send/push.md) - Vollständige Anleitung zu Push-Benachrichtigungen
* [Konfigurieren des Push-Benachrichtigungs-Kanals](../send/push-settings.md) - Kanaleinrichtung
* [Entwerfen einer Android Rich-Push](../send/rich-push-android.md) - Rich-Benachrichtigungen zu Android
* [Entwerfen einer iOS Rich-Push](../send/rich-push-ios.md) - Rich-Benachrichtigungen zu iOS
* [Mit Datenerfassung konfigurieren](../send/push-data-collection.md) - Moderne überarbeitete Integrationsmethode
* [Nachverfolgen und Überwachen](tracking.md) - Analysieren der Push-Leistung

+++

+++ Wie erstelle ich eine Landingpage?

Sie können den Digital Content Editor von Adobe Campaign verwenden, um Landingpages zu entwerfen und die Zuordnung zu Datenbankfeldern zu definieren.

[Weitere Informationen](../dev/landing-pages.md) finden Sie in der Dokumentation zu Campaign v8.

Sie können auch die Web-Benutzeroberfläche von Campaign verwenden, um Landingpages zu erstellen und zu veröffentlichen [Weitere Informationen](https://experienceleague.adobe.com/de/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Wie kann ich Sendungen nachverfolgen?

Sie können mit Campaign v8 gesendete Sendungen mithilfe dedizierter [Versandberichte](../reporting/delivery-reports.md) verfolgen und dann Ihre Sendungen überwachen.

Weitere Informationen zur Tracking-Verwaltung in Campaign [auf dieser Seite](../start/tracking.md).

**Verwandte Themen:**

* [Nachverfolgen und Überwachen von Nachrichten](tracking.md)
* [Versandberichte](../reporting/delivery-reports.md)
* [Ursachen für das Fehlschlagen von Sendungen](../send/delivery-failures.md)
* [Konfigurieren getrackter Links](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (Dokumentation zu Campaign Classic v7)

+++

+++ Wie übersetze ich eine Fehlermeldung?

Eine Fehlermeldung wird in einer Fremdsprache angezeigt? Alle Fehlermeldungen und deren Übersetzung werden auf [dieser Seite](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=de){target="_blank"} aufgelistet.

+++

+++ Kann ich in Campaign ein Web-Formular erstellen und Antworten sammeln?

Ja. Erstellen Sie Web-Formulare mit **Campaign Web-Anwendungen und Forms** (Client-Konsole), um die Formularlogik und -validierung vollständig zu steuern, oder verwenden Sie **Campaign-Landingpages** (Web-Benutzeroberfläche) mit einer modernen Drag-and-Drop-Oberfläche für Abonnements und die Lead-Generierung. Beide sammeln Daten direkt in Campaign und integrieren sie in Workflows für automatisierte Aktionen.

[Erfahren Sie mehr über Web-Anwendungen und Formulare](../dev/webapps.md) | [Landingpages der Campaign-Web-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8 im Vergleich zu vorherigen Versionen {#v7-differences}

Machen Sie sich mit den wichtigsten Unterschieden zwischen Campaign v8 und früheren Versionen (Classic v7 und Standard) vertraut, einschließlich Architektur, Bereitstellung, Migrationspfade und Funktionsänderungen. Erfahren Sie, was neu ist und wie Sie den Übergang reibungslos gestalten können, unabhängig davon, ob Sie von Campaign Classic v7 oder Campaign Standard kommen.

+++ Was sind die Hauptunterschiede zwischen Campaign v8 und früheren Versionen?

Campaign v8 ist eine vollständige Neugestaltung von Adobe Campaign, die für eine moderne Cloud-native Architektur entwickelt wurde und gegenüber Campaign Classic v7 und Campaign Standard erhebliche Verbesserungen mit sich bringt:

**Bereitstellungsmodell:**

* **v8:** Nur Managed Cloud Services - vollständig von Adobe gehostet und verwaltet
* **v7/Standard:** Verfügbare Optionen für On-Premise, Hybrid oder Hosted
* **Vorteil:** Infrastrukturmanagement ohne zusätzliche Kosten, automatische Skalierung, Sicherheit auf Unternehmensniveau, proaktive Überwachung

**Architektur und Leistung:**

* **v8:** Verbesserte FFDA-Architektur (FFDA) mit PostgreSQL-Datenbank
* **v8:** Batch-Verarbeitungsdurchsatz erreicht bis zu **20 Millionen Vorgänge pro Stunde**
* **v8:** Transaktionsnachrichten-Durchsatz von **1 Million pro Stunde**
* **v8:** Echtzeit-Datenexploration und schnelle Zielgruppenbildung (Minuten vs. Stunden)
* **Vorteil:** bessere Leistung für groß angelegte Vorgänge und komplexe Kampagnen

**Benutzeroberfläche:**

* **v8:** Neue **Web-Benutzeroberfläche von Campaign** zusammen mit der Client-Konsole - intuitiv, barrierefrei, ideal für Marketing-Experten
* **v8:** Modernes, responsives Design mit Drag-and-Drop-Funktionen
* **v8:** Vereinfachtes Erstellen und Verwalten von Kampagnen
* **v8:** weist viele Ähnlichkeiten mit der Benutzeroberfläche von Campaign Standard auf
* **Vorteil:** Schnelleres Onboarding, einfachere Kampagnenausführung, bessere Barrierefreiheit, minimale Lernkurve

**Neue wichtige Funktionen:**

* **Rich-Push** Benachrichtigungen mit Bildern, Videos, interaktiven Schaltflächen, Karussells und Timern
* **KI-Assistent** für die Inhaltserstellung (E-Mail, SMS, Push) mit Bewertung der Markenausrichtung
* **Aktualisierte SMS-Infrastruktur (SMS v2.0)** verbesserte Zuverlässigkeit und Kompatibilität
* **Adobe Experience Manager as a Cloud Service-Integration** für nahtloses Content-Management
* **Verbessertes Reporting** einschließlich dynamischer Berichterstellung für Campaign Standard-Benutzer

**Aktualisierungen und Wartung:**

* **v8:** Von Adobe verwaltete automatische Upgrades - immer auf der neuesten stabilen Version mit kontinuierlichem Bereitstellungsmodell
* **v7/Standard:** Planung und Ausführung manueller Upgrades erforderlich
* **Vorteil** Geringerer Wartungsaufwand, sofortiger Zugriff auf neue Funktionen, keine Ausfallzeiten

**APIs und Integration:**

* **v8:** Moderne REST-APIs mit verbesserter Leistung und Zuverlässigkeit
* **v8:** Nahtlose Integration mit Adobe Experience Cloud und Adobe Experience Platform
* **Vorteil:** Integrationen, bessere Interoperabilität, moderne Entwicklungspraktiken

[Weitere Informationen zu den wichtigsten Funktionen von Campaign v8](whats-new.md)

**Verwandte Themen:**

* [Von Campaign Classic v7 zu v8](v7-to-v8.md) | [v7 zu v8 - Übergangshandbuch](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}
* [Von Campaign Standard zu v8](acs-to-v8.md) | [Campaign Standard-Transition](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Übernahmeleitfaden für Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Funktionsmatrix von Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Architektur von Campaign v8](../architecture/architecture.md)
* [Schutzmechanismen und Einschränkungen](ac-guardrails.md)

+++

+++ Sollte ich von Campaign Classic v7 oder Campaign Standard zu v8 migrieren?

**Campaign v8 ist ideal für Unternehmen, die Folgendes benötigen:**

* **Kampagnen mit hohem Volumen** - Senden von Millionen von Nachrichten mit verbesserter Leistung und Zuverlässigkeit (20 Millionen Vorgänge/Stunde)
* **Skalierbarkeit für Unternehmen** - Datenbank und Kampagnen ohne Leistungsprobleme erweitern
* **Moderne Web-Benutzeroberfläche** - Intuitive, responsive Web-Benutzeroberfläche von Campaign für schnellere Kampagnenerstellung und verbessertes Benutzererlebnis
* **Cloud-native Vorteile** - Nutzen Sie automatische Updates, verwaltete Infrastruktur, elastische Skalierung und proaktive Überwachung
* **Langfristiger Support** - Campaign v8 ist die strategische Plattform von Adobe mit erweiterter Unterstützung, während frühere Versionen in den nächsten Jahren das Ende der Unterstützung erreichen werden
* **Geringerer IT-Overhead** - Eliminierung des Infrastrukturmanagements und der Planung von Upgrades
* **Erweiterte Funktionen** - KI-Assistent, Rich-Push, erweiterte SMS, Adobe Experience Platform-Integration

**Für Campaign Standard-Benutzer:**

Campaign Standard-Benutzer können jetzt zu Campaign v8 Managed Cloud Services wechseln. Zu den wichtigsten Vorteilen gehören:

* **Bekannte Benutzeroberfläche** - Die Web-Benutzeroberfläche von Campaign weist viele Ähnlichkeiten mit Campaign Standard auf und minimiert so die Lernkurve
* **Funktionsparität** - Wichtige Campaign Standard-Funktionen wurden zu v8 hinzugefügt (dynamisches Reporting, zentralisiertes Branding, REST-APIs, Landingpages, visuelle Fragmente)
* **Verbesserter Support** - Erstklassige Unterstützung bei reibungslosem Übergang und kontinuierlicher Plattformüberwachung
* **Datenmigration** - Alle Ihre Daten aus Campaign Standard werden mit minimaler Unterbrechung importiert
* **Konsistentes Benutzererlebnis** - Fortsetzung der Arbeit mit vertrauten Workflows und Benutzeroberflächen

**Für Campaign Classic v7-Benutzer:**

Campaign v8 bietet erhebliche Verbesserungen bei gleichzeitiger Beibehaltung der zentralen Campaign-Funktionen:

* **Doppelte Benutzeroberfläche** - Zugriff sowohl auf die leistungsstarke Client-Konsole als auch auf die moderne Campaign Web-Benutzeroberfläche
* **Bessere Leistung** - Deutlich verbesserte Abfrageleistung und Datenverarbeitung
* **Cloud-Vorteile** - Automatische Upgrades, Sicherheits-Patches, Backup/Recovery mit Adobe
* **Moderne Architektur** - Verbesserte FFDA-Architektur mit PostgreSQL für bessere Skalierbarkeit

**Wann eine Migration in Betracht gezogen werden sollte:**

* Ihre aktuelle Campaign-Instanz verarbeitet große Datenmengen (Millionen Profile)
* Bei komplexen Workflows oder Targeting treten Leistungsprobleme auf.
* Sie möchten die Kosten für Infrastrukturverwaltung und Wartung senken
* Sie benötigen eine nahtlose Integration mit Adobe Experience Cloud oder Adobe Experience Platform
* Sie planen ohnehin ein umfangreiches Upgrade oder eine Aktualisierung der Infrastruktur.
* **Sie wollen zukunftssichere Technologie** - frühere Versionen erreichen das Ende der Unterstützung
* **Ihr Team benötigt eine moderne Benutzeroberfläche** - Die Web-Benutzeroberfläche von Campaign bietet Marketing-Experten eine bessere Barrierefreiheit

**Überlegungen zur Migration:**

* Adobe bietet Unterstützung, Anleitungen und Tools für die Migration
* v8 ist nur Managed Cloud Service (keine On-Premise- oder Hybridbereitstellung)
* Einige technische Implementierungen können unterschiedlich sein. Überprüfen Sie die [Funktionsmatrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* Datenmigration und -tests erfordern Planung und Ressourcen
* **Für Campaign Standard-**: Die Umstellung soll reibungslos und mit minimaler Workflow-Unterbrechung erfolgen

**Nächste Schritte:**

Wenden Sie sich an den Adobe-Support unter:

* Bewertung der Migrationsbereitschaft und des Zeitplans
* Die spezifischen Vorteile für Ihren Anwendungsfall
* Migrationsplanung und Ressourcenzuweisung
* Zugriff auf Migrationstools und Support

**Verwandte Themen:**

**Für Campaign Classic v7-Benutzer:**

* [Wechsel von Campaign Classic v7 zu v8](v7-to-v8.md)
* [v7 zu v8 - Detailliertes Handbuch](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Für Campaign Standard-Benutzer:**

* [Campaign Standard-Wechsel zu v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Übernahmeleitfaden für Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Überblick über Campaign Standard zu v8](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/overview){target="_blank"}
* [Erste Schritte für Marketing-Fachleute](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/marketers){target="_blank"}
* [Erste Schritte für Admin/Entwickler](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Allgemeine Ressourcen:**

* [Funktionsmatrix von Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Kompatibilitätsmatrix](compatibility-matrix.md)

+++

+++ Worin bestehen die wichtigsten terminologischen und funktionalen Unterschiede in Campaign v8?

Campaign v8 bietet die meisten Campaign Classic v7- und Campaign Standard-Funktionen mit Verbesserungen. Einige Funktionen haben jedoch Änderungen aufgrund der Cloud-nativen Architektur, und einige Begriffe unterscheiden sich zwischen den Versionen.

**Terminologieunterschiede (von Campaign Standard zu v8):**

* **Benutzerdefinierte Ressourcen** sind jetzt **Schemata**
* **Nachrichten** werden als &quot;**&quot;**
* **Produktbenutzer** sind jetzt **Benutzer**
* **Rollen** werden mit **spezifischen Berechtigungen** konfiguriert
* **Sicherheitsgruppen** sind jetzt **Benutzergruppen**
* **Organisationseinheiten** werden über **Ordnerberechtigungen“**

**Terminologieaktualisierungen für die Campaign Web-Benutzeroberfläche:**

Die folgenden Begriffe wurden in der Web-Benutzeroberfläche von Campaign aktualisiert (die Client-Konsole verwendet herkömmliche Begriffe):

* **Empfänger** sind jetzt **Profile**
* **Testadressen** sind jetzt **Testprofile**
* **Versandanalyse** ist jetzt **Versandvorbereitung** (klicken Sie auf **Vorbereiten**)
* **E-Mail-Vorschau** ist über die Schaltfläche **Inhalt simulieren** verfügbar
* **Listen** sind jetzt **Zielgruppen**

**In v8 nicht verfügbar:**

* **On-Premise- und Hybridbereitstellungen** - v8 ist nur Managed Cloud Services
* **Direkter Datenbankzugriff** - Verwenden Sie stattdessen die bereitgestellten APIs und Tools.
* **Kundenverwaltete Infrastruktur** - Adobe verwaltet die gesamte Infrastruktur
* **Manuelle Build-Upgrades** - Jetzt automatisch (Adobe verwaltet)

**Verschiedene Implementierungen in v8:**

* **Technische Workflows** - Einige für die Cloud-Architektur optimierte Workflows funktionieren möglicherweise anders
* **Datenbankstruktur** - Die erweiterte FFDA-Architektur erfordert möglicherweise Schemaanpassungen
* **Benutzerdefinierte Integrationen** - Möglicherweise sind Updates für die Cloud-basierte Architektur erforderlich
* **Anpassungen auf niedriger Ebene** - Einige erfordern unterschiedliche Ansätze in verwalteten Umgebungen

**Erweitert oder ersetzt in v8:**

* **Build-Upgrades** - Automatisch mit dem Modell der kontinuierlichen Bereitstellung anstelle von manuell
* **Leistungsoptimierung** - Wird von der Adobe-Infrastrukturoptimierung verarbeitet.
* **Sicherheits-Patches** - werden automatisch von Adobe angewendet
* **Sicherung und Wiederherstellung** - Verwaltet von Adobe im Rahmen des Service
* **Benutzeroberfläche** - Neue Campaign Web-Benutzeroberfläche zusammen mit der Client-Konsole

**Funktionen hinzugefügt für Campaign Standard-Benutzer, die zu v8 wechseln:**

* **Dynamisches Reporting** - Anpassbare Echtzeitberichte mit demografischer Analyse
* **Zentralisiertes Branding** - Definition von visuellen und technischen Richtlinien für Marken
* **REST-APIs** - Erstellen von Integrationen und Aufbau Ihres Ökosystems
* **Verbesserungen bei Landingpages** - Verbesserte Funktionsparität mit Campaign Standard
* **Visual Fragments** - Wiederverwendbare visuelle Komponenten für E-Mails und Inhaltsvorlagen

**Wichtig:** Die meisten Marketing- und Betriebsfunktionen sind in v8 verfügbar und wurden verbessert. Technische Funktionen und Funktionen auf Infrastrukturebene werden von Adobe in der Cloud-Umgebung verwaltet.

**Verwandte Themen:**

* [Funktionsmatrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} - Vergleichen von Funktionen über Schnittstellen hinweg
* [Kompatibilitätsmatrix](compatibility-matrix.md) - Unterstützte Systeme und Komponenten
* [Schutzmechanismen und Einschränkungen](ac-guardrails.md)
* [v7- zu v8-Umstellungshandbuch](v7-to-v8.md)
* [Wechsel von Campaign Standard zu v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## Profile und Zielgruppen {#audiences}

Hier finden Sie Antworten auf Fragen zur Verwaltung von Profilen, zur Erstellung von Audiences, zum Datenimport und zur Zielgruppenbestimmung von Empfängern für Ihre Kampagnen.

+++ Wie erstelle ich Empfänger?

Manuelles Erstellen von Empfängern für einzelne Profile, Import aus Dateien (CSV/TXT) für Massenhinzufügungen, Verwendung von Web-Formularen zur Selbstregistrierung oder Integration über APIs von externen Systemen. Verwenden Sie Import-Workflows für wiederkehrende Datenladevorgänge.

[Manuelles Erstellen von Profilen](../audiences/create-profiles.md) | [Importieren von Profilen aus einer Datei](../audiences/import-profiles.md) | [Erfassen von Profilen mit Web-Formularen](../audiences/collect-profiles.md)

+++

+++ Wie importiere ich Profile?

Campaign bietet mehrere Importmethoden: einen einfachen Dateiimport mit dem Importassistenten, einen Workflow-basierten Import für komplexe Umwandlungen, wiederkehrende Importe mit geplanten Workflows aus SFTP und einen API-Import für die programmgesteuerte Integration.

Bereiten Sie Ihre Datendatei (CSV/TXT, UTF-8-Kodierung) für den Dateiimport vor, verwenden Sie den Importassistenten oder -Workflow, ordnen Sie Spalten Campaign-Feldern zu, definieren Sie Regeln zum Aktualisieren/Einfügen und testen Sie sie zuerst mit einem kleinen Muster. Verwenden Sie Workflows für wiederkehrende Importe und wenden Sie Deduplizierungsregeln an.

[Datenimport-Handbuch](../start/import.md) | [Workflow für wiederkehrenden Import](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=de){target="_blank"} | [Aktivität „Laden“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=de){target="_blank"}

+++

+++ Wie kann ich die Zielpopulation für meine Marketing-Kampagne definieren?

Campaign bietet mehrere Zielgruppenbestimmungsmethoden: Abfragen mit visuellen Kriterien erstellen, vorhandene Listen oder Segmente ansprechen, Empfänger aus externen Dateien (CSV, TXT) importieren oder vordefinierte Filter anwenden. Sie können Kriterien mit UND/ODER-Logik kombinieren, bestimmte Populationen ausschließen, Kontrollgruppen verwenden und für A/B-Tests aufteilen. Zeigen Sie vor dem Versand immer die Größe Ihrer Zielpopulation in der Vorschau an.

[Definieren von Kampagnenzielen](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=de){target="_blank"} | [Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"} | [Zielgruppen erstellen](../audiences/create-audiences.md)

+++

+++ Wie kann ich eine Profilliste erstellen?

Eine Liste ist eine statische Gruppe von Empfängern, die Sie in Sendungen auswählen und kampagnenübergreifend wiederverwenden können.

**Drei Erstellungsmethoden:**

* **Manuelle Erstellung:** Navigieren Sie zu **[!UICONTROL Profile und Zielgruppen >]** und klicken Sie auf **[!UICONTROL Erstellen]**. Hinzufügen von Empfängern aus einer Abfrage, einer individuellen Auswahl oder einem Ordner.

* **Workflow-Automatisierung:** Verwenden Sie die Aktivität **[!UICONTROL Listen-Update]**, um Listen automatisch aus Abfrageergebnissen oder importierten Daten zu erstellen und zu pflegen.

* **Beim Import:** beim Importieren von Profilen eine Liste, um sie als wiederverwendbare Gruppe zu speichern.

>[!TIP]
>
>Verwenden Sie Workflows für Listen, die regelmäßige Aktualisierungen erfordern, und manuelle Erstellung für eine einmalige Segmentierung.

[Zielgruppen erstellen](../audiences/create-audiences.md) | [Aktivität „Listen-Update“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Wie kann ich eine Population vor dem Nachrichtenversand deduplizieren?

Verwenden Sie die **[!UICONTROL Deduplizierung]** in einem Workflow, um doppelte Empfänger vor dem Versand zu entfernen. Platzieren Sie sie zwischen Ihren **[!UICONTROL Abfrage]**- und **[!UICONTROL Versand]**-Aktivitäten und wählen Sie dann Ihre Deduplizierungskriterien (normalerweise E-Mail-Adresse oder Empfänger-ID) und den beizubehaltenden Datensatz aus.

>[!TIP]
>
>Deduplizieren Sie Ihre Nachricht vor dem Versand immer, damit jede Person Ihre Nachricht nur einmal erhält.

[Aktivität „Deduplizierung“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=de){target="_blank"}

+++

+++ Wie kann ich Abonnenten meines Newsletters identifizieren und ansprechen?

Campaign verfolgt Newsletter-Abonnements automatisch über Informations-Services. An Abonnenten richten:

* Verwenden Sie eine **[!UICONTROL Abfrage]**-Aktivität und filtern Sie nach **[!UICONTROL Abonnements]** > wählen Sie Ihren Newsletter-Service aus.
* Sprechen Sie Abonnentinnen und Abonnenten direkt aus Ihrem Versand an, indem Sie **[!UICONTROL An > Abonnentinnen und Abonnenten eines Informationsdienstes auswählen]**
* Erstellen von Abonnentenlisten mit der Workflow **[!UICONTROL Aktivität „Abonnement]**

Campaign verfolgt den Verlauf von An-/Abmeldungen und verwaltet die An-/Abmeldung automatisch.

[Abonnements verwalten](../start/subscriptions.md) | [Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"}

+++

+++ Was sind die Best Practices beim Ausschließen von Profilen aus einer Zielpopulation?

Verwenden Sie die **[!UICONTROL Ausschluss]**-Aktivität in einem Workflow, um unerwünschte Profile aus Ihrer Zielgruppe zu entfernen. Platzieren Sie sie nach Ihren Zielgruppenbestimmungsaktivitäten und definieren Sie, welche Population ausgeschlossen werden soll.

[Ausschlussaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Kann ich externe Profile verwenden, ohne sie in Campaign zu importieren?

Ja, mit Campaign v8 können Sie mit externen Profilen arbeiten, die in einer externen Datenbank gespeichert sind, ohne sie in Adobe Campaign zu laden. [Weitere Informationen](../audiences/external-profiles.md).

+++

+++ Wie erstelle ich Testprofile für meine Sendungen?

Testprofile sind spezielle Empfängerinnen und Empfänger, die zum Durchführen von Testsendungen und zur Validierung von Sendungen verwendet werden, ohne dass sich dies auf Ihre Produktionsdatenbank auswirkt. Erstellen Sie sie unter **[!UICONTROL Profile und Zielgruppen > Testprofile]** oder verwenden Sie die Funktion **[!UICONTROL Testadressen]**, um Ihren Sendungen automatisch Testempfängerinnen und Testempfänger hinzuzufügen, um die Qualität zu gewährleisten und den Posteingang zu überwachen.

[Testprofile](../audiences/test-profiles.md)

+++

## Nachrichtendesign {#design}

Erfahren Sie, wie Sie in Campaign v8 effektive Marketing-Nachrichten entwerfen, einschließlich E-Mail-Vorlagen, Personalisierungstechniken und mehrsprachiger Inhalte. Gestalten Sie Ihre Nachrichten in der Client-Konsole oder verwenden Sie den modernen **E-Mail-Designer** in der Web-Benutzeroberfläche von Campaign, um die visuelle Bearbeitung zu verbessern.

+++ Was sind die Best Practices für die Gestaltung von E-Mails in Campaign?

Wichtige Richtlinien: Sicherstellen eines responsiven Designs für Mobilgeräte, Verwenden von HTML 4.0/XHTML-kompatiblem Code mit Inline-CSS, Optimieren von Bildern (unter 100 KB) mit Alt-Text, Verwenden von Personalisierungszusammenführungsfeldern, Testen über E-Mail-Clients hinweg vor dem Versand und Einschließen einer Nur-Text-Version. Für optimale Zustellbarkeit wird eine E-Mail-Gesamtgröße von unter 500 KB angestrebt.

[E-Mail-Design-Handbuch](../send/email.md) | [Best Practices beim Versand](delivery-best-practices.md)

+++

+++ Was ist eine Versandvorlage?

Eine Versandvorlage ist ein vorkonfigurierter Versand, der alle Einstellungen und Parameter speichert, um sie in mehreren Kampagnen wiederzuverwenden. Zu den Vorlagen gehören Zielgruppenregeln, Inhaltsdesign, Personalisierung, technische Einstellungen (Absender, Antwortadresse) und Typologieregeln. Einmal erstellen und wiederverwenden, um Konsistenz zu wahren und die Kampagnenerstellung zu beschleunigen.

[Erstellen von Versandvorlagen](../send/create-templates.md)

+++

+++ Kann ich eine vorhandene HTML-Datei einfach importieren, um eine E-Mail in Campaign zu erstellen?

Ja. Importieren Sie HTML-Inhalte per Direktkopie/Einfügen in den Inhaltseditor, über Ihren Computer hochgeladene Dateien oder über eine URL. Stellen Sie sicher, dass Ihre HTML E-Mail-kompatiblen Code (HTML 4.0/XHTML) mit Inline-CSS verwendet und Bilder auf einem öffentlichen Server hosten. Campaign fügt importierten HTML automatisch Personalisierung und Tracking hinzu.

>[!TIP]
>
>Für ein optimales E-Mail-Design-Erlebnis **Sie den E-Mail-Designer** in der Web-Benutzeroberfläche von Campaign, der moderne Drag-and-Drop-Funktionen und integrierte responsive Vorlagen bietet, anstatt unbearbeitetes HTML zu importieren.

[HTML-Inhalt importieren](../send/defining-the-email-content.md)

+++

+++ Wie kann ich in Campaign einen Newsletter zum Abonnieren erstellen?

Ja. Verwenden Sie die Informations-Services von Campaign, um Newsletter-Abonnements zu verwalten. Zu den wichtigsten Funktionen gehören die automatische Handhabung von Opt-in/Opt-out, Abonnement-Tracking, Compliance-Management (DSGVO, CAN-SPAM), Unterstützung für mehrere Newsletter, Web-Integration für Anmeldeformulare und zielgerichteter Versand an Abonnenten.

[Verwalten von Abonnements](../start/subscriptions.md)

+++

+++ Wie kann ich Nachrichten personalisieren?

Campaign bietet Personalisierungsfunktionen, mit denen basierend auf Empfängerdaten, Verhalten und Voreinstellungen relevante, zielgerichtete Nachrichten erstellt werden können.

**Personalization-Optionen:**

* **Personalisierungsfelder** - Empfängerdaten einfügen (z. B. `"Hello {{firstName}}")`
* **Gestaltungsbausteine** - Verwenden vordefinierter oder benutzerdefinierter Inhaltsbausteine
* **Bedingter Inhalt** - Unterschiedlicher Inhalt wird basierend auf Empfängerkriterien angezeigt
* **Verhaltensdaten** - Nutzen Sie den Browser-Verlauf, Kaufmuster oder Interaktionsmetriken

Testen Sie die Personalisierung vor dem Senden, um zu überprüfen, ob Zusammenführungsfelder und die bedingte Logik ordnungsgemäß funktionieren.

[Handbuch zu Personalization](../send/personalize.md) | [Personalisierungsfelder](../send/personalization-fields.md) | [Bedingter Inhalt](../send/conditions.md)

+++

+++ Kann ich mehrsprachige Nachrichten senden?

Ja. Campaign v8 bietet mehrsprachige Funktionen, wobei die **Campaign Web-Benutzeroberfläche** den einfachsten Ansatz bietet. Die Web-Benutzeroberfläche bietet einen nativen mehrsprachigen Versand mit Sprachvarianten. Fügen Sie Ihrem Versand Sprachvarianten hinzu, und Campaign sendet automatisch die entsprechende Version basierend auf der bevorzugten Sprache des Empfängers. Verfügbar für E-Mail, Push-Benachrichtigungen, SMS und Transaktionsnachrichten.

Hauptfunktionen: automatische Inhaltsduplizierung, automatisches sprachbasiertes Senden, standardmäßiges Sprachfallback und einfache Variantenverwaltung.

Die Client-Konsole unterstützt auch mehrsprachige Inhalte mit bedingten Inhalten und Workflows, erfordert jedoch eine manuellere Konfiguration.

[Mehrsprachige Sendungen (Web-Benutzeroberfläche)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Bedingter Inhalt (Client-Konsole)](../send/conditions.md)

+++

+++ Kann ich ein Web-Formular lokalisieren?

Ja. Web-Anwendungen von Campaign unterstützen die Lokalisierung in mehreren Sprachen. Definieren Sie Übersetzungen für alle Formularelemente (Beschriftungen, Schaltflächen, Meldungen, Fehlertext), mit automatischer Spracherkennung basierend auf Empfängerprofil- oder Browser-Einstellungen. Innerhalb einer einzelnen Webanwendung werden mehrere Sprachversionen unterstützt, wobei bei Bedarf auf eine Standardsprache zurückgegriffen wird.

[Lokalisierung von Web-Anwendungen](../dev/webapps.md)

+++

+++ Kann ich KI-gestützte Inhalte in meinen E-Mails verwenden?

Ja, aber **nur über die Campaign Web-Benutzeroberfläche**. Der KI-Assistent unterstützt Microsoft Azure OpenAI und Adobe Firefly und hilft beim Erstellen professioneller, markenkonsistenter Inhalte für E-Mail, SMS und Push-Benachrichtigungen.

**Schlüsselfunktionen:**

* Generieren von Text (E-Mail-Kopie, Betreffzeilen, SMS-/Push-Inhalt) und markenorientierten Bildern
* Erstellen von Inhaltsvarianten, die für verschiedene Zielgruppen optimiert sind
* Inhalte verfeinern (ausarbeiten, zusammenfassen, umformulieren, vereinfachen)
* Hochladen von Marken-Assets und Abrufen der Bewertung bei der Markenausrichtung
* Vorhandenen Inhalt als Referenz verwenden und Stilreferenzbilder hochladen

>[!NOTE]
>
>Der KI-Assistent ist ausschließlich in der Web-Benutzeroberfläche von Campaign verfügbar und unterstützt derzeit nur Englisch. Benutzer benötigen entsprechende Berechtigungen und müssen einer Benutzervereinbarung zustimmen.

[Überblick über den KI-Assistenten](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Anwendungsfälle des KI-Assistenten](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Markenausrichtung](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Testen und Senden von Nachrichten {#send}

Erfahren Sie mehr über Best Practices zum Testen, Validieren, Senden und Tracking Ihrer Marketing-Nachrichten, um den erfolgreichen Versand einer Kampagne sicherzustellen.

+++ Was ist die Versandanalyse?

Die Versandanalyse ist eine Validierungsphase, die Campaign vor dem Versand durchführt. Es berechnet die Zielpopulation, validiert den Inhalt, sucht nach Fehlern, wendet Typologieregeln an und schätzt das Versandvolumen.

Campaign generiert Protokolle mit Warnungen und Fehlern. Fehler blockieren den Versand und müssen behoben werden. Warnungen sind empfehlenswert. Überprüfen Sie vor dem Versand immer die Analyseprotokolle.

[Handbuch zur Versandanalyse](../send/delivery-analysis.md)

+++

+++ Warum sollte ich Testsendungen durchführen?

Testsendungen sind Testnachrichten, die Ihren Versand validieren, bevor Sie ihn an Ihre Hauptzielgruppe senden. Testsendungen verwenden, um die Personalisierung zu überprüfen, das Rendering von Inhalten für E-Mail-Clients zu testen, Links und Tracking-Arbeit zu bestätigen, Bilder und Anhänge zu überprüfen und die Reaktionsfähigkeit auf Mobilgeräten zu validieren.

Testsendungen helfen dabei, Fehler zu erkennen, bevor sie Tausende von Empfängern erreichen, ermöglichen die Genehmigung durch Stakeholder und testen die Posteingangsplatzierung. Führen Sie Testsendungen an mehrere E-Mail-Clients und -Geräte durch und holen Sie sich immer die Genehmigung ein, bevor die Produktion gesendet wird.

[Handbuch zu Testsendungen und zur Vorschau](../send/preview-and-proof.md)

+++

+++ Wie werden Testadressen in Adobe Campaign verwendet?

Testadressen sind spezielle Empfängerinnen und Empfänger, die automatisch zu jedem Versand hinzugefügt werden, um ihn zu testen, zu prüfen und zu überwachen - ohne dass sie Ihren Zielgruppenkriterien entsprechen. Nützlich für die laufende Überwachung, Tests der Posteingangsplatzierung, Direkt-Mail-Validierung und die Sichtbarkeit für Stakeholder.

**Die wichtigsten Unterschiede zu Testsendungen:**

* **Testadressen**: Die Testadressen werden automatisch zum Versandvolumen in der Produktion hinzugefügt.
* **Testsendungen** - Testsendungen vor der Produktion, werden nicht zum Volumen gezählt, sondern zur Validierung verwendet

Testadressen verwalten in **[!UICONTROL Ressourcen > Kampagnen-Management > Testadressen]**. Halten Sie Listen klein, um eine Beeinträchtigung der Versandmetriken zu vermeiden.

[Leitfaden zu Testadressen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Wie kann ich vor dem Versand einen Validierungsprozess einrichten?

Campaign bietet Validierungs-Workflows, um sicherzustellen, dass Nachrichten vor dem Versand den Qualitätsstandards entsprechen. Konfigurieren von Validierungen für Inhalt, Zielgruppe, Extraktion (Briefpost) und Budget auf Kampagnen- oder Versandebene.

**Setup:**

Erstellen Sie Benutzergruppen unter **[!UICONTROL Administration > Zugriffsverwaltung > Benutzergruppen]** und weisen Sie dann in den Kampagnen- oder Versandeigenschaften Validierungsgruppen zu. Campaign sendet Benachrichtigungs-E-Mails an Validierungsverantwortliche, die Änderungen genehmigen, ablehnen oder anfordern können.

**Für eigenständige Sendungen (nicht in einer Kampagne):**

Verwenden **Testsendungen als Genehmigungsprozess**. Führen Sie Testsendungen zur Validierung an Ihre Genehmigungsgruppe durch und senden Sie nach der Vornahme von Änderungen immer einen neuen Testversand, um sicherzustellen, dass die Verantwortlichen die neueste Version überprüfen.

[Versandvalidierung](../send/preview-and-proof.md) | [Kampagnengenehmigungen](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=de){target="_blank"}

+++

+++ Was ist eine Typologieregel?

Typologieregeln sind automatisierte Geschäftslogiken, die während der Versandanalyse angewendet werden, um den Nachrichtenversand zu validieren und zu optimieren. Sie gewährleisten die Einhaltung von Marketing-Richtlinien, schützen die Zustellbarkeit und verhindern Kundenmüdigkeit.

**Hauptregeltypen:**

* **Filterregeln** - Empfänger ausschließen (auf die Blockierungsliste gesetzt, abgemeldet, unter Quarantäne gestellt)
* **Druckregeln** - Kontrollieren Sie die Häufigkeit von Nachrichten, um zu vermeiden, dass Empfänger überfordert werden
* **Kapazitätsregeln** - Nachrichtenvolumen für Verarbeitungskapazität oder ISP-Beschränkungen begrenzen
* **Kontrollregeln** - Gültigkeit der Nachricht überprüfen (Betreffzeile, Abmelde-Link, Absenderformat)

Regeln werden in Typologien gruppiert und bei der Versandanalyse angewendet. Campaign kann Empfänger anhand der Regeln ausschließen, den Versand blockieren oder Warnungen generieren.

[Handbuch zu Typologieregeln](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=de){target="_blank"}

+++

+++ Wie kann ich E-Mails in mehreren Schüben senden?

Ja. Der Wellenversand unterteilt Ihren Versand in mehrere Batches, die in terminierten Intervallen gesendet werden. Dies ist für Kampagnen mit großem Volumen unerlässlich, um die Server-Last auszugleichen, ISP-Drosselungen zu verhindern, die Reputation der Absender mit neuen IPs aufzubauen und Opt-outs/Bounces zwischen Schüben zu verwalten.

**Konfiguration:**

Aktivieren Sie in den Versandeigenschaften das Senden von Wellen und definieren Sie die Anzahl der Wellen (oder die Batch-Größe), das Intervall zwischen den Wellen und die Wellenverteilung (lineare oder benutzerdefinierte Prozentsätze). Campaign teilt Ihre Zielpopulation automatisch auf und sendet jede Welle planmäßig.

Verwenden Sie Wellen für große Kampagnen, überwachen Sie die Leistung der ersten Welle, bevor Sie fortfahren, und lassen Sie ausreichend Zeit zwischen den Wellen, um Bounces und Opt-outs zu verarbeiten.

[Wellenversand konfigurieren](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Was sind die wichtigsten Schritte bei der Erstellung einer E-Mail in Campaign?

Die Erstellung einer E-Mail in Campaign v8 umfasst die folgenden wichtigen Schritte: Erstellen des Versands, Definieren der Zielgruppe, Entwerfen des Inhalts, Hinzufügen einer Personalisierung, Konfigurieren der Einstellungen (Absender, Betreff, Antwort an), Ausführen der Versandanalyse, Durchführen von Testsendungen für Tests und schließlich Senden oder Planen.

**Wichtige Schritte:**

1. **Versand erstellen** - Wählen Sie E-Mail als Kanal und wählen Sie optional eine Versandvorlage aus
1. **Zielgruppe definieren** - Wählen Sie Ihre Empfänger-Zielgruppe mithilfe von Abfragen, Listen oder importierten Dateien aus.
1. **Inhalt gestalten** - Erstellen Sie Ihre Nachricht mit dem E-Mail-Editor (E-Mail-Designer in der Web-Benutzeroberfläche oder Client-Konsolen-Editor).
1. **Personalisierung hinzufügen** - Dynamische Felder, Gestaltungsbausteine und bedingte Inhalte einfügen
1. **Einstellungen konfigurieren** - Festlegen von Absenderadresse, Betreffzeile, Antwort-an und Versandparametern
1. **Versandanalyse ausführen** - Campaign validiert Inhalte, berechnet die Zielgruppe und sucht nach Fehlern.
1. **Testsendungen durchführen** - Testen Sie Ihre E-Mail mit Genehmigungsgruppen, um Rendering und Inhalt zu validieren.
1. **Senden oder Zeitplan** - Sofort an die Hauptzielgruppe oder an einen späteren Zeitplan senden

**Zwei Schnittstellenoptionen:**

* **Campaign Web-Benutzeroberfläche** - Moderne Benutzeroberfläche mit erweiterten E-Mail-Designer-, KI-Assistenten- und mehrsprachigen Funktionen
* **Client-**: Herkömmliche Benutzeroberfläche mit erweiterten Targeting- und Workflow-Funktionen


>[!TIP]
>
>Verwenden Sie die Web-Benutzeroberfläche von Campaign für eine schnellere, intuitivere E-Mail-Erstellung mit modernen Design-Tools. Verwenden Sie die Client-Konsole für komplexe Zielgruppenbestimmungen oder erweiterte Workflow-basierte Kampagnen.

[Erste E-Mail erstellen](create-message.md) | [E-Mail-Design-Handbuch](../send/email.md)

+++

+++ Wie wird ein Versand terminiert?

Mit Campaign können Sie Sendungen für den zukünftigen Versand planen, um Versandzeiten zu optimieren und Kampagnen zu koordinieren.

**Planungsoptionen:**

* **Versandeigenschaften** - Sofort senden, für ein bestimmtes Datum/eine bestimmte Uhrzeit planen oder nach Stunden/Tagen verschieben
* **Kampagnenebene** - Koordinieren aller Sendungen innerhalb einer Kampagne
* **Workflow-Planungsaktivität** - Für wiederkehrende Sendungen, komplexe Muster und ereignisausgelöste Kampagnen

Campaign unterstützt auch die Optimierung des Kontaktdatums (beste Versandzeit pro Empfänger) und die Anpassung der Zeitzone (gleiche lokale Zeit für alle Empfänger).

[Versand planen](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Kann ich zu E-Mails einen Anhang hinzufügen?

Ja. Campaign unterstützt statische Anhänge (dieselbe Datei für alle Empfänger) und personalisierte Anhänge (je nach Empfänger unterschiedliche Dateien basierend auf Profildaten). Fügen Sie Anlagen im **[!UICONTROL Anlagen]** Ihrer Versandeigenschaften hinzu.

**Wichtige Überlegungen:**

* Anhänge für eine optimale Zustellbarkeit unter 1 MB speichern
* Anhänge können Spam-Filter zum Trigger bringen. Vor dem Versand gründlich testen
* Vermeiden Sie Dateitypen, die häufig von E-Mail-Clients (.exe, .zip, .js) blockiert werden
* Bei großen Dateien sollten Sie stattdessen getrackte Download-Links verwenden

Sichere Dateiformate verwenden (PDF, JPEG, PNG, DOCX) und Testadressen testen, bevor die Produktion gesendet wird.

[Handbuch zu E-Mail-Anhängen](../send/email.md#attachments)

+++

+++ Wie kann ich getrackte Links in einem E-Mail-Versand konfigurieren?

Campaign konvertiert automatisch alle URLs in Ihrer E-Mail in getrackte Links, um die Empfängerinteraktion zu überwachen. Rufen Sie den **[!UICONTROL Tracking]** in Ihrem Versand auf, um die Tracking-Einstellungen für jeden Link zu konfigurieren.

**Konfigurationsoptionen:**

* **Tracking aktivieren/deaktivieren** - Tracking pro Link steuern
* **Link-Kennzeichnungen** - Fügen Sie beschreibende Namen für das Reporting hinzu (z. B. „Jetzt CTA kaufen„)
* **Link-Kategorien** - Gruppieren von Links nach Typ für die aggregierte Analyse
* **Tracking-Typ** - Klicks, Öffnungen oder beides verfolgen

Campaign verfolgt Inhalts-Links, Mirrorseiten-Links und Abmelde-Links und kann ein optionales Tracking-Pixel für E-Mail-Öffnungen enthalten. Verwenden Sie aussagekräftige Bezeichnungen und Kategorien, um das Reporting zu vereinfachen und leistungsstarke Inhalte schnell zu identifizieren.

[Linktracking-Handbuch](../start/tracking.md) | [Best Practices für das Tracking](../send/send.md)

+++

+++ Wo kann ich auf Versand- und Trackinglogs zugreifen?

Zugreifen auf Versand- und Trackinglogs direkt über jedes Versand-Dashboard. Klicken Sie in der Client-Konsole **[!UICONTROL unten auf]** Registerkarte „Versand“. Navigieren Sie in der Web-Benutzeroberfläche von Campaign zum Abschnitt **[!UICONTROL Protokolle]** .

**Verfügbare Protokolle:**

* **Versandlogs** - Gesendete Nachrichten mit Empfängerdetails und Status (gesendet, ausstehend, fehlgeschlagen)
* **Trackinglogs** - Empfängerinteraktionen (Öffnungen, Klicks) mit Zeitstempeln
* **Ausschlusslogs** - Ausgeschlossene Empfänger mit Gründen (Quarantäne, Typologieregeln, Duplikate)
* **Broadcast-Protokolle** - Vollständiger Versandverlauf einschließlich weiterer Versuche und Fehler

Verwenden Sie diese Protokolle, um Versandprobleme zu beheben, die Interaktion zu analysieren und die Listenhygiene aufrechtzuerhalten.

[Versand-Monitoring](../send/send.md) | [Tracking-Anleitung](../start/tracking.md)

+++

+++ Wo finde ich Versandberichte?

Campaign bietet umfassende integrierte Berichte, um die Versandleistung, die Interaktion mit Empfängern und die Effektivität der Kampagne zu analysieren. Greifen Sie auf Berichte über die **[!UICONTROL Berichte]** in jedem Versand, über das Kampagnen-Dashboard oder über das globale Menü **[!UICONTROL Berichte]** für die kampagnenübergreifende Analyse zu.

**Zu den wichtigsten Berichten gehören:**

* **Versandzusammenfassung** - Versandstatistiken, Öffnungen, Klicks, Bounces und Abmeldungen
* **Klicks** - Visuelle Heatmap der Link-Performance
* **Tracking-Indikatoren** - Klickraten und Interaktionsmetriken
* **Fehler** - Bounce-Analyse mit Fehlerursachen

Berichte sind sowohl in der Client-Konsole als auch in der Campaign Web-Benutzeroberfläche mit modernen Visualisierungen verfügbar.

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

>[!TIP]
>
>Überwachen Sie Ihre Quarantäneliste regelmäßig. Steigende Quarantäneraten deuten häufig auf Datenqualitätsprobleme hin, die beachtet werden müssen, bevor sie sich auf die Reputation des Absenders auswirken.

[Handbuch zur Quarantäneverwaltung](../send/quarantines.md) | [Bounce-Verwaltung](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Erfahren Sie, wie Sie mithilfe von Workflows Prozesse automatisieren, Daten verwalten und komplexe Marketing-Kampagnen in Adobe Campaign koordinieren können.

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

* [Erstellen eines Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"}
* [Workflow-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [Best Practices bei Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"}
* [Workflow-Anwendungsfälle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Wie kann ich Daten in Campaign importieren?

Importieren Sie Daten je nach Bedarf mit mehreren Methoden in Campaign:

**Einfacher Dateiimport:**

* Verwenden des Import-Assistenten für einmalige CSV/TXT-Importe mit einer geführten Oberfläche
* Ideal für manuelle Uploads und schnelles Laden von Daten

**Workflow-basierter Import:**

* Erstellen von Workflows mit **[!UICONTROL Aktivität „Laden (Datei)]** für komplexe Importe
* Hinzufügen von Datenumwandlungen, Anreicherung und Deduplizierung
* Planen wiederkehrender Importe aus SFTP, lokalen Verzeichnissen oder Cloud-Speicher

**API-Integration:**

* Verwenden von REST-APIs zum programmgesteuerten Importieren von Daten aus externen Systemen
* Ideal für die Echtzeit-Synchronisation mit CRM, E-Commerce oder anderen Plattformen

**Best Practices:** Testen Sie immer mit kleinen Stichproben, verwenden Sie UTF-8-Kodierung, ordnen Sie Felder korrekt zu, wenden Sie Deduplizierungsregeln an und planen Sie große Importe außerhalb der Spitzenzeiten.

**Verwandte Themen:**

* [Best Practices beim Datenimport](../start/import.md)
* [Aktivität „Laden“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=de){target="_blank"}
* [Workflow für wiederkehrenden Import](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=de){target="_blank"}

+++

+++ Kann ich die Ausführung von Workflows überwachen?

Ja. Campaign bietet umfassende Workflow-Überwachungsfunktionen, um die Ausführung zu verfolgen, Probleme zu identifizieren und die Leistung zu optimieren.

**Überwachungsoptionen:**

* **Workflow-Dashboard** - Anzeigen des Ausführungsstatus, des Fortschritts und der Aktivitätsstatus in Echtzeit
* **Ausführungsprotokolle** - Zugriff auf detaillierte Protokolle für jede Aktivität und Transition
* **Audit-Protokoll** - Verfolgen von Workflow-Änderungen und Ausführungsverlauf
* **Warnhinweise und Benachrichtigungen** - Einrichten von E-Mail-Warnhinweisen für Fehler oder bestimmte Bedingungen

**Wichtige Überwachungsfunktionen:**

* Visuelle Statusanzeigen (ausstehend, in Bearbeitung, abgeschlossen, fehlgeschlagen)
* Tracking der Ausführungszeit zur Leistungsoptimierung
* Fehlermeldungen auf Aktivitätsebene zur Fehlerbehebung
* Workflows bei Bedarf anhalten, stoppen oder neu starten

Greifen Sie über **[!UICONTROL Administration > Produktion > Automatisch erstellte Objekte > Kampagnen-Workflows]** oder direkt über das Workflow-Dashboard auf die Überwachung zu.

**Verwandte Themen:**

* [Überwachen der Workflow-Ausführung](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}
* [Best Practices bei Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"}
* [Workflow starten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=de){target="_blank"}

+++

+++ Wie kann ich Daten in Campaign mit einem Workflow aktualisieren?

Verwenden Sie die Aktivität **[!UICONTROL Daten aktualisieren]** in Workflows, um Massenvorgänge in Ihrer Datenbank durchzuführen:

**Unterstützte Vorgänge:**

* **Einfügen** - Hinzufügen neuer Datensätze zur Datenbank
* **Aktualisieren** - Ändern vorhandener Datensätze basierend auf übereinstimmenden Kriterien
* **Einfügen oder Aktualisieren** - Hinzufügen neuer Datensätze oder Aktualisieren vorhandener Datensätze (upsert)
* **Löschen** - Entfernen von Datensätzen, die bestimmten Kriterien entsprechen

**Häufige Anwendungsfälle:**

* Aktualisieren von Profilattributen nach der Datenanreicherung
* Synchronisieren von Daten mit externen Systemen
* Listenmitgliedschaften basierend auf dem Verhalten verwalten
* Daten bereinigen und deduplizieren
* Massenstatusänderungen anwenden (z. B. Opt-out, Quarantäne)

Abstimmschlüssel so konfigurieren, dass die Datensätze genau übereinstimmen, und Aktualisierungsoptionen auswählen (alle Felder oder nur leere Felder aktualisieren).

**Verwandte Themen:**

* [Aktivität „Daten-Update“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=de){target="_blank"}
* [Daten-Management-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Wie kann ich Daten-Management-Funktionen verwenden?

Die Daten-Management-Aktivitäten von Campaign ermöglichen innerhalb von Workflows ausgefeilte Datenoperationen für ein komplexes Targeting und eine komplexe Segmentierung.

**Wichtige Daten-Management-Aktivitäten:**

* **Anreicherung** - Hinzufügen von Daten aus verknüpften Tabellen oder externen Quellen zur Arbeitspopulation
* **Aufspaltung** - Segmentpopulationen basierend auf Kriterien oder zufällig verteilt
* **Deduplizierung** - Entfernt doppelte Einträge basierend auf angegebenen Schlüsseln
* **Daten aktualisieren** - Masseneinfüge-, Aktualisierungs- oder Löschvorgänge durchführen
* **Dimensionsänderung** - Wechseln von Zielgruppendimensionen (z. B. von Empfängern zu Abonnements)
* **Schnittmenge/Vereinigung/Ausschluss** - Kombinieren oder Filtern mehrerer Populationen

**Häufige Anwendungsfälle:**

* Profile mit Daten zum Kaufverlauf oder zum Verhalten anreichern
* Segmentieren von Audiences in mehrere Gruppen für verschiedene Nachrichten
* Duplikate vor dem Versand entfernen
* Integrieren von Daten aus externen Datenbanken (FDA - Federated Data Access)
* Erstellen komplexer Abfragen und Joins für mehrere Tabellen

Mit diesen Aktivitäten können Sie mit Daten arbeiten, die sich nicht direkt in der Hauptempfängertabelle befinden, und erweiterte Datenbankvorgänge durchführen.

**Verwandte Themen:**

* [Daten-Management-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [Zielgruppen-Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=de){target="_blank"}
* [Aktivität „Anreicherung“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=de){target="_blank"}

+++

+++ Kann ich den Versand personalisierter Nachrichten automatisieren?

Ja. Workflows ermöglichen vollständig automatisierte personalisierte Nachrichtenkampagnen auf der Basis von Empfängerdaten, Verhalten und benutzerdefinierten Kriterien.

**Automatisierungs-Workflow-Struktur:**

1. **Abfrage** - Auswahl der Zielgruppe anhand von Kriterien
1. **Anreicherung** - Personalisierungsdaten aus verknüpften Tabellen hinzufügen
1. **Aufspaltung** - Segmentieren in Gruppen für verschiedene Nachrichtenvarianten (optional)
1. **Versand** - Senden personalisierter Nachrichten mit Zusammenführungsfeldern
1. **Planung** - Einrichten der wiederkehrenden Ausführung für automatisierte Kampagnen

**Personalization-Optionen:**

* Empfängerprofildaten verwenden (Name, Standort, Voreinstellungen)
* Verhaltensdaten einschließen (Kaufverlauf, Interaktionswerte)
* Anwenden bedingter Inhalte basierend auf Segmenten oder Attributen
* Dynamische Werte berechnen (Treuepunkte, Ablaufdaten)

Häufige Szenarien: Geburtstagskampagnen, Warenkorbabbrüche, Treueprogramme, Win-back-Kampagnen und ereignisgesteuerte Nachrichten.

**Verwandte Themen:**

* [Handbuch zu Personalization](../send/personalize.md)
* [Workflow-Anwendungsfälle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=de){target="_blank"}
* [Aktivität „Anreicherung“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=de){target="_blank"}

+++

+++ Wie kann ich eine Zielgruppe mit einem Workflow in Teilmengen unterteilen?

Verwenden Sie die **[!UICONTROL Aufspaltung]**, um eine einzelne Population basierend auf Kriterien oder Verteilungsregeln in mehrere Teilmengen zu unterteilen.

**Split-Methoden:**

* **Filterbedingungen** - Erstellen von Teilmengen anhand von Kriterien (z. B. Altersgruppen, Standort, VIP-Status)
* **Prozentverteilung** - Für A/B-Tests zufällig in gleiche oder benutzerdefinierte Prozentsätze aufteilen
* **Datensätze begrenzen** - Größe der Teilmengen beschränken (erste N Datensätze, oberste X %, zufällige Auswahl)
* **Datengruppierung** Erstellen einer Untergruppe pro bestimmtem Wert (z. B. eine Untergruppe pro Land)

**Häufige Anwendungsfälle:**

* A/B-Tests mit Kontrollgruppen
* Routing mit Kanalvoreinstellungen (E-Mail vs. SMS)
* Progressiver Rollout (an 10 % und dann 90 % senden)
* Segmentspezifisches Messaging (VIP, Stammkunden, Neukunden)
* Lastenausgleich über mehrere Versand-Server hinweg

Jede aufgeteilte Teilmenge wird zu einer separaten Transition geleitet, sodass für jede Gruppe eine andere Verarbeitung oder ein anderer Versand möglich ist.

**Verwandte Themen:**

* [Aufspaltungsaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=de){target="_blank"}
* [A/B-Test-Handbuch](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Wie kann ich Empfängerdaten durch eine externe Datei aktualisieren?

Ja. Verwenden Sie Workflows, um Campaign-Daten mit Werten aus externen Dateien (CSV, TXT) zu aktualisieren.

**Workflow-Struktur:**

1. **Laden (Datei)** - Laden der externen Datei und Zuordnen von Spalten
1. **Anreicherung** (optional) - Hinzufügen zusätzlicher Daten oder Umwandlungen
1. **Abstimmung** - Definieren Sie Schlüssel, um Dateidatensätze mit Datenbankdatensätzen abzugleichen (z. B. E-Mail-Adresse, Empfänger-ID)
1. **Daten aktualisieren** - Update-Optionen auswählen:
   * Nur übereinstimmende Einträge aktualisieren
   * Vorhandene Felder aktualisieren oder nur leere Felder
   * Neue Einträge einfügen, wenn keine Übereinstimmung gefunden wurde

**Häufige Szenarien:**

* Aktualisieren von Profilattributen aus CRM-Exporten
* Abonnementstatus von externen Systemen aktualisieren
* Treuepunkte oder Kundenbewertungen synchronisieren
* Aktualisieren der Opt-in-/Opt-out-Voreinstellungen
* Profile mit Verhaltensdaten anreichern

**Best Practices:** Verwenden Sie eindeutige Kennungen für die Abstimmung, validieren Sie Daten vor der Aktualisierung, testen Sie sie mit kleinen Stichproben und planen Sie regelmäßige Aktualisierungen für die laufende Synchronisierung.

**Verwandte Themen:**

* [Handbuch zum Datenimport](../start/import.md)
* [Aktivität „Laden“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=de){target="_blank"}
* [Aktivität „Daten-Update“](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=de){target="_blank"}

+++

+++ Wie kann ich neue Empfänger identifizieren und ansprechen?

Verwenden Sie Workflows mit Abfrageaktivitäten, um kürzlich hinzugefügte Empfänger und Trigger-automatisierte Willkommenskampagnen zu identifizieren.

**Abfrageansatz:**

Erstellen Sie eine Abfragefilterung nach dem Feld **[!UICONTROL Erstellungsdatum]**, um die innerhalb eines bestimmten Zeitraums hinzugefügten Empfänger auszuwählen (z. B. letzte 24 Stunden, letzte Woche).

**Automatisierte Willkommens-Workflow-Struktur:**

1. **Planung** - Täglich oder in bestimmten Intervallen ausführen
1. **Abfrage** - Auswahl der seit der letzten Ausführung erstellten Empfänger
1. **Deduplizierung** (optional): Stellen Sie sicher, dass keine Duplikate vorhanden sind
1. **Versand** - Willkommensnachricht senden
1. **Daten aktualisieren** (optional) - Empfänger als „willkommen“ markieren

**Erweiterte Technik mit Aggregaten:**

Verwenden Sie Aggregatfunktionen, um die neuesten Ergänzungen dynamisch zu identifizieren und mit zuvor verarbeiteten Empfängern zu vergleichen, um eine ausgefeilte Erkennung neuer Empfänger zu ermöglichen.

**Verwandte Themen:**

* [Abfrageaktivität](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"}
* [Verwendung von Aggregaten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=de){target="_blank"}
* [Begrüßungsprogramme](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=de){target="_blank"}

+++

+++ Wie verwende ich Workflow-Aktivitäten?

Kampagnen-Workflows werden aus vier Hauptkategorien von Aktivitäten erstellt, die jeweils bestimmten Zwecken dienen:

**Targeting-Aktivitäten** - Definieren und Verfeinern Ihrer Audience

* Abfrage, Aufspaltung, Deduplizierung, Anreicherung, Schnittmenge, Vereinigung, Ausschluss
* Verwenden Sie diese zum Auswählen von Empfängern, Segmentpopulationen und Kombinieren von Datenquellen

**Steuerungsaktivitäten** - Workflow-Logik und -Timing verwalten

* Planung, Warten, Testen, Verzweigung, UND-Verknüpfung, ODER-Verknüpfung, Sprung
* Ausführungsfluss kontrollieren, Bedingungen hinzufügen und parallele Pfade verwalten

**Aktionsaktivitäten** - Ausführen von Vorgängen und Senden von Nachrichten

* Versand, Daten-Update, Laden (Datei), Datenextraktion (Datei), JavaScript-Code
* Ausführen von Datenbankvorgängen, Dateiübertragungen und Nachrichtenversand

**Ereignisaktivitäten** - Reaktion auf externe Trigger

* Externes Signal, Datei-Wächter, HTTP-Übertragung, SMS, E-Mail
* Eingehende Daten und externe Systeminteraktionen verarbeiten

Um Aktivitäten zu verwenden, ziehen Sie sie aus der Palette in die Arbeitsfläche des Workflows, doppelklicken Sie zum Konfigurieren von Parametern und verbinden Sie sie mit Transitionen.

**Verwandte Themen:**

* [Referenz zu Zielgruppenaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=de){target="_blank"}
* [Referenz zu Flusssteuerungs-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=de){target="_blank"}
* [Referenz zu Aktionsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=de){target="_blank"}
* [Referenz zu Ereignisaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=de){target="_blank"}

+++

+++ Was sind die Best Practices für Workflows?

Befolgen Sie diese Best Practices, um effiziente, verwaltbare und zuverlässige Workflows zu erstellen:

**Design und Organisation:**

* Verwenden klarer, beschreibender Namen für Workflows und Aktivitäten
* Hinzufügen von Beschriftungen und Beschreibungen zu Dokumentlogiken
* Gruppieren Sie verwandte Aktivitäten visuell, um die Lesbarkeit zu verbessern
* Aufteilen komplexer Prozesse in mehrere kleinere Workflows

**Leistungsoptimierung:**

* Begrenzung der Abfrageergebnisgrößen mit entsprechenden Filtern
* Verwenden temporärer Tabellen für die Zwischenspeicherung von Daten
* Planen ressourcenintensiver Workflows außerhalb der Spitzenzeiten
* Vermeiden Sie unnötige Schleifen und übermäßige Iterationen

**Fehlerbehandlung und -überwachung:**

* Hinzufügen von Fehlerbehandlungspfaden mit Supervisoren
* Konfigurieren von Warnhinweisen für fehlgeschlagene Workflows
* Testen mit kleinen Datenmustern vor der vollständigen Ausführung
* Überprüfen Sie die Ausführungsprotokolle regelmäßig auf Leistungsprobleme.

**Wartung und Governance:**

* Archivieren oder Löschen veralteter Workflows
* Workflow-Änderungen zur Versionskontrolle und Dokumentänderungen
* Workflow-Komplexität begrenzen (Ziel &lt; 20 Aktivitäten)
* Verwenden von Workflow-Vorlagen für wiederkehrende Muster

**Sicherheit und Daten-Management:**

* Anwenden der entsprechenden Benutzerberechtigungen
* Bereinigen temporärer Daten mit Workflow-Bereinigung
* Hartkodierungswerte vermeiden - Variablen und Optionen verwenden
* Regelmäßige Überprüfung und Optimierung schlecht funktionierender Workflows

**Verwandte Themen:**

* [Handbuch mit Best Practices für Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"}
* [Erstellen eines Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"}
* [Überwachen von Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

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


[Ändern der Sprache in der Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Erste Schritte mit der Campaign-Client-Konsole](connect.md)

+++

+++ Kann ich Campaign v8 mit anderen Adobe-Lösungen verwenden?

Ja. Campaign v8 lässt sich nahtlos in Adobe Experience Cloud-Lösungen integrieren, um ein leistungsstarkes, einheitliches Marketing-Ökosystem zu schaffen. Als Managed Cloud Service wurde v8 für die native Integration mit Unternehmensanwendungen von Adobe entwickelt.

**Wichtige Integrationen verfügbar:**

* **Adobe Experience Platform** - Nutzung einheitlicher Kundenprofile und Echtzeitdaten
* **Adobe Analytics** - Kampagnenleistung und Kundenverhalten kanalübergreifend messen
* **Adobe Target** - Personalisieren von Inhalten basierend auf Kundensegmenten und Kundenverhalten
* **Adobe Experience Manager** - Zentralisierung der Inhaltserstellung und Asset-Verwaltung
* **Adobe Audience Manager** - Zielgruppensegmente plattformübergreifend erstellen und aktivieren

**Vorteile:** Kundendaten, konsistente Benutzererlebnisse, optimierte Workflows und erweiterte Personalisierungsfunktionen.

**Setup:** Für die Integration mit Adobe-Lösungen ist die Adobe Identity Management System (IMS)-Authentifizierung erforderlich, die automatisch für Campaign v8 Managed Cloud Services konfiguriert wird.

[Adobe Campaign-Integrationen](../connect/integration.md) | [Verbinden mit Adobe ID](connect.md)

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

[Verfolgen und Überwachen von Sendungen](tracking.md) | [Konfigurieren getrackter Links](../send/email.md)

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

[Über die Zustellbarkeit in Campaign](../send/about-deliverability.md) | [Best Practice-Handbuch zur Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"}

+++

+++ Welche externen Datenbanken kann ich mit Campaign verknüpfen?

Campaign v8 unterstützt Federated Data Access (FDA)-Verbindungen zu wichtigen Unternehmensdatenbanksystemen, sodass Sie die vorhandene Dateninfrastruktur nutzen können.

**Unterstützte Datenbanken:**

* **Cloud-Datenbanken:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **Unternehmensdatenbanken:** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **Data Warehouses:** Teradata, Vertica, SAP HANA
* **Big Data:** Hadoop über Hive

**Plattformspezifische Überlegungen:** Unterstützte Datenbankversionen und Verbindungsanforderungen variieren. Campaign v8 als Managed Cloud Service kann bestimmte Netzwerk- und Sicherheitsanforderungen für den Zugriff auf externe Datenbanken aufweisen.

**Wichtig:** Überprüfen Sie immer die offizielle Kompatibilitätsmatrix für Ihre Campaign v8-Version, um die Unterstützung für bestimmte Datenbankversionen zu bestätigen und sicherzustellen, dass externe Datenbank-Connectoren ordnungsgemäß lizenziert werden.

[Kompatibilitätsmatrix](compatibility-matrix.md) | [Konfigurieren von FDA-Verbindungen](../connect/fda.md)

+++

+++ Kann Adobe Campaign in CRM-Systeme integriert werden?

Ja. Campaign bietet native CRM-Connectoren für eine nahtlose bidirektionale Synchronisation zwischen Campaign und Ihrem CRM-System, wodurch plattformübergreifend konsistente Kundendaten sichergestellt werden.

**Unterstützte CRM-Systeme:**

* **Salesforce** - Leads, Kontakte, Konten, Chancen, Kampagnen
* **Microsoft Dynamics 365** - Kontakte, Konten, Leads, benutzerdefinierte Entitäten
* Andere CRMs über benutzerdefinierte API-Integrationen

**Was synchronisiert:**

* **Vom CRM bis zur Kampagne:** Kontaktaufzeichnungen, Kontoinformationen, Leads, benutzerdefinierte Felder, Segmentierungsdaten
* **Von Campaign zum CRM:** Versandlogs, Tracking-Daten, Interaktionsmetriken, Kampagnenantworten, Abonnementstatus

**Synchronisationsmodi:**

* **Geplant** - Automatische Synchronisierung in definierten Intervallen (stündlich, täglich)
* **Manuell** - On-Demand-Synchronisation durch Benutzer ausgelöst
* **Echtzeit** - Über API für sofortige Aktualisierungen (benutzerdefinierte Entwicklung)

**Konfiguration:** Verwenden Sie den integrierten CRM-Connector-Assistenten von Campaign, um CRM-Felder Campaign-Attributen zuzuordnen, Tabellen zur Synchronisierung auszuwählen und die Synchronisierung zu planen. Der Connector verarbeitet die Konfliktauflösung und wahrt die Datenkonsistenz.

**Best Practice:** Starten Sie mit der schreibgeschützten Synchronisierung, um die Zuordnung zu testen, und aktivieren Sie dann die bidirektionale Synchronisierung. Überwachen Sie Synchronisierungsprotokolle auf Fehler und sorgen Sie in beiden Systemen für saubere Daten.

[CRM-Connector-Konfiguration](../connect/crm.md) | [Workflow-CRM-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

+++

+++ Wie lösche ich den Cache der Client-Konsole?

Durch Löschen des Caches der Client-Konsole werden viele gängige Anzeige- und Funktionsprobleme behoben. Der Cache speichert lokale Konfigurationsdateien, die gelegentlich beschädigt oder veraltet sein können.

**Wann der Cache gelöscht werden soll:**

* Neue Branding-Elemente (Logos, Farben) werden nicht korrekt angezeigt
* Export-/Importfunktionen schlagen unerwartet fehl
* Elemente der Benutzeroberfläche werden nach Konfigurationsänderungen nicht aktualisiert
* Leistungsprobleme oder langsame Konsolenreaktion
* Nach der Aktualisierung auf eine neue Version der Client-Konsole

**Schritte zum Löschen des Cache:**

1. Öffnen der Campaign-Client-Konsole
2. Zum Menü **[!UICONTROL Datei]** wechseln
3. Wählen **[!UICONTROL Löschen des lokalen Cache…]**
4. Bestätigen der Aktion bei Aufforderung
5. Starten Sie die Client-Konsole neu



[Installieren und Konfigurieren der Client-Konsole](connect.md)

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
* **Benutzergruppe** - Von allen Gruppenmitgliedern übernommene Einstellungen


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


[Datenmodell erweitern](../dev/extend-schema.md) | [Schemastruktur](../dev/schemas.md) | [Best Practices für Datenmodelle](../dev/datamodel-best-practices.md)

+++

## Reporting {#reporting}

Erhalten Sie Einblicke in die Reporting-Funktionen von Campaign, einschließlich integrierter Berichte, benutzerdefinierter Berichte und Datenanalysetools wie Cubes.

+++ Wie kann ich neue Berichte erstellen?

Abgesehen von den integrierten Berichten können Sie in Adobe Campaign auch benutzerdefinierte Berichte entsprechend dem jeweiligen Kontext und Ihren Anforderungen erstellen.

Adobe Campaign ist keine auf Berichterstellung spezialisierte Anwendung: Die hier erstellten Berichte dienen hauptsächlich der Visualisierung aggregierter Daten.

[Weitere Informationen](../reporting/gs-reporting.md) über die Reporting-Funktionen von Campaign.

+++

+++ Wie kann ich Statistikberichte zu Populationen erstellen und teilen?

Adobe Campaign [Deskriptive Analyseberichte](../reporting/built-in-reports.md) ermöglichen es Ihnen, Statistikberichte zu Ihren Populationen zu erstellen und freizugeben.

[Weitere Informationen](../reporting/built-in-reports.md).

+++

+++ Wie kann ich erweiterte Berichte zu meinen Daten erstellen?

In Campaign v8 können Sie [erweiterte Berichte erstellen](../reporting/custom-reports.md). Als erfahrener Benutzer können Sie benutzerdefinierte Berichte zu Ihren Daten erstellen, aktualisieren und verteilen.

Sie können auch die Web-Benutzeroberfläche von Campaign verwenden, um Berichte und Dashboards zu erstellen. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}.

+++

+++ Was ist ein Cube und wie kann ich einen solchen Bericht erstellen?

Dies ermöglicht es, die Kapazitäten zur Datenexploration und -analyse optimal zu nutzen. Gleichzeitig wird die Konfiguration der Berichte und Tabellen für den Endbenutzer vereinfacht: Es muss nur ein existierender, vollständig konfigurierter Cube bei der Bericht- oder Tabellenerstellung ausgewählt werden, um dessen Berechnungen, Kennzahlen und Statistiken zu übernehmen.

Nach ihrer Erstellung und Konfiguration werden die Cubes in den Abfrage-Aktivitäten der Berichte und Webanwendungen genutzt. Sie können außerdem in Pivot-Tabellen verwendet und verändert werden.

Erfahren Sie, wie Sie Ihre Daten [mit Cubes analysieren](../reporting/gs-cubes.md) können.

+++

+++ Kann ich einen Bericht aus Antworten auf eine Online-Umfrage erstellen?

Campaign v8 verfügt über keine integrierte Umfragefunktion. Sie können Adobe Experience Manager oder andere Web-Lösungen zum Erstellen von Umfragen verwenden.

Sie können jedoch Reporting-Funktionen verwenden, um alle erfassten Daten zu analysieren und benutzerdefinierte Berichte zu erstellen.

+++

+++ Wie kann ich den Zugriff auf meinen Bericht in der Campaign-Oberfläche freigeben?

Sie können festlegen, in welchem Kontext Ihr Bericht in der Benutzeroberfläche von Adobe Campaign angezeigt werden soll. Weiterführende Informationen zum Zugriff auf Berichte finden Sie in [diesem Abschnitt](../reporting/custom-reports.md).

+++

+++ Kann ich Berichte in verschiedenen Formaten exportieren?

Ja, Sie können Campaign-Berichte in verschiedene Formate wie Excel, PDF oder CSV exportieren. [Weitere Informationen](../reporting/custom-reports.md).

+++

## Entwickler {#developers}

Zugreifen auf technische Informationen für Entwickler, einschließlich Datenmodelldetails, Schemata, APIs und Anpassungsfunktionen.

+++ Was ist das Campaign-Datenmodell?

Das konzeptionelle Datenmodell der Adobe Campaign-Datenbank besteht aus einer Reihe integrierter Tabellen und deren Interaktion. Die physische und logische Struktur der in der Anwendung übertragenen Daten wird in XML beschrieben. Sie folgt einer Adobe Campaign-spezifischen Grammatik namens Schema.

[Erfahren Sie mehr zum Campaign-Datenmodell](../dev/datamodel.md).

[Auf dieser Seite finden Sie Best Practices](../dev/datamodel-best-practices.md).

+++

+++ Wie funktionieren Schemata in Campaign?

In Adobe Campaign werden Datenschemata folgendermaßen genutzt:

* Definieren der Verknüpfung zwischen den Datenobjekten in der Anwendung mit den zugrunde liegenden Datenbanktabellen
* Definieren von Beziehungen zwischen den unterschiedlichen Datenobjekten in der Campaign-Anwendung
* Definieren und Beschreiben der einzelnen Felder eines jeden Objekts

[Erste Schritte mit Tabellen und Schemata](../dev/schemas.md) um zu verstehen, wie Sie mit Datenschemata arbeiten, Campaign erweitern und an Ihre Anforderungen anpassen können.

+++

+++ Wie wird eine benutzerdefinierte Empfängertabelle verwendet?

Sie können eine benutzerdefinierte Empfängertabelle in Campaign erstellen und implementieren, um Nachrichten zu senden.

[Weitere Informationen](../dev/custom-recipient.md)

+++

+++ Was sind die Best Practices zum Definieren von Abfragen in Campaign?

Der Abfrage-Editor von Adobe Campaign ermöglicht das leistungsstarke Analysieren von Daten und Erstellen von Segmenten.

Die Adobe Campaign-Plattform bietet ein leistungsstarkes Abfragetool, das bei der Erfüllung verschiedener Funktionen wie Zielpopulationsbestimmung, Segmentation des Kundenstamms, Extraktion und Filterung von Trackinglogs sowie Erstellung von Filtern zur Anwendung kommt.

Sie können mit diesem generischen Abfrage-Editor Daten aus der Campaign-Datenbank abrufen. Der Zugriff darauf erfolgt über das Menü **Werkzeuge > Generischer Abfrage-Editor...** Sie können damit in einer Datenbank gespeicherte Informationen extrahieren sowie organisieren, gruppieren, sortieren usw. So kann ein Benutzer beispielsweise die Empfängerinnen und Empfänger abrufen, die innerhalb eines bestimmten Zeitraums mehr als x-mal auf einen Link in einem Newsletter geklickt haben. Mit diesem Tool können Sie Ergebnisse nach Bedarf sammeln, sortieren und anzeigen.

[Weitere Informationen](../start/query-editor.md). Weitere Informationen finden Sie im [Handbuch zur Kampagnenautomatisierung](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"}.

+++

+++ Wie kann ich Daten-Packages importieren?

Adobe Campaign ermöglicht über ein Package-System den Export oder Import von Plattformkonfigurationen und Daten. Mithilfe von Datenpackages können Entitäten in der Adobe Campaign-Datenbank als Dateien im XML-Format dargestellt werden. Dies umfasst alle Daten einer in einem Package enthaltenen Entität.

Das Prinzip der Datenpackages besteht darin, eine Datenkonfiguration zu exportieren und in ein anderes Adobe Campaign-System zu integrieren.

[Weitere Informationen](../dev/packages.md) wie Sie mit Datenpaketen arbeiten, um Campaign-Konfigurationen zu importieren und zu exportieren.

+++

+++ Wo finde ich die Liste der Campaign v8-APIs?

Alle Campaign-APIs inklusive vollständiger Beschreibung finden Sie in dieser speziellen [Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=de){target="_blank"}.

+++

+++ Was ist die Campaign REST-API?

Campaign v8 stellt eine Reihe von REST-APIs bereit, mit denen Sie Integrationen für Adobe Campaign erstellen und Ihr eigenes Ökosystem aufbauen können, indem Sie Adobe Campaign mit dem von Ihnen verwendeten Technologiebereich verbinden.

[Weitere Informationen](../dev/api/get-started-apis.md).

+++

+++ Wie kann ich Workflows über die API überwachen?

Erfahren Sie auf dieser [&#x200B; Seite , wie Sie Workflows mithilfe von Campaign-APIs &#x200B;](../dev/api/controlling-a-workflow.md).

+++

+++ Wie kann ich die Datenbankstruktur aktualisieren?

Wenn Sie Campaign-Datenschemata ändern, müssen Sie die Datenbankstruktur aktualisieren. Weitere Informationen dazu finden Sie in [diesem Abschnitt](../dev/update-database-structure.md).

+++

+++ Welche Einschränkungen gibt es in Campaign v8?

Campaign v8 weist einige Einschränkungen im Vergleich zu Campaign Classic v7 auf, die auf [&#x200B; Seite beschrieben &#x200B;](../start/v7-to-v8.md#limitations).

+++

## Datenschutz {#privacy}

Erfahren Sie, wie Sie mit Adobe Campaign Datenschutzbestimmungen wie die DSGVO und den CCPA einhalten und Anfragen von betroffenen Personen verwalten können.

+++ Was sind die Schlüsselbegriffe zum Datenschutz?

Die unten aufgelisteten Elemente verlinken zu den wichtigsten Begriffen und Konzepten im Zusammenhang mit Datenschutz und Einverständniserklärung in Adobe Campaign:

* [Verordnungen zur Datenschutzverwaltung](../start/privacy.md#privacy-regulations)
* [Personenbezogene Daten und Personas](../start/privacy.md#personal-data)
* [Recht auf Zugriff und Recht auf Vergessenwerden](../start/privacy.md#right-access-forgotten)
* [Einverständnis, Datenbeibehaltung und Benutzerrollen](../start/privacy.md#consent-retention-roles)

+++

+++ Was empfiehlt Adobe Campaign, um die neuesten Datenschutzverordnungen einzuhalten?

Adobe bietet keine Rechtsberatung. Sie sollten mit Ihrer eigenen Rechtsabteilung zusammenarbeiten, um sicherzustellen, dass alle notwendigen Schritte für DSGVO, CCPA, PDPA, LGPD oder andere relevante Vorschriften unternommen werden.

**Vorbereitung auf Datenzugriffs- und Datenlöschanfragen**

* Legen Sie ein Verfahren für den Empfang/die Beantwortung von Anfragen durch betroffene Personen fest und ernennen Sie einen Datenschutzbeauftragten.

* Überprüfen Sie die in Adobe Campaign gespeicherten Kundendaten und vergeben Sie eindeutige Kennungen (wahrscheinlich ist mehr als eine nötig).

* Bestimmen Sie eine Richtlinie und einen Prozess zur Validierung bzw. zur Authentifizierung, um die Identität von betroffenen Personen zu bestätigen.

* Achten Sie darauf, dass die Antwort an betroffene Personen einfach verständlich ist.

**Überarbeitung des Einverständnisprozesses**

* Nennen und aktualisieren Sie alle für die DSGVO relevanten Kontaktpunkte der Datenerfassung (z. B. Sprache, Verfahren zur Erteilung des Einverständnisses und Einverständnisprotokolle).

* Achten Sie darauf, dass alle Marketing-E-Mails Abmelde-Links enthalten.

* Überdenken Sie die globale Strategie für das E-Mail-Marketing, um landesspezifische Implementierungen festzulegen.

**Analyse der Daten**

* Überprüfen Sie alle Quellen für den Datenimport und die Datenerfassung, aus denen Daten in Adobe Campaign übertragen werden, und dokumentieren Sie, welche Felder für Ihre Marketing-Zwecke verwendet werden.

* Entfernen Sie nicht genutzte Datenattribute aus der Adobe Campaign-Datenbank.

* Verwenden Sie die in Adobe Campaign verfügbaren Daten zu dem Zweck, zu dem sie erfasst wurden, und bieten Sie Ihren Kunden stärker personalisierte Erlebnisse.

* Überarbeiten und aktualisieren Sie Datenzugriffsgenehmigungen, um sicherzustellen, dass Benutzer von Adobe Campaign nur die für ihre Kampagnen benötigten Daten verwenden, aber darüber hinaus auf keine weiteren Daten zugreifen können.

* Achten Sie darauf, dass jeder Benutzer von Adobe Campaign die entsprechenden Zugriffsberechtigungen für die Durchführung seiner Aufgaben hat, aber keine darüber hinausreichenden Rechte.

+++

+++ Wie können Datenverantwortliche das Einverständnis ihrer Kunden erlangen, ohne die Benutzerinteraktion zu beeinträchtigen?

In den Fällen, in denen das Einverständnis für bestimmte Marketing-Aktivitäten erforderlich ist, muss eine aktive Einverständniserklärung vom Verbraucher gegeben werden (d. h. kein Schweigen als Einverständnis oder vorab markierte Kontrollkästchen). Diese Einverständniserklärung muss außerdem ungebündelt erfolgen und darf nicht davon abhängig gemacht werden, dass Dienstleistungen angeboten werden.

Es kann sogar Fälle geben, in denen bestimmte Einverständniserklärungen aktualisiert werden müssen, damit die Daten in Zukunft weiterverwendet werden können.

Marketer sollten diese erweiterten Einverständnisanforderungen als echten Indikator für Markeninteraktion und -treue sowie für Kundenzufriedenheit und -vertrauen nutzen.

+++

+++ Wie können Datenverantwortliche das Einverständnis in Adobe Campaign verwalten?

Adobe Campaign bietet bereits Funktionen zur Einverständnisverwaltung auf mehr Ebenen, als die meisten Marketing-Experten nutzen: über benutzerdefinierte Datenfelder oder über einen oder mehrere Dienste.

Marketing-Experten sollten sich von ihrer Rechtsabteilung beraten lassen und dann die bereits in Adobe Campaign integrierten Funktionen nutzen.

So kann zum Beispiel das Datenmodell in Adobe Campaign erweitert werden, um nicht nur zu verfolgen, ob sich Personen für ein Einverständnis entschieden haben, sondern auch um den Zeitstempel des Einverständnisses und eine Art Indikator zu tracken, der den genauen Umfang des Einverständnisses erfasst.

+++

+++ Welche Daten können von Datenverantwortlichen in Adobe Campaign gelöscht werden, wenn sie eine Kundenanfrage einer betroffenen Person erhalten?

Alle mit der betroffenen Person verknüpften Daten werden gelöscht, einschließlich vordefinierter und benutzerdefinierter Tabellen.

Technisch gesehen werden alle Daten gelöscht, die mit der betroffenen Person mit `integrity="own"` verknüpft sind.

Als Datenverantwortlicher haben Sie die Möglichkeit, diese Einstellung anzupassen, indem Sie die Integrität der in den Datenschemata definierten Links ändern (z. B. wenn Sie einen geschäftlichen Grund haben, bestimmte Daten nicht zu löschen).

+++

+++ Wie wirkt sich die Löschung von Versand- und Trackinglogs auf Berichte aus?

Berichte in Adobe Campaign basieren auf Indikatoren, die von aggregierten Daten aus Versand- und Trackinglogs berechnet werden. Deshalb sollte das Entfernen von einzelnen Logs keine Auswirkungen auf die in den Berichten dargestellten Metriken haben.

+++

+++ Muss ich darauf achten, dass Daten zu einem späteren Zeitpunkt möglicherweise erneut importiert werden?

In Adobe Campaign werden Datensätze häufig aus einer externen Datenquelle hochgeladen.

Als Datenverantwortlicher müssen Sie sicherstellen, dass beim Erhalt einer Löschanfrage alle entsprechenden Daten der betroffenen Person aus allen Ihren Systemen gelöscht werden.

+++

+++ Kann sich eine betroffene Person, deren Daten aus Adobe Campaign gelöscht wurden, zu einem späteren Zeitpunkt wieder für ein Opt-in entscheiden?

Eine betroffene Person kann sich zu einem späteren Zeitpunkt wieder anmelden oder als neuer Empfänger hinzugefügt werden, nachdem ihre Daten aus Adobe Campaign gelöscht wurden.

Sie können das Audit-Protokoll verwenden, in dem angegeben wird, wann die vorherige Löschung durchgeführt und der neue Empfänger angelegt wurde.

+++

## Brauchen Sie noch Hilfe? {#get-help}

Du findest nicht, was du suchst? Im Folgenden finden Sie zusätzliche Ressourcen, die Ihnen bei der erfolgreichen Verwendung von Adobe Campaign v8 helfen.

### Unterstützung durch die Gemeinschaft

Tauschen Sie sich mit anderen Campaign-Benutzern und Adobe-Experten aus, um Informationen auszutauschen und Antworten zu erhalten.

* **[Adobe Campaign-Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=de){target="_blank"}** - Stellen Sie Fragen, teilen Sie Lösungen mit anderen und treten Sie in die Campaign-Community ein
* **[Experience League-](https://experienceleaguecommunities.adobe.com/){target="_blank"}**: Durchsuchen Sie Diskussionen über alle Adobe-Produkte hinweg.
* **[Campaign Community Office Hours](https://experienceleague.adobe.com/){target="_blank"}** - Nehmen Sie an Live-Sessions mit Adobe-Experten teil.

### Dokumentation und Lernen

Zugriff auf umfassende Handbücher, Tutorials und Schulungsmaterialien.

* **[Dokumentation zu Campaign v8 -](../campaign-home.md)** Produktdokumentation
* **[Campaign-Tutorials](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=de){target="_blank"}** - Schrittweise Videoanleitungen und praktische Tutorials
* **[Neue Funktionen](whats-new.md)** - Neueste Funktionen
* **[Versionshinweise](release-notes.md)** - Aktuelle und vorherige Versionsinformationen
* **[Best Practices](delivery-best-practices.md)** - Empfohlene Ansätze für häufige Aufgaben

### Technische Ressourcen

Hier finden Sie ausführliche technische Dokumentationen und Entwicklerressourcen.

* **[Campaign-](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=de){target="_blank"}**: Vollständige API-Referenzdokumentation
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** - Zur Dokumentation beitragen
* **[Technische Hinweise](https://experienceleague.adobe.com/de/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - Detaillierte technische Artikel
* **[Kompatibilitätsmatrix](compatibility-matrix.md)** - Unterstützte Systeme und Versionen

### Support und Services

Erhalten Sie Hilfe vom Support-Team von Adobe und verwalten Sie Ihre Instanz.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Support-Fälle protokollieren und Benutzer verwalten
* **[Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Kontaktieren Sie das Support-Team
* **[Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de){target="_blank"}** - Einstellungen der Campaign-Instanz verwalten
* **[Systemstatus](https://status.adobe.com/){target="_blank"}** - Überprüfen des Adobe Services-Status

### Schulung und Zertifizierung

Erweitern Sie Ihre Kenntnisse mit offiziellen Adobe-Schulungs- und Zertifizierungsprogrammen.

* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Offizielle, von Kursleitern geführte Kurse und Kurse zum Selbststudium
* **[Adobe Campaign-Zertifizierung](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Validieren Sie Ihr Fachwissen mit einer professionellen Zertifizierung.
* **[Experience League-Lernpfade](https://experienceleague.adobe.com/?lang=de#dashboard/learning){target="_blank"}** - Geführte Journey

### Weitere hilfreiche Ressourcen

* **[Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=de){target="_blank"}** - Referenz für Benutzer von Classic v7
* **[Dokumentation zur Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Handbuch für die neue Web-Benutzeroberfläche
* **[Best Practices für die Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de){target="_blank"}** - Optimieren des E-Mail-Versands
* **[Produktaktualisierungen](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** - Neueste Adobe Experience Cloud-Updates

**Zuletzt aktualisiert:** November 2025 | **Gilt für:** Campaign v8.6 und höher

*Fehler gefunden oder Verbesserungsvorschläge gemacht? [Bearbeiten Sie diese Seite auf GitHub](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*


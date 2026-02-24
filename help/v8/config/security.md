---
title: Best Practices für die Campaign-Sicherheit
description: Empfohlene Anleitungen zur sicheren Konfiguration für Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: 04dff810f5a838b2468280519948c88e29acf221
workflow-type: tm+mt
source-wordcount: '2875'
ht-degree: 67%

---

# Best Practices für die Campaign-Sicherheit {#ac-security}

Bei Adobe hat die Sicherheit Ihres digitalen Erlebnisses höchste Priorität. Sicherheitsmaßnahmen sind tief in unsere internen Prozesse und Tools rund um die Entwicklung und den Betrieb von Software implementiert und werden von unseren Teams über alle Funktionsbereiche hinweg strikt befolgt, um Sicherheitsvorfällen vorzubeugen bzw. diese schnellstmöglich zu erkennen und zu beheben.

Darüber hinaus arbeiten wir mit unseren Partnern sowie mit führenden Sicherheitsanalysten, Sicherheitsforschungseinrichtungen und anderen Branchenverbänden zusammen und gewährleisten so, mit den neuesten Bedrohungen und Schwachstellen Schritt halten zu können und regelmäßig fortschrittliche Sicherheitsverfahren in unsere Angebote und Services zu integrieren.

>[!NOTE]
>
>**Campaign v8 Managed Cloud Services:** Die Infrastruktur (Netzwerk, Server, TLS, Patching) wird von Adobe verwaltet. Diese Seite konzentriert sich auf die Konfiguration auf Mandanten- und Anwendungsebene, die Sie steuern: Zugriffsverwaltung, Authentifizierung, Instanzeneinstellungen, Datenschutz, Codierung und betriebliche Verfahren.


## Sicherheitscheckliste {#security-checklist}

Verwenden Sie diese Checkliste, um Ihre Konfiguration an den empfohlenen sicheren Standardwerten auszurichten:

* [Zugriffsverwaltung](#access-management): Sicherheitsgruppen erstellen, entsprechende Rechte zuweisen, Admin-Verwendung einschränken, einen Benutzer pro Benutzer verwenden, regelmäßig überprüfen
* [Authentifizierung und Sitzung](#authentication-and-session): Verwenden von Adobe IMS, starke Identitätsrichtlinie, Sitzungs-Timeout
* [Instanz- und Netzwerksicherheit](#instance-and-network-security): IP-Zulassungsliste, URL-Berechtigungen, GPG-Schlüssel über das Control Panel
* [Daten- und PII-](#data-and-pii-protection): HTTPS, Einschränkung der PII-Ansicht, Einschränkung von Passwörtern, Schutz sensibler Seiten
* [Kodierungsrichtlinien](#coding-guidelines): Keine hartcodierten Geheimnisse, Eingabe validieren, parametrisierte SQL, Captchas
* [Datenbeschränkung](#data-restriction): Beschränken des Zugriffs auf Passwort- und Geheimnisfelder in externen Konten
* [Betrieb und Compliance](#operational-and-compliance): Mit dieser Grundlinie regelmäßig vergleichen und Audit-Protokoll verwenden

### Wo Sie diese Anleitung finden {#public-guidance}

Adobe Campaign bietet derzeit keine empfohlenen sicheren Konfigurationsanleitungen in einem maschinenlesbaren Format. In der folgenden Dokumentation können Sie Ihre aktuellen Einstellungen mit den empfohlenen sicheren Standardeinstellungen vergleichen:

* **Diese Seite** - [Best Practices für die Campaign-Sicherheit](#ac-security) (Checkliste und detaillierte Abschnitte)
* **[Kampagneneinstellungen (FAQ)](../start/campaign-faq-comprehensive.md#settings)** - Einstellungen mit empfohlenen sicheren Standardeinstellungen vergleichen
* **[Erweitertes Sicherheits-Add-on](enhanced-security.md)** - Sichere CMK-Integration und sicheres VPN-Tunneln
* **[Erste Schritte mit Berechtigungen](../start/gs-permissions.md)** - Zugriff und Produktprofile
* **[Anzeige von personenbezogenen Daten einschränken](../dev/restrict-pi-view.md)** - Einschränken des Zugriffs auf sensible Felder
* **[Implementierungsrichtlinien](../start/implement.md)** - Sicherheit und Datenschutz vor dem Start

## Datenschutz

Um den Datenschutz korrekt zu handhaben und personenbezogene Daten korrekt zu verwalten, müssen Sie die für die Region(en) geltenden Gesetze einhalten, in denen Sie tätig sind. Die Funktionen von Adobe Campaign unterstützen Sie bei der Einhaltung der auf [dieser Seite](../start/privacy.md) aufgeführten Vorschriften.

### Adobe Experience Cloud – Datenschutz {#experience-cloud-privacy}

Adobe Campaign ist Teil der Adobe Experience Cloud-Lösungen. Die Art und Weise, wie der Datenschutz in Campaign gehandhabt wird, entspricht den allgemeinen Grundsätzen von Experience Cloud, z. B.:

* **Welche Informationen werden bei Verwendung von Adobe Experience Cloud erfasst?**

  Als Unternehmen, das Adobe Experience Cloud-Lösungen nutzt, entscheiden Sie selbst, welche Informationen erfasst und an Ihr Adobe Experience Cloud-Konto gesendet werden sollen. Beispiele für die Arten von Informationen, die erfasst werden können, sind Webbrowsing-Aktivitäten, IP-Adressen, Standortinformationen von Mobilgeräten, Erfolgsquoten von Kampagnen, gekaufte oder in den Warenkorb gelegte Artikel usw.

  >[!NOTE]
  >
  >Wie bei allen Produkten von Adobe erfasst Campaign Informationen über App- und Website-Benutzer. Weitere Informationen finden Sie in der [Datenschutzerklärung von Adobe](https://www.adobe.com/de/privacy/policy.html).

* **Verwendung von Adobe Experience Cloud zur Erfassung von Informationen**

   * Adobe Experience Cloud-Lösungen verwenden Cookies und ähnliche Technologien, wie Webbeacons (auch als Tags oder Pixel bezeichnet), um die Erfassung von Informationen zu ermöglichen. Weitere Informationen zu Cookies und Tracking-Funktionen mit Adobe Campaign finden Sie in [diesem Abschnitt](#tracking-capabilities).
   * Sie können Adobe Experience Cloud-Technologien auch in Ihren mobilen Apps verwenden. Weitere Informationen zu mobilen Sendungen mit Campaign finden Sie unter [SMS-Kanal](../send/sms/sms-channel.md) und „Mobile-App-Kanal“.

* **Datenschutzoptionen Ihrer Benutzer bezüglich Ihrer Verwendung von Adobe Experience Cloud**

  Adobe fordert Sie auf, Ihren Kunden Datenschutzrichtlinien bereitzustellen, in denen Folgendes beschrieben wird:

   * Ihre Datenschutzpraktiken in Verbindung mit Adobe Experience Cloud
   * Die Art und Weise, auf die Benutzer ihre Voreinstellungen für die Erfassung oder Verwendung ihrer Informationen in Verbindung mit Adobe Experience Cloud festlegen können

Weitere Informationen zum Datenschutz in Adobe Experience Cloud finden Sie auf [dieser Seite](https://www.adobe.com/de/privacy/marketing-cloud.html).

## Personenbezogene Daten und Personas {#personal-data}

Bei der Verwaltung des Datenschutzes ist es wichtig zu definieren, welche Daten von wem mit Sorgfalt behandelt werden sollen.
* **Personenbezogene Daten** sind Informationen, die eine lebende Person direkt oder indirekt identifizieren können.
* **Vertrauliche personenbezogene Daten** sind Informationen zu Rasse, politischen Ansichten, religiösen Überzeugungen, kriminellem Hintergrund, genetischen Informationen, Gesundheitsdaten, sexuellen Vorlieben, biometrischen Informationen sowie zur Gewerkschaftsmitgliedschaft.

Bei der Integration von Campaign mit anderen Experience Cloud-Lösungen, bei denen Zielgruppen von einem System auf ein anderes übertragen werden können, wie z. B. [Adobe Analytics](../connect/ac-aa.md), [Experience Cloud Audiences](../start/shared-audiences.md), Campaign Standard, oder mit anderen Lösungen durch [CRM-Connectoren](../../automation/workflow/crm-connector.md) müssen Sie dem Schutz personenbezogener Daten besondere Aufmerksamkeit widmen.

Die [wichtigsten Rechtsvorschriften](#privacy-regulations) beziehen sich auf die verschiedenen Einheiten, die Daten wie folgt verwalten:

* Ein **Datenverantwortlicher** ist die Autorität, die die Mittel und den Zweck der Erfassung, Verwendung und Weitergabe personenbezogener Daten festlegt.

* Ein **Auftragsverarbeiter** ist eine natürliche oder juristische Person, die personenbezogene Daten gemäß den Anweisungen des Datenverantwortlichen erfasst, verwendet oder weitergibt.

* Eine **betroffene Person** ist eine lebende Person, deren personenbezogene Daten erfasst, verwendet oder weitergegeben werden und die direkt oder indirekt anhand dieser personenbezogenen Daten identifiziert werden kann.

Als Unternehmen, das personenbezogene Daten erfasst und weitergibt, sind Sie daher der Datenverantwortliche, Ihre Kunden sind die betroffenen Personen und Adobe Campaign fungiert als Auftragsverarbeiter, wenn wir deren personenbezogene Daten gemäß Ihren Anweisungen verarbeiten. Beachten Sie, dass es in Ihrer Verantwortung als Datenverantwortlicher liegt, die Beziehung zu den betroffenen Personen zu verwalten, z. B. bei der Verwaltung von [Datenschutzanfragen](#privacy-requests).

### Anwendungsszenario {#use-case-scenario}

Um zu veranschaulichen, wie die verschiedenen Personas interagieren, finden Sie hier ein Beispiel für ein DSGVO-Kundenerlebnis auf hoher Ebene.

In diesem Beispiel ist eine Fluggesellschaft der Kunde von Adobe Campaign. Diese Firma ist der **Datenverantwortliche** und alle Kunden der Fluggesellschaft sind **betroffene Personen**. Laura ist in diesem speziellen Fall eine Kundin der Fluggesellschaft.

Die Personas in unserem Beispiel haben folgende Rollen:

* **Laura** ist die **betroffene Person**. Sie ist die Empfängerin, die Nachrichten von der Fluggesellschaft erhält. Laura mag eine Vielfliegerin sein, kann aber irgendwann entscheiden, dass sie keine personalisierten Werbe- oder Marketing-Nachrichten mehr von der Fluggesellschaft wünscht. Sie wird die Fluggesellschaft (anhand des entsprechenden Vorgangs) bitten, ihre Vielfliegernummer zu löschen.

* **Anne** ist die **Datenverantwortliche** der Fluggesellschaft. Sie erhält Lauras Anfrage, ruft die erforderlichen Kennungen ab, um die betroffene Person zu identifizieren, und leitet die Anfrage in Adobe Campaign weiter.

* **Adobe Campaign** ist der **Auftragsverarbeiter**.

![](assets/privacy-gdpr-flow.png)

Dies ist das übliche Verfahren für ein derartiges Szenario:

1. Die **betroffene Person** (Laura) übermittelt per E-Mail, über die Kundenunterstützung oder über ein Web-Portal eine DSGVO-Anfrage an die **Datenverantwortliche**.

1. Die **Datenverantwortliche** (Anne) sendet die DSGVO-Anfrage über die Benutzerschnittstelle oder eine API an Campaign.

1. Nachdem der **Auftragsverarbeiter** (Adobe Campaign) die Informationen erhalten hat, wird er in Bezug auf die DSGVO-Anfrage aktiv und sendet eine Antwort oder eine Bestätigung an die **Datenverantwortliche** (Anne).

1. Die **Datenverantwortliche** (Anne) prüft die Informationen und sendet sie an die **betroffene Person** (Laura).

## Datenakquise {#data-acquisition}

Mit Adobe Campaign können Sie Daten, einschließlich personenbezogener und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und überwachen.

* Fordern Sie die Empfänger immer auf, dem Empfang von Nachrichten zuzustimmen. Dazu müssen Sie Opt-out-Anfragen so schnell wie möglich erfüllen und das Einverständnis durch einen Anmeldeprozess mit zweifacher Bestätigung überprüfen. Weitere Informationen hierzu finden Sie unter [Abonnement-Formular mit zweifacher Bestätigung erstellen](https://experienceleague.adobe.com/de/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}.
* Importieren Sie keine betrügerischen Listen und verwenden Sie Testadressen, um sicherzustellen, dass Ihre Client-Datei nicht betrügerisch verwendet wird. Weiterführende Informationen dazu finden Sie im Abschnitt [Über Testadressen](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}.
* Mithilfe von Einverständnisverwaltung und Berechtigungs-Management können Sie die Voreinstellungen Ihrer Empfänger verfolgen und festlegen, wer in Ihrem Unternehmen auf welche Daten zugreifen kann. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#consent).
* Erleichtern und verwalten Sie Datenschutzanfragen von Ihren Empfängern. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#privacy-requests).

## Datenschutzverwaltung {#privacy-management}

Die Datenschutzverwaltung bezieht sich auf alle Prozesse und Tools, die Ihnen helfen, die Datenschutzbestimmungen (DSGVO, CCPA usw.) einzuhalten.

Adobe Campaign bietet Ihnen verschiedene Funktionen zur Datenschutzverwaltung:
* Einverständnisverwaltung, Datenbeibehaltung und Benutzerrollen. Siehe [diesen Abschnitt](#consent).
* Datenschutzanfragen (Recht auf Zugriff und Recht auf Vergessenwerden). Siehe [diesen Abschnitt](#privacy-requests).
* Abmeldung (Opt-out) vom Verkauf personenbezogener Daten (CCPA-spezifisch).

Die wichtigsten Datenschutzfunktionen in Campaign und ein Beispiel der beteiligten Personas werden in [diesem Abschnitt](https://helpx.adobe.com/de/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow) vorgestellt.

### Einverständnis, Datenbeibehaltung und Benutzerrollen {#consent}

Zunächst bietet Adobe Campaign wichtige Funktionen, die für den Datenschutz unerlässlich sind:

* **Einverständnisverwaltung**: Mithilfe der Abonnementverwaltung können Sie die Voreinstellungen Ihrer Empfänger verwalten und nachverfolgen, welche Empfänger sich für welche Art von Abonnements entschieden haben. Weitere Informationen hierzu finden Sie im Abschnitt [Über Abonnements](../../automation/workflow/subscription-services.md).
* **Datenbeibehaltung**: Alle integrierten standardmäßigen Protokolltabellen in Campaign verfügen über eine vordefinierte Beibehaltungsdauer, die üblicherweise auf maximal sechs Monate begrenzt ist. Mit Workflows können weitere Beibehaltungszeiträume eingerichtet werden. Weitere Informationen hierzu erhalten Sie von den Adobe-Beratern oder technischen Administratoren.
* **Berechtigungs-Management**: Adobe Campaign bietet Ihnen die Möglichkeit, die den unterschiedlichen Campaign-Benutzern zugewiesenen Rechte mithilfe von vordefinierten oder benutzerdefinierten spezifischen Rollen zu verwalten. Damit können Sie festlegen, wer in Ihrem Unternehmen auf unterschiedliche Arten von Daten zugreifen, diese ändern und exportieren kann. Weitere Informationen hierzu finden Sie unter [Über die Zugriffsverwaltung](https://experienceleague.adobe.com/de/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}.

### Datenschutzanfragen {#privacy-requests}

Adobe Campaign bietet zusätzliche Funktionen, mit denen Sie sich als Datenverantwortlicher auf bestimmte Datenschutzanfragen vorbereiten können:

* Das **Recht auf Zugriff** ist das Recht der betroffenen Person, vom Datenverantwortlichen eine Auskunft darüber zu erhalten, ob und warum personenbezogene Daten über sie verarbeitet werden oder nicht.

* Das **Recht auf Vergessenwerden** (Löschanfrage) berechtigt die betroffene Person dazu, vom Datenverantwortlichen die Löschung ihrer personenbezogenen Daten zu verlangen.

Näheres zu Anfragen zum **Zugriff** und zur **Löschung** finden Sie in [diesem Abschnitt](../start/privacy.md).

Die Implementierungsschritte zum Erstellen dieser Anfragen werden in [diesem Abschnitt](../start/privacy.md) beschrieben.

## Tracking-Funktionen {#tracking-capabilities}

### Cookies {#cookies}

Dank der Tracking-Funktionen können Sie mit Adobe Campaign die Navigation Ihrer Versandempfänger mit drei Cookie-Typen verfolgen: mit einem Sitzungs-Cookie und zwei dauerhaften Cookies.

* Ein **Sitzungs**-Cookie: Das **nlid**-Cookie enthält die Kennung der an den Kontakt gesendeten E-Mail (**broadlogId**) und die Kennung der Nachrichtenvorlage (**deliveryId**). Es wird gesetzt, sobald der Kontakt auf eine in einer mit Adobe Campaign gesendeten E-Mail enthaltene URL klickt, und ermöglicht, das Web-Verhalten des Kontakts zu verfolgen. Dieses Sitzungs-Cookie wird automatisch beim Schließen des Browsers gelöscht. Der Kontakt hat die Möglichkeit, das Setzen des Cookies zu verbieten, indem er seine Browser-Einstellungen dementsprechend ändert.

* Zwei **dauerhafte** Cookies:
   * Das **UUID**-Cookie (Universal Unique IDentifier) wird von verschiedenen Adobe Experience Cloud-Lösungen verwendet. Es wird einmal gesetzt, bis es beim Generieren eines neuen Werts aus dem Clientbrowser verschwindet. Dieses Cookie ermöglicht die Identifizierung eines Benutzers, der bei Website-Besuchen mit Experience Cloud-Lösungen interagiert. Es kann von einer Landingpage (um unbekannte Kundenaktivitäten einem Empfänger zuzuordnen) oder von einem Versand hinterlegt werden. Eine Beschreibung dieses Cookies finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html?lang=de#ec-cookies).
   * Das **nllastdelid**-Cookie (eingeführt in Campaign Classic 20.3) ist ein dauerhaftes Cookie, das die **deliveryId** des letzten Versands enthält, von dem aus der Benutzer auf den Link geklickt hat. Dieses Cookie wird (wenn das Sitzungs-Cookie fehlt) zur Identifizierung der zu verwendenden Tracking-Tabelle verwendet.

Vorschriften wie die EU-Datenschutz-Grundverordnung (DSGVO) besagen, dass Unternehmen die Zustimmung der Website-Benutzer benötigen, bevor sie Cookies installieren.

* Vermeiden Sie jedoch Pop-ups, da diese häufig von den Browsern blockiert werden.

### Nachrichten-Tracking {#message-tracking}

Mit Adobe Campaign können Sie die gesendeten E-Mails sowie das Verhalten der Empfängerinnen und Empfänger Ihrer Sendungen verfolgen: Öffnen, Klicks auf Links, Abmeldungen usw. Weitere Informationen hierzu finden Sie im Abschnitt [Über Nachrichten](../start/gs-message.md).

Fügen Sie zu diesem Zweck getrackte Links zu Ihren Nachrichten hinzu, um die Wirkung Ihres Versands und das Verhalten Ihrer Empfängerinnen und Empfänger auf der Registerkarte „Tracking“ des Versand-Dashboards zu messen. Tracking-Daten werden im Bericht zu Trackingindikatoren interpretiert. Weiterführende Informationen zum Tracking finden Sie auf [dieser Seite](../send/tracking.md).

### Webtracking {#web-tracking}

>[!AVAILABILITY]
>
>Webtracking ist in Campaign v8 nicht verfügbar. Weitere Informationen zu nicht verfügbaren Funktionen finden Sie auf [dieser Seite](../start/v7-to-v8.md#gs-unavailable-features).

## Daten- und Datenschutz {#data-and-pii-protection}

Die Datenschutzkonfiguration und entsprechende Härtungsmaßnahmen sind zentrale Bestandteile der Optimierung der Sicherheit. Befolgen Sie die folgenden Best Practices:

* **HTTPS für alle Endpunkte verwenden** - Stellen Sie sicher, dass alle von Campaign verwendeten Endpunkte (Tracking, Mirrorseite, Web-Anwendungen, APIs) über HTTPS bereitgestellt werden.
* **PII-Ansicht beschränken** - Verwenden Sie [PII-Ansichtsbeschränkung](../dev/restrict-pi-view.md), damit nur autorisierte Benutzende sensible Felder (z. B. E-Mail, Telefon) in Schemata und Bildschirmen sehen können.
* **Zugriff auf verschlüsselte Kennwörter beschränken** - Beschränken des Zugriffs auf Passwort- und Geheimnisfelder in externen Konten und anderen Schemata, sodass nur Administratoren oder eine minimale Gruppe von Benutzern sie anzeigen können. Siehe [Dateneinschränkung](#data-restriction) unten.
* **Schutz sensibler Seiten** - Beschränken des Zugriffs auf Mirrorseiten, Web-Anwendungen und Landingpages, die personenbezogene Daten anzeigen oder erfassen; Verwenden von Benutzer- und Ordnerberechtigungen und gegebenenfalls Captchas und Einverständnis.

>[!NOTE]
>
>Adobe unterstützt Sie als Benutzerin bzw. Benutzer von Managed Cloud Services bei der Implementierung dieser Konfigurationen in Ihrer Umgebung.

## Zugriffsverwaltung  {#access-management}

Die Zugriffsverwaltung ist ein wichtiger Bestandteil des Sicherheits-Managements. Im Folgenden finden Sie die wichtigsten Best Practices:

* **ausreichend Sicherheitsgruppen erstellen** - Benutzergruppen definieren, die mit den Rollen übereinstimmen, und nur die Rechte zuweisen, die jede Rolle benötigt.
* **Überprüfen, ob jeder Benutzer über die entsprechenden Zugriffsrechte verfügt** - Wenden Sie das Prinzip der geringsten Rechte an. Gewähren Sie standardmäßig keine ADMINISTRATIONS- oder anderen allgemeinen Rechte.
* **Verwenden Sie nicht den Admin-Operator und vermeiden Sie zu viele Operatoren in der Admin-Gruppe** - Geben Sie das integrierte Admin-Konto nicht frei. Erstellen Sie für Rechenschaftspflicht und Audit einen Operator pro physischem Benutzer.
* **Ein Benutzer pro physischem Benutzer** - Geben Sie keine Konten frei. Erstellen Sie pro Person einen Campaign-Benutzer (Adobe ID), damit Audit-Protokolle zugeordnet werden können.
* **Spezifische Berechtigungen mit hohen Berechtigungen beschränken** - Gewähren Sie **ADMINISTRATION**, **PROGRAM EXECUTION** (createProcess) und **SQL** nur einer kleinen Anzahl vertrauenswürdiger Operatoren. Dokumentieren Sie, wer diese Berechtigungen hat und warum.
* **Zugriff regelmäßig überprüfen** - Überprüfen Sie Benutzer, Benutzergruppen und Ordnerberechtigungen regelmäßig. Entfernen oder reduzieren Sie den Zugriff, wenn sich die Rollen ändern oder Personen die Seite verlassen.
* **Produktprofile konsistent verwenden** - Weisen Sie in Admin Console vorzugsweise Benutzende Produktprofilen (Benutzergruppen) zu. Achten Sie auf eine konsistente Benennung (z. B. `campaign - <instance> - <group>`). Siehe [Erste Schritte mit Berechtigungen](../start/gs-permissions.md).
* **Zugriff auf das Control**: In Campaign v8 können Produktprofile oder spezifische Berechtigungen, deren Name „Admin“ enthält, Zugriff auf das Campaign Control Panel gewähren. Verwenden Sie „admin“ nicht in Profil- oder Gruppennamen, es sei denn, diese Benutzer sollten Zugriff auf das Control Panel haben.

Weiterführende Informationen zu Berechtigungen finden Sie in [diesem Abschnitt](../start/gs-permissions.md).

## Authentifizierung und Sitzung {#authentication-and-session}

* **Adobe IMS verwenden** - Alle Benutzer sollten sich mit ihrer Adobe ID (IMS) anmelden. Verlassen Sie sich nicht auf ältere Anmelde-/Kennworte für tägliche Benutzer.
* **Starke Identitäts- und Passwortrichtlinie erforderlich** - Verwenden Sie Admin Console oder Ihren Identitätsanbieter für MFA- und Passwortrichtlinien, um sicherzustellen, dass nur autorisierte Benutzende Campaign-Produktprofilen zugewiesen werden.
* **Sitzungs-Timeout konfigurieren** Legen Sie, sofern konfigurierbar (z. B. in der Client-Konsole), einen angemessenen Sitzungs-Timeout fest und sperren Sie den Bildschirm, wenn Sie die Workstation verlassen.

## Instanz- und Netzwerksicherheit {#instance-and-network-security}

Verwenden Sie als Produktadministrator von Campaign v8 das [Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de){target="_blank"}, um die Sicherheit auf Instanzebene zu verwalten:

* **IP-**: Verwalten Sie die IP-Zulassungsliste auf die Zulassungsliste setzte für den Zugriff auf Instanzen, beschränken Sie sie auf bekannte Netzwerke (z. B. Office, VPN) und vermeiden Sie nach Möglichkeit zu große Bereiche.
* **URL-Berechtigungen** - Beschränken Sie URL-Berechtigungen auf die Domains, die Ihre Instanz aufrufen muss (APIs, Tracking, externe Dienste), um das Risiko des Missbrauchs Server-seitiger Anfragen zu reduzieren.
* **GPG-Schlüssel** - Wenn Sie Verschlüsselung für Dateiübertragungen oder andere Anwendungsfälle verwenden, verwalten Sie GPG-Schlüssel über das Control Panel und drehen Sie sie entsprechend Ihrer Sicherheitsrichtlinie.

## Leitlinien zur Codierung {#coding-guidelines}

Bei Entwicklungsaufgaben in Adobe Campaign (Workflows, JavaScript, JSSP usw.) sollten Sie sich grundsätzlich an diesen Leitlinien orientieren:

* **Skripterstellung** - Versuchen Sie, unformatiertes SQL zu vermeiden. Verwenden Sie parametrisierte Funktionen anstelle der Verkettung von Zeichenfolgen. Vermeiden Sie SQL-Injection, indem Sie nur die SQL-Funktionen hinzufügen, die Sie zur Zulassungsliste benötigen.
* **Datenmodell sichern** - Verwenden Sie spezifische Berechtigungen, um Benutzeraktionen einzuschränken und Systemfilter hinzuzufügen (sysFilter).
* **Hinzufügen von Captchas in Web-Anwendungen** - Hinzufügen von Captchas zu öffentlichen Landingpages und Abonnementseiten.
* **Geheimnisse nicht fest kodieren** - Kennwörter, API-Schlüssel oder Token in Workflows, JavaScript oder JSSP nicht fest kodieren, sondern externe Konten oder sichere Konfigurationen verwenden.
* **Eingabe validieren und bereinigen** - Benutzereingaben in Web-Anwendungen und Workflow-Parametern überprüfen und bereinigen, um Injektions- und XSS-Risiken zu reduzieren.
* **Zulassungsliste für SQL verwenden** - Wenn eine SQL- oder Skriptausführung erforderlich ist, die Zulassungsliste für zulässige SQL-Funktionen verwenden und das Erstellen von Abfragen aus Benutzereingaben über eine Zeichenfolgenverkettung vermeiden.

Weitere Informationen finden Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=de#installing-campaign-classic){target="_blank"}.


## Personalisierung

Wenn Sie personalisierte Links zu Ihrem Inhalt hinzufügen, achten Sie darauf, dass im Hostname-Teil der URL keine Personalisierung vorhanden ist. So lassen sich mögliche Sicherheitslücken verhindern. Folgende Beispiele sollten niemals in den URL-Attributen &lt;`a href="">` oder `<img src="">` verwendet werden:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Dateneinschränkung {#data-restriction}

Sie müssen sicherstellen, dass keine authentifizierten Benutzer mit unzureichender Berechtigung auf die verschlüsselten Passwörter zugreifen können. Dazu können Sie den Zugriff entweder auf Passwortfelder oder auf die gesamte Entität einschränken.

Mit dieser Einschränkung können Sie Passwortfelder entfernen, das externe Konto jedoch für alle Benutzer über die Benutzeroberfläche zugänglich machen. Weitere Informationen finden Sie auf [dieser Seite](../dev/restrict-pi-view.md).

1. Gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Konfigurieren]** > **[!UICONTROL Datenschemata]**.

1. Erstellen Sie eine neue **[!UICONTROL Schemaerweiterung]**.

1. Wählen Sie **[!UICONTROL Externes Konto]** aus (extAccount).

1. Bearbeiten Sie im letzten Fenster Ihr neues srcSchema, um den Zugriff auf alle Passwortfelder einzuschränken:

   Das Hauptelement (`<element name="extAccount" ... >`) können Sie ersetzen durch:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Ihr erweitertes srcSchema sieht dann folgendermaßen aus:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >Sie können `$(loginId) = 0 or $(login) = 'admin'` durch `hasNamedRight('admin')` ersetzen, damit diese Passwörter für alle Benutzer mit Administratorberechtigung einsehbar sind.

## Betrieb und Compliance {#operational-and-compliance}

* **Mit sicherer Grundlinie vergleichen** - Vergleichen Sie regelmäßig Ihre Benutzergruppen, spezifischen Berechtigungen und Ordnerberechtigungen mit den Empfehlungen auf dieser Seite (und ggf. mit dem Add-on [Erweiterte Sicherheit](enhanced-security.md)), um die empfohlenen sicheren Standardwerte einzuhalten.
* **Verwenden des Audit-Protokolls** - Nutzen Sie das Audit-Protokoll von Campaign für wichtige Änderungen (z. B. Workflows, Sendungen, Schlüsselkonfiguration); bewahren Sie Protokolle auf und überprüfen Sie sie, wie es Ihre Compliance- und Aufbewahrungsrichtlinie erfordert.

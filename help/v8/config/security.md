---
title: Best Practices für die Campaign-Sicherheit
description: Erste Schritte mit Best Practices für die Campaign-Sicherheit
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2280'
ht-degree: 90%

---

# Best Practices für die Campaign-Sicherheit {#ac-security}

Bei Adobe hat die Sicherheit Ihres digitalen Erlebnisses höchste Priorität. Sicherheitsmaßnahmen sind tief in unsere internen Prozesse und Tools rund um die Entwicklung und den Betrieb von Software implementiert und werden von unseren Teams über alle Funktionsbereiche hinweg strikt befolgt, um Sicherheitsvorfällen vorzubeugen bzw. diese schnellstmöglich zu erkennen und zu beheben.

Darüber hinaus arbeiten wir mit unseren Partnern sowie mit führenden Sicherheitsanalysten, Sicherheitsforschungseinrichtungen und anderen Branchenverbänden zusammen und gewährleisten so, mit den neuesten Bedrohungen und Schwachstellen Schritt halten zu können und regelmäßig fortschrittliche Sicherheitsverfahren in unsere Angebote und Services zu integrieren.

## Datenschutz

Um den Datenschutz korrekt zu handhaben und personenbezogene Daten korrekt zu verwalten, müssen Sie die für die Region(en) geltenden Gesetze einhalten, in denen Sie tätig sind. Die Funktionen von Adobe Campaign helfen Ihnen bei der Einhaltung der auf [ Seite ](../start/privacy.md) Vorschriften

### Adobe Experience Cloud – Datenschutz {#experience-cloud-privacy}

Adobe Campaign ist Teil der Adobe Experience Cloud-Lösungen. Die Art und Weise, wie der Datenschutz in Campaign gehandhabt wird, entspricht den allgemeinen Grundsätzen von Experience Cloud, z. B.:

* **Welche Informationen werden bei Verwendung von Adobe Experience Cloud erfasst?**

  Als Unternehmen, das Adobe Experience Cloud-Lösungen nutzt, entscheiden Sie selbst, welche Informationen erfasst und an Ihr Adobe Experience Cloud-Konto gesendet werden sollen. Beispiele für die Arten von Informationen, die erfasst werden können, sind Webbrowsing-Aktivitäten, IP-Adressen, Standortinformationen von Mobilgeräten, Erfolgsquoten von Kampagnen, gekaufte oder in den Warenkorb gelegte Artikel usw.

  >[!NOTE]
  >
  >Wie bei allen Produkten von Adobe erfasst Campaign Informationen über App- und Website-Benutzer. Weitere Informationen finden Sie in der [Datenschutzerklärung von Adobe](https://www.adobe.com/de/privacy/policy.html).

* **Verwendung von Adobe Experience Cloud zur Erfassung von Informationen**

   * Adobe Experience Cloud-Lösungen verwenden Cookies und ähnliche Technologien, wie Webbeacons (auch als Tags oder Pixel bezeichnet), um die Erfassung von Informationen zu ermöglichen. Weitere Informationen zu Cookies und Tracking-Funktionen mit Adobe Campaign finden Sie in [diesem Abschnitt](#tracking-capabilities).
   * Sie können Adobe Experience Cloud-Technologien auch in Ihren mobilen Apps verwenden. Weiterführende Informationen zum Senden von Sendungen an Mobilgeräte mit Campaign finden Sie unter [SMS-Kanal](../send/sms/sms-channel.md) und Mobile-App-Kanal.

* **Datenschutzoptionen Ihrer Benutzer bezüglich Ihrer Verwendung von Adobe Experience Cloud**

  Adobe fordert Sie auf, Ihren Kunden Datenschutzrichtlinien bereitzustellen, in denen Folgendes beschrieben wird:

   * Ihre Datenschutzpraktiken in Verbindung mit Adobe Experience Cloud
   * Die Art und Weise, auf die Benutzer ihre Voreinstellungen für die Erfassung oder Verwendung ihrer Informationen in Verbindung mit Adobe Experience Cloud festlegen können

  >[!NOTE]
  >
  >Wie bei allen Produkten von Adobe können Campaign-Benutzer die Weitergabe von Informationen, die über Apps und Websites erfasst wurden, deaktivieren. Weitere Informationen finden Sie in den [häufig gestellten Fragen zu den Adobe Experience Cloud-Nutzungsinformationen](https://www.adobe.com/de/privacy/experience-cloud-usage-info-faq.html).

Weitere Informationen zum Datenschutz in Adobe Experience Cloud finden Sie auf [dieser Seite](https://www.adobe.com/de/privacy/marketing-cloud.html).

## Personenbezogene Daten und Personas {#personal-data}

Bei der Verwaltung des Datenschutzes ist es wichtig zu definieren, welche Daten von wem mit Sorgfalt behandelt werden sollen.
* **Personenbezogene Daten** sind Informationen, die eine lebende Person direkt oder indirekt identifizieren können.
* **Vertrauliche personenbezogene Daten** sind Informationen zu Rasse, politischen Ansichten, religiösen Überzeugungen, kriminellem Hintergrund, genetischen Informationen, Gesundheitsdaten, sexuellen Vorlieben, biometrischen Informationen sowie zur Gewerkschaftsmitgliedschaft.

Bei der Integration von Campaign mit anderen Experience Cloud-Lösungen, bei denen Zielgruppen von einem System in ein anderes übertragen werden können, z. B. [Adobe Analytics](../connect/ac-aa.md), [Experience Cloud Audiences](../start/shared-audiences.md), Campaign Standard, oder mit anderen Lösungen über [CRM-Connector](../../automation/workflow/crm-connector.md) müssen Sie besonders auf den Schutz personenbezogener Daten achten.

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

Datenschutzverwaltung bezieht sich auf alle Prozesse und Tools, die Ihnen bei der Einhaltung von Datenschutzbestimmungen (DSGVO, CCPA usw.) helfen.

Adobe Campaign bietet Ihnen verschiedene Funktionen zur Datenschutzverwaltung:
* Einverständnisverwaltung, Datenbeibehaltung und Benutzerrollen. Siehe [diesen Abschnitt](#consent).
* Datenschutzanfragen (Recht auf Zugriff und Recht auf Vergessenwerden). Siehe [diesen Abschnitt](#privacy-requests).
* Opt-out aus dem Verkauf personenbezogener Daten (CCPA-spezifisch).

Die wichtigsten Datenschutzfunktionen in Campaign und ein Beispiel der beteiligten Rollen werden in [diesem Abschnitt](https://helpx.adobe.com/de/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow) dargestellt.

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

* Eine Möglichkeit besteht darin, Besucher von Webtracking betroffenen Seiten zur Zustimmung aufzufordern, indem im oberen Bereich auf der ersten besuchten Seite ein Banner eingeblendet und zum Ankreuzen eines Feldes aufgefordert wird.
* Vermeiden Sie jedoch Pop-ups, da diese häufig von den Browsern blockiert werden.

### Nachrichten-Tracking {#message-tracking}

Mit Adobe Campaign können Sie die gesendeten E-Mails und das Verhalten der Empfänger Ihrer Sendungen verfolgen: Öffnen, Klicks auf Links, Abmeldungen usw. Weitere Informationen hierzu finden Sie unter [Über Nachrichten](../start/gs-message.md).

Fügen Sie dazu Ihren Nachrichten getrackte Links hinzu, um die Wirkung Ihres Versand- und Empfängerverhaltens auf der Registerkarte Tracking des Versand-Dashboards zu messen. Tracking-Daten werden im Bericht Tracking-Indikatoren interpretiert. Weitere Informationen zum Tracking finden Sie auf [dieser Seite](../start/tracking.md).

### Webtracking {#web-tracking}

Mit Adobe Campaign können Sie auch überwachen, wie Empfänger Ihre Website durchsuchen: Einfügen von Tracking-Tags, um Informationen zu sammeln und Besuche auf Web-Anwendungsseiten zu messen.

Die Konfiguration des Webtrackings wird in [diesem Abschnitt](../start/tracking.md) erläutert.

Zusätzlich können Sie in Adobe Campaign ein Opt-out-Banner anzeigen, über das Endbenutzer das Tracking ihres Web-Verhaltens beenden können. Weitere Informationen hierzu finden Sie unter [Opt-out vom Web-Anwendungs-Tracking](https://experienceleague.adobe.com/de/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out){target=_blank}.

<!--
Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.
-->

>[!NOTE]
>
>Adobe unterstützt Sie als Benutzerin bzw. Benutzer von Managed Cloud Services bei der Implementierung dieser Konfigurationen in Ihrer Umgebung.


## Zugriffsverwaltung 

Die Zugriffsverwaltung ist ein wichtiger Bestandteil des Sicherheits-Managements. Im Folgenden finden Sie die wichtigsten Best Practices:

* Erstellen Sie eine ausreichende Anzahl von Sicherheitsgruppen.
* Stellen Sie sicher, dass jeder Benutzer über geeignete Zugriffsberechtigungen verfügt.

Weiterführende Informationen zu Berechtigungen finden Sie in [diesem Abschnitt](../start/gs-permissions.md)

## Leitlinien zur Codierung

Bei Entwicklungsaufgaben in Adobe Campaign (Workflows, JavaScript, JSSP usw.) sollten Sie sich grundsätzlich an diesen Leitlinien orientieren:

* **Skripterstellung**: Vermeiden Sie SQL-Anweisungen, verwenden Sie parametrierte Funktionen anstelle von String-Konkatenation, und vermeiden Sie SQL-Injection, indem Sie die zu verwendenden SQL-Funktionen auf die Zulassungsliste setzen.

* **Schutz des Datenmodells**: Verwenden Sie spezifische Berechtigungen, um Benutzeraktionen einzuschränken, und fügen Sie Systemfilter hinzu (sysFilter).

* **Hinzufügen von Captchas in Web-Anwendungen**: Hier erfahren Sie, wie Sie Captchas in Ihren öffentlichen Landingpages und Anmeldeseiten hinzufügen können.

Weitere Informationen finden Sie in der Dokumentation zu [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=de#installing-campaign-classic){target="_blank"}.


## Personalisierung

Wenn Sie personalisierte Links zu Ihrem Inhalt hinzufügen, achten Sie darauf, dass im Hostname-Teil der URL keine Personalisierung vorhanden ist. So lassen sich mögliche Sicherheitslücken verhindern. Folgende Beispiele sollten niemals in den URL-Attributen &lt;`a href="">` oder `<img src="">` verwendet werden:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Dateneinschränkung

Sie müssen sicherstellen, dass keine authentifizierten Benutzer mit unzureichender Berechtigung auf die verschlüsselten Passwörter zugreifen können. Dazu können Sie den Zugriff entweder auf Passwortfelder oder auf die gesamte Entität einschränken.

Mit dieser Einschränkung können Sie Passwortfelder entfernen, das externe Konto jedoch für alle Benutzer über die Benutzeroberfläche zugänglich machen. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/restrict-pi-view.md).

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


## Zugriffsverwaltung 

Die Zugriffsverwaltung ist ein wichtiger Bestandteil des Sicherheits-Managements. Im Folgenden finden Sie die wichtigsten Best Practices:

* Erstellen Sie eine ausreichende Anzahl von Sicherheitsgruppen.
* Stellen Sie sicher, dass jeder Benutzer über geeignete Zugriffsberechtigungen verfügt.

Weiterführende Informationen zu Berechtigungen finden Sie in [diesem Abschnitt](../start/gs-permissions.md).

## Leitlinien zur Codierung

Bei Entwicklungsaufgaben in Adobe Campaign (Workflows, JavaScript, JSSP usw.) sollten Sie sich grundsätzlich an diesen Leitlinien orientieren:

* **Skripterstellung**: Vermeiden Sie SQL-Anweisungen, verwenden Sie parametrierte Funktionen anstelle von String-Konkatenation, und vermeiden Sie SQL-Injection, indem Sie die zu verwendenden SQL-Funktionen auf die Zulassungsliste setzen.

* **Schutz des Datenmodells**: Verwenden Sie spezifische Berechtigungen, um Benutzeraktionen einzuschränken, und fügen Sie Systemfilter hinzu (sysFilter).

* **Hinzufügen von Captchas in Web-Anwendungen**: Hier erfahren Sie, wie Sie Captchas in Ihren öffentlichen Landingpages und Anmeldeseiten hinzufügen können.

Weitere Informationen finden Sie in der Dokumentation zu [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=de#installing-campaign-classic){target="_blank"}.

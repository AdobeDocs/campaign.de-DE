---
title: Best Practices beim Versand
description: Erfahren Sie mehr zu Best Practices für das Erstellen und Durchführen von Sendungen in Adobe Campaign
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2970'
ht-degree: 97%

---

# Best Practices beim Versand {#delivery-best-practices}

Lesen Sie die folgenden Best Practices für die Versandfunktionen in Campaign.

## Optimieren des Versands {#optimize-delivery}

Bevor Sie mit dem Erstellen von Sendungen beginnen, können Sie mehrere Maßnahmen treffen, um den vorgelagerten Versandprozess zu optimieren.  Im folgenden Abschnitt werden Best Practices und empfohlene Verfahren für die optimale Konfiguration von Adobe Campaign erläutert.

### Performance der Plattform

Mehrere Faktoren können die Server-Leistung direkt beeinflussen und die Campaign-Plattform verlangsamen:

* Anzahl und Art der [Personalisierungselemente](../send/personalize.md): Durch Personalisierung in E-Mails werden Daten für jede Empfängerin bzw. jeden Empfänger aus der Datenbank abgerufen. Bei vielen Personalisierungselementen ist die für die Versandvorbereitung benötigte Datenmenge größer. Dies kann Ihre Plattform verlangsamen. Weiterführende Informationen zu Schutzmechanismen für die Personalisierung finden Sie in [diesem Abschnitt](../send/personalize.md#perso-guardrails).

* Auslastung des Servers: Wenn der Marketing-Server viele verschiedene Aufgaben gleichzeitig ausführt, kann die Leistung reduziert werden. Der Marketing-Server muss alle eingehenden und ausgehenden Daten für alle Sendungen koordinieren, um sicherzustellen, dass die Daten korrekt sind und rechtzeitig gesendet werden.
Um dies zu vermeiden, koordinieren Sie die zeitliche Durchführung von Sendungen mit anderen Team-Mitgliedern, sodass eine optimale Leistung gewährleistet ist.

* Workflow-Ausführung: Die Überwachung Ihrer Workflows ist unverzichtbar, um Probleme mit der Performance der Plattform zu vermeiden. Befolgen Sie die [in diesem Dokument](../../automation/workflow/workflow-best-practices.md#execution-and-performance) aufgeführten Richtlinien.

* Stellen Sie eine Verbindung zu Ihren [Funktionen des Campaign Control Panels](https://experienceleague.adobe.com/de/docs/control-panel/using/discover-control-panel/key-features){target="_blank"} her, um Ihre Plattform mithilfe der Funktionen [Leistungsüberwachung](https://experienceleague.adobe.com/de/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"} zu überwachen.

#### Quarantäneverwaltung {#quarantine-management}

Achten Sie in Ihrem eigenen Interesse auf eine gute Quarantäneverwaltung.

Wenn Sie auf einer neuen Plattform erstmals E-Mails versenden, verwenden Sie möglicherweise eine Liste mit fehlerhaften Adressen. Wenn Sie Nachrichten an ungültige Adressen oder an Honeypot-Adressen (Postfächer, die ausschließlich der Täuschung von Spammern dienen) senden, mindert dies die Reputation Ihrer Plattform. Mit guten Prozessen für die Quarantäneverwaltung können Sie die Adressqualität pflegen, verhindern, dass Sie von ISPs auf eine Blockierungsliste gesetzt werden, und Ihre Fehlerrate senken, was den Versand beschleunigt und den Durchsatz erhöht.


Im Handbuch zu Best Practices für die Zustellbarkeit von [Adobe erfahren Sie, wie Sie eine neue Plattform ](https://experienceleague.adobe.com/de/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}.

Technische Empfehlungen finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/de/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}.


+++ **Hier finden Sie einige Best Practices**

* Adobe empfiehlt den Import ungültiger Adressen in die Quarantänetabelle über **[!UICONTROL Administration]** > **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Unzustellbarkeitsverwaltung]** > **[!UICONTROL Adressen unzustellbarer Sendungen]**.

* Empfänger, deren Adressen sich in Quarantäne befinden, werden zum Zeitpunkt der Versandanalyse standardmäßig ausgeschlossen und fließen somit nicht in die Berechnung der Zielgruppe ein. Dies beschleunigt Sendungen, da sich die Fehlerrate maßgeblich auf die Versandgeschwindigkeit auswirkt. Eine E-Mail-Adresse kann zum Beispiel unter Quarantäne gestellt werden, weil das Postfach voll ist oder die Adresse nicht existiert.
Adobe Campaign verwaltet fehlerhafte Adressen je nach zurückgegebenem Fehlertyp. [Weitere Informationen zu Quarantänen](../send/quarantines.md)

* Teilweise werden E-Mails von Providern automatisch als Spam eingestuft, wenn die Anzahl ungültiger Adressen zu hoch ist. Durch die Quarantäne können Sie also vermeiden, von diesen Providern auf eine Blockierungsliste gesetzt zu werden.

+++



### Anmeldemöglichkeit mit doppelter Bestätigung (Double opt-in) {#double-opt-in}

Um den Nachrichtenversand an ungültige Adressen zu vermeiden, unnütze Kommunikation zu minimieren und die Reputation des Absenders zu schützen, empfiehlt Adobe die doppelte Anmeldung zur Bestätigung eines Abonnements. Damit können Sie sicherstellen, dass sich eine Empfängerin bzw. ein Empfänger absichtlich angemeldet hat.

## Verwenden von Vorlagen {#use-templates}

Versandvorlagen ermöglichen eine effiziente Nutzung, da sie für die häufigsten Aktivitäten vordefinierte Szenarien enthalten. Mit Vorlagen können Marketing-Fachleute in kürzerer Zeit neue Kampagnen bei minimaler Anpassung bereitstellen.  [Erfahren Sie mehr über Versandvorlagen](../send/create-templates.md).

### Subdomains und Branding {#subdomains-and-branding}

Wenn Sie mehrere Marken in Adobe Campaign verwalten, empfiehlt Adobe die Zuweisung einer Subdomain pro Marke. Eine Bank kann beispielsweise für jede ihrer regionalen Niederlassungen über eine Subdomain verfügen. Angenommen die Domain einer Bank heißt bluebank.com, dann könnten ihre Subdomains @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com usw. lauten. Mit einer Versandvorlage pro Subdomain können Sie stets die richtigen vorkonfigurierten Parameter für jede Marke verwenden, um Fehler zu vermeiden und Zeit zu sparen.  Weitere Informationen zum Subdomain-Branding finden Sie in [ Dokumentation zum Campaign Control Panel ](https://experienceleague.adobe.com/de/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}.

### Konfigurieren von Adressen {#configure-addresses}

Achten Sie darauf, die folgenden Richtlinien anzuwenden:

* Die Angabe der Absenderadresse ist für den E-Mail-Versand zwingend erforderlich.  Manche ISPs (Internet Service Provider) prüfen die Gültigkeit der Absenderadresse, bevor sie Nachrichten akzeptieren.
* Eine schlecht formulierte Adresse könnte vom Empfangs-Server abgelehnt werden. Achten Sie darauf, dass eine korrekte Adresse angegeben ist.
* Die Adresse muss die Identität des Absenders enthalten. Die Domain muss im Besitz des Absenders und auf ihn registriert sein.
* Adobe empfiehlt, E-Mail-Konten zu erstellen, die der Absender- und Antwortadresse entsprechen. Wenden Sie sich diesbezüglich bitte an den Administrator Ihres E-Mail-Programms.

+++ **Schritte zum Konfigurieren von Adressen in der Campaign-Benutzeroberfläche**

Gehen Sie wie folgt vor, um Adressen in der Campaign-Benutzeroberfläche zu konfigurieren:

1. Wählen Sie in der [Versandvorlage](../send/create-templates.md) den Tab **[!UICONTROL Von]** aus. Geben Sie die Einstellungen im Fenster **[!UICONTROL E-Mail-Header-Parameter]** ein.

1. Stellen Sie im Feld **[!UICONTROL Absenderadresse]** sicher, dass die Adress-Domain mit der Subdomain übereinstimmt, die Sie an Adobe delegiert haben. Sie können den Teil vor dem „@“ ändern, nicht aber die Domain-Adresse.

1. Verwenden Sie im Feld **[!UICONTROL Von]** einen Namen, der von den Empfängern leicht identifiziert werden kann, z. B. den Namen Ihrer Marke, um die Öffnungsrate Ihrer Sendungen zu erhöhen. Um das Benutzererlebnis zu verbessern, können Sie den Namen einer Person einfügen, wie z. B. „Emma von Megastore“.

1. Im Feld **[!UICONTROL Text der Antwortadresse]** wird für Antworten standardmäßig die Adresse des Absenders verwendet. Adobe empfiehlt, eine echte Adresse zu verwenden, wie etwa den Kundendienst Ihrer Marke. So kann sich dieser gegebenenfalls um etwaige Antworten kümmern.

### Einrichten einer Kontrollgruppe {#set-up-control-group}

Sobald der Versand durchgeführt wurde, können Sie das Verhalten der ausgeschlossenen Empfänger mit den Empfängern vergleichen, die den Versand erhalten haben. Anschließend können Sie die Effizienz Ihrer Kampagnen messen. Weiterführende Informationen zu Kontrollgruppen finden Sie in [diesem Abschnitt](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Verwenden von Typologien, um Filter und Kontrollregeln anzuwenden {#create-typologies}

Eine Typologie enthält Regeln, die in der Analysephase vor dem Versand einer Nachricht angewendet werden.

In den Eigenschaften der Vorlage können Sie auf der Registerkarte **[!UICONTROL Typologie]** bei Bedarf eine benutzerdefinierte Typologie auswählen.

Um beispielsweise den ausgehenden Traffic besser zu steuern, können Sie festlegen, welche IP-Adressen verwendet werden können, indem Sie für jede Subdomain eine Affinität definieren und für jede Affinität eine Typologie erstellen. Affinitäten werden in der Konfigurationsdatei der Instanz bestimmt. Kontaktieren Sie dazu Ihren Adobe Campaign-Administrator.

Weiterführende Informationen zu Typologien finden Sie in [diesem Abschnitt](../../automation/campaign-opt/campaign-typologies.md).

## Optimieren von Inhalten {#optimize-content}

### Erstellen personalisierter Inhalte {#perso-content}

Um Ihre Nachrichten zu personalisieren, können Sie die Empfängerdaten verwenden, die in der Datenbank gespeichert sind oder mithilfe von Tracking, Landingpages oder Abonnements erfasst wurden.  Die Grundlagen der Personalisierung werden in [diesem Abschnitt](../send/personalize.md) dargestellt.

+++ **Hier finden Sie einige Best Practices**

* Überprüfen Sie Ihre Personalisierungseinstellungen – Stellen Sie sicher, dass Ihr Nachrichteninhalt korrekt aufgebaut ist, um Fehler zu vermeiden, die oft bei der Personalisierung auftreten. Ein Personalisierungs-Tag in Adobe Campaign präsentiert sich stets in folgender Form: `<%=table.field%>`.  Die falsche Verwendung von Parametern in Gestaltungsbausteinen kann Probleme verursachen. Variablen in JavaScript sollten beispielsweise folgendermaßen verwendet werden:

  ``
  <%
  var brand = "xxx"
  %>
  ``

  Weitere Informationen zu Gestaltungsbausteinen finden Sie in [diesem Abschnitt](../send/personalization-blocks.md).

* Bereiten Sie Personalisierungsdaten vor – Sie können die Personalisierungsdaten in einem Workflow vorbereiten, um die Analyse der Versandvorbereitung zu verbessern. Dies sollte insbesondere dann verwendet werden, wenn die Personalisierungsdaten über Federated Data Access (FDA) aus einer externen Tabelle stammen. Diese Option wird in diesem [Abschnitt beschrieben](../send/personalization-data.md#optimize-personalization).
+++

### Erstellen optimierter Inhalte {#build-optimized-content}

Achten Sie beim Erstellen von E-Mails darauf, die allgemeinen Best Practices für E-Mail-Inhalte anzuwenden.

+++ **Hier finden Sie einige Best Practices**

* Halten Sie das Design einfach.

* Denken Sie an Benutzer mit Smartphones und Tablets.

* Vermeiden Sie vollständig bildbasierte E-Mails.

* Verwenden Sie E-Mail-sichere Schriftarten.

* Kodieren Sie Sonderzeichen.

+++


### Betreff  {#subject-line-check}

Achten Sie besonders auf den [Betreff](../send/personalization-fields.md#personalization-fields-uc) der E-Mail, um die Öffnungsraten zu verbessern.


+++ **Hier finden Sie einige Best Practices**


* Vermeiden Sie einen zu langen Betreff. Verwenden Sie maximal 50 Zeichen.

* Vermeiden Sie die wiederholte Verwendung von Wörtern wie „gratis“ oder „Angebot“, die als Spam angesehen werden könnten.

* Vermeiden Sie Großbuchstaben.

* Verwenden Sie keine Sonderzeichen wie „!“, „£“, „€“ oder „$“.

+++

### Mirrorseite {#mirror-page-check}

Beziehen Sie stets einen Link zur Mirrorseite ein. Die bevorzugte Position ist am Anfang der E-Mail – Weitere Informationen zur Mirrorseite finden Sie auf [dieser Seite](../send/mirror-page.md).

### Abmelde-Link {#unsub-link-check}

Ein Abmelde-Link muss unbedingt vorhanden sein. Er muss gut sichtbar und gültig sein, und das Formular muss funktionieren. Bei der Analyse einer Nachricht überprüft die [Typologieregel](../../automation/campaign-opt/control-rules.md) **[!UICONTROL Genehmigung des Abmelde-Links]** standardmäßig, ob ein Ausschluss-Link vorhanden ist. Ist dies nicht der Fall, wird ein Warnhinweis erstellt.

[In diesem Abschnitt](../send/personalization-blocks.md) erfahren Sie, wie Sie einen Ausschluss-Link einfügen.

+++ **Wenden Sie diese Best Practice an**

Da menschliche Fehler immer möglich sind, prüfen Sie vor jedem Versand, ob der Abmelde-Link ordnungsgemäß funktioniert. Achten Sie beispielsweise beim Testversand darauf, dass der Link gültig ist, dass das Formular online ist und dass sich das Feld `No longer contact this recipient ` in `Yes` ändert.

+++

### Größe der E-Mail {#email-size-check}

Um Performance- oder Zustellbarkeitsprobleme zu vermeiden, wird eine E-Mail mit einer maximalen Größe von **35 KB** empfohlen. Um die Nachrichtengröße zu überprüfen, durchsuchen Sie die Registerkarte **[!UICONTROL Vorschau]** und wählen Sie ein Testprofil aus. Nach der Erstellung der Nachricht wird deren Größe in der Ecke rechts oben dargestellt.


+++ **Hier finden Sie einige Best Practices**

* Entfernen Sie redundante oder nicht verwendete Stile.

* Verschieben Sie einen Teil des E-Mail-Inhalts auf eine Landingpage.

* Minimieren Sie den Code.

Testen Sie alle Änderungen vor dem endgültigen Senden.

+++


### Länge der SMS {#sms-length-check}

Standardmäßig kommt in Bezug auf die maximal zulässige Zeichenanzahl einer SMS der Mobilfunkstandard GSM (Global System for Mobile Communications) zur Anwendung. SMS, die das GSM-Alphabet verwenden, sind auf 160 Zeichen begrenzt oder auf 153 Zeichen pro SMS bei Nachrichten, die in mehreren Teilen gesendet werden.


+++ **Hier finden Sie einige Best Practices**

* Aktivieren Sie die Transliteration nicht, wenn Sie alle Zeichen Ihrer SMS beibehalten möchten, um beispielsweise Eigennamen unverändert zu übermitteln.

* Sollte Ihre SMS jedoch eine hohe Anzahl an Zeichen enthalten, die vom GSM-Standard nicht unterstützt werden, aktivieren Sie die Transliteration, um Ihre Versandkosten zu begrenzen.  Weitere Informationen finden Sie in [diesem Abschnitt](../send/sms/smpp-external-account.md#smpp-transliteration).

* Sie können eine SMS-Transliteration anwenden. Hierbei wird ein Zeichen einer SMS durch ein anderes ersetzt, wenn das erste Zeichen nicht vom GSM-Standard unterstützt wird. Beachten Sie, dass die Verwendung von Personalisierungsfeldern im SMS-Inhalt dazu führen kann, dass von der GSM-Kodierung nicht unterstützte Zeichen eingefügt werden. Als Campaign-Admin können Sie die Transliteration von Zeichen aktivieren, indem Sie das entsprechende Kästchen auf der Registerkarte „SMPP-Kanaleinstellungen“ des entsprechenden **[!UICONTROL externen Kontos]** markieren.  [Weitere Informationen](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### Anhänge vermeiden

Anhänge zählen zu den häufigsten Trägern von Malware, besonders wenn sie in einer Massensendung verschickt werden. Fügen Sie in die Nachricht einen sicheren Link ein, anstatt ein Dokument anzuhängen. Dies sorgt für zusätzlichen Schutz vor unbeabsichtigter Weiterverbreitung und verringert auch die Gefahr, dass die Nachricht an eingehenden E-Mail-Gateways wegen der Nachrichtengröße oder aus Sicherheitsgründen abgelehnt wird.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->

## Verwalten von Bildern {#manage-images}

Im Folgenden finden Sie einige spezifische Richtlinien für die Optimierung von Bildern für Ihre E-Mail-Marketing-Kampagne.

### Verhindern der Bildblockierung {#image-blocking}

Manche E-Mail-Clients blockieren Bilder standardmäßig. Einstellungen können aber auch von Benutzenden so konfiguriert werden, dass Bilder blockiert werden, um den Datenverbrauch zu reduzieren.   Daher kann die gesamte Nachricht verloren gehen, wenn keine Bilder heruntergeladen werden.

+++ Um dies zu vermeiden, können Sie diese Best Practices anwenden:

* Vermeiden Sie vollständig bildbasierte E-Mails.  Achten Sie auf eine ausgewogene Mischung aus Bild und Text.

* Wenn in einem Bild Text enthalten sein muss, verwenden Sie „alt“ (formatierten Alternativtext) oder „title text“ (Titeltext), um die Botschaft richtig zu übermitteln. Gestalten Sie „alt“/„title text“, um sein Erscheinungsbild zu verbessern.

* Vermeiden Sie eine Verwendung von Hintergrundbildern, da diese von einigen E-Mail-Clients nicht unterstützt werden.
+++

### Verwenden responsiver Bilder {#responsive-images}

Versuchen Sie, Bilder responsiv und anpassbar zu machen, damit sie in allen Kontexten und auf allen Geräten sichtbar sind. Beachten Sie, dass sich dies auf die Kosten auswirken kann, da die Erstellung länger dauert.

### Verwenden absoluter Bildreferenzen {#absolute-images}

Damit Empfänger auf die Bilder zugreifen können, müssen die in E-Mails und öffentlichen Ressourcen verwendeten Bilder, die mit Kampagnen verknüpft sind, auf einem extern zugänglichen Server gespeichert sein.

* Sie können eine HTML-Seite mit Bildern über den Versandassistenten importieren oder Bilder direkt mithilfe des HTML-Editors über das **[!UICONTROL Bildsymbol]** einfügen.

* Wenn keine Bilder dargestellt werden, prüfen Sie, ob die Bilder auf dem Server verfügbar sind. Durchsuchen Sie dazu die Registerkarte **Quelle** in Ihrem Versand. Suchen Sie Ihre Bilder und kopieren Sie die URL eines jeden Bildes in einen Webbrowser. Wenn die Bilder nicht dargestellt werden, kontaktieren Sie Ihre bzw. Ihren IT-Admin oder den Drittanbieter, der Ihnen den Versandinhalt bereitgestellt hat.

### Anzeigen einer Vorschau und Testen der Nachricht {#preview-msg}

Adobe empfiehlt eine Vorschau Ihrer Nachricht, um die Personalisierung zu überprüfen und festzustellen, wie Ihre Empfängerinnen und Empfänger den Versand sehen werden.

Im Versandassistenten können Sie auf der Unterregisterkarte **[!UICONTROL Vorschau]** das Rendering der einzelnen Inhalte für eine Empfängerin oder einen Empfänger anzeigen. Die Personalisierungsfelder und bedingten Inhaltselemente werden durch die entsprechenden Informationen für das ausgewählte Profil ersetzt.  [Weitere Informationen](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## Definieren der richtigen Zielgruppe {#define-the-right-audience}

Die Bestimmung der Zielpopulation ist besonders wichtig. Gehen Sie bei der Erstellung Ihrer Listen sorgfältig vor, testen Sie Ihre E-Mails in den gängigsten E-Mail-Clients sowie auf Smartphones und Tablets und stellen Sie sicher, dass Ihre E-Mail-Listen aktuell sind (und keine unbekannten oder veralteten Adressen enthalten).  Sie können auch Testsendungen vornehmen, um einen vollständigen Validierungszyklus durchzuführen.  Weitere Informationen zu Zielgruppen finden Sie in [diesem Abschnitt](../audiences/gs-audiences.md).

### Ansprechen der richtigen Audience {#target-the-right-audience}

Wenn Ihr Inhalt fertiggestellt ist, müssen Sie sorgfältig auswählen, wer Ihre Nachricht erhalten soll.

Um einen erfolgreichen Versand durchzuführen, müssen Sie möglichst relevanten personalisierten Inhalt an die richtigen Empfänger senden. Mit Adobe Campaign können Sie eine präzise Zielgruppe bestimmen, indem Sie die Empfänger nach Alter, Ort, Einkäufen, Klicks auf frühere Sendungen usw. auswählen. Sie können mit Adobe Campaign auch Testprofile und Kontrollgruppen definieren und Testsendungen durchführen, um sicherzustellen, dass Sie die richtige Zielgruppe erreichen.

### Zielgruppen-Mappings {#target-mappings}

Standardmäßig werden in Campaign mit Versandvorlagen **Empfangende** angesprochen. Adobe Campaign ermöglicht aber auch andere Zielgruppen-Mappings für Ihre Sendungen, die Sie entsprechend Ihren Anforderungen anpassen können.  So können Sie beispielsweise Nachrichten an Benutzer senden, deren Profile Sie über soziale Netzwerke erfasst haben oder die einen Informationsdienst abonniert haben.

Diese Zuordnungen (Mapping) werden [in diesem Abschnitt](../audiences/target-mappings.md) dargestellt.

### Externe Empfänger {#external-recipients}

Sie können Nachrichten an Empfänger senden, die in einer externen Datei anstatt in der Datenbank gespeichert sind. Weiterführende Informationen finden Sie [in diesem Abschnitt](create-message.md#select-external-recipients-selecting-external-recipients).

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### Testempfangende {#test-recipients-seed-addresses}

Nutzen Sie Testsendungen, bevor Sie Ihre Nachricht an die Hauptzielgruppe senden.

Achten Sie darauf, geeignete Testversand-Empfänger auszuwählen, da diese die Form und den Inhalt Ihrer Nachricht validieren. Die Schritte zum Festlegen der Testversand-Empfänger werden [in diesem Abschnitt](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target) beschrieben.


### Deduplizieren von Adressen {#deduplicate-addresses}

Vermeiden Sie doppelte E-Mail-Adressen, da sich dies auf Ihre Zielgruppe auswirken kann:

* Wenn eine Zielgruppe geteilt wird, kann es vorkommen, dass dieselbe Nachricht öfter als ein Mal gesendet wird.

* Wenn sich ein Empfänger nach dem Erhalt einer Nachricht abmeldet, könnten an sein dupliziertes Profil weiterhin Nachrichten gesendet werden.

Die Deduplizierung von Adressen schützt Ihre Reputation und gewährleistet eine gute Quarantäneverwaltung.

**Verwandte Themen:**

* [Aktivität „Deduplizierung“](../../automation/workflow/deduplication.md).
* [Anwendungsfall: Verwenden der Zusammenführungsfunktion der Aktivität „Deduplizierung“](../../automation/workflow/deduplication-merge.md).


## Durchführen aller Prüfungen vor dem Senden {#perform-all-checks}

Wenn Ihre Nachricht fertig ist, prüfen Sie, ob ihr Inhalt auf allen Geräten richtig dargestellt wird, und stellen Sie sicher, dass sie keine Fehler wie falsche Personalisierung oder defekte Links enthält.  Prüfen Sie vor dem Nachrichtenversand außerdem, ob die Parameter und die Konfiguration dem Versand entsprechen.

In [diesem Abschnitt](../send/preview-and-proof.md) werden die Schritte zur Validierung eines Versands vorgestellt.

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### Nachrichten in Testsendungen {#proof-messages}

Mit Testsendungen können Sie den Ausschluss-Link, die Mirrorseite und andere Links testen, die Nachricht validieren, die Anzeige von Bildern überprüfen und mögliche Fehler erkennen. Außerdem können Sie das Design und die Darstellung auf verschiedenen Geräten testen.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### Überprüfen der Nachrichtenzustellung {#make-sure-your-message-is-delivered}

Optimieren Sie Ihre Geschäftschancen und nutzen Sie die Funktionen von Adobe Campaign, um sicherzustellen, dass Ihre Nachricht tatsächlich bei den entsprechenden Empfängerinnen und Empfängern ankommt.

#### Validierungsprozess

Sie können einen vollständigen Validierungsprozess einschließlich der Adobe Campaign-Benutzer und -Gruppen definieren, um die Zielgruppe und den Nachrichteninhalt zu validieren. Dadurch wird eine umfassende Steuerung und Kontrolle der unterschiedlichen Kampagnenprozesse ermöglicht. Hierzu gehören Zielgruppenbestimmung, Inhalt, Budget, Extraktion und Testversand. Je nach Berechtigung werden Benutzer benachrichtigt, erhalten Testsendungen und können die Nachricht validieren oder ablehnen. Weiterführende Informationen finden Sie [in diesem Abschnitt](../../automation/campaigns/marketing-campaign-approval.md).

#### Schübe verwenden

Mit Schüben können Sie das gesendete Nachrichtenvolumen nach und nach steigern. Dadurch wird verhindert, dass Ihre Nachrichten als Spam gekennzeichnet werden, oder Sie können die Anzahl der pro Tag versendeten Nachrichten beschränken. Mit Schüben können Sie Sendungen in mehrere Teilsendungen unterteilen, anstatt große Mengen von Nachrichten gleichzeitig zu senden. Weiterführende Informationen finden Sie [in diesem Abschnitt](../send/configure-and-send.md#sending-using-multiple-waves).

#### Nachrichten priorisieren

Sie können die Reihenfolge der Sendungen durch Angabe der Versandpriorität festlegen. Gehen Sie dabei folgendermaßen vor:

1. Bearbeiten Sie die Versandeigenschaften und wählen Sie den Tab **[!UICONTROL Versand]** aus.

1. Bestimmen Sie dann die Dringlichkeit von **[!UICONTROL Sehr niedrig]** bis **[!UICONTROL Sehr hoch]**.

>[!NOTE]
>
>Die Reihenfolge der versendeten Nachrichten innerhalb eines Versands kann nicht festgelegt werden.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### Typologien verwenden

Typologieregeln ermöglichen den kriterienbasierten Ausschluss eines Teils der Zielgruppe. Auf diese Weise werden ein ideal auf Kundenbedürfnisse abgestimmter Nachrichtenversand sowie eine kohärente Unternehmenskommunikation sichergestellt. Beispielsweise können Sie minderjährige Empfänger aus der Zielgruppe Ihres Newsletters herausfiltern. Weiterführende Informationen finden Sie [in diesem Beispiel](../../automation/campaign-opt/filtering-rules.md).


## Verfolgen und überwachen {#track-and-monitor}

Sie haben auf die Schaltfläche **Senden** geklickt? Lassen Sie uns sehen, was dann passiert. Nach dem Versand der Nachrichten ermöglicht es Ihnen Adobe Campaign die gesendeten Nachrichten zu verfolgen und festzustellen, wie Ihre Empfänger darauf reagieren. Dadurch können Sie den zukünftigen Versand verbessern und Ihre nächsten Kampagnen optimieren.

## Überwachen von Sendungen {#monitoring-deliveries}

Um Ihre Kampagnen steuern zu können, müssen Sie zunächst sichergehen, dass Ihre Nachricht bei Ihren Empfängerinnen und Empfängern tatsächlich angekommen ist.

Prüfen Sie im Versand-Dashboard von Campaign die verarbeiteten Nachrichten und Versand-Auditlogs.  In den Versandlogs können Sie den Status der Nachrichten feststellen.

[ Weitere Informationen zur Versandüberwachung finden Sie in der Dokumentation zu Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=de){target="_blank"}


## Nachverfolgen von Verhaltensmustern {#track-behaviour}

Um das Verhalten Ihrer Empfangenden besser kennenzulernen, können Sie ihre Reaktion auf einen Versand verfolgen: Empfang, Öffnung, Klicks auf Links, Abmeldungen usw. In Campaign werden diese Informationen auf der Registerkarte **Tracking** der Empfangenden, die der Versand anspricht, und auf der Registerkarte „Tracking“ des Versands angezeigt.

Das Nachverfolgen von Nachrichten ist standardmäßig aktiviert. Um URLs zu konfigurieren, wählen Sie im unteren Bereich des Versandassistenten die Option „URLs anzeigen“ aus. Sie können für jede URL der Nachricht festlegen, ob Sie die Nachverfolgung aktivieren möchten.


[Weitere Informationen zu Tracking-Funktionen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=de#sending-messages){target="_blank"}

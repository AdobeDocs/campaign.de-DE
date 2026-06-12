---
title: Pixel für E-Mail-Tracking und CNIL-Anleitung
description: Verstehen der aktualisierten CNIL-Anleitung zu E-Mail-Tracking-Pixeln und den Adobe Campaign-Funktionen, die Compliance-Bemühungen unterstützen können.
feature: Overview
role: User
level: Beginner
hide: true
source-git-commit: b285c321f3b905150b31621941ea99608d627739
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 2%

---

# Grundlegendes zur aktualisierten CNIL-Anleitung zu E-Mail-Tracking-Pixeln

Dieser Beitrag dient nur zu Informationszwecken. Es ist keine Rechtsberatung und garantiert nicht, dass Sie das geltende Recht einhalten. Die unten beschriebenen Adobe Campaign-Produktfunktionen sind Bausteine, die eine konforme Implementierung unterstützen können, wenn sie entsprechend konfiguriert und betrieben werden. Jeder Kunde ist für die Feststellung und Erfüllung seiner Verpflichtungen nach geltendem Recht verantwortlich.

## Übersicht

Am 14. April 2026 veröffentlichte die _Commission nationale de l&#39;informatique et des libertés_ (CNIL), Frankreichs Datenschutzbehörde, eine [Empfehlung zur Verwendung von Tracking-Pixeln in E-Mails](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). In der Anleitung wird klargestellt, wann eine Zustimmung erforderlich ist, und die Bedeutung ordnungsgemäßer Zustimmungspraktiken für das E-Mail-Pixel-Tracking hervorgehoben. Diese Richtlinie könnte sich auf die Versandpraktiken von Entitäten auswirken, die E-Mails an Abonnenten mit Sitz in Frankreich versenden.

CNIL räumte Unternehmen ab dem Datum der Empfehlung einen Zeitraum von drei Monaten ein, um ihre E-Mail-Empfänger („Benutzer„) über das Vorhandensein der Tracking-Pixel, ihren Zweck und das Recht der Benutzer auf Opt-out zu informieren. Während dieser Übergangsphase wird von den Kunden erwartet, dass sie die Benutzer über das Pixel-Tracking informieren und ihnen bei Bedarf ein Opt-out anbieten. CNIL wird voraussichtlich nach dem 14. Juli 2026 mit Durchsetzungsmaßnahmen beginnen.

Während die CNIL und andere Regulierungsbehörden die Leitlinien zur Verfolgung von Pixeln und damit zusammenhängenden Problemen erläutern, wird Adobe weiterhin Aktualisierungen überwachen und Kunden über die technischen Funktionen von Adobe-Produkten informieren, die E-Mail-Marketing, einschließlich Adobe Campaign, unterstützen.

Adobe-Programme zur Ausführung von E-Mail-Marketing, einschließlich Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign und Marketo Engage, bieten Steuerelemente, mit denen Kunden das Öffnungs-Tracking auf Versand- oder E-Mail-Ebene verwalten können. Kunden sind dafür verantwortlich, ihre eigenen Compliance-Verpflichtungen gemäß den geltenden CNIL-Richtlinien und anderen Gesetzen zu bestimmen, aber diese Funktionen können die Bemühungen um die Einhaltung von Kundenrichtlinien unterstützen.

## Was ist ein E-Mail-Tracking-Pixel?

Ein E-Mail-Tracking-Pixel ist ein 1 x 1 transparentes Bild, das in die HTML einer E-Mail eingebettet ist. Wenn der E-Mail-Client des Empfängers dieses Bild lädt, pingt das Pixel einen Server, der Daten wie Zeitstempel, Gerätetyp, E-Mail-Client und manchmal eine IP-Adresse als ungefähren Speicherort aufzeichnet. Dieses Protokoll wird dann an den Datensatz eines Empfängers gebunden, sodass Marketing-Experten sehen können, ob eine E-Mail geöffnet wird.

## Kunden-Support

Kunden, die Unterstützung bei der Implementierung der oben beschriebenen Änderungen benötigen, können mit ihrem bestehenden Adobe-Ökosystem interagieren. Wenden Sie sich bei technischen Fragen zu den Funktionen von Adobe, auf die verwiesen wird, an Ihren Customer Success Manager oder technischen Kundenbetreuer.

## Adobe Campaign-Funktionen im Zusammenhang mit dem E-Mail-Tracking

Kunden können die nativen Tracking-, Schema- und Personalisierungsmechanismen von Adobe Campaign verwenden, um bei der Konfiguration der Architektur bestimmte Aspekte zu berücksichtigen, die den CNIL-Richtlinien entsprechen:

* **Klassifizierung des Versands.** Erweitern Sie `nms:delivery` mit einem `emailType`-Attribut (Authentifizierung, Nur-Zustellbarkeit, Transaktion, Marketing, öffentlicher Dienst, B2B-Interessentengewinnung). Die Klassifizierung bestimmt, welche Pixel ohne Zustimmung zulässig sind.
* **Einverständniserfassung.** Erweitern Sie `nms:recipient` mit einer zweckbezogenen Einverständnisstruktur, die die Formulierungsversion, den Zeitstempel, die Erfassungsquelle und den Ablauf enthält. Erweitern Sie Anmeldeformulare und Präferenzzentren, um Pixel-Einverständnis getrennt vom E-Mail-Opt-in zu erfassen.
* **Pixelemission.** Definieren Sie einen `NmsTracking_OpenFormula` pro Pixel-Zweck (Authentifizierung, Zustellbarkeit, Leistung, Profilerstellung, Betrugserkennung). Eine Versandtypologieregel wählt basierend auf dem emailType und der zweckgebundenen Zustimmung des Empfängers aus, welche Formeln ausgegeben werden sollen. Gestaltungsbausteine kapseln die Logik, sodass sie nicht in einzelnen Kreativen vorhanden ist.
* **Zurücknahme.** Fügen Sie jeder E **Mail-Fußzeile einen Link** Tracker-Einstellungen verwalten“ hinzu, der sich vom Abmelde-Link unterscheidet. Der Link verweist auf eine `nms:webApp` Landingpage, die über `idTracking` authentifiziert wurde. Der Empfänger widerruft die Zustimmung mit einem Klick, ohne seine E-Mail-Adresse erneut einzugeben. Ein Filterschritt, der zum standardmäßigen **Tracking**-Workflow hinzugefügt wurde, verhindert, dass zuvor gesendete E-Mails nach dem Widerruf erneut geöffnet werden.
* **Einverständnisnachweis.** Erfassen Sie jedes Einverständnisereignis in einem Protokoll, das nur angehängt wird (z. B. einem Namespace der `pix:consentLog`-Erweiterung), wobei die Formulierungsversion nach Änderungen des Wortlauts separat gespeichert wird, um sie abzurufen. Legen Sie das Protokoll über den Adobe Campaign-Explorer und als periodischen Export an.
* **Governance durch erneute Anfragen.** Ein `lastPixelRefusalDate` und eine Filtertypologieregel verhindern eine erneute Abfrage für mindestens sechs Monate nach einer Ablehnung. Ein periodischer Workflow kann Ihnen bei der Verwaltung des Einverständnisablaufs helfen.
* **Berichterstellung.** Vorhandene Adobe Campaign-Berichte werden weiterhin für die neuen Felder (urlCategory, emailType, die Einverständnisflags) ohne Code-Änderungen ausgeführt.

Weitere Informationen zum E-Mail-Tracking in Adobe-Programmen zur Ausführung von E-Mail-Marketing finden Sie in der Dokumentation hier:

| Produkt | Dokumentationsreferenz |
|---|---|
| Campaign v8 | [Nachrichten-Tracking](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [Erste Schritte mit dem Nachrichten-Tracking](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [Konfigurieren des E-Mail-Kanals](https://experienceleague.adobe.com/en/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [Dokumentation zum Nachrichten-Tracking](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [Deaktivieren des Trackings für einen E-Mail-Link](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [Dokumentation zu E-Mail-Einstellungen](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |


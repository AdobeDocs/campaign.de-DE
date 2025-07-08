---
product: campaign
title: Über die Zustellbarkeit in Adobe Campaign Classic
description: Erfahren Sie mehr über die Verwaltung der Zustellbarkeit in Adobe Campaign 
feature: Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: dcd3a9f9-5fe9-4c28-a4a5-5aed67b036ab
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 98%

---

# Steuern der Nachrichteninhalte{#control-message-content}

Um sicherzustellen, dass Ihre E-Mails Ihre Empfänger erreichen und um Ihre E-Mail-Zustellrate zu verbessern, müssen sie eine Reihe von Regeln beachten. Andernfalls kann der Inhalt bestimmter Nachrichten als Spam eingestuft werden. Adobe Campaign stellt Ihnen mehrere Tools zur Verfügung, die Ihnen ermöglichen, Ihre Inhalte entsprechend diesen Regeln zu erstellen.

Befolgen Sie beim Entwerfen Ihrer Nachrichteninhalte die folgenden Grundsätze:

* [Absenderadresse](#sender-address): Die Adresse muss den Absender explizit identifizieren. Die Domain muss im Besitz des Absenders und auf ihn registriert sein. Die Domain-Registrierung darf nicht privat erfolgen.
* [Personalisierung](#personalization): Die Personalisierung von Inhalten und das Definieren einer Sendezeit pro Empfänger erhöhen die Wahrscheinlichkeit, dass Ihre Nachricht geöffnet wird.
* Bilder und Text: Achten Sie auf ein angemessenes Verhältnis zwischen Text und Bildern (z. B. 60 % Text und 40 % Bilder).
* [Abmelde-Link](#opt-out) und Landingpage: Ein Abmelde-Link muss unbedingt vorhanden sein. Er muss gut sichtbar und gültig sein; außerdem muss das Formular funktionieren.
* Vorschau: Verwenden Sie die von Adobe Campaign angebotenen Tools, um den Inhalt Ihrer E-Mails zu überprüfen und zu optimieren ([Inbox Rendering](#message-responsiveness), [SpamAssassin](#spamassassin)).

Weitere Tipps zur Optimierung der Zustellbarkeit beim Entwerfen von Inhalten finden Sie im [Adobe-Handbuch mit den Best Practices zur Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=de){target="_blank"}.

>[!NOTE]
>
>Weitere Informationen zum Bearbeiten von E-Mail-Inhalten finden Sie unter [Definieren des E-Mail-Inhalts](defining-the-email-content.md).

## Absenderadresse {#sender-address}

Bestimmte Internet-Anbieter überprüfen die Gültigkeit der Absenderadresse (**[!UICONTROL Von]**), bevor sie Nachrichten annehmen. Eine fehlerhafte Adresse kann dazu führen, dass sie vom empfangenden Server abgelehnt wird.

Sie müssen sicherstellen, dass auf Instanzebene (Menü **[!UICONTROL Tools > Erweitert > Bereitstellungassistent...]**) oder in den am häufigsten verwendeten Szenarien eine richtige Adresse angegeben wird.

Weitere Informationen zur Bestimmung der Absenderadresse finden Sie auf [dieser Seite](defining-the-email-content.md#sender).

## Personalisierung {#personalization}

Um das Nutzererlebnis zu verbessern und Empfängerinnen und Empfänger dazu zu bewegen, Ihre E-Mail zu öffnen, ermöglicht Adobe Campaign Ihnen, Ihre Nachrichten zu personalisieren.

Weitere Informationen zur Verwendung von Personalisierungsfeldern in Adobe Campaign finden Sie in [diesem Abschnitt](personalization-fields.md).

## Ausschluss-Link und -Formular {#opt-out}

Bei der Analyse einer Nachricht wird standardmäßig von einer [Typologieregel](../../automation/campaign-opt/apply-rules.md) überprüft, ob ein Ausschluss-Link vorhanden ist. Ist dies nicht der Fall, wird ein Warnhinweis erstellt. Sie können diese Regel ändern, sodass anstatt eines einfachen Warnhinweises ein Fehler angezeigt wird und ein Versand ohne diesen Link nicht möglich ist.

Sie müssen vor jedem Versand überprüfen, ob der Abmelde-Link korrekt funktioniert. Achten Sie beispielsweise beim Testversand darauf, dass der Link gültig ist, das Formular online ist und dass sich durch seine Validierung der Wert des Feldes **[!UICONTROL Diese Person nicht mehr kontaktieren]** auf **[!UICONTROL Ja]** ändert. Führen Sie diese Prüfung regelmäßig durch, da bei der manuellen Eingabe des Links oder der Änderung des Formulars Fehler auftreten können.

[In diesem Abschnitt](personalization-blocks.md#ootb-personalization-blocks) erfahren Sie, wie man einen Ausschluss-Link einfügt.

Wenn ein Abmeldeproblem erkannt wird, nachdem der Versand bereits begonnen hat, können Sie diejenigen, die auf den Ausschluss-Link klicken, manuell abmelden (z. B. über die gebündelte Aktualisierung), selbst wenn sie ihre Auswahl nicht bestätigen konnten.

Generell empfehlen wir, Empfänger nicht daran zu hindern, sich abzumelden, indem Sie von ihnen verlangen, Felder wie beispielsweise ihre E-Mail-Adresse oder ihren Namen auszufüllen. Das Formular sollte nur eine einzige Validierungsschaltfläche aufweisen und die Abstimmung sollte ausschließlich in der verschlüsselten Kennung stattfinden.

Das Anfordern einer zusätzlichen Bestätigung ist keine zuverlässige Methode: Ein Benutzer kann zwei E-Mail-Adressen in dasselbe Postfach umgeleitet haben (z. B. Vorname.Nachname@club.com und Vorname.Nachname@internet-club.com). Wenn sich der Empfänger nur an die erste Adresse erinnert und sich über eine an die andere Adresse gesendete Nachricht abmelden möchte, würde das Formular dies ablehnen, da die verschlüsselte Kennung und die eingegebene E-Mail-Adresse nicht übereinstimmen.

## Inbox Rendering {#message-responsiveness}

Bevor Sie Ihre Nachricht senden, können Sie testen, wie responsiv Ihre Nachricht ist, indem Sie überprüfen, wie sie auf verschiedenen Geräten aussehen wird. So wird sichergestellt, dass sie in unterschiedlichen Webclients, Webmails und Geräten optimal dargestellt wird.

Zu diesem Zweck unterstützt Adobe Campaign das Rendering und stellt dessen Ergebnisse in einem entsprechenden Bericht zur Verfügung. Dadurch können Sie sich ansehen, wie Nachrichten je nach verwendetem Empfangsmedium beim Empfänger dargestellt werden.

Weiterführende Informationen dazu finden Sie im Abschnitt [Inbox Rendering](inbox-rendering.md).

## SpamAssassin {#spamassassin}

Adobe Campaign bietet die Möglichkeit der Nutzung von SpamAssassin, einem Filterprogramm, das E-Mails eine Punktzahl zuordnet. Diese gibt Auskunft über die Wahrscheinlichkeit, von Anti-Spam-Programmen als unerwünscht eingestuft zu werden.

Auf diese Weise kann vor dem Versandstart im Tab **[!UICONTROL Vorschau]** das Spam-Risiko ausgewertet werden. Ein Hinweis zeigt die erfolgreiche Durchführung der Anti-Spam-Prüfung an.

Weitere Informationen finden Sie in diesem [Abschnitt](spamassassin.md).

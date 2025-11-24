---
title: Konfigurieren von E-Mail-Parametern in Adobe Campaign
description: Erfahren Sie mehr zu den Optionen und Einstellungen, die spezifisch für den E-Mail-Versand in Adobe Campaign sind.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 6b70ad987b828dc1c17bc4f0683046be4eff0408
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 70%

---

# E-Mail-Parameter {#email-parameters}

In diesem Abschnitt werden die in den Versandeigenschaften verfügbaren Optionen und Parameter beschrieben, die für den E-Mail-Versand spezifisch sind.

## Verwenden von E-Mail BCC {#email-bcc}

Sie können Adobe Campaign so konfigurieren, dass eine Kopie der von der Plattform gesendeten E-Mails beibehalten wird. Die Option wird auf [dieser Seite](email-bcc.md) detailliert beschrieben.

## Auswählen von Nachrichtenformaten {#selecting-message-formats}

Sie können das Format der gesendeten E-Mail-Nachrichten ändern. Bearbeiten Sie hierzu die Versandeigenschaften und klicken Sie auf die Registerkarte **[!UICONTROL Versand]**.

![](assets/email-message-format.png)

Im unteren Bereich des Fensters haben Sie die Wahl zwischen:

* **[!UICONTROL Empfängerangaben berücksichtigen]** (Standardmodus)

  Das Nachrichtenformat wird anhand der im Empfängerprofil im Feld **[!UICONTROL E-Mail-Format]** gespeicherten Informationen bestimmt. Wenn ein Empfänger ein bestimmtes Format angegeben hat, wird ihm die Nachricht in diesem Format zugestellt. Wenn das Feld leer ist, wird die Nachricht im Multipart-Alternative-Format versandt (siehe unten).

* **[!UICONTROL E-Mail-Programm des Empfängers das beste Format wählen lassen]**

  Die Nachricht enthält beide Formate: Text und HTML. Das beim Empfänger angezeigte Format hängt von der Konfiguration des E-Mail-Programms ab (Multipart-Alternative).

  >[!IMPORTANT]
  >
  >Diese Option umfasst beide Versionen der Nachricht. Dadurch verringert sich der Versanddurchsatz, da die Nachricht größer ist.

* **[!UICONTROL Alle Nachrichten im Textformat senden]**

  Die Nachricht wird im Textformat gesendet. Das HTML-Format wird nicht gesendet, sondern nur für die Mirrorseite verwendet, auf die ein Empfänger gelangt, wenn er auf den entsprechenden Link in der Nachricht klickt.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Festlegen der Zeichencodierung {#character-encoding}

Auf dem Tab **[!UICONTROL SMTP]** der Versandparameter können Sie im Abschnitt **[!UICONTROL Zeichenkodierung]** eine bestimmte Kodierung festlegen.

Die Standardkodierung ist UTF-8. Wenn einige E-Mail-Anbieter Ihrer Empfänger keine UTF-8-Standardkodierung unterstützen, sollten Sie eine bestimmte Kodierung einrichten, sodass Sonderzeichen den Empfängern Ihrer E-Mails korrekt angezeigt werden.

Gehen wir davon aus, dass Sie eine E-Mail mit japanischen Zeichen versenden möchten. Um sicherzustellen, dass Ihren Empfängern in Japan alle Zeichen korrekt dargestellt werden, sollten Sie eine Kodierung verwenden, die anstelle der standardmäßigen UTF-8-Kodierung japanische Zeichen unterstützt.

Wählen Sie dazu die Option **[!UICONTROL Nachrichtenkodierung erzwingen (Codepage)]** im Abschnitt **[!UICONTROL Zeichenkodierung]** und wählen Sie eine Kodierung aus der angezeigten Dropdown-Liste.

![](assets/email-smtp-encoding.png)

## Verwalten von Bounce Messages {#managing-bounce-emails}

Auf der Registerkarte **[!UICONTROL SMTP]** der Versandeigenschaften lässt sich der Umgang mit Bounce Messages konfigurieren.

* **[!UICONTROL Fehler-an-Adresse]**: Standardmäßig gehen Bounce Messages im Standard-Fehlerpostfach der Plattform ein. Es besteht jedoch die Möglichkeit, für einen Versand durch Abwählen der Standardoption eine spezifische Fehleradresse anzugeben.

* **[!UICONTROL Bounce-Adresse]**: Sie können auch eine andere Adresse definieren, an die die nicht verarbeiteten Bounce Messages weitergeleitet werden. Diese Adresse ermöglicht es, die Gründe für das Bounce-Verhalten zu untersuchen, wenn E-Mails von der Anwendung nicht automatisch qualifiziert werden konnten.

Jedes dieser Felder kann mithilfe des dedizierten Symbols personalisiert werden. In [diesem Abschnitt](personalization-fields.md) erfahren Sie mehr über Personalisierungsfelder.

![](assets/email-smtp-bounce.png)

Weitere Informationen zur Bounce-Message-Verwaltung finden Sie in [diesem Abschnitt](delivery-failures.md#bounce-mail-management).

## Abmelde-Liste mit einem Klick aktivieren {#one-click-list-unsubscribe}

Die Abmelde-URL mit einem Klick ist ein Link oder eine Schaltfläche neben den E-Mail-Absenderinformationen, über den bzw. die Empfänger Ihre Mailing-Listen sofort mit einem einzigen Klick abmelden können. <!--[Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}-->

Es wird als **Abmelden**-Link in den E-Mail-Schnittstellen der ISPs angezeigt. Beispiel:

![](assets/email-list-unsubscribe-example.png)

Das Hinzufügen eines SMTP-Headers namens List-Unsubscribe ist obligatorisch, um eine optimale Zustellbarkeitsverwaltung zu gewährleisten, und kann als Alternative zum Symbol „Als SPAM melden“ verwendet werden. Die Verwendung dieser Funktion senkt die Beschwerderate und trägt zum Schutz Ihrer Reputation bei.

>[!IMPORTANT]
>
>Um die Abmelde-URL mit einem Klick in der E-Mail-Kopfzeile anzuzeigen, muss der E-Mail-Client der Empfänger diese Funktion unterstützen.

Um diese Funktion zu aktivieren, wählen Sie die Option **[!UICONTROL Hinzufügen der Kopfzeile „Ein-Klick-Liste]** auf der Registerkarte **[!UICONTROL SMTP]** der Versandeigenschaften aus.

>[!NOTE]
>
>Standardmäßig ist diese Option aktiviert.

![](assets/email-smtp-list-unsubscribe.png)

<!--
>[!WARNING]
>
>If you uncheck this option in the delivery template, it will still be enabled by default in the deliveries created from this template. You need to enable the option again at the delivery level.-->

Je nach E-Mail-Client und der Methode, die er zum Opt-out verwendet, kann das Klicken auf den **Abmelden**-Link in der E-Mail-Kopfzeile die folgenden Auswirkungen haben:

* Wenn der E-Mail-Client die Methode **Ein-Klick** Listen-Abmelden verwendet, wird der Empfänger direkt abgemeldet.

  >[!NOTE]
  >
  >Wichtige ISPs wie Google und Yahoo! Absender werden aufgefordert, die Regeln **Liste mit einem Klick - Abmelden** einzuhalten.

* Wenn der E-Mail-Client One-Click List-Unsubscribe nicht unterstützt, kann er weiterhin die **„mailto“** List-Unsubscribe-Methode verwenden, die eine vorausgefüllte E-Mail an die in der E-Mail-Kopfzeile angegebene Abmelde-Adresse sendet.

  Sie können die Adresse entweder explizit in der Kopfzeile angeben oder eine dynamische Adresse verwenden (z. B. mithilfe von &lt;%=errorAddress%> oder der Option &#39;NmsEmail_DefaultErrorAddr&#39;), die über den Bereitstellungsassistenten festgelegt werden kann.

>[!NOTE]
>
>Sie können auch die Methoden [One-Click List-Unsubscribe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#one-click-list-unsubscribe){target="_blank"} und [„mailto“ List-Unsubscribe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#mailto-list-unsubscribe){target="_blank"} manuell festlegen. Die detaillierten Schritte werden im Experience Cloud [Handbuch mit den Best Practices zur Zustellbarkeit](https://experienceleague.adobe.com/de/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#list-unsubscribe){target="_blank"} beschrieben.


## Hinzufügen von SMTP-Headern {#adding-smtp-headers}

Sie können Ihren Sendungen auch SMTP-Header hinzufügen. Verwenden Sie dazu den entsprechenden Abschnitt der Registerkarte **[!UICONTROL SMTP]** im Versand.

Das in diesem Fenster eingegebene Skript muss pro Zeile einen Header im Format **Name:value** enthalten.

Werte werden bei Bedarf automatisch verschlüsselt.

>[!IMPORTANT]
>
>Das Hinzufügen eines Skripts zum Einfügen zusätzlicher SMTP-Header ist fortgeschrittenen Benutzern vorbehalten.
>
>Die Syntax des Scripts muss die Anforderungen für diesen Inhaltstyp (keine überflüssigen Leerzeichen, keine Leerzeilen usw.) erfüllen.

![](assets/email-smtp-headers.png)


## Generieren einer Mirrorseite {#generating-mirror-page}

Eine Mirrorseite ist eine HTML-Seite, die über einen Webbrowser online abgerufen werden kann und deren Inhalt mit dem der E-Mail identisch ist. Dies kann nützlich sein, wenn bei Ihren Empfängerinnen und Empfängern Rendering-Probleme oder fehlerhafte Bilder auftreten, wenn sie versuchen, Ihre E-Mail in ihrem Posteingang anzuzeigen.

Weitere Informationen dazu, wie Sie einen Link zur Mirrorseite einfügen, finden Sie in [diesem Abschnitt](mirror-page.md).

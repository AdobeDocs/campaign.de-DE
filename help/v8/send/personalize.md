---
title: Erste Schritte mit der Personalisierung
description: Erfahren Sie, wie Sie Nachrichteninhalte personalisieren können
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 6d54f072ad0e67b435cd6e03433fa9ddd0794dea
workflow-type: ht
source-wordcount: '480'
ht-degree: 100%

---

# Erste Schritte mit der Personalisierung {#personalize-content}

Um jede Marketing-Kampagne optimal zu nutzen, bietet Ihnen Adobe Campaign eine Möglichkeit, benutzerdefinierte Inhalte bereitzustellen, die Kundinnen und Kunden auf ihrer Ebene ansprechen. Basierend auf den Profildaten sind Personalisierungsfunktionen zum Erstellen eines benutzerdefinierten Erlebnisses für verschiedene Gruppen und Einzelpersonen verfügbar: Sie können Ihre Nachrichten an jede Empfängerin und jeden Empfänger einzeln anpassen, indem Sie die vorhandenen Daten und Informationen nutzen. Dies können Vornamen, Interessen, Wohnorte, bisherige Käufe und vieles mehr sein.

Adobe Campaign vereinfacht die Personalisierung: Sie können mit einer einzigen [Nachrichtenvorlage](create-templates.md) verschiedene Arten von Inhalten anzeigen, die für jede Empfängerin und jeden Empfänger angepasst werden. Nehmen Sie in Ihre Transaktionsnachrichten, wie z. B. E-Mails zur Kaufbestätigung oder zum Warenkorbabbruch, Produktlisteninformationen für jeden Kontakt in eine E-Mail-Vorlage auf.


## Personalisierungsstrategien {#personalization-strategy}

Verwenden Sie Campaign, um dynamische Inhalte zu erstellen und personalisierte Nachrichten zu versenden. Personalisierungsfunktionen können kombiniert werden, um Ihre Nachrichten zu verbessern und ein individuelles Benutzererlebnis zu schaffen.

Sie können den Nachrichteninhalt wie folgt personalisieren:

* Einfügen von dynamischen **Personalisierungsfeldern**

  Personalisierungsfelder werden für die oberste Ebene der Nachrichtenpersonalisierung verwendet. Sie können jedes in der Datenbank verfügbare Feld aus dem Personalisierungseditor auswählen. Für einen Versand können Sie jedes Feld auswählen, das sich auf die Empfängerin oder den Empfänger, die Nachricht oder den Versand bezieht. Diese Personalisierungsattribute können in die Betreffzeile oder in den Text Ihrer Nachrichten eingefügt werden. [Weitere Informationen](personalization-fields.md).

  Mit der folgenden Syntax wird die Stadt des Empfängers bzw. der Empfängerin in Ihren Inhalt eingefügt: &lt;%= recipient.location.city %>.

* Einfügen von vordefinierten **Inhaltsbausteinen**

  Campaign verfügt über eine Reihe von Gestaltungsbausteinen, die ein bestimmtes Rendering enthalten, das Sie in Ihre Sendungen einfügen können. Sie können zum Beispiel ein Logo, eine Grußbotschaft oder einen Link zur Mirrorseite der Nachricht hinzufügen. Inhaltsbausteine sind über einen eigenen Eintrag im Personalisierungseditor verfügbar. [Weitere Informationen](personalization-blocks.md).

* Erstellen **bedingter Inhalte**

  Konfigurieren Sie bedingte Inhalte, um beispielsweise eine dynamische Personalisierung basierend auf dem Empfängerprofil hinzuzufügen. Textblöcke und/oder Bilder werden eingefügt, wenn eine bestimmte Bedingung erfüllt ist. [Weitere Informationen](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Schutzmechanismen und Empfehlungen{#perso-guardrails}

### Personalisierungs-Timeout{#perso-timeout}

Um die Versandsicherheit zu erhöhen, können Sie für die Personalisierungsphase einen Timeout-Zeitraum festlegen.

Wählen Sie auf dem Tab **[!UICONTROL Versand]** der **[!UICONTROL Versandeigenschaften]** einen Maximalwert in Sekunden für die Option **[!UICONTROL Maximale Laufzeit der Personalisierung]** aus.

Wenn die Personalisierungsphase während der Vorschau oder beim Senden die in diesem Feld angegebene maximale Zeit überschreitet, wird der Prozess mit einer Fehlermeldung abgebrochen und der Versand schlägt fehl.

Der Standardwert ist 5 Sekunden.

Wenn Sie diese Option auf 0 setzen, gilt für die Personalisierungsphase keine Zeitbeschränkung.


### Interne Variablen{#internal-variables}

Bei den folgenden Variablen handelt es sich um interne Variablen, die im Rahmen der Personalisierung verwendet werden können, aber nicht abgeändert werden dürfen: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Tutorial-Video {#personalization-video}

Machen Sie sich mit den verschiedenen Arten von dynamischem Content vertraut und erfahren Sie, wie Sie Gestaltungsbausteine und bedingte Anweisungen erstellen und auf einen Versand anwenden.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)

---
title: Personalisieren von Inhalten
description: Erfahren Sie, wie Sie den Nachrichteninhalt personalisieren.
feature: Personalization
role: User
level: Beginner
source-git-commit: 4885f15c71d2be27dc32a239fb22abc3a96503c7
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 59%

---

# Personalisieren von Inhalten {#personalize-content}

Um jede Marketing-Kampagne optimal zu nutzen, bietet Ihnen Adobe Campaign eine Möglichkeit, benutzerdefinierte Inhalte bereitzustellen, die Kunden auf ihrer Ebene ansprechen. Basierend auf den Profildaten, Personalisierungsfunktionen zum Erstellen eines benutzerdefinierten Erlebnisses für verschiedene Gruppen und Einzelpersonen: Sie können Ihre Nachrichten an jeden einzelnen Empfänger anpassen, indem Sie die vorhandenen Daten und Informationen nutzen. Es kann sein Vorname, Interessen, wo sie leben, was sie kauften und vieles mehr.

Adobe Campaign vereinfacht die Personalisierung: Sie können verschiedene Arten von Inhalten anzeigen, die für jeden Empfänger mit einem einzigen [E-Mail-Vorlage](create-templates.md). Schließen Sie in Ihren Transaktionsnachrichten, wie z. B. E-Mails zur Kaufbestätigung oder zum stehen gelassenen Warenkorb, Produktlistungsinformationen für jede Person in einer E-Mail-Vorlage ein.


## Personalisierungsstrategien {#personalization-strategy}

Verwenden Sie Campaign, um dynamische Inhalte zu erstellen und personalisierte Nachrichten zu versenden. Personalisierungsfunktionen können kombiniert werden, um Ihre Nachrichten zu verbessern und ein benutzerdefiniertes Benutzererlebnis zu schaffen.

Sie können den Nachrichteninhalt wie folgt personalisieren:

* Einfügen von dynamischen **Personalisierungsfeldern**

   Personalisierungsfelder werden für die oberste Ebene der Nachrichtenpersonalisierung verwendet. Sie können jedes in der Datenbank verfügbare Feld aus dem Personalisierungseditor auswählen. Für einen Versand können Sie jedes Feld auswählen, das sich auf die Empfängerin oder den Empfänger, die Nachricht oder den Versand bezieht. Diese Personalisierungsattribute können in die Betreffzeile oder in den Text Ihrer Nachrichten eingefügt werden. [Weitere Informationen](personalization-fields.md).

   Mit der folgenden Syntax wird die Stadt des Empfängers bzw. der Empfängerin in Ihren Inhalt eingefügt: &lt;%= recipient.location.city %>.

* Einfügen von vordefinierten **Inhaltsbausteinen**

   Campaign verfügt über eine Reihe von Gestaltungsbausteinen, die ein bestimmtes Rendering ermöglichen, das Sie in Ihre Sendungen einfügen können. Sie können zum Beispiel ein Logo, eine Grußbotschaft oder einen Link zur Mirror-Seite der Nachricht hinzufügen. Inhaltsbausteine sind über einen eigenen Eintrag im Personalisierungseditor verfügbar. [Weitere Informationen](personalization-blocks.md).

* Erstellen **Bedingter Inhalt**

   Konfigurieren Sie bedingte Inhalte, um beispielsweise eine dynamische Personalisierung basierend auf dem Empfängerprofil hinzuzufügen. Textblöcke und/oder Bilder werden eingefügt, wenn eine bestimmte Bedingung wahr ist. [Weitere Informationen](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Limits und Empfehlungen{#perso-guardrails}

### Personalisierungszeitlimit{#perso-timeout}

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
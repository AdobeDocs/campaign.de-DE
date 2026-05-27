---
title: Hinzufügen von Personalisierungsfeldern
description: Erfahren Sie, wie Sie Personalisierungsdaten in Ihren Nachrichteninhalt einfügen
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
TQID: https://experienceleague.adobe.com/9TZEv5GZwgyl5SJkod5GRaWGgMJMls3iNSVqE09BT7M
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 83%

---

# Hinzufügen von Personalisierungsfeldern{#personalization-fields}

Verwenden Sie Personalisierungsfelder, um personalisierte Inhalte auf Basis der von Ihnen für eine Empfängerin oder einen Empfänger festgelegten Regeln einzeln bereitzustellen.

Ein Personalisierungsfeld ist eine Referenz für einzelne Datenfelder, die bei der Personalisierung eines Versands für einen bestimmten Empfänger verwendet wird. Der tatsächliche Datenwert wird während der Versandanalyse eingefügt.

![Beispiel für die Nachrichtenpersonalisierung](assets/perso-name-sample.png)

## Syntax

Ein Personalisierungs-Tag hat immer die folgende Syntax: `<%=table.field%>`.

Um beispielsweise den in der Empfängertabelle gespeicherten Empfängernamen einzufügen, verwendet das Personalisierungsfeld die Syntax `<%= recipient.lastName %>`.

>[!CAUTION]
>
>Inhalt von Personalisierungsfeldern darf 1.024 Zeichen nicht überschreiten.

## Personalisierungsfeld einfügen {#insert-a-personalization-field}

Klicken Sie zum Einfügen von Personalisierungsfeldern auf das Symbol der Dropdown-Liste, das für jedes Kopfzeilen-, Betreff- und Nachrichtentextfeld zur Verfügung steht.

![Einfügen eines Personalisierungsfelds](assets/perso-field-insert.png)

Die Personalisierungsfelder werden eingefügt und können von Adobe Campaign interpretiert werden: Bei der Nachrichtenvorbereitung werden die Felder durch den Wert für eine bestimmte Empfängerin bzw. einen bestimmten Empfänger ersetzt.

![Personalisierungsfelder in einer E-Mail](assets/perso-fields-in-msg.png)

Diese Ersetzung kann dann auf der Registerkarte **[!UICONTROL Vorschau]** getestet werden.

<!--Learn more about message preview in [this page]().-->

## Anwendungsfall: Personalisieren des E-Mail-Betreffs {#personalization-fields-uc}

Im folgenden Anwendungsbeispiel erfahren Sie, wie Sie den Betreff und Text einer E-Mail mit Empfängerdaten personalisieren:

1. Erstellen Sie einen neuen Versand oder öffnen Sie einen vorhandenen E-Mail-Versand.
1. Navigieren Sie zum Link **[!UICONTROL Betreff]**, um den Betreff der Nachricht zu bearbeiten.
1. Geben Sie z. B. den Text **Sonderangebot für** ein. Nutzen Sie nun die Schaltfläche in der Symbolleiste, um ein Personalisierungsfeld einzufügen. Wählen Sie **[!UICONTROL Empfängerinnen und Empfänger > Titel]**.
1. Wiederholen Sie den Vorgang, um den Namen des Empfängers einzufügen. Fügen Sie Leerzeichen zwischen allen Personalisierungsfeldern ein.
1. Wählen Sie zur Bestätigung **[!UICONTROL OK]** aus.
1. Fügen Sie die Personalisierung in den Nachrichtentext ein. Klicken Sie dazu auf den Nachrichteninhalt und dann auf die Schaltfläche zum Einfügen des Felds.
1. Wählen Sie **[!UICONTROL Empfänger > Sonstige...]**.
1. Markieren Sie das Feld, das die gewünschte Information enthält, und klicken Sie auf **[!UICONTROL OK]**.
1. Klicken Sie auf **[!UICONTROL Vorschau]**, um das Personalisierungsergebnis anzuzeigen. Sie müssen einen Empfänger auswählen, um die Nachricht dieses Empfängers anzuzeigen.



## Anleitungsvideo {#personalization-field-video}

Im folgenden Video erfahren Sie, wie Sie der Betreffzeile und dem Inhalt eines E-Mail-Versands ein Personalisierungsfeld hinzufügen.

>[!VIDEO](https://video.tv.adobe.com/v/30081?captions=ger&quality=12)

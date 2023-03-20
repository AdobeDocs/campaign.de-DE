---
title: Personalisierungsfelder
description: Erfahren Sie, wie Sie Personalisierungsdaten in Ihren Nachrichteninhalt einfügen
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 42%

---


# Personalisierungsfelder {#personalization-fields}

Verwenden Sie Personalisierungsfelder, um personalisierte Inhalte auf Basis der von Ihnen für jeden Empfänger festgelegten Regeln einzeln bereitzustellen.

Ein Personalisierungsfeld ist eine Referenz für einzelne Datenfelder, die bei der Personalisierung eines Versands für einen bestimmten Empfänger verwendet wird. Der tatsächliche Datenwert wird während der Versandanalyse eingefügt.

![Beispiel für die Nachrichtenpersonalisierung](assets/perso-name-sample.png)

## Syntax

Ein Personalisierungs-Tag verwendet immer die folgende Syntax: `<%=table.field%>`.

Um beispielsweise den in der Empfängertabelle gespeicherten Empfängernamen einzufügen, verwendet das Personalisierungsfeld die `<%= recipient.lastName %>` Syntax.

>[!CAUTION]
>
>Inhalt von Personalisierungsfeldern darf 1.024 Zeichen nicht überschreiten.

## Personalisierungsfeld einfügen {#insert-a-personalization-field}

Um Personalisierungsfelder einzufügen, klicken Sie auf das Dropdown-Symbol, auf das Sie von einem beliebigen Header-, Betreff- oder Nachrichtentext aus zugreifen können.

![Personalisierungsfeld einfügen](assets/perso-field-insert.png)

Die Personalisierungsfelder werden eingefügt und können von Adobe Campaign interpretiert werden: bei der Nachrichtenvorbereitung werden die Felder durch den Wert für einen bestimmten Empfänger ersetzt.

![Personalisierungsfelder in einer E-Mail](assets/perso-fields-in-msg.png)

Dieser Austausch kann dann im **[!UICONTROL Vorschau]** Registerkarte.

<!--Learn more about message preview in [this page]().-->

## Anwendungsfall: E-Mail-Betreff personalisieren {#personalization-fields-uc}

Im folgenden Anwendungsbeispiel erfahren Sie, wie Sie einen E-Mail-Betreff und -Hauptteil mit Empfängerdaten personalisieren:

1. Erstellen Sie einen neuen Versand oder öffnen Sie einen bestehenden E-Mail-Versand.
1. Navigieren Sie zum **[!UICONTROL Betreff]** -Link, um den Betreff der Nachricht zu bearbeiten.
1. Geben Sie z. B. den Text &quot;**Sonderangebot für**&quot; ein. Nutzen Sie nun die Schaltfläche der Personalisierungsfelder und wählen Sie aus der Dropdown-Liste **[!UICONTROL Empfänger > Vorname]** aus.
1. Wiederholen Sie den Vorgang, um den Nachnamen der Empfänger einzufügen. Vergessen Sie die Leerzeichen zwischen den Personalisierungsfeldern nicht.
1. Wählen Sie zur Bestätigung **[!UICONTROL OK]** aus.
1. Im nächsten Schritt wird der Nachrichten-Textkörper angepasst. Klicken Sie dazu in das Inhaltsfeld der Nachricht und danach auf die Schaltfläche zum Einfügen von Personalisierungsfeldern.
1. Wählen Sie **[!UICONTROL Empfänger > Sonstige...]**.
1. Markieren Sie das Feld, das die gewünschte Information enthält, und klicken Sie auf **[!UICONTROL OK]**.
1. Klicken Sie nun auf den **[!UICONTROL Vorschau]**-Tab und wählen Sie einen Empfänger aus, um sich das Ergebnis der Personalisierung anzusehen.



## Tutorial-Video {#personalization-field-video}

Im folgenden Video erfahren Sie, wie Sie der Betreffzeile und dem Inhalt eines E-Mail-Versands ein Personalisierungsfeld hinzufügen.

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)


---
product: campaign
title: Kohärenzregeln
description: Kohärenzregeln
feature: Typology Rules
exl-id: dcb4ffcf-71e5-48a2-b0f7-42915a599652
TQID: 'https://experienceleague.adobe.com/KaybpQFNgtTiMgQOWX0-bNqPEMeWGWR8vb6qjZzr63k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 95%
---
# Kohärenzregeln{#consistency-rules}

Adobe Campaign garantiert konsistente Kommunikation dank einer Reihe von Regeln, die in Kampagnentypologien enthalten sind. Sie dienen der Steuerung der an Empfängerinnen und Empfänger gesendeten Sendungen, z. B. hinsichtlich Menge, Art, Relevanz usw.

**Kapazitätsregeln** können beispielsweise verhindern, dass die vom Nachrichtenversand betroffene Plattform überlastet wird. Beispielsweise dürfen Sonderangebote mit einem Download-Link nicht an zu viele Personen gleichzeitig gesendet werden, um den Server nicht zu überlasten; Telefonkampagnen dürfen die Verarbeitungskapazität von Callcentern usw. nicht überschreiten.

## Kontrollieren der Kapazität {#control-capacity}

Stellen Sie vor dem Versand von Nachrichten sicher, dass Ihr Unternehmen über genügend Kapazitäten (physische Infrastruktur und Callcenter-Kapazität) verfügt, um beispielsweise den Versand, die durch den Versand möglicherweise erzeugten eingehenden Nachrichten und die Anzahl der Anrufe, die beispielsweise an Abonnierende zu richten sind, zu verarbeiten.

Erstellen Sie hierfür Typologieregeln vom Typ **[!UICONTROL Kapazität]**.

Im folgenden Beispiel erstellen wir eine Typologieregel für eine telefonische Treuekampagne. Wir beschränken die Anzahl der Nachrichten auf 20 pro Tag, was der täglichen Verarbeitungskapazität eines Callcenters entspricht. Nachdem die Regel auf zwei Sendungen angewendet wurde, können wir den Verbrauch über Logs überwachen.

Gehen Sie wie folgt vor, um eine neue Kapazitätsregel zu erstellen:

1. Klicken Sie im Ordner **[!UICONTROL Administration > Kampagnen-Verwaltung > Typologieverwaltung > Typologieregeln]** auf **[!UICONTROL Neu]**.
1. Wählen Sie eine Regel vom Typ **[!UICONTROL Kapazität]** aus.

   ![](assets/campaign_opt_create_capacity_01.png)

1. Erstellen Sie in der Registerkarte **[!UICONTROL Kapazität]** die Verfügbarkeitszeilen. In unserem Beispiel sind dies Zeiträume, in denen Anrufe getätigt werden können. Wählen Sie einen Zeitraum von 24 Stunden aus und geben Sie als anfängliche Menge 150 ein, was bedeutet, dass das Callcenter 150 Anrufe pro Tag verarbeiten kann.

   ![](assets/campaign_opt_create_capacity_02.png)

   >[!NOTE]
   >
   >Die Verfügbarkeitszeilen dienen nur als Richtwerte. Sie können bei Bedarf jedoch auch festlegen, dass bei Erreichen der Kapazitätsbegrenzung Nachrichten ausgeschlossen werden. Näheres hierzu finden Sie in [diesem Abschnitt](#exclude-messages-when-capacity-limit-reached).

1. Weisen Sie diese Regel einer Typologie zu und referenzieren Sie die Typologie in Ihrer Sendung, damit die Kapazitätsregel von dieser angewendet wird. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](apply-rules.md#apply-a-typology-to-a-delivery).
1. Über die Tabs **[!UICONTROL Entnahmen]** und **[!UICONTROL Kapazität]** für diese Regel können Sie die Auslastung der Kapazitäten überwachen.

   Wenn eine Regel in einem Versand verwendet wird, zeigen die Spalten **[!UICONTROL Entnommen]** und **[!UICONTROL Verbleibend]** die verbrauchte Menge an, wie im unten stehenden Beispiel:

   ![](assets/campaign_opt_create_capacity_03.png)

   Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#monitor-consumption).

## Festlegen der maximalen Auslastung {#define-the-maximum-load}

Um die maximale Auslastung zu definieren, müssen Sie Verfügbarkeitszeilen festlegen. Dazu stehen zwei Optionen zur Verfügung: Sie können manuell [eine oder mehrere Verfügbarkeitszeilen erstellen](#add-availability-lines-one-by-one) oder ganze Verfügbarkeitsbereiche erstellen. Die Häufigkeit dieser Zeiträume kann automatisiert werden. [Weitere Informationen](#add-a-set-of-availability-lines).

### Verfügbarkeitszeilen einzeln hinzufügen {#add-availability-lines-one-by-one}

Um eine einzelne Verfügbarkeitszeile zu erstellen, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Option **[!UICONTROL Eine Verfügbarkeitszeile hinzufügen]** aus. Geben Sie den Verfügbarkeitszeitraum und die mögliche Belastung ein.

![](assets/campaign_opt_create_capacity_02.png)

Sie können die Ihrer Verarbeitungskapazität entsprechende Anzahl an Zeilen hinzufügen.

### Mehrere Verfügbarkeitszeilen hinzufügen {#add-a-set-of-availability-lines}

Um Verfügbarkeitszeiträume für einen bestimmten Zeitraum zu definieren, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Option **[!UICONTROL Mehrere Verfügbarkeitszeilen hinzufügen]** aus. Geben Sie eine Dauer für jeden Zeitraum und die Anzahl der zu erstellenden Zeiträume an.

Um die Zeitraumerstellung zu automatisieren, klicken Sie auf die Schaltfläche **[!UICONTROL Ändern]** und legen Sie die Planung der Zeiträume fest.

![](assets/campaign_opt_create_capacity_07.png)

Definieren wir beispielsweise einen Zeitplan zur Erstellung von Verfügbarkeitszeiträumen für alle Werktage mit einer Kapazität von 10 Anrufen pro Stunde zwischen 9 und 17 Uhr. Gehen Sie hierzu wie folgt vor:

1. Wählen Sie den Häufigkeitstyp und die Gültigkeitszeiträume aus:

   ![](assets/campaign_opt_create_capacity_08.png)

1. Geben Sie die Gültigkeitsdaten an:

   ![](assets/campaign_opt_create_capacity_09.png)

1. Überprüfen Sie die Konfiguration, bevor Sie sie beenden:

   ![](assets/campaign_opt_create_capacity_10.png)

Der Workflow **[!UICONTROL Planungen]** erstellt automatisch alle entsprechenden Zeilen.

![](assets/campaign_opt_create_capacity_12.png)

>[!NOTE]
>
>Wir empfehlen, Verfügbarkeitszeilen über Dateiimporte zu erstellen. Auf dieser Registerkarte können Sie Verbrauchszeilen anzeigen und überprüfen.

## Nachrichten bei Erreichen des Kapazitätslimits ausschließen {#exclude-messages-when-capacity-limit-reached}

Die Verfügbarkeitszeilen dienen nur als Richtwerte. Um überschüssige Nachrichten auszuschließen, aktivieren Sie die Option **[!UICONTROL Die die Kapazität übersteigenden Nachrichten aus der Zielgruppe ausschließen]**. Die Kapazität kann so nicht überschritten werden. Für dieselbe Population wie im vorherigen Beispiel dürfen Verbrauch und verbleibende Kapazität die ursprüngliche Menge nicht übersteigen:

![](assets/campaign_opt_create_capacity_04.png)

Die maximale Anzahl von Nachrichten, die verarbeitet werden können, ist gleichmäßig über den definierten Verfügbarkeitsbereich verteilt. Dies ist besonders für Callcenter von Bedeutung, da die Anzahl der Anrufe pro Tag begrenzt ist. Im Fall von E-Mail-Sendungen können Sie mit der Option **[!UICONTROL Sofortige Versandkapazität nicht begrenzen]** diesen Verfügbarkeitsbereich ignorieren und gleichzeitig Ihre E-Mails senden.

![](assets/campaign_opt_create_capacity_05.png)

>[!NOTE]
>
>Bei Überlastung werden die beizubehaltenden Nachrichten nach einer in den Versandeigenschaften bestimmten Formel ausgewählt.

![](assets/campaign_opt_create_capacity_06.png)

## Überwachen des Verbrauchs {#monitoring-consumption}

Kapazitätsregeln dienen standardmäßig lediglich Informationszwecken. Wählen Sie die Option **[!UICONTROL Die die Kapazität übersteigenden Nachrichten aus der Zielgruppe ausschließen]**, damit die festgelegte Menge nicht überschritten werden kann. Überschüssige Nachrichten werden dann automatisch von Sendungen ausgeschlossen, die diese Typologieregel anwenden.

Im Tab **[!UICONTROL Kapazität]** der Typologieregel haben Sie die Möglichkeit, in der **[!UICONTROL Verbraucht]**-Spalte die Inanspruchnahme der vorhandenen Ressourcen zu verfolgen.

![](assets/campaign_opt_create_capacity_04.png)

Klicken Sie zur Ansicht der Verbrauchszeilen auf den Tab **[!UICONTROL Verbrauch]** der Regel.

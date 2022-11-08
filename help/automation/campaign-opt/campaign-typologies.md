---
product: campaign
title: Erste Schritte mit Kampagnentypologien
description: Erfahren Sie, wie Sie Kampagnentypologien konfigurieren und implementieren
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 74%

---

# Erste Schritte mit Kampagnentypologien{#about-campaign-typologies}

**Campaign Optimization ist das Adobe Campaign-Modul, mit dem Sie die Durchführung von Sendungen steuern, filtern und überwachen können.** Um Konflikte zwischen Kampagnen zu vermeiden, kann Adobe Campaign verschiedene Kombinationen durch Anwendung spezifischer Beschränkungsregeln testen. Auf diese Weise werden ein ideal auf Kundenbedürfnisse abgestimmter Nachrichtenversand sowie eine kohärente Unternehmenskommunikation sichergestellt.

![](assets/do-not-localize/how-to-video.png) [Entdecken Sie diese Funktion im Video](#typologies-video).

>[!NOTE]
>
>Abhängig von Ihrem Abonnement ist die Kampagnenoptimierung entweder im Lieferumfang enthalten oder als Add-on verfügbar. Überprüfen Sie diesbezüglich Ihren Lizenzvertrag.

## Typologieregeln und Typologien {#typology-rules}

Campaign verfügt standardmäßig über integrierte Typologien und Typologieregeln.

Bei einer Typologie handelt es sich um eine Reihe von Überprüfungsregeln, die bei der Versandanalyse auf alle Nachrichten angewendet werden.

Eine Kampagnentypologie kann mehrere Typologieregeln enthalten, ein Versand kann jedoch nur eine Typologie referenzieren.

Integrierte Typologieregeln und Typologien sind im Knoten **[!UICONTROL Administration > Kampagnenverwaltung > Typologieverwaltung]** des Campaign-Explorers verfügbar.

Für jede Typologie können Sie auf der Registerkarte **[!UICONTROL Regeln]** die anzuwendenden Typologieregeln hinzufügen, löschen oder anzeigen.

![](assets/campaign_opt_rules_tab.png)

Nach ihrer Erstellung werden die Regeln in **Kampagnentypologien** gruppiert, die in den Sendungen zur Anwendung kommen. [Weitere Informationen](#apply-typologies).


Campaign verfügt über einen Standardsatz **Filter** und **Kontrolle** Regeln:

* **Filter** -Regeln verwendet werden, um einen Teil der Zielgruppe anhand von Kriterien auszuschließen. [Weitere Informationen](filtering-rules.md).
* **Kontrolle** -Regeln können Sie die Gültigkeit von Nachrichten vor dem Versand überprüfen. [Weitere Informationen](control-rules.md).

Das Campaign Optimization-Add-on bietet zwei zusätzliche Typen von **Typologieregeln**:

* **Druckregeln** erlauben es, die Marketing-Müdigkeit zu kontrollieren. [Weitere Informationen](pressure-rules.md).
* **Kapazitätsregeln** erlauben es, die Auslastung zu begrenzen, um optimale Verarbeitungsbedingungen zu gewährleisten. [Weitere Informationen](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Wenn Sie die **Interaction** -Modul zur Verwaltung von Angeboten verwenden, können Sie auch **Angebotsunterbreitung** Typologieregeln zur Steuerung des Angebotsvorschlags mithilfe von Unterbreitungsregeln. [Weitere Informationen](../../v8/interaction/interaction-offer.md#offer-presentation).


## Wichtige Schritte zum Erstellen und Verwenden von Typologien {#apply-typologies}

Gehen Sie wie folgt vor, um eine Typologie für Ihre Sendungen zu erstellen und zu verwenden:

1. Erstellen Sie Typologieregeln und eine Typologie, um die Regeln darin zu referenzieren.
Ausführliche Schritte dazu finden Sie im folgenden Abschnitt:

   * [Filterregeln](filtering-rules.md)
   * [Kontrollregeln](control-rules.md)
   * [Druckregeln](pressure-rules.md)
   * [Kapazitätsregeln](consistency-rules.md)

1. Konfigurieren Sie Ihren Versand so, dass er die von Ihnen erstellte Typologie verwendet. [Weitere Informationen](apply-rules.md#apply-a-typology-to-a-delivery).
1. Testen und steuern Sie das Verhalten mithilfe von Kampagnensimulationen. [Weitere Informationen](campaign-simulations.md).

Bei der Versandvorbereitung werden Empfänger ausgeschlossen, wenn ein bestimmtes Kriterium erfüllt ist. Sie können Protokolle überprüfen, um Ausschlüsse zu überwachen.

Anwendungsbeispiele zu Drucktypologieregeln finden Sie auf [dieser Seite](pressure-rules.md#use-cases-on-pressure-rules).

## Anleitungsvideos {#typologies-video}

### Einrichten der Ermüdungsverwaltung mithilfe von Typologieregeln

In diesem Video wird erläutert, wie die Ermüdungsverwaltung in Adobe Campaign mithilfe von Typologieregeln implementiert wird.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Einrichten der Ermüdungsverwaltung mithilfe vordefinierter Filter

Die Ermüdungsverwaltung steuert die Häufigkeit und Anzahl von Nachrichten, um eine Überforderung der Empfänger zu vermeiden. Wenn Sie das Modul zur Kampagnenoptimierung nicht in Ihrer Kampagneninstanz haben, können Sie einen vordefinierten Filter konfigurieren, der die Zielgruppe nach der Anzahl der empfangenen Nachrichten filtert.
In diesem Video wird erläutert, wie Sie die Ermüdungsverwaltung in Adobe Campaign mithilfe von Filtern implementieren.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)

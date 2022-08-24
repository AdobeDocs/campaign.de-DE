---
product: campaign
title: Erste Schritte mit Kampagnentypologien
description: Erfahren Sie, wie Sie Kampagnentypologien konfigurieren und implementieren
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Erste Schritte mit Kampagnentypologien{#about-campaign-typologies}

Campaign Optimization ist das Adobe Campaign-Modul, mit dem Sie die Durchführung von Sendungen steuern, filtern und überwachen können. Um Konflikte zwischen Kampagnen zu vermeiden, kann Adobe Campaign verschiedene Kombinationen durch Anwendung spezifischer Beschränkungsregeln testen. Auf diese Weise werden ein ideal auf Kundenbedürfnisse abgestimmter Nachrichtenversand sowie eine kohärente Unternehmenskommunikation sichergestellt.

![](assets/do-not-localize/how-to-video.png) [Entdecken Sie diese Funktion im Video](#typologies-video).

>[!NOTE]
>
>Abhängig von Ihrem Abonnement ist die Kampagnenoptimierung entweder im Lieferumfang enthalten oder als Add-on verfügbar. Überprüfen Sie diesbezüglich Ihren Lizenzvertrag.

## Typologieregeln und Typologien {#typology-rules}

Mit Adobe Campaign können vier Arten von **Typologieregeln** erstellt und angewendet werden:

* **Filterregeln** erlauben es, einen Teil der Zielgruppe anhand von Kriterien auszuschließen. [Weitere Informationen](filtering-rules.md).
* **Druckregeln** erlauben es, die Marketing-Müdigkeit zu kontrollieren. [Weitere Informationen](pressure-rules.md).
* **Kapazitätsregeln** erlauben es, die Auslastung zu begrenzen, um optimale Verarbeitungsbedingungen zu gewährleisten. [Weitere Informationen](consistency-rules.md#controlling-capacity).
* **Kontrollregeln** erlauben es, die Gültigkeit von Nachrichten zu überprüfen, bevor sie gesendet werden. [Weitere Informationen](control-rules.md).

Nach ihrer Erstellung werden die Regeln in **Kampagnentypologien** gruppiert, die in den Sendungen zur Anwendung kommen. [Weitere Informationen](#apply-typologies).

Eine Kampagnentypologie kann mehrere Typologieregeln enthalten, ein Versand kann jedoch nur eine Typologie referenzieren.

Integrierte Typologieregeln und Typologien sind im Knoten **[!UICONTROL Administration > Kampagnenverwaltung > Typologieverwaltung]** des Campaign-Explorers verfügbar.

Für jede Typologie können Sie auf der Registerkarte **[!UICONTROL Regeln]** die anzuwendenden Typologieregeln hinzufügen, löschen oder anzeigen.

![](assets/campaign_opt_rules_tab.png)

## Wichtige Schritte zum Anwenden von Typologien {#apply-typologies}

Gehen Sie wie folgt vor, um eine Typologie zu erstellen und auf Ihre Sendungen anzuwenden:

1. Erstellen Sie Typologieregeln und eine Typologie, um die Regeln darin zu referenzieren.
Ausführliche Schritte dazu finden Sie im folgenden Abschnitt:
   * [Druckregeln](pressure-rules.md)
   * [Filterregeln](filtering-rules.md)
   * [Kapazitätsregeln](consistency-rules.md)
   * [Kontrollregeln](control-rules.md)

1. Konfigurieren Sie Ihren Versand so, dass er die von Ihnen erstellte Typologie verwendet. [Weitere Informationen](apply-rules.md#apply-a-typology-to-a-delivery).
1. Testen und steuern Sie das Verhalten mithilfe von Kampagnensimulationen. [Weitere Informationen](campaign-simulations.md).

Bei der Versandvorbereitung werden Empfänger ausgeschlossen, wenn ein bestimmtes Kriterium erfüllt ist. Sie können Protokolle überprüfen, um Ausschlüsse zu überwachen.

Anwendungsbeispiele zu Drucktypologieregeln finden Sie auf [dieser Seite](pressure-rules.md#use-cases-on-pressure-rules).

## Anleitungsvideos {#typologies-video}

### Einrichten der Ermüdungsverwaltung mithilfe von Typologieregeln

In diesem Video wird erläutert, wie die Ermüdungsverwaltung in Adobe Campaign mithilfe von Typologieregeln implementiert wird.

>[!VIDEO](https://video.tv.adobe.com/v/25090?quality=12)

### Einrichten der Ermüdungsverwaltung mithilfe vordefinierter Filter

Die Ermüdungsverwaltung steuert die Häufigkeit und Anzahl von Nachrichten, um eine Überforderung der Empfänger zu vermeiden. Wenn Sie das Modul zur Kampagnenoptimierung nicht in Ihrer Kampagneninstanz haben, können Sie einen vordefinierten Filter konfigurieren, der die Zielgruppe nach der Anzahl der empfangenen Nachrichten filtert.
In diesem Video wird erläutert, wie Sie die Ermüdungsverwaltung in Adobe Campaign mithilfe von Filtern implementieren.

>[!VIDEO](https://video.tv.adobe.com/v/25091?quality=12)

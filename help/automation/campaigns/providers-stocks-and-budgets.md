---
product: campaign
title: Dienstleister, Lager und Budgets
description: Dienstleister, Lager und Budgets
feature: Budget Management, Campaigns
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1d4a98e6-af11-4645-864e-29aa5766d9d8
TQID: https://experienceleague.adobe.com/-9-67l8H1X7fXH708FbQc0Tu37mWAxpuFFvHfT9hQoo
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1924
ht-degree: 69%

---

# Dienstleister, Lager und Budgets{#providers-stocks-and-budgets}

Mit Adobe Campaign können Sie Dienstleister definieren, die an der Ausführung der Kampagnen beteiligt sind. Informationen über die Dienstleister und die damit verbundenen Kostenstrukturen werden vom Adobe Campaign-Administrator aus der Hauptansicht definiert. Der Dienstleister wird vom Versand aus referenziert, und seine Kostenstrukturen ermöglichen die Berechnung der mit diesem Versand verbundenen Kosten sowie die Verwaltung des betroffenen Lagers.

## Erstellung von Dienstleistern und deren Kostenstrukturen {#create-service-providers-and-their-cost-structures}

Jeder Dienstleister wird in einer Datei gespeichert, die seine Kontaktdaten, Dienstleistungsvorlagen und verbundene Aufträge enthält.

Dienstleister werden im Ordner **[!UICONTROL Administration > Kampagnen-Management]** des Campaign-Explorers konfiguriert.

Die während der Sendungen ausgeführten Aufträge werden von Dienstleistern ausgeführt, insbesondere für Briefpost und mobile Kanäle. Diese Dienstleister können beispielsweise am Drucken oder Verteilen von Nachrichten beteiligt sein. Diese Aufträge beinhalten Konfigurationen und Kosten, die für jeden Dienstleister spezifisch sind. Die Konfiguration von Dienstleistern erfolgt in vier Phasen:

1. Erstellung eines Dienstleisters in Adobe Campaign. [Weitere Informationen](#add-a-service-provider)

1. Definition der Kostenstellen und -strukturen der entsprechenden Dienstleistungsvorlagen. [Weitere Informationen](#define-cost-categories)

1. Konfiguration der Vorgänge. [Weitere Informationen](#configure-processes-associated-with-a-service).

1. Referenzierung des Dienstleisters auf Kampagnenebene. [Weitere Informationen](#associate-a-service-with-a-campaign).

### Erstellen eines Dienstleisters und seiner Kostenkategorien {#create-a-service-provider-and-its-cost-categories}

#### Hinzufügen eines Dienstleisters {#add-a-service-provider}

Sie können so viele Dienstleister erstellen, wie für Ihre Sendungen erforderlich sind. Gehen Sie wie folgt vor, um einen Dienstleister hinzuzufügen:

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Neu]** oberhalb der Liste der Dienstleister.
1. Geben Sie im unteren Abschnitt des Fensters Namen und Kontaktdaten des Dienstleisters an.

   ![](assets/add-a-supplier.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, um ihn der Liste hinzuzufügen.

#### Definieren der Kostenstellen {#define-cost-categories}

Sie können jetzt Dienstleistungsvorlagen mit jedem Dienstleister verknüpfen. In diesen Vorlagen müssen Sie zunächst die Kostenstellen und bei Bedarf den betreffenden Bestand festlegen. Anschließend können Sie über die Kostenstrukturen die Kostenberechnungsregeln für jede Kategorie erstellen. [Weitere Informationen](#define-the-cost-structure).

Eine Kostenkategorie ist eine Gruppe verschiedener Kosten, die für einen bestimmten Versandtyp (E-Mail, Briefpost, SMS usw.) verwendet werden können. Kostenstellen sind in den mit den Dienstleistern verknüpften Dienstleistungsvorlagen zusammengefasst. Jeder Dienstleister kann auf eine oder mehrere Dienstleistungsvorlagen verweisen.

Um eine Dienstleistungsvorlage zu erstellen und ihren Inhalt zu bestimmen, gehen Sie wie folgt vor:

1. Klicken Sie auf der Registerkarte **[!UICONTROL Services]** des Dienstleisters auf die Schaltfläche **[!UICONTROL Hinzufügen]** und geben Sie den Namen der Dienstleistungsvorlage ein.

   ![](assets/supplier-new-template.png)

1. Erstellen Sie die Kostenkategorien für jeden Prozesstyp (Versand durch Direkt-Mail/E-Mail/etc. oder Aufgabe). Klicken Sie dazu auf die Registerkarte **[!UICONTROL Kostenkategorien]** und dann auf die Schaltfläche **[!UICONTROL Hinzufügen]** und geben Sie die Parameter jeder Kostenkategorie an.

   ![](assets/add-cost-categories.png)

   * Geben Sie eine Bezeichnung für diese Kostenkategorie ein und wählen Sie den betreffenden Vorgangstyp aus: **[!UICONTROL Briefpost]**, **[!UICONTROL E-Mail]**, **[!UICONTROL Mobilgerät]** usw.
   * Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**, um die mit dieser Kostenkategorie verbunden Kostentypen zu bestimmen.
   * Bei Bedarf können Sie jedem Kostentyp eine Lagerposition hinzufügen, um den bestehenden Lagern automatisch die verwendeten Mengen anzurechnen.

     >[!NOTE]
     >
     >Die Lagerpositionen werden im Knoten **[!UICONTROL Lagerverwaltung]** definiert. [Weitere Informationen](#stock-and-order-management).

1. Sie können einen Wert für diese Kostenstelle vorab auswählen. Dieser wird dann der Standardwert in den Kostenstellen des Dienstleisters (anstelle eines leeren Werts). Aktivieren Sie dazu in der Spalte **[!UICONTROL Ausgewählt]** für den betreffende Kategorietyp die Option **Ja**:

   ![](assets/default-cost-type.png)

   Auf Versandebene wird der Wert standardmäßig vorgeschlagen.

### Definieren der Kostenstruktur {#define-the-cost-structure}

Eine Kostenstruktur spezifiziert für jede Kostenkategorie die anzuwendenden Berechnungsregeln.

Klicken Sie auf die Registerkarte **[!UICONTROL Kostenstruktur]**, um die Kostenberechnung für jede Kostenkategorie und jeden Kostentyp zu konfigurieren. Klicken Sie auf **[!UICONTROL Hinzufügen]** und geben Sie die Kostenstruktur ein.

![](assets/add-cost-structure.png)

* Um die Kostenstruktur zu erstellen, wählen Sie in den Dropdown-Listen den Nachrichtentyp, die betreffende Kostenkategorie sowie den Kostentyp aus, auf den die Berechnungsregel angewendet werden soll. Der Inhalt dieser Dropdown-Listen stammt aus den Informationen, die über die Registerkarte **[!UICONTROL Kostenkategorien]** eingetragen wurden.

  Sie müssen der Kostenstruktur einen Titel zuweisen. Standardmäßig hat sie den folgenden Versandentwurf: **Kostenkategorie – Kostentyp**.

  Dieser kann jedoch angepasst werden: Erfassen Sie den gewünschten Wert direkt im Feld **[!UICONTROL Titel]**.

* Die Formel zur Berechnung der Kosten wird im unteren Abschnitt des Fensters definiert.

  Diese Formel kann unabhängig von der Nachrichtenanzahl festgelegt oder entsprechend der Nachrichtenanzahl berechnet werden.

  Wenn die Formel von der Nachrichtenanzahl abhängt, kann die Struktur der Kostenberechnung **[!UICONTROL Linear]**, **[!UICONTROL Linear mit Schwellen]** oder **[!UICONTROL Pauschal mit Schwellen]** sein.

#### Lineare Struktur {#linear-structure}

Wenn es sich unabhängig von der Gesamtzahl von Nachrichten immer um den gleichen Betrag für eine Nachricht (oder eine Gruppe von Nachrichten) handelt, wählen Sie den Strukturtyp **[!UICONTROL Linear]** aus und geben Sie die Kosten pro Nachricht an.

Wenn der Betrag auf eine bestimmte Anzahl an Nachrichten angewandt wird, geben Sie diese im Feld **[!UICONTROL für]** an.

![](assets/supplier_cost_structure_calc.png)


#### Lineare Struktur mit Schwellen {#linear-structure-by-threshold}

Wenn der Betrag nach Schwellenwert für jede Nachricht gilt, müssen Sie eine Berechnungsstruktur **[!UICONTROL Linear nach Schwellenwert]** definieren. Bei dieser Kostenstruktur kostet jede Nachricht 0,13, z. B. wenn die Gesamtzahl der Nachrichten zwischen 1 und 100 liegt, 0,12 bei zwischen 100 und 1.000 versendeten Nachrichten und 0,11 jenseits von 1.000 Nachrichten.

Die entsprechende Konfiguration sieht wie folgt aus:

![](assets/supplier-cost-structure-linear.png)

Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** rechts von der Liste, um einen neuen Schwellenwert zu definieren.

#### Konstante Struktur mit Schwellen {#constant-structure-by-threshold}

Schließlich können Sie eine Kostenberechnung entsprechend der Gesamtzahl der Nachrichten konfigurieren. Wählen Sie dazu die Berechnungsstruktur **[!UICONTROL Pauschal mit Schwellen]**. Beispielsweise werden die Kosten für 1 bis 100 Nachrichten auf einen festen Betrag von 12,00 gesetzt, für einen Versand von 101 bis 1000 Nachrichten auf 100,00 und für jeden Versand von über 1000 Nachrichten auf 500,00, unabhängig von der Gesamtzahl.

![](assets/supplier-cost-structure-constant.png)

### Konfigurieren von mit einem Service verknüpften Aufträgen {#configure-processes-associated-with-a-service}

Über die Registerkarte **[!UICONTROL Aufträge]** können Sie Informationen über die mit dem Dienstleister verbundenen Prozesse zuordnen. In diesem Bereich können Sie den Informationsversand an den Router konfigurieren.

![](assets/cost-supplier-jobs.png)

* Der Abschnitt **[!UICONTROL Dateiextraktion]** gibt die Exportvorlage an, die bei Auswahl dieses Dienstes für den Versand verwendet wird. Sie können den Namen der Ausgabedatei im Feld **[!UICONTROL Extraktionsdatei]** angeben. Die rechts vom Feld gelegene Schaltfläche ermöglicht das Einfügen von Variablen.

* Im Abschnitt **[!UICONTROL Benachrichtigungs-E]** können Sie die Vorlage angeben, die Service-Provider nach dem Versand von Dateien benachrichtigen soll. Wählen Sie die Vorlage, mit der die Warnmeldung erstellt wird, und die Empfängergruppe aus.

  Die Versandvorlagen für Benachrichtigungen werden standardmäßig im Ordner **[!UICONTROL Administration > Kampagnen-Management > Vorlagen technischer Sendungen]** gespeichert, auf den über die allgemeine Ansicht zugegriffen werden kann.

* Im **[!UICONTROL Anschlussvorgang]** können Sie den Workflow auswählen, der nach der Genehmigung des Versands gestartet werden soll. Wenn eine Workflow-Vorlage eingegeben wird, wird automatisch eine Workflow-Instanz erstellt und gestartet, sobald die Genehmigung wirksam wird. Dieser Workflow kann die Extraktionsdatei beispielsweise zur Verarbeitung an einen externen Dienstleister senden.

### Zuordnen von Services zu Kampagnen {#associate-a-service-with-a-campaign}

Dienstleister sind mit dem Kampagnenversand verknüpft. Sie werden in Versandvorlagen referenziert, damit sie ihre Dienstleistungen in den mithilfe dieser Vorlagen erstellten Sendungen anbieten können.

Wenn ein Service ausgewählt wird, die Kostenkategorien, die dem Versandtyp entsprechen (Briefpost, E-Mail usw.) werden automatisch in der zentralen Tabelle zusammen mit den definierten Verarbeitungsoptionen angezeigt.

>[!NOTE]
>
>Wenn bei der Auswahl eines Dienstes keine Kostenkategorie angezeigt wird, bedeutet dies, dass für diese Art von Prozess keine Kostenkategorie definiert wurde. Beispiel: Falls bei einem E-Mail-Versand keine Kostenkategorie mit dem Typ **[!UICONTROL E-Mail]** definiert wurde, wird keine Kategorie angezeigt und die Auswahl des Dienstes hat keine Auswirkungen.

* Beim Briefpost-Versand können Sie den Dienst über das Konfigurationsfenster auswählen.

  ![](assets/supplier-mail-delivery-select.png)

* Beim Versand über mobile Kanäle werden Dienste auf die gleiche Weise wie beim Briefpost-Versand ausgewählt.
* In E-Mail-Sendungen werden Dienstleistungen über den Tab **[!UICONTROL Erweitert]** der Eigenschaften des jeweiligen Versands ausgewählt, wie im folgenden Beispiel:

  ![](assets/supplier-email-delivery-select.png)

Über die Spalte **[!UICONTROL Zu belastender Betrag]** können Kosten für diese Stelle im Kontext des betreffenden Versands oder der Aufgabe hinzugefügt werden.

Bei der Bestimmung der Kostenstellen eines Versands können Sie eine obligatorische Auswahl eines Kostentyps definieren. Wählen Sie dazu **[!UICONTROL Auswahl eines Werts aus der Kostentypliste erforderlich]**.

![](assets/cost-type-must-be-selected.png)

## Verwaltung von Lagern und Lagerergänzungen {#stock-and-order-management}

Kostentypen können Lagerpositionen zugeordnet werden, um Bestandsmeldungen zu verwalten, Lagerergänzungen zu verfolgen und Bestellungen zu tätigen.

Um die Verwaltung von Lagern und Lagerergänzungen in Adobe Campaign einzusetzen und Benutzern für die Durchführung eines Versands unzureichende Bestände zu melden, ist die Einhaltung folgender Schritte erforderlich:

1. Erstellung von Lagern und Bezüge auf zugeordnete Dienstleister. [Weitere Informationen](#create-a-stock).

1. Hinzufügen von Lagerpositionen. [Weitere Informationen](#add-stock-lines).

1. Benachrichtigung der Benutzenden im Falle eines Warnhinweises. [Weitere Informationen](#alert-operators).

1. Bestellungen und Lieferungen. [Weitere Informationen](#orders).

### Lagerverwaltung {#stock-management}

Adobe Campaign kann eine Benutzergruppe benachrichtigen, wenn das Lager leer ist oder einen Mindestbestand erreicht hat. Auf die Lagerbestände kann über den Link **[!UICONTROL Lager]** im Tab **[!UICONTROL Kampagnen]** über den Link **[!UICONTROL Andere Auswahlmöglichkeiten]** des Navigationsbereichs zugegriffen werden.

![](assets/stock-dashboard.png)

#### Erstellen eines Lagers {#creating-a-stock}

Folgen Sie den nachstehenden Etappen, um ein neues Lager zu erstellen:

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Erstellen]** oberhalb der Liste der existierenden Lager.
1. Geben Sie den Titel des Lagers an und wählen Sie in der Dropdown-Liste den zugehörigen Dienstleister aus. [Weitere Informationen](#create-service-providers-and-their-cost-structures).

#### Hinzufügen von Lagerpositionen {#add-stock-lines}

Ein Lager umfasst verschiedene Lagerpositionen. Eine Lagerposition enthält eine Anfangsmenge an Ressourcen, die von Sendungen verbraucht werden. Jede Lagerposition gibt die verbrauchte Menge, die Lagermenge und die bestellte Menge an.

Klicken Sie bei der Erstellung eines Lagers auf den Tab **[!UICONTROL Lagerpositionen]**, um neue Positionen hinzuzufügen.

![](assets/stock-new-lines.png)

Nachdem das Lager erstellt wurde, können Sie sein Dashboard verwenden, um Lagerpositionen zu erstellen und zu überwachen.

Klicken Sie auf die Schaltfläche **[!UICONTROL Erstellen]**, um neue Lagerpositionen hinzuzufügen.

![](assets/add-stock-lines.png)

* Geben Sie die Anfangsmenge des Lagerbestands im Feld **[!UICONTROL Anfangsbestand]** an. Die Felder **[!UICONTROL Entnommen]** und **[!UICONTROL Restbestand]** werden automatisch berechnet und entsprechend dem Fortschritt der Kampagnen aktualisiert.

  ![](assets/create-new-stock-line.png)

* Geben Sie im Feld „Alarmstufe“ den Schwellenwert an **[!UICONTROL ab dem Benutzer auf]** gewarnt werden sollen. Wenn die Warnstufe erreicht wird, wird im Validierungsfenster von Sendungen, die diese Lagerhaltung verwenden, eine Warnmeldung angezeigt.

#### Zuordnen einer Lagerposition zu Kostenkategorien {#associate-a-stock-with-cost-categories}

Folgendes Beispiel zeigt, wie Lagerpositionen in Dienstleistungen über die Kostenkategorien zugeordnet werden können:

![](assets/select-stock-line-supplier.png)

### Lagerverfolgung {#stock-tracking}

#### Warnen von Benutzenden {#alert-operators}

Ein Warnhinweis wird angezeigt, wenn ein Bestand, auf den in einem Versand verwiesen wird, nicht ausreicht. Beispielsweise wird folgender Warnhinweis angezeigt, wenn eine Extraktionsdatei validiert wurde:

![](assets/stock-alert.png)

#### Lagerergänzungen {#orders}

Im Untertab **[!UICONTROL Lagerergänzungen]** werden die laufenden Bestellungen angezeigt und neue Ergänzungen gespeichert.

Um eine neue Ergänzung zu speichern, öffnen Sie die entsprechende Lagerposition, klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und geben Sie das Lieferdatum sowie die bestellte Menge an.

![](assets/order-stocks.png)

>[!NOTE]
>
>Sobald das Lieferdatum erreicht ist, verschwindet die bestellte Lagerposition automatisch und die im Feld **[!UICONTROL Menge auf Bestellung]** eingegebene Menge wird der Registerkarte **[!UICONTROL Tracking]** hinzugefügt. Diese Menge wird automatisch zum Lagerbestand hinzugefügt.

Die **[!UICONTROL Verbrauchswerte]** enthält das pro Kampagne verbrauchte Volumen. Die Informationen auf dieser Registerkarte werden automatisch entsprechend den durchgeführten Sendungen eingegeben. Klicken Sie auf die Schaltfläche **[!UICONTROL Bearbeiten]**, um die betroffene Kampagne zu öffnen.

## Berechnen von Budgets {#calculate-budgets}

### Funktionsprinzip {#principle}

Kosten werden für Sendungen und Kampagnen verwaltet. Je nach Fortschritt werden diese Kosten den Haushalten zugewiesen.

Die Versandkosten für eine Kampagne werden auf Kampagnenebene konsolidiert, und die Kosten aller Kampagnen eines Programms werden an das Programm weitergegeben, mit dem sie verknüpft sind. Mit speziellen Berichten können Sie die Budgets für die gesamte Plattform oder für jeden Plan und jedes Programm verfolgen.

### Umsetzung {#implementation}

Wenn Sie in einer Kampagne das Budget auswählen, müssen Sie den Ausgangsbetrag eingeben. Die berechneten Kosten werden automatisch entsprechend der Höhe der Mittelbindung der angegebenen Beträge aktualisiert (getätigte, erwartete, reservierte, gebundene Ausgaben).


<!--
See [Calculating amounts](../../mrm/using/controlling-costs.md#calculating-amounts).

>[!NOTE]
>
>The procedure for creating budgets is presented in [Creating a budget](../../mrm/using/controlling-costs.md#creating-a-budget).
-->

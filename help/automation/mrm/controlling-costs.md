---
product: campaign
title: Kosten kontrollieren
description: Erfahren Sie, wie Sie Kosten kontrollieren können
feature: Campaigns, Resource Management
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 51f3add9-a083-4db1-84a6-3aaaeec0465c
TQID: 'https://experienceleague.adobe.com/OQtmoiTmvFeWbYfLNpjuk5FZLb2Si-mPBbMNMWnDGoo'
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
  - id: 8d5d4b17-44c6-5e7b-891c-b4277613013d
    internal-label: Resource Management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '3121'
ht-degree: 79%
---
# Kosten kontrollieren{#controlling-costs}

Adobe Campaign ermöglicht mit dem MRM-Modul die Kontrolle der geplanten, eingesetzten und berechneten Marketing-Kosten sowie ihre Aufschlüsselung nach Kategorien.

Die für die unterschiedlichen Kampagnenvorgänge anfallenden Kosten werden einem zuvor von der Marketing-Abteilung festgesetzten Budget zugeteilt. Die Beträge können auf verschiedene Kategorien verteilt werden, um eine bessere Lesbarkeit und detailliertere Berichte der Marketing-Kosten zu ermöglichen.

Die Budgetverwaltung und -nachverfolgung wird in einem dedizierten Knoten der Adobe Campaign-Struktur zentralisiert. Von hier aus können Sie alle Budgets sowie die zugeteilten, reservierten, eingesetzten und verbrauchten Beträge überwachen.

![Budgetknoten der Kampagnenverwaltungsstruktur mit dem E-Marketing-Budget, der die Beträge und Ausgabenkategorien anzeigt.](assets/s_ncs_user_budget_node_02.png)

Zur Nutzung der Budget-Verwaltung mit MRM sind folgende Etappen umzusetzen:

1. Definieren Sie das Budget. [Weitere Informationen](#creating-a-budget).

1. Definieren Sie die Kostenberechnungsmethode: Für die Dienstleister werden Kostenstrukturen definiert. [Weitere Informationen](../campaigns/providers-stocks-and-budgets.md).

1. Definieren Sie die Kosten der Kampagne (Sendungen/Aufgaben): Die durch Sendungen und Aufgaben anfallenden Kosten werden einzeln oder pauschal in der Kampagnenvorlage angegeben. [Weitere Informationen](../campaigns/marketing-campaign-deliveries.md#compute-costs-and-stocks).

1. Konsolidieren Sie: Gemäß dem Fortschrittsstatus der Aufgaben, Sendungen und Kampagnen werden die Kosten berechnet und das entsprechende Budget wird damit belastet. Wenn die Erstellung der Kampagne ausreichend fortgeschritten ist, kann der Erfüllungsstatus des Kampagnenbudgets in **[!UICONTROL Angegeben]** geändert werden. Die berechneten Kosten des Programms werden daraufhin automatisch mit den berechneten Kosten der Kampagnen konsolidiert. [Weitere Informationen](#cost-commitment--calculation-and-charging).

## Erstellen eines Budgets {#creating-a-budget}

Gehen Sie wie folgt vor, um ein Budget zu erstellen:

1. Navigieren Sie zum Knoten **[!UICONTROL Kampagnen-Management > Budgets]** des Campaign-Explorers.
1. Klicken Sie auf das Symbol **[!UICONTROL Neu]**, benennen und speichern Sie das Budget.
1. Anfangsbetrag eingeben: geben Sie im entsprechenden Feld den zugewiesenen Betrag an. Die anderen Beträge werden automatisch angegeben. [Weitere Informationen](#calculating-amounts).
1. Definieren Sie den Gültigkeitszeitraum durch Eingabe des Start- und Enddatums. Diese Informationen sind lediglich als Hinweis zu verstehen.
1. Erstellen Sie die Ausgabenkategorien, denen die für Kampagnen, Sendungen, Aufgaben usw. anfallenden Kosten in diesem Budget zugeordnet werden können. [Weitere Informationen](#expense-categories).

![Neues Budgetformular mit Titel, Zeitplan, zugewiesenem Betrag und den Ausgabenkategorien Design, Ressourcen und Daten.](assets/s_ncs_user_budget_create_and_save.png)

>[!NOTE]
>
>Sie können ein übergeordnetes Budget auswählen. Weitere Informationen hierzu finden Sie unter [Verknüpfen von Budgets mit anderen](#linking-a-budget-to-another).
>

### Beträge berechnen {#calculating-amounts}

Der Anfangsbestand eines Budgets verringert sich im Zuge der ihm zugeordneten Kampagnen, Sendungen oder Aufgaben um die anfallenden Kosten, sobald diese geplant oder realisiert wurden. Der Status der Beträge (Geplant, Reserviert, Eingesetzt, Verbraucht, Fakturiert) hängt vom Kostentyp und dem Verbindlichkeitsniveau ab, die in der Kampagne, dem Versand oder der Aufgabe festgelegt wurden.

>[!NOTE]
>
>Die in den Kategorien eingetragenen Beträge müssen dem im Feld **[!UICONTROL Zugeteilt]** angegebenen Gesamtbudget entsprechen.

In Kampagnen können je nach Verbindlichkeitsniveau Kosten für eine zukünftige Aktion geplant, eingesetzt oder reserviert werden.

![Kampagnenbudgetbereich mit geöffneter Liste der Verpflichtungsebenen, in der „Geplant“, „Reserviert“ und „Eingesetzt“ angezeigt werden.](assets/s_user_cost_op_engaged.png)

>[!CAUTION]
>
>Bei der Erstellung einer Kampagne muss der Fortschrittsstatus im **[!UICONTROL Budget]** auf **[!UICONTROL Angegeben]** eingestellt sein, damit die Kosten bei der Ausführung berücksichtigt werden. Wenn der Status **[!UICONTROL In Bearbeitung]** ist, werden die Kosten nicht konsolidiert.
>   
>Die Option **[!UICONTROL Verbindlichkeitsniveau]** stellt eine Prognose der Kosten für die Zukunft dar, bevor sie dem Budget angelastet werden. Je nach Fortschritt einer Kampagne, Aufgabe oder Sendung können Sie festlegen, ob ein höheres oder ein niedrigeres Verbindlichkeitsniveau zugewiesen wird (1. Geplant, 2. Reserviert, 3. Eingesetzt). Verwenden Sie das Kombinationsfeld.

Beispiel: Die Kosten einer Web-Kampagne werden auf 45 000 Euro geschätzt.

![Kampagnenbudget-Abschnitt mit geschätzten vorläufigen Kosten von 45.000, die dem Web-Budget auf der geplanten Ebene angelastet werden.](assets/s_user_edit_budget_node_impact_0.png)

Wenn der Erfüllungsstatus des Budgets in der Kampagne **[!UICONTROL Angegeben]** ist, werden die tatsächlichen Kosten der Kampagne (oder, wenn nicht angegeben, die berechneten Kosten) in die Budgetbeträge übertragen.

![Kampagnenbudget-Abschnitt mit dem Feld „Prozessstatus“ auf „Definiert“, sodass die Kosten bei der Ausführung konsolidiert werden.](assets/s_user_budget_in_op_a.png)

Je nach Verbindlichkeitsniveau der Kampagne wird der Betrag in das Feld **[!UICONTROL Geplant]**, **[!UICONTROL Reserviert]** oder **[!UICONTROL Eingesetzt]** übertragen.

Das Verbindlichkeitsniveau kann geändert werden:

* auf der **Kampagnenebene** im Fenster **[!UICONTROL Budget]** der Registerkarte **[!UICONTROL Bearbeiten]**. Hier werden Budgets, Kosten und Ausgaben konfiguriert.
* in einer **Aufgabe** im Fenster **[!UICONTROL Ausgaben und Einnahmen]**.

![Kampagnenbudget-Abschnitt mit geöffneter Liste der Verpflichtungsebenen, oberhalb der Registerkarte Ausgaben , in der eine Ausgabenzeile aufgeführt ist.](assets/s_user_op_engagement_level_costs.png)

Sobald ein Budget **[!UICONTROL Reserviert]** ist, wird automatisch das zugeteilte Budget aktualisiert.

![Budgetformular, in dem der reservierte Betrag 45.000 anzeigt, nachdem die Kampagnenbindungsebene auf „Reserviert“ gesetzt wurde.](assets/s_user_edit_budget_node_impact_2.png)

Der Ablauf entspricht dem der Aufgaben:

![Fenster „Aufgaben - Ausgaben und Einnahmen“ mit geöffneter Liste der Verpflichtungsebenen, in der „Geplant“, „Reserviert“ und „Eingesetzt“ angezeigt werden.](assets/s_user_edit_budget_node_impact_task.png)

Wenn eine Ausgabe in Rechnung gestellt und diese Rechnung beglichen wird, wird der jeweilige Betrag im Feld **[!UICONTROL Fakturiert]** eintragen.

### Ausgabenkategorien {#expense-categories}

Die Beträge können in verschiedene Ausgabenkategorien verteilt werden, um eine bessere Lesbarkeit der Daten und eine detailliertere Berichterstattung über Marketing-Investitionen zu erreichen. Die Ausgabenkategorien werden bei der Budgeterstellung über den Knoten **[!UICONTROL Budgets]** des Baums definiert.

Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** im unteren Abschnitt des Fensters, um eine Kategorie hinzuzufügen.

![Budgetformular mit der Schaltfläche Hinzufügen der Liste Ausgabenkategorien für die Kategorien Design, Druck und Web.](assets/s_user_budget_category.png)

Sie können eine Kategorie aus den vorhandenen auswählen oder eine neue Kategorie definieren, indem Sie sie direkt in das Feld eingeben. Bei der Bestätigung Ihrer Eingabe wird Ihnen ermöglicht, die Kategorie der Liste der existierenden Kategorien hinzuzufügen und sie bei Bedarf einer Art zuzuordnen. Diese Informationen werden in den Budgetberichten verwendet.

### Zuordnung von Budgets untereinander {#linking-a-budget-to-another}

Sie können ein Budget mit einem Hauptbudget verknüpfen. Wählen Sie dazu das Hauptbudget im Feld **[!UICONTROL Übergeordnetes Budget]** der sekundären Budgets aus.

![Sekundäres Budgetformular mit dem entsprechenden Budgetfeld, das auf das E-Marketing-Hauptbudget festgelegt ist.](assets/budget_link.png)

Dem Hauptbudget wird daraufhin ein Tab zur Auflistung der untergeordneten Budgets hinzugefügt.

![Hauptbudget mit der Registerkarte „Hinzugefügte Budgets“, auf der die verknüpften Budgets aufgeführt sind.](assets/budget_link_new_tab.png)

Diese Informationen werden in den Budgetberichten ausgewertet.

## Ausgabenzeilen hinzufügen {#adding-expense-lines}

Ausgabenzeilen werden automatisch zum Budget hinzugefügt. Sie werden bei der Versandanalyse und beim Abschluss einer Aufgabe erstellt.

![Registerkarte „Ausgaben budgetieren“ mit der Schaltfläche Detail, über die eine Ausgabenzeile mit der Aufteilung von Kampagne, Versand und Kostenkategorie geöffnet wird.](assets/s_ncs_user_budget_line_edit.png)

Die für Kampagnen, Sendungen oder Aufgaben anfallenden Kosten werden in den Ausgabenzeilen des Budgets zusammengefasst, dem sie zugeteilt sind. Diese Ausgabenzeilen werden abhängig von den Kostenkategorien des beteiligten Dienstleisters erstellt und ausgehend von den verbundenen Kostenstrukturen berechnet.

Damit enthält jede Ausgabenzeile folgende Informationen:

* die Kampagne und Sendung oder Aufgabe, der sie zugeordnet ist;
* den ausgehend von den Kostenstrukturen oder den Plankosten berechneten Betrag;
* die tatsächlichen Kosten der Sendung oder der betreffenden Aufgabe;
* die entsprechende Rechnungszeile (ausschließlich in MRM);
* die Liste der berechneten Kosten je Kostenkategorie (wenn eine Kostenstruktur existiert).

Im obigen Beispiel enthält die bearbeitete Ausgabenzeile die berechneten Kosten für den Versand **Neue Karten** für die Kampagne **Loyalty Spring Pack**. Bei der Bearbeitung des Versands zeigt die Registerkarte **[!UICONTROL Briefpost]** an, wie die Ausgabenzeile berechnet wird.

Als Grundlage der Kostenberechnung für diesen Versand dienen die für den betroffenen Dienstleister ausgewählten Kostenkategorien.

![Ausgabenzeile, die mit einem Versand verknüpft ist, dessen Registerkarte „Briefpost“ die Kostenkategorien des Dienstleisters auflistet.](assets/s_user_edit_del_supplier_costs.png)

Abhängig von diesen Kostenkategorien werden die entsprechenden Kostenstrukturen zur Berechnung der Kostenzeilen angewandt. Im vorliegenden Beispiel handelt es sich um folgende Kostenstrukturen für den betroffenen Dienstleister:

![Registerkarte „Service-Kostenstruktur“ mit der Grafik - 01-Kostenstruktur-Detail: Briefpost-Kanal, pro Nachricht, linear.](assets/s_user_edit_node_supplier_costs.png)

>[!NOTE]
>
>Kostenkategorien und -strukturen werden unter [Erstellen eines Dienstleisters und seiner Kostenkategorien](../campaigns/providers-stocks-and-budgets.md#create-a-service-provider-and-its-cost-categories)

## Entstehung, Berechnung und Anrechnung von Kosten {#cost-commitment--calculation-and-charging}

Kosten können für Sendungen und Aufgaben eingesetzt werden. Abhängig vom Bearbeitungsfortschritt des jeweiligen Vorgangs wird der Kostenstatus aktualisiert.

### Kostenarten {#cost-calculation-process}

Kosten werden in drei Kategorien eingeteilt:

1. Plankosten

   Die Plankosten entsprechen einer Schätzung der Kosten für die Kampagnenprozesse. Solange sie bearbeitet werden, werden die eingegebenen Beträge nicht konsolidiert. Der Status **[!UICONTROL Angegeben]** ist hier nötig, damit die eingegebenen Beträge in den Berechnungen berücksichtigt werden.

   Dieser Betrag wird manuell eingegeben und kann in mehrere Ausgabenkategorien unterteilt werden. Klicken Sie zum Aufschlüssen von Kosten auf den Link **[!UICONTROL Aufschlüsselung…]** und dann auf die Schaltfläche **[!UICONTROL Hinzufügen]**, um einen neuen Betrag zu definieren.

   ![Fenster „Kostenaufschlüsselung bearbeiten“ über den Link „Geschätzte vorläufige Kostenaufschlüsselung“, in dem die Kosten nach Kategorie aufgeteilt werden.](assets/s_user_edit_budget_tab_ventil.png)

   Jeder Kostenbetrag kann einer Kategorie zugeordnet werden. Dies ermöglicht eine Aufschlüsselung der Kosten nach Ausgabenkategorien im übergeordneten Budget sowie in den Budgetberichten.

1. Berechnete Kosten

   Die berechneten Kosten hängen von den jeweiligen Elementen ab (Kampagne, Versand, Aufgabe usw.) und dessen Status (In Bearbeitung, Abgeschlossen). Wenn die tatsächlichen Kosten angegeben werden, verwenden die berechneten Kosten in jedem Fall diesen Betrag.

   Wenn die tatsächlichen Kosten nicht angegeben sind, gelten folgende Regeln:

   * In einer sich in Bearbeitung befindenden Kampagne entsprechen die berechneten Kosten dem Betrag der Plankosten der Kampagne. Wenn diese nicht global für die Kampagne angegeben wurden, setzen sich die berechneten Kosten aus der Summe der Plankosten der einzelnen Sendungen und Aufgaben der Kampagne zusammen. Nach Abschluss der Kampagne entsprechen die berechneten Kampagnenkosten der Summe aller berechneten Kosten.
   * In einem noch nicht analysierten Versand entsprechen die berechneten Kosten dem Betrag der Plankosten. Wenn die Analyse bereits stattgefunden hat, setzen sich die berechneten Kosten aus den basierend auf den Kostenstrukturen des Dienstleisters und der Anzahl der ausgewählten Empfangenden berechneten Beträgen zusammen.
   * Für eine laufende Aufgabe verwenden die berechneten Kosten die Plankosten. Nach Abschluss der Aufgabe entsprechen die berechneten Kosten der Summe aller basierend auf den Kostenstrukturen des Dienstleisters und – falls zutreffend – der Anzahl an insgesamt benötigten Tagen berechneten Kosten.
   * Sowohl für Marketing-Pläne als auch für Programme entsprechen die berechneten Kosten der Summe der für die verknüpften Kampagnen berechneten Kosten. Wenn diese nicht angegeben sind, werden die Plankosten anstelle der berechneten Kosten verwendet.

   >[!NOTE]
   >
   >Über den **[!UICONTROL Aufschlüsselung]**-Link der berechneten Kosten können Details der Berechnung sowie das Datum der letzten Kostenberechnung eingesehen werden.

1. Tatsächliche Kosten

   Tats. Kosten werden manuell erfasst und bei Bedarf zwischen unterschiedlichen Ausgabenkategorien verteilt.

### Anrechnung auf Budgets {#calculation-and-charging}

Kosten werden mithilfe der Kostenstrukturen berechnet und auf die in den betroffenen Kampagnen, Sendungen oder Aufgaben ausgewählten Budgets angerechnet.

Über die Budgetvalidierung kann eine Prüfung der an Kampagnen gebundenen Beträge durchgeführt werden. Zusätzlich ist die Erstellung von Kontrollaufgaben ein weiteres Mittel, um einzelne Bereiche einer Kampagne zur Validierung zu unterbreiten. Siehe [Aufgabenarten](creating-and-managing-tasks.md#types-of-task).

### Beispiel {#example}

Im Folgenden wird eine Kampagne mit folgenden Elementen erstellt:

* Briefpost-Versand mit Kostenstrukturen eines Dienstleisters
* Aufgabe mit Fixkosten
* Aufgabe mit Tageskosten

#### Schritt 1: Budget erstellen {#step-1---creating-the-budget}

1. Erstellen Sie ein neues Budget über den Knoten **[!UICONTROL Kampagnenverwaltung > Budgets]**.

1. Definieren Sie ein Budget von 10.000 Euro im Feld **[!UICONTROL Zugeteilt]** des Abschnitts **[!UICONTROL Beträge]**. Fügen Sie drei Ausgabenkategorien im unteren Abschnitt des Fensters hinzu:

![Budgetformular mit 10.000 zugewiesenen und zwei Ausgabenkategorien, 1. Kategorie und 2. Kategorie.](assets/s_user_cost_mgmt_sample_1.png)

#### Schritt 2: Dienstleister konfigurieren und Kostenstrukturen festlegen {#step-2---configuring-the-service-provider-and-defining-the-cost-structures}

1. Erstellen Sie einen Dienstleister sowie eine Dienstleistungsvorlage mit Kostenstruktur über den Knoten **[!UICONTROL Administration > Kampagnen > Dienstleister]**. Weitere Informationen hierzu finden Sie unter [Erstellen eines Dienstleisters und seiner Kostenkategorien](../campaigns/providers-stocks-and-budgets.md#create-a-service-provider-and-its-cost-categories).

   Erstellen Sie für Briefpost-Sendungen die Kostenkategorien **[!UICONTROL Briefumschläge]** (Typen 114x229 und 162x229), **[!UICONTROL Porto]** und **[!UICONTROL Druck]** (Typen A3 und A4). Erstellen Sie dann die folgenden Kostenstrukturen:

   ![Kostenstrukturen Briefumschläge - 114x229, Porto - Standard und Print - A4: Briefpost, pro Nachricht, lineare Beträge.](assets/s_user_cost_mgmt_sample_2.png)

1. Fügen Sie in den Kostenkategorien Fixkosten vom Typ &quot;Festpreis&quot; hinzu, deren Betrag in der entsprechenden Kostenstruktur leer ist. (Dieser wird einzeln für jeden Versand angegeben.)

   ![Kostenstruktur Festkosten - Gestaltung mit dem Briefpostkanal, Feste Berechnung und einem Leerbetrag.](assets/s_user_cost_mgmt_sample_5.png)

   Erstellen Sie für die Aufgaben die folgenden zwei Kostenkategorien:

   * **[!UICONTROL Raumreservierung]** (Typen Kleiner Saal und Großer Saal) mit einer **Pauschale** von 300 und 500 Euro.

   ![Kostenstruktur Raumbuchung - Groß für den Aufgabenkanal mit einer festen Berechnung und einem Betrag von 500,](assets/s_user_cost_mgmt_sample_6.png)

   * **[!UICONTROL Erstellung]** (Typ **Inhaltsvorlage**) mit von der **Dauer in Tagen** abhängigen Kosten in Höhe von 300 Euro:

   ![Kostenstruktur-Design - Inhaltsvorlage für den Aufgabenkanal mit einer täglichen Berechnung und einem Betrag von 300,](assets/s_user_cost_mgmt_sample_7.png)

#### Schritt 3: Anfallende Kosten auf das Kampagnenbudget anrechnen {#step-3---charging-the-budget-in-the-campaign}

1. Erstellen Sie eine Kampagne und wählen Sie das im 1. Schritt erstellte Budget aus.

   >[!NOTE]
   >
   >Das im Programm ausgewählte Budget wird standardmäßig für alle Kampagnen des Programms angewandt.

   ![Kampagnenbudget-Bereich mit offener Ladungsliste, in der die Programme für Sondereinsätze, eMarketing und Pflege angezeigt werden.](assets/s_user_cost_mgmt_sample_4.png)

1. Geben Sie die Plankosten mit Aufschlüsselung an:

   ![Geschätzte vorläufige Kosten von 3.000, aufgeschlüsselt nach der ersten und zweiten Kategorie im Fenster „Kosten bearbeiten“.](assets/s_user_cost_mgmt_sample_9.png)

1. Klicken Sie auf **[!UICONTROL OK]** und dann auf **[!UICONTROL Speichern]**, um diese Informationen zu bestätigen. Die berechneten Kosten der Kampagne werden daraufhin mit den Plankosten aktualisiert.

#### Schritt 4: Briefpost-Versand erstellen {#step-4---creating-the-direct-mail-delivery}

1. Erstellen einen Kampagnen-Workflow mit einer Abfrage zur Zielgruppenbestimmung. Stellen Sie sicher, dass die Postadresse der ausgewählten Empfänger angegeben ist.

1. Erstellen Sie nun einen Briefpost-Versand und wählen Sie den im zweiten Schritt erstellten Dienstleister aus: Die Kostenkategorien werden automatisch angezeigt.

1. Überschreiben Sie die Kosten der Umschläge und fügen Sie Fixkosten hinzu. Wählen Sie auch die von diesen Kosten betroffenen Kategorien aus.

   ![Katalogversand im Workflow mit den Kostenkategorien des Dienstleisters, einschließlich der Fixkosten von 560,](assets/s_user_cost_mgmt_sample_3.png)

   >[!NOTE]
   >
   >Wenn eine der Kostenkategorien nicht verwendet wird, fallen durch diese keinerlei Ausgaben an.

1. Starten Sie den gerade erstellten Workflow, um die Analyse zu beginnen und die Kosten zu berechnen.

   ![Symbolleiste des Zielgruppen-Workflows mit ausgewählter Schaltfläche „Start“, um die Analyse auszuführen und die Kosten zu berechnen.](assets/s_user_cost_mgmt_sample_10.png)

1. Wenn die Budgetvalidierung für diese Kampagne aktiviert wurde, validieren Sie das Budget über das Dashboard. Sie können die Validierung der Kostenkategorien überprüfen.

   ![Menü Versandvalidierung mit Budget validieren Öffnet die Aktion im Versand-Dialogfeld mit Kostenaufteilung und Budgetvalidierung.](assets/s_user_cost_mgmt_sample_10b.png)

Die den Versand betreffende Ausgabenzeile wird in der Registerkarte **[!UICONTROL Bearbeiten > Budget]** der Kampagne hinzugefügt. Bearbeiten Sie diese, um die Details der Berechnung anzuzeigen.

![Registerkarte „Kampagnenbudget - Ausgaben“ mit der Schaltfläche „Details“, mit der die Ausgabenzeile des Versands und seine Kostenaufteilung geöffnet wird.](assets/s_user_cost_mgmt_sample_11.png)

Auf Versandniveau werden die berechneten Kosten mit folgenden Daten aktualisiert:

![Versandkosten und Umsatz Fenster mit den berechneten Kosten von 22.844 aus den Kostenstrukturen.](assets/s_user_cost_mgmt_sample_12.png)

Beim Bearbeiten der berechneten Kosten können Sie die Aufschlüsselung der Kosten sowie Status und Datum der Kostenberechnung überprüfen.

#### Schritt 5: Aufgaben erstellen {#step-5---creating-tasks}

Zu dieser Kampagne fügen wir die beiden Aufgaben hinzu, für die die Kostenstrukturen [früher erstellt](#step-2---configuring-the-service-provider-and-defining-the-cost-structures) wurden.

Klicken Sie dazu im Kampagnen-Dashboard auf die Schaltfläche **[!UICONTROL Aufgabe hinzufügen]**. Benennen Sie die Aufgabe und klicken Sie auf **[!UICONTROL Speichern]**.

1. Die Aufgabe wird dann zur Aufgabenliste hinzugefügt. Sie müssen sie bearbeiten, um sie zu konfigurieren.

1. Klicken Sie auf **[!UICONTROL Eigenschaften]**, um die Dienstleistung sowie die entsprechende Kostenkategorie auszuwählen:

   ![Fenster „Aufgabeneigenschaften“ mit geöffneter Liste „Zimmerbuchungskostentyp“ mit den Listen „Groß“, &quot;Medium&quot; und „Klein“.](assets/s_user_cost_mgmt_sample_14.png)

1. Öffnen Sie anschließend die **[!UICONTROL Ausgaben und Einnahmen]** der Aufgabe und geben Sie ihre Plankosten an.

   ![Fenster „Aufgabenausgaben und Einnahmen“ mit geschätzten vorläufigen Kosten in Höhe von 5.500, die Sondereinsätzen angelastet werden.](assets/s_user_cost_mgmt_sample_15.png)

   Mit Speicherung der Aufgabe übernehmen die berechneten Kosten den für die Plankosten angegebenen Wert.

   Nach Abschluss der Aufgabe (Status **[!UICONTROL Abgeschlossen]**) werden die berechneten Kosten automatisch mit den Kosten des großen Saals entsprechend der Angabe in seiner Kostenstruktur aktualisiert. Diese Kosten werden auch in dieser Kategorie in der Aufschlüsselung angezeigt.

1. Erstellen Sie auf die gleiche Weise eine zweite Aufgabe mit einer Planung über fünf Tage und verbinden Sie sie mit der zuvor erstellen Kostenstruktur.

   ![Zweite Aufgabe - Inhaltserstellung, deren Fenster „Aufgabeneigenschaften“ eine geöffnete Liste des Kostentyps anzeigt.](assets/s_user_cost_mgmt_sample_16.png)

   Nach Abschluss der Aufgabe übernehmen die berechneten Kosten den aus der Kostenstruktur stammenden Wert, in unserem Beispiel also 1500 Euro (5 Tage x 300 Euro).

   ![Aufgabe zur Inhaltserstellung wurde im Fenster „Ausgaben und Umsatz“ mit berechneten Kosten von 1.500 abgeschlossen.](assets/s_user_cost_mgmt_sample_17.png)

#### Schritt 6: Status des Kampagnenbudgets aktualisieren {#step-6---update-the-campaign-budget-status}

Wenn die Kampagne konfiguriert ist, kann ihr Status durch Festlegen von **[!UICONTROL Angegeben]** aktualisiert werden. Die berechneten Kosten der Kampagne zeigen dann die Summe der berechneten Kosten des Versands und der Aufgabe der Kampagne an:

![Kampagnenbudget-Abschnitt mit geöffneter Prozessstatusliste: In Bearbeitung, Definition und Ausführung, oberhalb der Kostenzeilen.](assets/s_user_cost_mgmt_sample_18.png)

#### Validierung von Budgets {#budget-approval}

Bei aktivierter Validierung können Sie das Budget über einen speziellen Link im Kampagnen-Dashboard validieren. Der Link wird angezeigt, sobald der Zielgruppenbestimmungs-Workflow gestartet wurde und ein Briefpostversand validiert werden muss.

![Option Budget genehmigen im Menü „Versandvalidierung“, das die Aktion beim Versand mit der Genehmigung „Akzeptieren“, „Ablehnen“ und „Budget“ öffnet.](assets/s_user_cost_mgmt_sample_19.png)

Sie können dann die Validierung über diesen Link akzeptieren oder ablehnen. Wenn Benachrichtigungen für die Kampagne aktiviert wurden, können Sie den Link auch in der Benachrichtigungs-E-Mail verwenden.

Nach Budgetvalidierung und Abschluss des Versands werden die Kosten automatisch über einen speziellen technischen Workflow weiter verarbeitet.

## Lagerergänzungen und Rechnungen {#orders-and-invoices}

Im Kontext von MRM können Sie bei Dienstleistern aufgegebene Bestellungen und zugehörige Rechnungen erfassen. Der gesamte Kreislauf dieser Bestellungen und Rechnungen kann über die Adobe Campaign-Oberfläche verwaltet werden.

### Lagerergänzungen {#order-creation}

Um eine Lagerergänzung zu erfassen, gehen Sie zum Knoten **[!UICONTROL MRM > Lagerergänzungen]** des Navigationsbaums und klicken Sie auf die Schaltfläche **[!UICONTROL Neu]**.

Geben Sie die Nummer der Lagerergänzung, den entsprechenden Dienstleister sowie die Gesamtkosten für die Lagerergänzung an.

![Knoten „Orders“ unter MRM mit der Liste der Bestellungen und einem Bestellformular mit der Nummer, dem Dienstleister und dem Betrag.](assets/s_user_cost_create_order.png)

### Rechnungen erstellen und verfolgen {#issuing-and-tracking-invoices}

Sie können für jeden Dienstleister Rechnungen speichern und ihren Status sowie das betroffene Budget angeben.

Rechnungen werden im Knoten **[!UICONTROL MRM > Rechnungen]** des Adobe Campaign-Navigationsbaums erstellt.

![Rechnungsknoten unter MRM mit einem Rechnungsformular, das die Nummer, den Dienstleister, das Budget, den Betrag und den Status anzeigt.](assets/s_user_cost_create_invoice.png)

Eine Rechnung besteht aus Rechnungszeilen, deren Summe die automatische Berechnung des Betrags ermöglicht. Diese Zeilen werden manuell über die Registerkarte **[!UICONTROL Rechnungszeilen]** erstellt. Sie können einer Bestellung zugeordnet werden, um die Informationen in die Bestellungen hochzuladen.

![Registerkarte „Rechnungszeilen“ mit der Schaltfläche „Hinzufügen“, über die ein Rechnungszeilenformular mit der Option „Bestellung, Betrag und Ausgeglichen“ geöffnet wird.](assets/s_user_cost_invoice_add_line.png)

Die Rechnungen jeden Dienstleisters werden im **[!UICONTROL Rechnungen]**-Tab seines Profils angezeigt:

![Knoten „Dienstleister“ mit der Registerkarte „Rechnungen“, auf der die Rechnungen des ausgewählten Dienstleisters aufgeführt sind.](assets/s_ncs_user_invoice_from_supplier.png)

Im **[!UICONTROL Details]**-Tab kann der Inhalt der jeweiligen Rechnung eingesehen werden.

Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine neue Rechnung zu erstellen.

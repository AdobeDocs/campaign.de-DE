---
product: campaign
title: Erste Schritte mit Kampagnensimulationen
description: Erfahren Sie, wie Sie Kampagnensimulationen konfigurieren
feature: Campaigns
exl-id: 2b2b668f-87d9-4265-adbc-9098b85c5aab
TQID: https://experienceleague.adobe.com/U78259I0GrAXCvnDrUCP-RyQZ-caoY0fjWndcONm5EQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1358
ht-degree: 79%

---

# Campaign-Simulationen{#campaign-simulations}

Mit der Kampagnenoptimierung können Sie die Effizienz eines Kampagnenplans mithilfe von Simulationen testen. Auf diese Weise lässt sich der potenzielle Erfolg einer Kampagne messen: generierter Umsatz, Zielvolumen basierend auf den angewendeten Typologieregeln usw.

Mithilfe der Simulation können die voraussichtlichen Auswirkungen von Sendungen miteinander verglichen werden.

## Einrichten einer Simulation {#set-up-a-simulation}

### Vorsicht


Sendungen, die im Modus **Test** vorbereitet wurden, beeinflussen sich gegenseitig nicht, z. B. bei der Auswertung einer Kampagne im verteilten Marketing oder solange die Sendungen nicht im vorläufigen Kalender eingeplant sind.

Das bedeutet, dass die Druck- und Kapazitätsregeln nur auf Sendungen im Modus **[!UICONTROL Zielgruppenschätzung und Nachrichtenpersonalisierung]** angewendet werden. Sendungen im Modus **[!UICONTROL Schätzung und Validierung der geplanten Zielgruppe]** und im Modus **[!UICONTROL Zielgruppenauswertung]** werden nicht berücksichtigt.

Der Versandmodus wird in den Eigenschaften des jeweiligen Versands im Tab **[!UICONTROL Typologie]** ausgewählt.

![](assets/simu_campaign_select_delivery_mode.png)


### Erstellen einer Simulation {#create-a-simulation}

Folgen Sie den nachstehenden Schritten, um eine Simulation zu erstellen:

1. Öffnen Sie den Tab **[!UICONTROL Kampagnen]**, klicken Sie im Abschnitt **[!UICONTROL Erstellen]** auf den Link **[!UICONTROL Andere Optionen]** und wählen Sie **[!UICONTROL Simulation]** aus.

   ![](assets/simu_campaign_opti_01.png)

1. Wählen Sie eine Simulationsvorlage aus und geben Sie einen Titel an. Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, um die Simulation zu erstellen.

   ![](assets/simu_campaign_opti_02.png)

1. Klicken Sie auf den Tab **[!UICONTROL Bearbeiten]**, um sie zu konfigurieren.

   ![](assets/simu_campaign_opti_edit.png)

1. Geben Sie im Tab **[!UICONTROL Perimeter]** die für diese Simulation zu berücksichtigenden Sendungen an. Klicken Sie hierfür auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie den gewünschten Modus aus.

   ![](assets/simu_campaign_opti_edit_scope.png)

   Sie können entweder jeden Versand einzeln oder alle zu einer bestimmten Kampagne, einem Programm oder einem Plan gehörenden Sendungen auswählen.

   >[!NOTE]
   >
   >Wenn Sie die Sendungen eines Plans, eines Programms oder einer Kampagne auswählen, kann Adobe Campaign automatisch die Liste der zu berücksichtigenden Sendungen bei jedem Simulationsstart aktualisieren. Kreuzen Sie dafür die Option **[!UICONTROL Versandauswahl bei jedem Simulationsstart aktualisieren]** an.
   >  
   >Andernfalls werden nur die zum Zeitpunkt der Simulationserstellung im Plan, Programm oder in der Kampagne vorhandenen Sendungen berücksichtigt: Später hinzugefügte Sendungen werden nicht beachtet.

   ![](assets/simu_campaign_opti_edit_scope_update.png)

1. Auswahl der Elemente, die in den Simulationsumfang aufgenommen werden sollen. Bei Bedarf können Sie mit den Tasten UMSCHALT und STRG mehrere Elemente auswählen.

   ![](assets/simu_campaign_opti_edit_scope_select.png)

   Klicken Sie auf die Schaltfläche **[!UICONTROL Beenden]**, um die Auswahl zu bestätigen.

   Es besteht die Möglichkeit, manuell ausgewählte Sendungen mit solchen aus verschiedenen Plänen, Programmen oder Kampagnen zu kombinieren.

   ![](assets/simu_campaign_opti_edit_scope_save.png)

   Über den Link **[!UICONTROL Dynamische Bedingung bearbeiten…]** können Sie eine dynamische Bedingung verwenden.

   Klicken Sie zur Bestätigung der Konfiguration auf die Schaltfläche **[!UICONTROL Speichern]**.

   >[!NOTE]
   >
   >In den Simulationsberechnungen werden nur die Sendungen berücksichtigt, deren Zielgruppe bereits berechnet wurde (Status **Zielbestimmung abgeschlossen** oder **Versandbereit**).

1. Wählen Sie im **[!UICONTROL Berechnungen]**-Tab eine Analysedimension, beispielsweise das Empfängerschema aus.

   ![](assets/simu_campaign_opti_dimension.png)

1. Im Anschluss können Sie Ausdrücke hinzufügen.

   ![](assets/simu_campaign_opti_dimension_02.png)

### Ausführungsparameter {#execution-settings}

Im Tab **[!UICONTROL Allgemein]** der Simulation können Sie ihre Ausführungsparameter eingeben:

* Mit **[!UICONTROL Option „Ausführung für]** planen“ wird der Simulationsstart je nach ausgewählter Prioritätsstufe auf einen kürzeren Zeitraum verschoben. Simulationen verwenden erhebliche Datenbankressourcen. Daher sollten nicht dringende Simulationen beispielsweise für die Ausführung in der Nacht geplant werden.
* Die **[!UICONTROL Priorität]** entspricht der Dringlichkeit, die der Simulation zugeteilt wird, um sie schnellstmöglich durchzuführen oder ihren Start zu verzögern.
* **[!UICONTROL SQL-Abfragen im Protokoll]**. Mit SQL-Protokollen können Sie eine Simulation diagnostizieren, wenn sie mit Fehlern endet. Außerdem erfahren Sie, warum eine Simulation zu langsam ist. Die entsprechenden Logs sind nach der Simulation auf der Unterregisterkarte **[!UICONTROL SQL-Logs]** der Registerkarte **[!UICONTROL Verfolgung]** verfügbar.

## Ausführen einer Simulation {#execute-a-simulation}

### Starten einer Simulation {#start-a-simulation}

Sobald der Perimeter der Simulation definiert wurde, kann sie ausgeführt werden.

Öffnen Sie das Simulations-Dashboard und klicken Sie auf die Schaltfläche **[!UICONTROL Simulation starten]**.

![](assets/simu_campaign_opti_start.png)

Öffnen Sie nach der Ausführung die Simulation und klicken Sie auf den Tab **[!UICONTROL Ergebnisse]**, um die für die Sendungen berechneten Zielgruppen anzuzeigen.

![](assets/simu_campaign_opti_results.png)

1. Die Unterregisterkarte **[!UICONTROL Sendungen]** listet alle Sendungen auf, die von der Simulation berücksichtigt wurden. Es werden zwei Zahlen angezeigt:

   * Die **[!UICONTROL Ursprüngliche Zählung]** entspricht der Schätzung der Zielgruppe auf Ebene des Versands;
   * Die **[!UICONTROL Endgültige Zählung]** zeigt die Anzahl der nach Ausführung der Simulation verbleibenden Empfänger an.

     Der Unterschied zwischen ursprünglicher und endgültiger Zählung spiegelt die vor der Simulation konfigurierten unterschiedlichen Regeln oder Filter wider.

     Gehen Sie in den Untertab **[!UICONTROL Ausschlüsse]**, um die Details der Berechnung anzusehen.

1. Die **[!UICONTROL Ausschlüsse]** werden nach Sendungen aufgestaffelt dargestellt.

   ![](assets/simu_campaign_opti_14.png)

1. Die Unterregisterkarte **[!UICONTROL Warnhinweise]** enthält alle Warnhinweise, die während der Simulation generiert wurden. Warnmeldungen können im Falle einer Kapazitätsüberlastung gesendet werden (z. B. wenn die Anzahl der Zielgruppenempfänger die festgelegte Kapazität überschreitet).
1. Über **[!UICONTROL Unterregisterkarte Ausschlussanalyse]** Sie eine Ergebnistabelle erstellen. Der Benutzer muss Variablen in der Abszisse/Ordinatenachse angeben.

   Ein Beispiel für die Erstellung einer Analysetabelle finden Sie am Ende [dieses Abschnitts](#explore-results).

### Anzeigen von Ergebnissen {#view-results}

#### Verfolgung {#audit}

Die Registerkarte **[!UICONTROL Audit]** ermöglicht die Überwachung der Simulation. Die Unterregisterkarte **[!UICONTROL SQL-Logs]** ist insbesondere für erfahrene Benutzer hilfreich. Es werden Ausführungslogs im SQL-Format aufgelistet. Damit die SQL-Logs angezeigt werden, muss vor Ausführung der Simulation auf der Registerkarte **[!UICONTROL Allgemein]** die Option **[!UICONTROL SQL-Abfragen im Protokoll speichern]** aktiviert werden.

![](assets/simu_campaign_opti_11.png)

#### Analysieren von Ergebnissen {#explore-results}

Die Unter-Registerkarte **[!UICONTROL Ausschlussanalyse]** ermöglicht die Analyse der aus der Simulation resultierenden Daten.

<!--
Descriptive analysis is detailed in [this section](../../reporting/using/about-adobe-campaign-reporting-tools.md).
-->

## Ergebnisse einer Simulation {#results-of-a-simulation}

Die in den Tabs **[!UICONTROL Log]** und **[!UICONTROL Ergebnisse]** dargestellten Indikatoren geben einen ersten Einblick in das Ergebnis der Simulation. Im Tab **[!UICONTROL Berichte]** können Sie eine präzise Analyse der Informationen vornehmen.

### Berichte {#reports}

Um das Ergebnis einer Simulation zu analysieren, nutzen Sie die mit ihr verbundenen Berichte: Sie stellen die Simulationsausschlüsse und ihre Gründe dar.

Standardmäßig werden folgende Berichte angeboten:

* **[!UICONTROL Detail der Simulationsausschlüsse]**: Dieser Bericht bietet eine detaillierte Tabelle aller Ausschlussgründe für alle von dieser Simulation betroffenen Sendungen.
* **[!UICONTROL Simulationszusammenfassung]**: Dieser Bericht zeigt den Umfang der von der Simulation ausgeschlossenen Populationen während der verschiedenen Sendungen an.
* **[!UICONTROL Zusammenfassung der simulationsbedingten Ausschlüsse]**: Dieser Bericht zeigt eine Tabelle der Ausschlüsse durch die Simlation an. Des Weiteren werden die Typologieregeln aufgeführt, die zum Ausschluss geführt haben, sowie ihr jeweiliger Anteil an den regelbedingten Ausschlüssen.

<!--
>[!NOTE]
>
>You can create new reports and add them to the ones offered. For more on this, refer to [this section](../../reporting/using/about-adobe-campaign-reporting-tools.md).
-->

Um Berichte zu öffnen, klicken Sie auf den für die jeweilige Simulation im Dashboard verfügbaren **[!UICONTROL Berichte]**-Link.

![](assets/campaign_opt_reporting_edit_from_board.png)

Klicken Sie auf den Link **[!UICONTROL Berichte]** auf dem Dashboard der entsprechenden Simulation, um auf die Berichte zuzugreifen.

### Vergleich von Simulationen {#compare-simulations-}

Bei wiederholter Ausführung einer Simulation wird das vorherige Ergebnis durch das neu berechnete Ergebnis ersetzt; die Ergebnisse unterschiedlicher Ausführungen können daher nicht angezeigt und miteinander verglichen werden.

Zum Vergleichen der Ergebnisse müssen Sie Berichte verwenden. Mit Adobe Campaign können Sie einen Berichtsverlauf speichern, um ihn später erneut anzuzeigen. Dieser Verlauf wird während des gesamten Lebenszyklus der Simulation gespeichert.

**Beispiel:**

1. Erstellen Sie eine Simulation für einen Versand, der die Typologie **A** anwendet.
1. Öffnen Sie im Tab **[!UICONTROL Berichte]** einen der verfügbaren Berichte, zum Beispiel **[!UICONTROL Detail der simulationsbedingten Ausschlüsse]**.
1. Klicken Sie oben rechts auf das Symbol zur Erstellung eines neuen Verlaufs.

   ![](assets/campaign_opt_reporting_create_hist.png)

1. Schließen Sie diese Simulation und ändern Sie die Konfiguration der Typologie **A**.
1. Führen Sie die Simulation erneut aus und vergleichen Sie das Ergebnis mit dem in dem Bericht angezeigten Ergebnis, in dem zuvor ein Verlauf erstellt wurde.

   ![](assets/campaign_opt_reporting_edit_hist.png)

   Es können beliebig viele Berichtsverläufe gespeichert werden.

### Berichtsachsen {#reporting-axes}

Auf der Registerkarte **[!UICONTROL Berechnungen]** können Sie Berichtsachsen bezüglich der Zielgruppe definieren. Diese Achsen werden während der [Ergebnisanalyse](#explore-results) verwendet.

>[!NOTE]
>
>Es ist empfehlenswert, die Berichtsachsen in einer Simulationsvorlage zu bestimmen und nicht in jeder einzelnen Simulation.\
>Die Simulationsvorlagen werden im Ordner **[!UICONTROL Ressourcen > Vorlagen > Simulationsvorlagen]** des Campaign-Explorers gespeichert.

**Beispiel:**

Es soll eine zusätzliche Berichtsachse über den Empfängerstatus (&quot;Kunde&quot;, &quot;Interessent&quot; oder kein Status) erstellt werden.

1. Um eine Berichtsachse zu definieren, wählen Sie die Tabelle aus, die die zu verarbeitenden Informationen im Feld **[!UICONTROL Analysedimension]** enthält. Diese Informationen sind obligatorisch.
1. An dieser Stelle wird das entsprechende Feld der Empfängertabelle ausgewählt.

   ![](assets/simu_campaign_opti_09.png)

1. Folgende Optionen stehen zur Verfügung:

   * **[!UICONTROL Erzeugen von Zielüberschneidungsstatistiken]** ermöglicht das Wiederherstellen aller Überschneidungsstatistiken im Simulationsbericht. Überschneidungen sind Empfänger, die in mindestens zwei Sendungen innerhalb einer Simulation angesprochen werden.

     >[!CAUTION]
     >
     >Die Auswahl dieser Option verlängert die Ausführungsdauer der Simulation beträchtlich.

   * **[!UICONTROL Simulationsarbeitstabelle beibehalten]**, um Spuren der Simulation zu speichern.

     >[!CAUTION]
     >
     >Die systematische Speicherung dieser Tabellen erfordert eine erhöhte Speicherkapazität: Stellen Sie sicher, dass Ihre Datenbank über entsprechenden Speicherplatz verfügt.

Bei der Anzeige der Simulationsergebnisse werden Informationen bezüglich des ausgewählten Ausdrucks im Untertab **[!UICONTROL Überschneidungen]** angezeigt.

Die Überschneidungen geben die Empfänger an, die in mindestens zwei verschiedenen Sendungen einer Simulation den Zielgruppen angehören.

![](assets/simu_campaign_opti_13.png)

>[!NOTE]
>
>Dieser Untertab wird nur angezeigt, wenn die Option **[!UICONTROL Statistiken der Zielgruppenüberschneidung erzeugen]** aktiviert wurde.

Informationen bezüglich der Berichtsachsen können in den Berichten der Ausschlussanalyse genutzt werden, die im Unter-Tab **[!UICONTROL Ausschlussanalyse]** erstellt werden. [Weitere Informationen](#explore-results).

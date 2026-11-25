---
product: campaign
title: Angebote auf einem Outbound-Kanal
description: Angebote auf einem Outbound-Kanal
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 55%
---
# Angebote auf einem Outbound-Kanal{#offers-on-an-outbound-channel}



## Angebote per E-Mail versenden {#email-offer-delivery}

In unserer Datenbank gibt es eine Kategorie von Reiseangeboten nach Afrika. Die Eignung, der Kontext und die Darstellungen jedes Angebots wurden konfiguriert. Wir möchten nun eine Kampagne erstellen, um unsere Angebote per E-Mail zu präsentieren.

1. Erstellen Sie Ihre Kampagne und den Workflow zur Bestimmung der Zielgruppe.

   ![Zielgruppenbestimmungs-Workflow der Kampagne „Reisen nach Afrika“: Ordner, Versand, Deduplizierung und zwei Aktivitäten zur Listen-Aktualisierung](assets/offer_delivery_example_001.png)

1. Öffnen Sie die Versand-Aktivität und klicken Sie auf das Symbol **[!UICONTROL Angebote]**.

   ![E-Mail-Versand mit dem Symbol Angebote , das das Fenster Angebotsverwaltung öffnet, sowie Optionen zur Angebotsauswahl und das Feld Platzierung](assets/offer_delivery_example_002.png)

1. Wählen Sie die E-Mail-Platzierung der Live-Umgebung aus, die die Reiseangebote enthält.

   ![Fenster „Angebotsverwaltung“ mit der Liste der Platzierungen, in der die verfügbaren E-Mail-Platzierungen angezeigt werden, einschließlich der Journey der Abonnenten](assets/offer_delivery_example_003.png)

1. Wählen Sie die Kategorie mit den Angeboten für Afrikareisen aus.

   ![Fenster „Angebotsverwaltung“ mit hervorgehobener Kategoriestruktur unter Angebotskatalog und Journey, Kategorie Afrika](assets/offer_delivery_example_004.png)

1. Geben Sie an, dass pro E-Mail jeweils zwei Angebote unterbreitet werden sollen.

   ![Fenster Angebotsverwaltung mit der Kategorie Afrika und der Anzahl der Vorschläge pro Nachricht auf 2 gesetzt](assets/offer_delivery_example_005.png)

1. Schließen Sie das Fenster für die Angebotsverwaltung und erstellen Sie den Inhalt Ihres Versands.

   ![HTML-Inhaltseditor für den E-Mail-Versand mit den Standardansichten „Include“, die für Angebotsvorschläge bereit sind](assets/offer_delivery_example_006.png)

1. Fügen Sie nun mithilfe der Personalisierungsfelder den ersten Angebotsvorschlag in den Versandinhalt ein und wählen Sie die HTML-Rendering-Funktion.

   ![HTML-Symbolleistenmenü für Inhalte: Vorschläge, dann Vorschlag 1, Rendering-Funktion und HTML-Rendering](assets/offer_delivery_example_007.png)

1. Fügen Sie auf die gleiche Weise den zweiten Angebotsvorschlag ein.

   ![HTML-E-Mail-Inhalte mit beiden Vorschlägen enthalten Zeilen, die die Rendering-/HTML-Ansicht vor dem Abmelde-Link verwenden](assets/offer_delivery_example_008.png)

1. Klicken Sie auf **[!UICONTROL Vorschau]** und wählen Sie einen Empfänger aus, um Nachricht und Angebote so anzeigen zu lassen, wie der Empfänger sie erhalten wird.

   ![Registerkarte Versandvorschau , auf der die E-Mail mit dem Angebotstitel „Überqueren der Sahara“, dem Text und dem Bild für einen ausgewählten Empfänger angezeigt wird](assets/offer_delivery_example_009.png)

1. Speichern Sie den Versand und starten Sie den Zielgruppen-Workflow.
1. Öffnen Sie den Versand und gehen Sie in den Tab **[!UICONTROL Verfolgung]**: Sie können feststellen, dass das Angebotsmodul die zu unterbreitenden Vorschläge aus den verschiedenen, in der Kategorie verfügbaren Angeboten ausgewählt hat.

   ![Registerkarte Versandprüfung : Protokollvorschläge, die pro Angebot generiert wurden, wie z. B. die Angebote Pyramiden und Sahara](assets/offer_delivery_example_010.png)

## Durchführen einer Angebotssimulation {#perform-an-offer-simulation}

1. Klicken Sie im Tab **[!UICONTROL Profile und Zielgruppen]** auf die Schaltfläche **[!UICONTROL Simulationen]** und anschließend auf **[!UICONTROL Erstellen]**.

   ![Simulationsliste mit der Schaltfläche Erstellen, die das Dialogfeld „Neue Angebotssimulation“ mit Vorlage, Titel und Ordner öffnet](assets/offer_simulation_001.png)

1. Benennen Sie die Simulation und geben Sie gegebenenfalls Ausführungsparameter an.

   ![Dialogfeld „Neue Angebotssimulation“ mit der Bezeichnung 1-Jahres-Abonnenten, dem Simulationsordner und den Ausführungseinstellungen](assets/offer_simulation_example_002.png)

1. Speichern Sie die Simulation. Sie wird anschließend in einem neuen Tab geöffnet.

   ![Simulations-Dashboard von Abonnentinnen und Abonnenten mit einem Jahr Dauer mit der Registerkarte Bearbeiten und einer Schaltfläche Simulation starten](assets/offer_simulation_example_003.png)

1. Gehen Sie in den Tab **[!UICONTROL Bearbeiten]** > **[!UICONTROL Perimeter]**.

   ![Registerkarte „Simulation bearbeiten“, Bereich „Umfang“, mit Umgebung oder Kategorie, Platzierung, Themen, Kontaktdatum und Vorschlägen](assets/offer_simulation_example_004.png)

1. Wählen Sie die Kategorie aus, für die Sie die Angebotssimulation durchführen möchten.

   ![Die Umgebungs- oder Kategorieliste wurde unter Angebote - Design und Angebotskatalog mit der ausgewählten Reisekategorie erweitert](assets/offer_simulation_example_005.png)

1. Wählen Sie die Platzierung für die Simulation aus.

   ![Platzierungsliste unter der Kategorie „Reisen“ mit Briefpost und E-Mail (Umgebung - Empfänger)](assets/offer_simulation_example_006.png)

1. Geben Sie Gültigkeitsdaten ein. Sie müssen mindestens ein Startdatum eingeben. Dies ermöglicht es dem Angebotsmodul, Angebote zu filtern und nur jene zu berücksichtigen, die zum angegebenen Zeitpunkt tatsächlich verfügbar sind.
1. Geben Sie bei Bedarf Themen an, um die Anzahl der Angebote zu begrenzen.

   Im vorliegenden Beispiel enthält die Kategorie **Finanzdienstleistungen** zwei Unterkategorien mit je einem unterschiedlichen Thema. Die Simulation soll sich nur auf die Kategorie mit dem Anwendungsthema **Kunden > 1 Jahr** beziehen.

   ![Bereich Umfang mit dem Thema Kunde > 1 Jahr, das in das Feld Designs für die Kategorie Reise eingegeben wurde](assets/offer_simulation_example_007.png)

1. Definieren Sie die Zielgruppe.

   ![Assistent für den Zielgruppenauswahlfilter wählen Sie zuerst eine Empfängerliste und dann die Liste der Vielreisenden aus](assets/offer_simulation_example_008.png)

1. Geben Sie die Anzahl an Angeboten an, die Sie jedem Empfänger unterbreiten möchten.

   Im vorliegenden Beispiel soll das Angebotsmodul für jeden Empfänger die drei Angebote auswählen, die die höchste Gewichtung aufweisen.

   ![Bereich „Umfang“ mit der auf 3 gesetzten Anzahl der Vorschläge und der Zielgruppenabfrage auf der Versandliste für Sonderangebote](assets/offer_simulation_example_009.png)

1. Speichern Sie die Konfiguration und klicken Sie im **[!UICONTROL Dashboard]** auf **[!UICONTROL Simulation starten]**.

   ![Das Dashboard startet den Simulationsdialog und fordert zur Bestätigung auf, wobei die Schaltfläche „OK“ hervorgehoben ist](assets/offer_simulation_example_010.png)

1. Nach Abschluss der Simulation können Sie im Tab **[!UICONTROL Ergebnisse]** die Aufschlüsselung der Vorschläge pro Angebot ansehen.

   Im vorliegenden Beispiel beruht die Aufschlüsselung wie konfiguriert auf drei Vorschlägen.

   ![Registerkarte Simulationsergebnisse mit Aufschlüsselung der Vorschläge nach Angeboten: Populationsgröße 30, Anzahl der Vorschläge 30](assets/offer_simulation_example_011.png)

1. Rufen Sie den Bericht **[!UICONTROL Angebotsaufschlüsselung nach Rang]** auf, um die Reihenfolge der durch das Angebotsmodul ausgewählten Angebote im Detail anzusehen.

   ![Aufschlüsselung der Angebote nach Ranking-Bericht mit Ranking-Tabelle für Reisen in die USA und nach Frankreich sowie Tortendiagramm](assets/offer_simulation_example_012.png)

1. Ändern Sie bei Bedarf den Perimeter Ihrer Simulation und klicken Sie erneut auf **[!UICONTROL Simulation starten]**, bis das Ergebnis Ihren Erwartungen entspricht.

   ![Das Dashboard startet den Simulationsdialog und fordert zur Bestätigung auf, wobei die Schaltfläche „OK“ hervorgehoben ist](assets/offer_simulation_example_010.png)

1. Sie haben mithilfe der Verlaufs- und Exportfunktionen des Berichts die Möglichkeit, die Simulationsdaten zu speichern.

   ![Aufschlüsselung der Angebote nach Ranking, wobei das Menü „Exportieren“ und das Symbol „Speichern“ hervorgehoben sind](assets/offer_simulation_example_013.png)

---
product: campaign
title: Anreichern von Daten
description: Erfahren Sie mehr über die Workflow-Aktivität "Anreicherung".
feature: Workflows, Enrichment Activity
role: User
exl-id: 3b3fa15f-b16e-42c8-a2e6-03350aee1903
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 70%

---

# Anreichern von Daten{#enriching-data}



## Über die Anreicherung von Daten {#about-enriching-data}

In diesem Anwendungsbeispiel werden mögliche Verwendungen der Aktivität **[!UICONTROL Anreicherung]** in einem Zielgruppen-Workflow beschrieben. Weitere Informationen zur Verwendung der Aktivität **[!UICONTROL Anreicherung]** finden Sie unter [Anreicherung](enrichment.md).

In [diesem Abschnitt](email-enrichment-with-custom-date-fields.md) finden Sie außerdem ein Anwendungsbeispiel zur Anreicherung eines E-Mail-Versands mit benutzerdefinierten Datumsangaben.

Den Kontakten in der Marketingdatenbank wird über eine Webanwendung eine Einladung zur Teilnahme an einem Wettbewerb geschickt. Die Ergebnisse des Wettbewerbs werden im **[!UICONTROL Wettbewerbsergebnisse]** Tabelle. Diese Tabelle ist mit der Kontakttabelle verknüpft (**[!UICONTROL Empfänger]**). Die **[!UICONTROL Wettbewerbsergebnisse]** -Tabelle enthält die folgenden Felder:

* Wettbewerbsname (@game),
* Versuchnummer (@trial),
* Score (@score).

![](assets/uc1_enrich_1.png)

Ein in der **[!UICONTROL Empfängertabelle]** enthaltener Kontakt kann mehrere Einträge in der Tabelle der **[!UICONTROL Wettbewerbsergebnisse]** aufweisen. Die Relation zwischen beiden Tabellen ist somit vom Typ 1:n. Nachfolgend werden für einen Empfänger beispielhaft die Ergebnislogs dargestellt:

![](assets/uc1_enrich_2.png)

Ziel des vorliegenden Beispiels ist es, den Teilnehmern des letzten Wettbewerbs eine je nach erreichtem Score personalisierte Mitteilung zukommen zu lassen. Der Teilnehmer mit dem höchsten Score erhält den ersten Preis, der Teilnehmer mit dem zweithöchsten Score einen Trostpreis und alle anderen Teilnehmer werden aufgefordert, ihr Glück beim nächsten Wettbewerb erneut zu versuchen.

Der Workflow für dieses Anwendungsbeispiel stellt sich wie folgt dar:

![](assets/uc1_enrich_3.png)

Die Workflow-Erstellung gliedert sich in folgende Schritte:

1. Platzierung von zwei **[!UICONTROL Abfragen]** und einer **[!UICONTROL Schnittmenge]** zum Abruf aller neuen Abonnenten, die am letzten Wettbewerb teilgenommen haben.
1. Die Aktivität **[!UICONTROL Anreicherung]** wird verwendet, um Daten hinzuzufügen, die in der Tabelle **[!UICONTROL Wettbewerbsergebnisse]** gespeichert sind. Das Feld **[!UICONTROL Score]**, in dem die Personalisierung des Versands ausgeführt wird, wird der Arbeitstabelle des Workflows hinzugefügt.
1. Mithilfe der Aktivität des Typs **[!UICONTROL Aufspaltung]** werden je nach erreichtem Score Empfänger-Teilmengen erstellt.
1. Jeder Teilmenge wird eine Aktivität **[!UICONTROL Versand]** hinzugefügt.

## 1. Schritt: Zielgruppenbestimmung {#step-1--targeting}

In der ersten Abfrage werden Kontakte abgerufen, die innerhalb der letzten sechs Monate in die Datenbank aufgenommen wurden.

![](assets/uc1_enrich_4.png)

In der zweiten Abfrage werden die Kontakte abgerufen, die am letzten Wettbewerb teilgenommen haben.

![](assets/uc1_enrich_5.png)

Die **[!UICONTROL Schnittmenge]** ermittelt dann die Population, die beiden Bedingungen entspricht.

## 2. Schritt: Anreicherung {#step-2--enrichment}

In diesem Beispiel erfahren Sie, wie Sie Sendungen entsprechend des Felds **[!UICONTROL Score]** in der Tabelle **[!UICONTROL Wettbewerbsergebnisse]** personalisieren. Diese Tabelle weist eine 1:n-Beziehung mit der Empfängertabelle auf. Die Aktivität **[!UICONTROL Anreicherung]** wird verwendet, um Daten aus einer mit der Filterdimension verknüpften Tabelle zur Arbeitstabelle des Workflows hinzuzufügen.

1. Klicken Sie auf den Link **[!UICONTROL Daten hinzufügen...]** im Bearbeitungsbildschirm der Anreicherung und aktivieren Sie die Option **[!UICONTROL Daten in Relation mit der Filterdimension]**. Klicken Sie dann auf **[!UICONTROL Weiter]**.

   ![](assets/uc1_enrich_6.png)

1. Aktivieren Sie im nächsten Bildschirm wiederum die Option **[!UICONTROL Daten in Relation mit der Filterdimension]**, markieren Sie die Tabelle **[!UICONTROL Wettbewerbsergebnisse]** und klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/uc1_enrich_7.png)

1. Geben Sie eine ID und einen Titel ein und wählen Sie die **[!UICONTROL Zeilenanzahl begrenzen]** in der **[!UICONTROL Erfasste Daten]** -Feld. Im **[!UICONTROL Abrufen von Zeilen]** als Wert &quot;1&quot;ein. Für jeden Empfänger fügt die Anreicherungsaktivität eine Zeile aus der **[!UICONTROL Wettbewerbsergebnisse]** in die Arbeitstabelle des Workflows. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/uc1_enrich_8.png)

1. In diesem Beispiel möchten wir das höchste Ergebnis des Empfängers abrufen, jedoch nur für den letzten Wettbewerb. Fügen Sie dazu einen Filter zum **[!UICONTROL Wettbewerbsname]** -Feld, um alle Zeilen auszuschließen, die sich auf frühere Auswahlverfahren beziehen. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/uc1_enrich_9.png)

1. Navigieren Sie zu **[!UICONTROL Sortieren]** und klicken Sie auf **[!UICONTROL Hinzufügen]** -Schaltfläche, wählen Sie die **[!UICONTROL Ergebnis]** und aktivieren Sie das Kontrollkästchen im **[!UICONTROL absteigend]** -Spalte, um Elemente der **[!UICONTROL Ergebnis]** in absteigender Reihenfolge. Für jeden Empfänger fügt die Anreicherungsaktivität eine Zeile hinzu, die dem höchsten Wert für das letzte Spiel entspricht. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/uc1_enrich_10.png)

1. Im **[!UICONTROL Daten zum Hinzufügen]** durch Doppelklick auf das **[!UICONTROL Ergebnis]** -Feld. Für jeden Empfänger fügt die Anreicherungsaktivität nur die **[!UICONTROL Ergebnis]** -Feld. Klicken Sie auf **[!UICONTROL Beenden]**.

   ![](assets/uc1_enrich_11.png)

Klicken Sie mit der rechten Maustaste auf die in die Anreicherungsaktivität eingehende Transition und wählen Sie die Option **[!UICONTROL Ergebnis anzeigen...]**. Die Arbeitstabelle enthält folgende Daten:

![](assets/uc1_enrich_13.png)

Das Schema der Arbeitstabelle stellt sich wie folgt dar:

![](assets/uc1_enrich_15.png)

Wiederholen Sie den Vorgang für die ausgehende Transition der Anreicherungsaktivität. Sie können sehen, dass die Score-Daten der Empfänger hinzugefügt wurden. Für jeden Empfänger wurde der höchste Score abgerufen.

![](assets/uc1_enrich_12.png)

Auch das Schema wurde entsprechend angereichert.

![](assets/uc1_enrich_14.png)

## 3. Schritt: Aufspaltung und Versand {#step-3--split-and-delivery}

Im Anschluss an die Anreicherung sorgt die **[!UICONTROL Aufspaltung]** für die Verteilung der Empfänger nach den erreichten Scores.

![](assets/uc1_enrich_18.png)

1. Die erste Teilmenge (**Gewinner**) enthält den Empfänger mit dem höchsten Score. Definieren Sie hierzu eine Begrenzung der Datensatzanzahl, sortieren Sie die Scores in absteigender Reihenfolge und begrenzen Sie die Datensatzanzahl auf 1.

   ![](assets/uc1_enrich_16.png)

1. Die zweite Teilmenge (**Trostpreis**) enthält den Empfänger mit dem zweithöchsten Score. Konfigurieren Sie die zweite Teilmenge analog zur ersten.

   ![](assets/uc1_enrich_17.png)

1. Die dritte (**Verlierer**) enthält alle anderen Empfänger. Navigieren Sie zu **[!UICONTROL Allgemein]** und überprüfen Sie die **[!UICONTROL Komplement erzeugen]** , um alle Empfänger auszuwählen, die nicht die beiden höchsten Werte erreicht haben.

   ![](assets/uc1_enrich_19.png)

1. Schließen Sie an jede Teilmenge einen **[!UICONTROL Versand]** an. Verwenden Sie für jeden Versand eine andere Versandvorlage.

   ![](assets/uc1_enrich_20.png)

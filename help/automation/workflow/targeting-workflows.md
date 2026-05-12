---
title: Erstellen eines Zielgruppen-Workflows
description: Hier erfahren Sie, wie Sie in einem Workflow Zielgruppen erstellen.
feature: Query Editor, Data Management
version: Campaign v8, Campaign Classic v7
exl-id: 27be9d5a-168c-470e-a480-f3c71858fc75
TQID: https://experienceleague.adobe.com/njUqAgkAYMjYMBQvnwt9HOO0aBNX8BRmKJZeccYejhc
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 2377
ht-degree: 71%

---

# Erstellen eines Zielgruppen-Workflows{#target-data}

Workflows können für die Abfrage einer Datenbank und die Segmentierung von Daten verwendet werden. Das Workflow-Modul von Campaign ist ein leistungsstarkes Tool, um Daten-Management-Aktivitäten durchzuführen, Daten zu extrahieren, anzureichern und umzuwandeln, Zielgruppen zu verwalten und Populationen zu verfeinern.

Zielgruppen-Workflows ermöglichen die Erstellung mehrerer Versandziele. Sie können Abfragen erstellen, Vereinigungen oder Ausschlüsse basierend auf bestimmten Kriterien definieren, mithilfe von Workflow-Aktivitäten Zeitpläne hinzufügen. Das Ergebnis dieser Zielgruppenbestimmung kann automatisch in eine Liste übertragen werden, die als Zielgruppe der Versandaktionen dienen kann.

Adobe Campaign bietet in den Workflows darüber hinaus Data Management-Optionen, die erweiterte Funktionen für komplexe Zielgruppenbestimmungen enthalten. Weitere Informationen hierzu finden Sie unter [Data Management](targeting-workflows.md#data-management).

Alle diese Aktivitäten sind im ersten Tab der Workflow-Palette enthalten.

>[!NOTE]
>
>Zielgruppenbestimmungs-Aktivitäten werden in diesem [Abschnitt](activities.md) beschrieben.

Der Zugriff auf Zielgruppen-Workflows erfolgt im Navigationsbaum über den Knoten **[!UICONTROL Profile und Zielgruppen > Aufträge > Zielgruppen-Workflows]** oder auf der Startseite über die Rubrik **[!UICONTROL Profile und Zielgruppen]**.

![](assets/target_wf.png)

Im Gegensatz dazu werden die im Rahmen einer Kampagne erstellten Zielgruppen-Workflows zusammen mit den anderen Kampagnen-Workflows gespeichert.

## Wichtige Schritte zum Erstellen eines Zielgruppen-Workflows {#implementation-steps-}

In den folgenden Abschnitten finden Sie Details zum Erstellen eines Zielgruppen-Workflows:

1. **Identifizieren** von Daten in der Datenbank – Siehe [Erstellen von Abfragen](#create-queries)
1. **Vorbereiten** der Daten auf die Versandanforderungen – Siehe [Anreichern und Ändern von Daten](#enrich-and-modify-data)
1. **Verwenden** von Daten zur Durchführung von Aktualisierungen oder innerhalb eines Versands – Siehe [Aktualisieren der Datenbank](use-workflow-data.md#update-the-database)

Die Ergebnisse aller Anreicherungen und aller Behandlungen, die während der Zielgruppenbestimmung durchgeführt werden, werden gespeichert und können über Personalisierungsfelder beispielsweise zur Gestaltung individueller Nachrichten verwendet werden. Weitere Informationen hierzu finden Sie im Abschnitt [Zielgruppendaten](use-workflow-data.md#target-data).

## Zielgruppenbestimmungs- und Filterdimensionen {#targeting-and-filtering-dimensions}

Bei Vorgängen zur Datensegmentierung wird der Zielgruppenbestimmungsschlüssel einer Filterdimension zugeordnet. Mit der Zielgruppendimension können Sie die Population definieren, auf die sich der Vorgang bezieht: Empfängerinnen und Empfänger, Vertragsbegünstigte, Benutzerinnen und Benutzer, Abonnentinnen und Abonnenten usw. Mit der Filterdimension können Sie die Population anhand bestimmter Kriterien auswählen: Vertragsinhaber, Newsletter-Abonnenten usw.

Um beispielsweise Kunden auszuwählen, die seit mehr als 5 Jahren über eine Lebensversicherungspolice verfügen, wählen Sie die folgende Zielgruppendimension aus: **Kunden** und die folgende Filterdimension: **Vertragsinhaber**. Anschließend können Sie die Filterbedingungen innerhalb der Abfrageaktivität definieren

Nach Auswahl einer Zielgruppendimension stehen nur die Filterdimensionen zur Verfügung, die mit der gewählten Zielgruppendimension kompatibel sind.

Diese beiden Dimensionen müssen miteinander verknüpft sein. Der Inhalt der Liste **[!UICONTROL Filterdimension]** hängt somit von der im ersten Feld angegebenen Zielgruppendimension ab.

Bei Auswahl der Empfängerinnen und Empfänger (**Empfänger**) stehen folgende Filterdimensionen zur Verfügung:

![](assets/query-filter-dimensions.png)

Für **Besuchende** dagegen enthält die Liste die folgenden Filterdimensionen:

![](assets/query-filter-dimension-2.png)

## Erstellen von Abfragen {#create-queries}

### Arbeiten mit zusätzlichen Daten {#select-data}

Mit einer **[!UICONTROL Abfrageaktivität]** können Sie grundlegende Daten zum Aufbau der Zielpopulation auswählen. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](query.md#create-a-query).

Sie können auch mithilfe der folgenden Aktivitäten Daten aus der Datenbank abfragen und weiter filtern: [Inkrementelle Abfrage ](incremental-query.md), [Liste lesen](read-list.md).

Es ist möglich, zusätzliche Daten zu sammeln, die während des gesamten Lebenszyklus des Workflows weitergeleitet und verarbeitet werden. Weitere Informationen hierzu finden Sie unter [Hinzufügen von Daten](query.md#add-data) und [Bearbeiten von zusätzlichen Daten](#edit-additional-data).

### Bearbeiten zusätzlicher Daten {#edit-additional-data}

Nach Hinzufügung der zusätzlichen Daten können Sie diese bearbeiten oder zur Verfeinerung der in der Abfrageaktivität definierten Zielgruppe verwenden.

Über den Link **[!UICONTROL Zusätzliche Daten bearbeiten...]** können Sie die hinzugefügten Daten anzeigen und sie gegebenenfalls ändern oder ergänzen.

![](assets/edit-additional-data.png)

Um Daten zu den zuvor definierten Ausgabespalten hinzuzufügen, wählen Sie sie in der Liste der verfügbaren Felder aus. Um eine neue Ausgabespalte zu erstellen, klicken Sie auf das Symbol **[!UICONTROL Hinzufügen]**, wählen Sie das Feld aus und klicken Sie auf **[!UICONTROL Ausdruck bearbeiten]**.

![](assets/query_add_an_output_column.png)

Klicken Sie auf die Schaltfläche **Erweiterte Auswahl**.

![](assets/query_add_an_output_column_formula.png)

Kreuzen Sie den gewünschten Formeltyp an, beispielsweise Aggregat.

![](assets/query_add_aggregate.png)

Mit **[!UICONTROL Option „Unterelement hinzufügen]** können Sie berechnete Daten an die Sammlung anhängen. Auf diese Weise können Sie zusätzliche Daten aus der Sammlung auswählen oder Aggregatberechnungen für Sammlungselemente definieren.

Die Unterelemente erscheinen als Unterordner der Sammlung, der sie angehören.

Sammlungen werden in der Unterregisterkarte **[!UICONTROL Sammlungen]** angezeigt. Sie können die gesammelten Elemente filtern, indem Sie auf das Symbol **[!UICONTROL Detail]** der ausgewählten Sammlung klicken. Mit dem Filterassistenten können Sie die gesammelten Daten auswählen und die auf die Daten in der Sammlung anzuwendenden Filterbedingungen festlegen.

### Einschränken einer Zielgruppe mithilfe zusätzlicher Daten {#refine-the-target-using-additional-data}

Mit den gesammelten zusätzlichen Daten können Sie die Datenfilterung in der Datenbank verfeinern. Klicken Sie dazu auf den Link **[!UICONTROL Zielgruppe mithilfe zusätzlicher Daten einschränken…]**: Dies ermöglicht die Überfilterung der hinzugefügten Daten.

![](assets/wf_add_data_use_additional_data.png)

### Vereinheitlichen von Daten {#homogenize-data}

Bei Aktivitäten vom Typ **[!UICONTROL Vereinigung]** oder **[!UICONTROL Schnittmenge]** können Sie festlegen, dass nur gemeinsame Zusatzdaten beibehalten werden, um eine konsistente Datenbasis zu erhalten. In diesem Fall enthält die resultierende temporäre Arbeitstabelle dieser Aktivität nur die Zusatzdaten, die in allen eingehenden Mengen enthalten sind.

![](assets/use-common-add-data-only.png)

### Abstimmen mit zusätzlichen Daten {#reconciliation-with-additional-data}

Während der Datenabstimmungsphasen (**[!UICONTROL Vereinigung]**, **[!UICONTROL Schnittmenge]** usw.) können Sie die für die Datenabstimmung zu verwendenden Spalten aus den zusätzlichen Spalten auswählen. Konfigurieren Sie dazu eine Abstimmung über eine Auswahl von Spalten und geben Sie die Hauptmenge an. Wählen Sie dann die Spalten in der unteren Spalte des Fensters aus, wie im folgenden Beispiel gezeigt:

![](assets/select-column-and-join.png)

Wählen Sie einen Ausdruck aus und bestätigen Sie Ihre Auswahl.

![](assets/select-column-and-join-2.png)


### Erstellen von Teilmengen {#create-subsets}

Mit **[!UICONTROL Aktivität „Aufspaltung]** können Sie Teilmengen aus Kriterien erstellen, die über Extraktionsabfragen definiert wurden. Wenn Sie für jede Teilmenge eine Filterbedingung für die Population bearbeiten, greifen Sie dann auf die Standardabfrageaktivität zu, mit der Sie die Zielgruppensegmentierungsbedingungen definieren können.

Sie können eine Zielgruppe in mehrere Teilmengen unterteilen, indem Sie als Filterbedingungen nur zusätzliche Daten oder aber diese zusätzlich zu den Zielgruppendaten verwenden. Sie können auch externe Daten nutzen, wenn Sie die Option **Federated Data Access** besitzen.

Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#create-subsets-using-the-split-activity).

## Segmentieren von Daten {#segment-data}

### Kombinieren mehrerer Zielgruppen (Vereinigung) {#combine-several-targets--union-}

Die Aktivität Vereinigung ermöglicht es, das Ergebnis mehrerer Aktivitäten innerhalb einer Transition zu kombinieren. Sets müssen nicht unbedingt homogen sein.

![](assets/union-keys-only.png)

Zur Abstimmung der Daten stehen folgende Optionen zur Verfügung:

* **[!UICONTROL Nur die Schlüssel]**

  Diese Option kann bei homogenen Eingangspopulationen verwendet werden.

* **[!UICONTROL Alle gemeinsamen Spalten]**

  Diese Option ermöglicht die Abstimmung der Datensätze über alle den verschiedenen Zielpopulationen gemeinsamen Spalten.

  Adobe Campaign identifiziert Spalten anhand ihres Namens. Eine Toleranzschwelle wird akzeptiert: Beispielsweise kann eine Spalte „E-Mail“ als identisch mit einer Spalte &quot;@email“ erkannt werden.

* **[!UICONTROL Auswahl an Spalten]**

  Diese Option ermöglicht die Auswahl der Spalten, die zur Abstimmung herangezogen werden sollen.

  Wählen Sie zunächst die die Quelldaten enthaltende Hauptmenge aus und anschließend die Spalten, die den Join herstellen sollen.

  ![](assets/join-reconciliation-options.png)

  >[!CAUTION]
  >
  >Die Populationen werden im Rahmen der Abstimmung nicht auf Duplikate geprüft.

  Sie können die Populationsgröße auf eine bestimmte Anzahl von Datensätzen beschränken. Klicken Sie dazu auf die entsprechende Option und geben Sie die Anzahl der beizubehaltenden Datensätze an.

  Geben Sie außerdem die Priorität der Eingangspopulationen an. Im unteren Bereich des Fensters werden die in die Vereinigungsaktivität eingehenden Transitionen aufgelistet. Die Reihenfolge kann mithilfe der blauen Pfeile rechts verändert werden.

  Die beibehaltenen Datensätze stammen zunächst aus der ersten eingehenden Transition und werden, falls die gewünschte Anzahl noch nicht erreicht ist, durch die Population der folgenden Transitionen ergänzt.

  ![](assets/join_limit_nb_priority.png)

### Extrahieren gemeinsamer Daten (Schnittmenge) {#extract-joint-data--intersection-}

![](assets/traitements.png)

Über die Schnittmenge lassen sich nur die Zeilen abrufen, die alle Populationen der eingehenden Transitionen gemeinsam haben. Diese Aktivität muss wie die Vereinigungsaktivität konfiguriert werden.

Es ist außerdem möglich, nur eine Auswahl an Spalten oder nur die Spalten, die in allen eingehenden Populationen enthalten sind, abzurufen.

Die Schnittmengenaktivität wird im Abschnitt [Schnittmenge](intersection.md) detailliert beschrieben.

### Ausschließen von Populationen (Ausschluss) {#exclude-a-population--exclusion-}

Mithilfe der Ausschlussaktivität können Sie die Elemente einer Zielgruppe aus einer anderen Zielpopulation ausschließen. Die Zielgruppendimension der Ausgabe dieser Aktivität ist die der Hauptgruppe.

Bei Bedarf können eingehende Tabellen bearbeitet werden. Um eine Zielgruppe aus einer anderen Dimension auszuschließen, muss diese Zielgruppe tatsächlich auf dieselbe Zielgruppendimension wie die Hauptzielgruppe zurückgesetzt werden. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Hinzufügen]** und geben Sie die Bedingungen der Dimensionsänderung an.

Die Abstimmung der Daten kann über die Kennungen, eine Achsenänderung oder einen Join erfolgen.

![](assets/exclusion-add-rule.png)

### Erstellen von Teilmengen mithilfe der Aufspaltungs-Aktivität {#create-subsets-using-the-split-activity}

Bei der Aktivität **[!UICONTROL Aufspaltung]** handelt es sich um eine Standardaktivität, die die unbegrenzte Erstellung von Teilmengen mit einer oder mehreren Filterdimensionen ermöglicht. Es kann eine ausgehende Transition pro Teilmenge oder eine eindeutige Transition erzeugt werden.

Dabei können von der Transition übermittelte Zusatzdaten in den Filterbedingungen verwendet werden.

Zur Konfiguration wählen Sie zunächst die Bedingungen aus:

1. Ziehen Sie in Ihren Workflow die Aktivität **[!UICONTROL Aufspaltung]**.
1. Wählen Sie im Tab **[!UICONTROL Allgemein]** die gewünschte Option aus: **[!UICONTROL Zielgruppendaten und zusätzliche Daten nutzen]**, **[!UICONTROL Nur zusätzliche Daten nutzen]** oder **[!UICONTROL Externe Daten nutzen]**.
1. Bei Auswahl der Option **[!UICONTROL Zielgruppendaten und zusätzliche Daten nutzen]** erlaubt die Zielgruppendimension die Verwendung aller von der eingehenden Transition übermittelten Daten.

   ![](assets/split-general-tab-options.png)

   Bei der Erstellung von Teilmengen werden die zuvor definierten Filterparameter genutzt.

   Um Filterbedingungen zu definieren, wählen Sie die Option **[!UICONTROL Filterbedingung für die eingehende Population hinzufügen]** und klicken Sie auf den Link **[!UICONTROL Bearbeiten…]**. Geben Sie dann die Filterbedingungen für die Erstellung dieser Teilmenge an.

   ![](assets/split-subset-config-all-data.png)

   Ein Beispiel für die Verwendung der Aktivität **[!UICONTROL Aufspaltung]** zur Segmentierung der Zielgruppe in unterschiedliche Populationen finden Sie in [diesem Abschnitt](cross-channel-delivery-workflow.md).

   Im Feld **[!UICONTROL Titel]** können Sie die erstellte Teilmenge benennen. Der Titel wird auf der ausgehenden Transition angezeigt.

   Sie können der Teilmenge außerdem einen Segment-Code zuweisen, welcher ihre Identifizierung und ihre Verwendung als Zielpopulation ermöglicht.

   Bei Bedarf können die Zielgruppenbestimmungs- und Filterungsdimensionen für jede Teilmenge, die Sie erstellen wollen, einzeln angepasst werden. Bearbeiten Sie dazu die Filterbedingung der Teilmenge und aktivieren Sie die Option **[!UICONTROL Spezifische Filterdimension verwenden]**.

   ![](assets/split-subset-config-specific-filtering.png)

1. Wenn die Option **[!UICONTROL Nur Zusatzdaten verwenden]** aktiviert wurde, stehen nur die zusätzlichen Daten zur Filterung der Teilmengen zur Verfügung.

1. Wenn die Option **Federated Data Access** aktiviert wurde, bietet die Option **[!UICONTROL Externe Daten verwenden]** die Möglichkeit, Daten einer bereits verbundenen externen Datenbank zu verwenden oder eine neue Verbindung herzustellen.

Danach müssen neue Teilmengen hinzugefügt werden:

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und definieren Sie die Filterbedingungen.

   ![](assets/wf_split_add_a_tab.png)

1. Definieren Sie die Filterdimension im **[!UICONTROL Allgemein]**-Tab (siehe oben). Sie gilt automatisch für alle Teilmengen.

   ![](assets/wf_split_edit_filtering.png)

1. Bei Bedarf können Sie die Filterdimension für jede Teilmenge einzeln ändern. Auf diese Weise können Sie ein Set für alle Gold-Karteninhaber erstellen: einen für alle Empfänger, die auf den neuesten Newsletter geklickt haben, und einen dritten für Personen im Alter von 18 bis 25 Jahren, die innerhalb der letzten 30 Tage einen Kauf im Geschäft getätigt haben, wobei alle die gleiche Aufspaltungsaktivität verwenden. Wählen Sie dazu die Option **[!UICONTROL Spezifische Filterdimension verwenden]** und wählen Sie den Kontext der Datenfilterung aus.

Nach der Erstellung von Teilmengen zeigt die Aufspaltungsaktivität standardmäßig so viele ausgehende Transitionen an, wie Teilmengen vorhanden sind:

![](assets/wf_split_multi_outputs.png)

Sie können alle diese Teilmengen in einer einzigen Ausgabetransition gruppieren. In diesem Fall wird beispielsweise der Link zu den entsprechenden Teilmengen im Segment-Code angezeigt. Wählen Sie dazu die Option **[!UICONTROL Alle Teilmengen in derselben Tabelle erzeugen]**.

![](assets/wf_split_single_output.png)

Dies ist beispielsweise dann interessant, wenn Sie eine einzige Versandaktivität anschließen, den Inhalt aber je nach Segment-Code der Empfänger-Teilmenge personalisieren möchten.


Teilmengen können auch mithilfe der Aktivität **[!UICONTROL Segmente]** erstellt werden. Weitere Informationen hierzu finden Sie im Abschnitt [Segmente](cells.md).

### Verwenden von Zielgruppendaten {#using-targeted-data}

Nach Identifizierung und Aufbereitung der Daten können diese in folgenden Kontexten verwendet werden:

* Update der Datenbank im Anschluss an die verschiedenen Workflow-Aktivitäten.

  Weitere Informationen hierzu finden Sie unter [Daten aktualisieren](update-data.md).

* Update von existierenden Listen.

  Weitere Informationen hierzu finden Sie unter [Listen-Update](list-update.md).

* Vorbereitung und/oder Start von Sendungen direkt im Workflow.

  Weitere Informationen hierzu finden Sie unter [Versand](delivery.md), [Versand bearbeiten](delivery-control.md) und [Versand (fortlaufend)](continuous-delivery.md).

## Daten-Management {#data-management}

In Adobe Campaign kombiniert das Daten-Management eine Reihe von Aktivitäten zur Lösung komplexer Zielgruppenbestimmungsprobleme, indem effizientere und flexiblere Tools bereitgestellt werden. Auf diese Weise können Sie für alle Kommunikationen mit einem Kontakt eine konsistente Verwaltung einrichten, indem Sie Informationen zu seinen Verträgen, Abonnements, Reaktionszeiten auf Sendungen usw. verwenden. Mit dem Daten-Management können Sie den Datenlebenszyklus während der Segmentierungsvorgänge verfolgen, insbesondere:

* Zielbestimmungen vereinfacht, u. a. durch Einschluss von nicht im Datamart modelisierten Daten (Erstellung neuer Tabellen: lokale Erweiterung auf jeden Zielgruppen-Workflow in Abhängigkeit von seiner Konfiguration);
* Zwischenergebnisse gespeichert und weitergegeben (interessant im Zuge der Zielbestimmung oder der Datenbankadministration);
* Zugriffe auf externe Datenbanken ermöglicht (optional), was die Berücksichtigung heterogener Datenbanken bei Zielgruppenbestimmungsprozessen zulässt.

Hierfür bietet Adobe Campaign:

* Datenerfassungsaktivitäten: [Dateiübertragung](file-transfer.md), [Laden (Datei)](data-loading-file.md), [Laden (DBMS)](data-loading-rdbms.md), [Daten-Update](update-data.md). Dieser erste Schritt der Datenerfassung bereitet die Daten so vor, dass sie in anderen Aktivitäten verarbeitet werden können. Mehrere Parameter müssen überwacht werden, um sicherzustellen, dass der Workflow korrekt ausgeführt wird und die erwarteten Ergebnisse liefert. Wenn Sie beispielsweise Daten importieren, muss der Primärschlüssel (Pkey) für diese Daten für jeden Datensatz eindeutig sein.
* Zielgruppenbestimmungsaktivitäten wurden um Datenverwaltungsoptionen erweitert: [Abfrage](query.md), [Vereinigung](union.md), [Schnittmenge](intersection.md) [Aufspaltung](split.md). Auf diese Weise können Sie eine Vereinigung oder Schnittmenge zwischen Daten aus verschiedenen Zielgruppendimensionen konfigurieren, sofern eine Datenabstimmung möglich ist.
* Formatierungsaktivitäten: [Anreicherung](enrichment.md), [Dimensionsänderung](change-dimension.md).

>[!CAUTION]
>
>In Workflows löst bei in Relation stehenden Tabellen das Löschen eines Elements der Quelltabelle nicht das Löschen der verbundenen Elemente aus.
>  
>Wenn Sie beispielsweise einen Empfänger über einen Workflow löschen, werden nicht alle Versandverläufe des Empfängers gelöscht. Wenn Sie einen Empfänger jedoch direkt im Ordner „Empfänger“ löschen, werden alle mit diesem Empfänger verknüpften Daten gelöscht.

### Anreichern und Ändern von Daten {#enrich-and-modify-data}

Ergänzend zur Zielgruppendimension ermöglicht die Filterdimension, die Art der abgerufenen Daten zu präzisieren. Weitere Informationen finden Sie in [diesem Abschnitt](targeting-workflows.md#targeting-and-filtering-dimensions).

Identifizierte und abgerufene Daten können angereichert, zusammengefasst und bearbeitet werden, um die Zielgruppenerstellung zu optimieren. Verwenden Sie dazu zusätzlich zu den in [diesem Abschnitt](#segmen-data) beschriebenen Datenmanipulationsaktivitäten die folgenden:

* Mit der Aktivität **[!UICONTROL Anreicherung]** können Sie vorübergehend Spalten zu einem Schema sowie Informationen zu bestimmten Elementen hinzufügen. Weitere Informationen hierzu finden Sie im Abschnitt [Anreicherung](enrichment.md) des Aktivitäten-Repositorys.
* Mit der Aktivität **[!UICONTROL Schema-Bearbeitung]** können Sie die Struktur eines Schemas ändern. Weitere Informationen hierzu finden Sie im Abschnitt [Schema-Bearbeitung](edit-schema.md) des Aktivitäten-Repositorys.
* Mit der Aktivität **[!UICONTROL Dimensionsänderung]** können Sie die Zielgruppendimension beim Erstellen der Zielgruppe ändern. Weitere Informationen hierzu finden Sie im Abschnitt [Dimensionsänderung](change-dimension.md).

---
title: Workflow-Daten verwenden
description: Erfahren Sie, wie Sie die Workflow-Daten verwenden.
feature: Workflows, Data Management
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 75%

---

# Workflow-Daten verwenden{#how-to-use-workflow-data}

Sie können Workflow-Aktivitäten verwenden, um mehrere Aufgaben auszuführen. Im Folgenden finden Sie Beispiele zur Aktualisierung der Datenbank durch die Erstellung von Listen, die Verwaltung von Abonnements, den Versand von Nachrichten über einen Workflow oder die Anreicherung von Sendungen und Zielgruppen.

Eine Reihe von Workflow-Anwendungsfällen finden Sie unter [diesem Abschnitt](workflow-use-cases.md).

## Lebenszyklus der Arbeitsdaten {#data-life-cycle}

### Workflow-temporäre Arbeitstabelle {#work-table}

In einem Workflow werden die von einer Aktivität zur anderen übertragenen Daten in temporären Arbeitstabellen gespeichert.

Die Daten können durch Rechtsklick auf die entsprechende Transition angezeigt und analysiert werden.

![](assets/wf-right-click-analyze.png)

Wählen Sie im Kontextmenü die entsprechende Option aus:

* **[!UICONTROL Zielgruppe anzeigen…]**

   In diesem Menü werden die verfügbaren Daten zur Zielpopulation angezeigt.

   ![](assets/wf-right-click-display.png)

   Sie können auf die Struktur der Arbeitstabelle im **[!UICONTROL Schema]** Registerkarte.

   ![](assets/wf-right-click-schema.png)

   Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](monitor-workflow-execution.md#worktables-and-workflow-schema).

* **[!UICONTROL Zielgruppe analysieren…]**

   Diese Option bietet Zugriff auf den Assistenten zur beschreibenden Analyse, welcher die Erstellung von Statistiken und Berichten über die in der Transition übermittelten Daten ermöglicht.

   Mehr dazu finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html?lang=de){target=&quot;_blank&quot;}.

Die Zielgruppendaten werden im Verlauf der Workflow-Ausführung nach und nach bereinigt. Nur die letzte Arbeitstabelle bleibt zugänglich. Sie haben die Möglichkeit, den Workflow dahingehend zu konfigurieren, dass alle Arbeitstabellen beibehalten werden. Kreuzen Sie hierzu in den Workflow-Eigenschaften die Option **[!UICONTROL Zwischen zwei Ausführungen die ermittelte Population festhalten]** an.

![](assets/wf-purge-data-option.png)

>[!CAUTION]
>
>Diese Option muss **never** in einem **production** Arbeitsablauf. Diese Option wird zur Analyse der Ergebnisse verwendet und ist nur für Testzwecke konzipiert und darf daher nur in Entwicklungs- oder Staging-Umgebungen verwendet werden.


### Zieldaten nutzen {#target-data}

Die in der temporären Arbeitstabelle des Workflows gespeicherten Daten stehen für Personalisierungsaufgaben zur Verfügung. Daten können in Personalisierungsfeldern verwendet werden.

Auf diese Weise können Sie beispielsweise Daten verwenden, die über eine Liste in einem Versand erfasst wurden. Verwenden Sie dazu die folgende Syntax:

```
%= targetData.FIELD %
```

Personalisierungsinformationen vom Typ **[!UICONTROL Erweiterung des Zieldatensatzes]** (targetData) stehen nur in Zielgruppen-Workflows zur Verfügung. Dies bedeutet, dass die Versandzielgruppe im Workflow zu bestimmen und in der in den Versand eingehenden Transition zu übermitteln ist.

Im folgenden Beispiel wird eine Liste mit Kundeninformationen gesammelt, die in einer personalisierten E-Mail verwendet werden können. Gehen Sie wie folgt vor:

1. Erstellen Sie einen Workflow, um die Informationen zu sammeln, sie mit der Datenbank abzustimmen und den Versand zu starten.

   ![](assets/wf-targetdata-sample-1.png)

1. Im vorliegenden Beispiel enthält die Datei folgende Informationen:

   ```
   Music,First name,Last name,Account,CD/DVD,Card
   Pop,David,BLAIR,4323,CD,0
   Rock,Daniel,ARCARI,3222,DVD,1
   Disco,Uma,ALTON,0488,DVD,0
   Jazz,Paul,BOLES,6475,CD,1
   Jazz,David,BOUKHARI,0841,DVD,1
   [...]
   ```

   Um die Datei zu laden, konfigurieren Sie die **[!UICONTROL Laden (Datei)]** Aktivität wie folgt:

   ![](assets/wf-targetdata-sample-2.png)

1. Konfigurieren Sie die **[!UICONTROL Anreicherung]** -Aktivität verwenden, um die erfassten Daten mit denen der Adobe Campaign-Datenbank abzustimmen. Hier dient die Kundennummer als Abstimmschlüssel:

   ![](assets/wf-targetdata-sample-3.png)

1. Konfigurieren Sie dann die **[!UICONTROL Versandaktivität]**. Sie wird basierend auf einer Vorlage erstellt und die Empfänger werden durch die eingehende Transition bestimmt.

   ![](assets/wf-targetdata-sample-4.png)

   >[!CAUTION]
   >
   >Nur die von der Transition übermittelten Daten können für die Versandpersonalisierung verwendet werden. Personalisierungsfelder vom Typ **targetData** stehen nur für die in die **[!UICONTROL Versandaktivität]** eingehende Population zur Verfügung.

1. Verwenden Sie in der Versandvorlage die im Workflow gesammelten Daten.

   Fügen Sie hierfür Personalisierungsfelder vom Typ **[!UICONTROL Erweiterung des Zieldatensatzes]** ein.

   ![](assets/wf-targetdata-sample-5.png)

   Im vorliegenden Beispiel wird der bevorzugte Musikstil des Kunden und der bevorzugte Datenträger (CD oder DVD) - gemäß den Informationen der geladenen Datei - eingefügt.

   Des Weiteren enthält der Versand ein Angebot für Kunden mit Kundenkarte, d. h. für Kunden, bei denen der Wert &#39;Kundenkarte&#39; gleich 1 ist.

   ![](assets/wf-targetdata-sample-6.png)

   Daten vom Typ **[!UICONTROL Erweiterung des Zieldatensatzes]** (targetData) werden wie andere Personalisierungsfelder auch in Sendungen eingefügt. D. h. sie können u. a. in Nachrichtenbetreffs, Linktiteln oder Links selbst verwendet werden.


## Aktualisieren der Datenbank {#update-the-database}

Alle in Workflows erhobenen Daten können zur Aktualisierung der Datenbank oder in Sendungen verwendet werden, um beispielsweise die Möglichkeiten der Inhaltspersonalisierung zu ergänzen (Einfügung der Anzahl von Versicherungspolicen, des durchschnittlichen Warenkorbs im vergangenen Jahr etc.) oder die Zielgruppenbestimmung zu verfeinern (eine Nachricht an die Mitversicherten adressieren, die 1.000 besten Kunden ansprechen etc.). Diese Daten können auch exportiert oder in einer Liste archiviert werden.

### Listen aktualisieren  {#list-updates}

Zur Aktualisierung der Adobe-Campaign-Datenbank und von Listen stehen zwei dedizierte Aktivitäten zur Verfügung:

* Über die Aktivität **[!UICONTROL Listen-Update]** können Arbeitstabellen in einer Datenliste gespeichert werden.

   Hierbei kann eine existierende Liste verwendet oder eine neue erstellt werden. In diesem Fall werden ihr Name und gegebenenfalls ihr Speicherverzeichnis berechnet.

   ![](assets/s_user_create_list.png)

   Siehe [Listen-Update](list-update.md).

* Die **[!UICONTROL Daten-Update]**-Aktivität ermöglicht eine gebündelte Aktualisierung von Datenbankfeldern.

   Weitere Informationen hierzu finden Sie im Abschnitt [Daten-Update](update-data.md).

### Verwalten von Abonnements {#subscription-management}

Die An- und Abmeldung von Empfängern für einen Informationsdienst im Rahmen eines Workflows wird im Abschnitt [An-/Abmeldedienst](subscription-services.md) beschrieben.




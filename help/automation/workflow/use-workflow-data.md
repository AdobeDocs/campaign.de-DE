---
title: Verwenden von Workflow-Daten
description: Erfahren Sie, wie Sie die Workflow-Daten verwenden.
feature: Workflows, Data Management
version: Campaign v8, Campaign Classic v7
exl-id: 5014c2ed-2a74-4122-b7b9-d3703db7ab12
TQID: https://experienceleague.adobe.com/MeXrY93e-BFOK0OdPAXrnv8baT15WZWwYhXMdFjf1vw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 749
ht-degree: 77%

---

# Verwenden von Workflow-Daten{#how-to-use-workflow-data}

Sie können Workflow-Aktivitäten zur Durchführung unterschiedlicher Aufgaben verwenden. Im Folgenden finden Sie Beispiele zur Aktualisierung der Datenbank durch die Erstellung von Listen, die Verwaltung von Abonnements, den Versand von Nachrichten über einen Workflow oder die Anreicherung von Sendungen und ihren Zielgruppen.

Mehrere Anwendungsfälle für Workflows finden Sie in [diesem Abschnitt](workflow-use-cases.md).

## Lebenszyklus der Arbeitsdaten {#data-life-cycle}

### Temporäre Arbeitstabelle für Workflows {#work-table}

In einem Workflow werden die von einer Aktivität zur anderen übertragenen Daten in temporären Arbeitstabellen gespeichert.

Die Daten können durch Rechtsklick auf die entsprechende Transition angezeigt und analysiert werden.

![](assets/wf-right-click-analyze.png)

Wählen Sie im Kontextmenü die entsprechende Option aus:

* **[!UICONTROL Zielgruppe anzeigen…]**

  In diesem Menü werden die verfügbaren Daten der Zielpopulation angezeigt.

  ![](assets/wf-right-click-display.png)

  Sie können auf die Struktur der Arbeitstabelle in der Registerkarte **[!UICONTROL Schema]** zugreifen.

  ![](assets/wf-right-click-schema.png)

  Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](monitor-workflow-execution.md#worktables-and-workflow-schema).

* **[!UICONTROL Zielgruppe analysieren…]**

  Greifen Sie über dieses Menü auf den Analyse-Assistenten (deskriptiv) zu, mit dem dem Sie Statistiken und Berichte über die Transitionsdaten erstellen können.

  Informationen zum Verwenden des Analyse-Assistenten (deskriptiv) finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html?lang=de){target="_blank"}.

Die Zielgruppendaten werden bei Ausführung des Workflows gelöscht. Nur die letzte Arbeitstabelle ist zugänglich. Sie haben die Möglichkeit, den Workflow dahingehend zu konfigurieren, dass alle Arbeitstabellen beibehalten werden. Aktivieren Sie hierzu in den Workflow-Eigenschaften die Option **[!UICONTROL Zwischen zwei Ausführungen die ermittelte Population festhalten]**.

![](assets/wf-purge-data-option.png)

>[!CAUTION]
>
>Diese Option darf **nie** in einem **Produktions**-Workflow aktiviert werden. Diese Option wird zur Analyse der Ergebnisse verwendet und ist nur für Testzwecke konzipiert und darf daher nur in Entwicklungs- oder Staging-Umgebungen verwendet werden.


### Verwenden der Zieldaten {#target-data}

Die in der temporären Arbeitstabelle des Workflows gespeicherten Daten stehen für Personalisierungsaufgaben zur Verfügung. Daten können in [Personalisierungsfeldern](../../v8/send/personalization-fields.md) verwendet werden.

Auf diese Weise können Sie beispielsweise Daten verwenden, die über eine Liste in einem Versand erfasst wurden. Verwenden Sie dazu die folgende Syntax:

```
%= targetData.FIELD %
```

Personalisierungselemente vom **[!UICONTROL Erweiterung des Zieldatensatzes]** (targetData) sind für Zielgruppen-Workflows nicht verfügbar. Die Versandzielgruppe muss im Workflow erstellt und in der eingehenden Transition des Versands spezifiziert werden.

Im folgenden Beispiel sollen Kundeninformationen in einer Liste gesammelt und dann in einer personalisierten E-Mail verwendet werden. Gehen Sie wie folgt vor:

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

   Um die Datei zu laden, konfigurieren Sie die Aktivität **[!UICONTROL Laden (Datei)]** wie folgt:

   ![](assets/wf-targetdata-sample-2.png)

1. Konfigurieren Sie nun eine Aktivität vom Typ **[!UICONTROL Anreicherung]**, um die geladenen Daten mit denen, die sich schon in der Adobe Campaign-Datenbank befinden, abzustimmen. Hier dient die Kundennummer als Abstimmschlüssel:

   ![](assets/wf-targetdata-sample-3.png)

1. Konfigurieren Sie dann die **[!UICONTROL Versandaktivität]**. Sie wird basierend auf einer Vorlage erstellt und die Empfänger werden durch die eingehende Transition bestimmt.

   ![](assets/wf-targetdata-sample-4.png)

   >[!CAUTION]
   >
   >Nur die von der Transition übermittelten Daten können für die Versandpersonalisierung verwendet werden. Personalisierungsfelder vom Typ **targetData** stehen nur für die in die **[!UICONTROL Versandaktivität]** eingehende Population zur Verfügung.

1. Verwenden Sie in der Versandvorlage die im Workflow gesammelten Daten.

   Fügen Sie hierfür Personalisierungsfelder vom Typ **[!UICONTROL Erweiterung des Zieldatensatzes]** ein.

   ![](assets/wf-targetdata-sample-5.png)

   Im vorliegenden Beispiel wird der bevorzugte Musikstil des Kunden und der bevorzugte Datenträger (CD oder DVD) - gemäß den Informationen der durch den Workflow geladenen Datei - eingefügt.

   Des Weiteren enthält der Versand ein Angebot für Kunden mit Kundenkarte, d. h. für Kunden, bei denen der Wert &#39;Kundenkarte&#39; gleich 1 ist.

   ![](assets/wf-targetdata-sample-6.png)

   **[!UICONTROL Erweiterung des Zieldatensatzes]** (targetData) werden Daten mit denselben Eigenschaften wie bei allen Personalisierungsfeldern in Sendungen eingefügt. Sie können auch im Betreff, in Link-Kennzeichnungen oder in den Links selbst verwendet werden.


## Aktualisieren der Datenbank {#update-the-database}

Alle erfassten Daten können zur Aktualisierung der Datenbank oder in Sendungen verwendet werden. Sie können beispielsweise die Möglichkeiten der Personalisierung von Nachrichteninhalten anreichern (einschließlich der Anzahl der Verträge in der Nachricht, Angabe des durchschnittlichen Warenkorbs im letzten Jahr usw.) oder die Zielgruppenbestimmung detaillierter darstellen (eine Nachricht an die Mitversicherten senden, die 1.000 besten Abonnenten von Online-Diensten ansprechen usw.). Diese Daten können auch exportiert oder in einer Liste archiviert werden.

### Aktualisieren von Listen  {#list-updates}

Zur Aktualisierung der Adobe Campaign-Datenbank und von Listen stehen zwei dedizierte Aktivitäten zur Verfügung:

* Über die Aktivität **[!UICONTROL Listen-Update]** können Arbeitstabellen in einer Datenliste gespeichert werden.

  Sie können eine vorhandene Liste auswählen oder erstellen. In diesem Fall werden der Name und ggf. der Datensatzordner berechnet.

  ![](assets/s_user_create_list.png)

  Siehe [Listen-Update](list-update.md).

* Die **[!UICONTROL Daten-Update]**-Aktivität ermöglicht eine gebündelte Aktualisierung von Datenbankfeldern.

  Weitere Informationen hierzu finden Sie im Abschnitt [Daten-Update](update-data.md).

### Abonnements verwalten {#subscription-management}

Die An- und Abmeldung von Empfängern für einen Informationsdienst im Rahmen eines Workflows wird im Abschnitt [An-/Abmeldedienst](subscription-services.md) beschrieben.

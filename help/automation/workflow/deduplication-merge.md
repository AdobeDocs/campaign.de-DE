---
title: Verwenden der Zusammenführungsfunktion der Deduplizierungsaktivität
description: Erfahren Sie, wie Sie die Zusammenführungsfunktion der Deduplizierungsaktivität verwenden.
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ee201cfd-a351-41d8-a5ad-2f2e538dc643
TQID: 'https://experienceleague.adobe.com/kGX1fF3yFVneX-HV67BJtS-h2v-HNhG9cXHH7wRw2Tw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 78%
---
# Verwenden der Zusammenführungsfunktion der Deduplizierungsaktivität {#deduplication-merge}



## Über dieses Anwendungsbeispiel {#about-this-use-case}

In diesem Anwendungsfall wird beschrieben, wie Sie die Funktion **[!UICONTROL Zusammenführen]** in der Aktivität **[!UICONTROL Deduplizierung]** verwenden.

Weitere Informationen zu dieser Funktion finden Sie unter [Zusammenführen von Feldern zu einem einzelnen Datensatz](deduplication.md#merging-fields-into-single-record).

Die Aktivität **[!UICONTROL Deduplizierung]** wird zum Entfernen von Duplikat-Zeilen aus einem Datensatz verwendet. In diesem Anwendungsfall werden die unten angezeigten Daten anhand des E-Mail-Felds dupliziert.

| Datum der letzten Änderung | Vorname | Nachname | E-Mail | Mobiltelefon | Telefon |
|-----|------------|-----------|-------|--------------|------|
| 19.5.2020 | Robert | Tisner | bob@mycompany.com | 444-444-444 | 777-777-7777 |
| 22.7.2020 | Bobby | Tisner | bob@mycompany.com | | 777-777-7777 |
| 3.10.2020 | Bob |  | bob@mycompany.com | | 888-888-8888 |

Mit der Funktion **[!UICONTROL Zusammenführen]** der Deduplizierungsaktivität können Sie einen Regelsatz für das Deduplizieren konfigurieren, um eine Feldgruppe zu definieren, die zu einem einzigen Ergebnisdatensatz zusammengeführt werden soll. Bei einer Reihe von Duplikat-Datensätzen können Sie beispielsweise entscheiden, jeweils die älteste Telefonnummer oder den neuesten Namen beizubehalten.

## Aktivieren der Zusammenführungsfunktion {#activating-merge}


Um die Zusammenführungsfunktion zu aktivieren, müssen Sie zunächst die Aktivität **[!UICONTROL Deduplizierung]** konfigurieren. Gehen Sie dazu wie folgt vor:

1. Öffnen Sie die Aktivität und klicken Sie dann auf den Link **[Konfiguration bearbeiten]**.

1. Wählen Sie das für das Deduplizierung zu verwendende Abstimmungsfeld aus und klicken Sie dann auf **[!UICONTROL Weiter]**. In diesem Beispiel möchten wir die Duplizierung basierend auf dem E-Mail-Feld deduplizieren.

   ![Fenster der Zielgruppendimension „Deduplizierung“, in dem die Empfänger und das Feld für die E-Mail-Abstimmung ausgewählt sind.](assets/uc_merge_edit.png)

1. Klicken Sie auf den Link **[!UICONTROL Erweiterte Parameter]** und aktivieren Sie dann die Optionen **[!UICONTROL Datensätze zusammenführen]** und **[!UICONTROL Mehrere Kriterien zum Zusammenführen von Datensätzen verwenden]**.

   ![Dialogfeld „Deduplizierungsparameter“ mit aktivierten Optionen Datensätze zusammenführen und Mehrere Datensätze verwenden](assets/uc_merge_advanced_parameters.png)

1. Die Registerkarte **[!UICONTROL Zusammenführen]** wird dem Konfigurationsbildschirm **[!UICONTROL Deduplizierung]** hinzugefügt. Auf dieser Registerkarte können Sie die Daten angeben, die beim Ausführen der Deduplizierung zusammengeführt werden sollen.

## Konfigurieren der zusammenzuführenden Felder {#configuring-rules}

Hier sind die Regeln, mit denen die Daten in einen einzigen Datensatz zusammengeführt werden sollen:

* Belassen Sie den neuesten Namen (Vorname- und Nachname-Felder),
* Behalten Sie die neueste Mobiltelefonnummer bei,
* Behalten Sie die älteste Telefonnummer bei,
* Alle Felder in einer Gruppe müssen ungleich null sein, damit sie für den endgültigen Datensatz infrage kommen.

Gehen Sie wie folgt vor, um diese Regeln zu konfigurieren:

1. Öffnen Sie die Registerkarte **[!UICONTROL Zusammenführen]** und klicken Sie dann auf die Schaltfläche **[!UICONTROL Hinzufügen]**.

   ![Registerkarte „Zusammenführen“ der Aktivität „Deduplizierung“ mit der Schaltfläche Hinzufügen oberhalb einer leeren Liste zusammengeführter Daten.](assets/uc_merge_add.png)

1. Geben Sie die Kennung und die Bezeichnung der Gruppe von Feldern an, die zusammengeführt werden sollen.

   ![Schritt Kennung und Bezeichnung des Assistenten Zusammenzuführende Daten auswählen mit dem Kennungsnamen und dem eingegebenen Kennungsnamen.](assets/uc_merge_identifier.png)

1. Geben Sie die Bedingungen für die Auswahl der zu berücksichtigenden Datensätze an.

   ![Filterschritt mit Bedingungen Vorname ist nicht leer und Nachname ist nicht leer, um die zusammenzuführenden Datensätze auszuwählen.](assets/uc_merge_filter.png)

1. Sortieren Sie nach dem Datum der letzten Änderung, um den neuesten Namen auszuwählen.

   ![Schritt mit Änderungsdatum in absteigender Reihenfolge sortieren, um den letzten Datensatz auszuwählen.](assets/uc_merge_sort.png)

1. Wählen Sie die zusammenzuführenden Felder aus. In diesem Beispiel möchten wir die Felder für Vor- und Nachnamen beibehalten.

   ![Beizubehaltende Felder, wobei Vorname und Nachname als Ausgabespalten ausgewählt sind.](assets/uc_merge_keep.png)

1. Die Felder werden dem Datensatz hinzugefügt, der zusammengeführt werden soll, und dem Workflow-Schema wird ein neues Element hinzugefügt.

   Wiederholen Sie diese Schritte, um die Felder für Mobil- und Festnetztelefonnummern zu konfigurieren.

   ![Registerkarte Zusammenführen mit dem Namen, dem Mobilgerät und dem Telefon der zusammengeführten Gruppen sowie ihren Aliassen und aktivierten Wenn-Bedingungen.](assets/dedup8.png)

   ![Registerkarte „Schema“ mit der generierten Datenstruktur der Deduplizierung mit den Knoten „Mobile“, „Name“ und „Telefon“.](assets/dedup9.png)

## Ergebnisse {#results}

Nach dem Konfigurieren dieser Regeln werden die folgenden Daten am Ende der Aktivität **[!UICONTROL Deduplizierung]** empfangen.

| Änderungsdatum | Vorname | Nachname | E-Mail | Mobiltelefon | Telefon |
|-----|------------|-----------|-------|--------------|------|
| 19.5.2020 | Robert | Tisner | bob@mycompany.com | 444-444-444 | 777-777-7777 |
| 22.7.2020 | Bobby | Tisner | bob@mycompany.com | | 777-777-7777 |
| 3.10.2020 | Bob |  | bob@mycompany.com | | 888-888-8888 |

Das Ergebnis wird aus den drei Datensätzen gemäß den zuvor konfigurierten Regeln zusammengeführt. Nach dem Vergleich wird der Schluss gezogen, dass der aktuelle Name und das Mobiltelefon zusammen mit der ursprünglichen Telefonnummer verwendet werden.

| Vorname | Nachname | E-Mail | Mobiltelefon | Telefon |
|------------|-----------|-------|--------------|------|
| Bobby | Tisner | bob@mycompany.com | 444-444-4444 | 888-888-8888 |

>[!NOTE]
>
> Beachten Sie, dass der Vorname nach der Zusammenführung &quot;Bobby&quot; ist, da wir eine &quot;Name&quot;-Regel konfiguriert haben, die sowohl aus dem Vor- als auch dem Nachnamen besteht.
>
>Daher konnte &quot;Bob&quot; (der letzte Vorname) nicht berücksichtigt werden, da das zugehörige Feld für den Nachnamen leer war. Die neueste Kombination aus Vor- und Nachnamen wurde im finalen Datensatz zusammengeführt.

---
product: campaign
title: Vereinigung
description: Erfahren Sie mehr über die Workflow-Aktivität "Vereinigung".
feature: Workflows, Targeting Activity
version: Campaign v8, Campaign Classic v7
exl-id: 4109e198-bf9d-4dd2-92a1-16bbadbe30e8
TQID: https://experienceleague.adobe.com/-P-pc2ps970pfhgXZfv8atoVKGB-vS0B8vBdrR0DLZQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 311
ht-degree: 65%

---

# Vereinigung{#union}

Eine **[!UICONTROL Vereinigung]** gruppiert das Ergebnis mehrerer eingehender Aktivitäten in einer einzigen Zielgruppe. Das Ziel wird mit allen erhaltenen Ergebnissen erstellt: Alle vorherigen Aktivitäten müssen daher abgeschlossen sein, damit die Vereinigung ausgeführt werden kann.

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>Weitere Informationen zum Konfigurieren und Verwenden der Aktivität **[!UICONTROL Vereinigung]** finden Sie auf [dieser Seite](targeting-workflows.md#combining-several-targets--union-).

## Anwendungsbeispiel für eine Vereinigung {#union-example}

Im folgenden Beispiel wurden die Ergebnisse zweier Abfragen kombiniert, um die Liste zu aktualisieren. Die beiden Abfragen zielen auf die Empfänger ab. Die Ergebnisse basieren daher auf derselben Tabelle.

1. Schließen Sie unmittelbar an die zwei Abfragen eine **[!UICONTROL Vereinigung]** an, gefolgt von einem Listen-Update.
1. Benennen Sie die Aktivität.
1. Wählen Sie als Abstimmoption **[!UICONTROL Nur die Schlüssel]**, da im vorliegenden Beispiel die aus den Abfragen stammenden Populationen homogen sind.
1. Falls Sie in den Abfragen Zusatzdaten verwenden, können Sie sich dafür entscheiden, nur gemeinsame Daten beizubehalten.
1. Wenn Sie die Größe der endgültigen Population begrenzen möchten, aktivieren Sie die Option **[!UICONTROL Größe der erzeugten Population begrenzen]**.

   Geben Sie in diesem Fall die Anzahl an beizubehaltenden Empfängern und die vorrangig zu berücksichtigende Abfrage an.

1. Bestätigen Sie die Aktivität **[!UICONTROL Vereinigung]** und konfigurieren Sie dann die Aktivität [Listen-Update](list-update.md).
1. Starten Sie den Workflow. Die Anzahl der Ergebnisse wird angezeigt und die in der Aktivität Listen-Update definierte Liste wird erstellt oder aktualisiert. Diese Liste enthält die Empfängergruppe für beide Abfragen oder gegebenenfalls die im vorherigen Schritt definierte Zahl.

   ![](assets/union_example.png)

## Eingabeparameter {#input-parameters}

* tableName
* schema

Jedes eingehende Ereignis muss eine durch diese Parameter definierte Zielgruppe angeben.

## Ausgabeparameter {#output-parameters}

* tableName
* schema
* recCount

Anhand der drei Werte lässt sich die durch die Vereinigung ermittelte Zielgruppe identifizieren. **[!UICONTROL tableName]** ist der Name der Tabelle, die die Zielgruppen-IDs enthält, **[!UICONTROL schema]** ist das Schema der Population, (i. d. R. nms:recipient) und **[!UICONTROL recCount]** ist die Anzahl der Elemente in der Tabelle.

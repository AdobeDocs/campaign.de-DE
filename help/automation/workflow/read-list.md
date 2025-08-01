---
product: campaign
title: Liste lesen
description: Erfahren Sie mehr über die Workflow-Aktivität "Liste lesen".
feature: Workflows, Targeting Activity
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 91c87f8f-bdd2-4ca1-94c2-ec9e7affc1a0
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: ht
source-wordcount: '508'
ht-degree: 100%

---

# Liste lesen{#read-list}

In Workflows genutzte Daten können aus Listen stammen, deren Daten zuvor aufbereitet und strukturiert wurden, beispielsweise in einer früheren Segmentierung oder im Zuge eines Datei-Ladevorgangs.

Die Aktivität **[!UICONTROL Liste lesen]** kopiert Daten aus einer Liste in eine Workflow-Arbeitstabelle (analog zu Daten aus Abfragen). Auf diese Weise stehen sie während der gesamten Workflow-Ausführung zur Verfügung.

Die zu verarbeitende Liste kann explizit angegeben, von einem Script berechnet oder dynamisch abgerufen werden. Dies hängt von den in der Aktivität **[!UICONTROL Liste lesen]** aktivierten Optionen oder angegebenen Parametern ab.

![](assets/list_edit_select_option_01.png)

Wenn die Liste nicht explizit bezeichnet wird, ist eine Beispielliste anzugeben, die als Strukturvorlage verwendet wird.

![](assets/s_advuser_list_template_select.png)

Nach erfolgter Konfiguration der Liste können Sie über die Option **[!UICONTROL Abfrage bearbeiten...]** einen Filter hinzufügen, um die für den weiteren Workflow-Verlauf zu nutzende Population einzuschränken.

![](assets/wf_readlist_1.png)

>[!CAUTION]
>
>Um in einer Liste-lesen-Aktivität Filter verwenden zu können, muss die Liste als Datei vorliegen.

Listen können direkt in der Adobe Campaign-Startseite über die Schaltfläche **[!UICONTROL Profile und Zielgruppen > Listen]** erstellt werden. Sie können auch im Rahmen eines Workflows über die Aktivität **[!UICONTROL Listen-Update]** erstellt werden.

**Anwendungsbeispiel: Ausschluss einer Adressenliste von einem Versand**

Im folgenden Beispiel soll eine Datei mit Adressen importiert werden, die gundsätzlich vom E-Mail-Versand auszuschließen sind (beispielsweise, weil die Empfänger nicht mehr existieren).

![](assets/s_advuser_list_read_sample_1.png)

Die im **Premiumkunden**-Ordner enthaltenen Profile sollen im Rahmen einer Marketing-Kampagne kontaktiert werden. Eine externe Liste enthält vom Versand auszuschließende Adressen. Für das vorliegende Beispiel werden nur die E-Mail-Adressen benötigt, um den Ausschluss vorzunehmen.

1. Die zum Laden der im **Premiumkunden**-Ordner enthaltenen Empfänger erstellte Abfrage muss die E-Mail-Adressen der Empfänger ausgeben, um die Abstimmung mit der Ausschlussliste zu ermöglichen.

   ![](assets/s_advuser_list_read_sample_0.png)

1. Im vorliegenden Beispiel ist die Liste im Ordner **Listen** gespeichert und der Titel wird berechnet.

   ![](assets/s_advuser_list_read_sample_2.png)

1. Konfigurieren Sie die Ausschlussaktivität, indem Sie den Ordner **Premiumkunden** als Hauptmenge angeben. Dies bedeutet, dass dieser Ordner die beizubehaltenden Daten enthält, dass jedoch alle Datensätze, die sowohl in diesem Ordner als auch in einer anderen in die Ausschlussaktivität eingehenden Datei enthalten sind, von der Zielgruppe ausgeschlossen werden.

   ![](assets/s_advuser_list_read_sample_3.png)

   Die Ausschlussregeln werden im mittleren Bereich des Fensters konfiguriert. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**, um den Ausschlusstyp zu definieren.

   Sie können für jede in die Aktivität eingehende Transition einen Ausschluss definieren.

1. Wählen Sie im Feld **[!UICONTROL Ausschlussmenge]** die Aktivität **[!UICONTROL Liste lesen]** aus. Die von dieser Aktivität übermittelten Daten werden somit von der Hauptmenge ausgeschlossen.

   Im vorliegenden Beispiel handelt es sich um einen Ausschluss über einen Join: Die Daten der Liste werden über das E-Mail-Feld mit der Hauptmenge abgestimmt. Wählen Sie zur Konfiguration des Joins im Feld **[!UICONTROL Dimensionsänderung]** die Option **[!UICONTROL Join]** aus.

   ![](assets/s_advuser_list_read_sample_4.png)

1. Wählen Sie dann für die Quelle und das Bestimmungsziel das der E-Mail-Adresse entsprechende Feld aus. Die Spalten werden entsprechend zugeordnet und die Empfänger, deren E-Mail-Adresse in der importierten Liste enthalten ist, werden aus der Zielgruppe ausgeschlossen.

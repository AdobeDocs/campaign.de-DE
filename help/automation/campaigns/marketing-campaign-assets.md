---
product: campaign
title: Assets, Dokumente und Versandentwürfe für Marketing-Kampagnen
description: Weitere Informationen zu Dokumenten und Versandentwürfen für Marketing-Kampagnen
feature: Campaigns
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
TQID: 'https://experienceleague.adobe.com/snshYvtbT3wG1N5-A4VHjl1bylxlXObi-97yVwuKAXk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 75%
---
# Verwalten von Assets und Dokumenten {#manage-assets-documents}

Sie können einer Kampagne verschiedene Dokumente zuordnen: Berichte, Fotos, Webseiten, Diagramme usw. Diese Dokumente können in jedem beliebigen Format vorliegen.

Sie können auch externe Elemente in Kampagnen referenzieren, wie zum Beispiel Werbe-Coupons, marken- oder verkaufsstellenspezifische Angebote etc. Diese können in einem Versandentwurf zusammengefasst und einem Briefpost-Versand zugeordnet werden. [Weitere Informationen](#associating-and-structuring-resources-linked-via-a-delivery-outline).


>[!CAUTION]
>
>Diese Funktion ist für kleine Assets und Dokumente vorgesehen.

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## Dokumente hinzufügen {#add-documents}

Dokumente können auf Kampagnenebene (kontextuelle Dokumente) oder Programmebene (allgemeine Dokumente) zugeordnet werden.

Für eine Kampagne enthält die Registerkarte **[!UICONTROL Dokumente]**:

* Die Liste aller für den Inhalt erforderlichen Dokumente (Vorlage, Bilder usw.), die von Adobe Campaign-Benutzenden mit entsprechenden Berechtigungen lokal heruntergeladen werden können,
* Informationen für den Router enthaltende Dokumente, wenn vorhanden.

Die Dokumente werden über den Tab **[!UICONTROL Bearbeiten > Dokumente]** einem Programm oder einer Kampagne zugeordnet.

![Registerkarte „Bearbeiten“ in Campaign, Unterregisterkarte „Dokumente“: Liste der angehängten Dokumente mit den Schaltflächen „Hinzufügen“, „Löschen“ und „Details“.](assets/op_add_document.png)

Es besteht darüber hinaus die Möglichkeit, Dokumente über den entsprechenden Link im Dashboard zu einer Kampagne hinzuzufügen.

![Kampagnen-Dashboard mit dem Link Dokument hinzufügen und dem Dialogfeld Marketing-Dokument zum Hochladen einer Datei.](assets/add_a_document_in_op.png)

Klicken Sie auf das Symbol **[!UICONTROL Detail...]**, um den Inhalt einer Datei anzusehen und ergänzende Informationen hinzuzufügen.

![Dokument-Dialogfeld geöffnet ab Detail: Bezeichnung, Version, Art, hochgeladener Datei-Link und Beschreibung.](assets/add_document_details.png)

Im Abschnitt **[!UICONTROL Dokument(e)]** des Kampagnen-Dashboards werden alle der Kampagne zugeordneten Dokumente aufgelistet, wie im folgenden Beispiel:

![Kampagnen-Dashboard mit dem Abschnitt „Dokument(e)“, in dem die an die Kampagne angehängten Dokumente hervorgehoben sind.](assets/edit_documents.png)

Über die Links können die Dokumente geöffnet und bearbeitet werden.

## Verwenden von Versandentwürfen {#delivery-outlines}

Ein Versandentwurf besteht aus einem strukturierten Satz von Elementen (Dokumente, Geschäfte, Werbegutscheine usw.), der vom Unternehmen und für eine bestimmte Kampagne erstellt wird. Er wird im Zusammenhang mit Briefpost-Sendungen verwendet.

Diese Elemente sind in Versandentwürfen gruppiert und jedem Versandentwurf wird ein Versand zugeordnet. Auf diesen Versand wird in der an den **Dienstleister** gesendeten Extraktionsdatei verwiesen, um an den Versand angehängt zu werden. Sie können beispielsweise einen Versandentwurf erstellen, der sich auf eine Unternehmenseinheit und die von ihr verwendeten Marketing-Prospekte bezieht.

Versandentwürfe ermöglichen es, für eine Kampagne externe Elemente zu strukturieren und nach bestimmten Kriterien zu einem Versand hinzuzufügen: entsprechende Filiale, Sonderangebot, Einladung zu einem lokalen Event usw.

>[!CAUTION]
>
>Versandentwürfe sind auf Briefpost-Kampagnen beschränkt.

### Erstellen eines Versandentwurfs {#create-an-outline}

Um einen Versandentwurf zu erstellen, klicken Sie auf die Unterregisterkarte **[!UICONTROL Versandentwürfe]** auf der Registerkarte **[!UICONTROL Bearbeiten > Dokumente]** der betreffenden Kampagne.

![Registerkarte „Bearbeiten“ in Campaign, Dokumente, Unterregisterkarte „Versandentwürfe“ mit dem Link Versandentwurf hinzufügen.](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>Wenn diese Registerkarte nicht angezeigt wird, ist diese Funktion für diese Kampagne nicht verfügbar oder der Briefpost-Versand ist in Ihrer Instanz nicht aktiviert. Weitere Informationen finden Sie im Abschnitt [Kampagnenvorlagenkonfiguration](marketing-campaign-templates.md#campaign-templates) oder in Ihrem Lizenzvertrag.

Klicken Sie anschließend auf **[!UICONTROL Versandentwurf hinzufügen]**. Es wird ein Navigationsbaum für die Kampagne erstellt:

1. Machen Sie einen Rechtsklick auf den Wurzelknoten und wählen Sie **[!UICONTROL Neu > Versandentwürfe]** aus, um einen neuen Versandentwurf hinzuzufügen.
1. Machen Sie einen Rechtsklick auf den soeben erstellten Versandentwurf und wählen Sie beispielsweise **[!UICONTROL Neu > Artikel]** oder **[!UICONTROL Neu > Personalisierungsfelder]** aus.

![Versandentwurf im Kontextmenü: Neu > Element, Personalisierungsfelder oder Angebot.](assets/del-outline-add-new-item.png)

Ein Versandentwurf kann Artikel, Personalisierungsfelder und Angebote enthalten:

* Artikel sind beispielsweise physische Dokumente, die an dieser Stelle referenziert und beschrieben und schließlich dem Versand angehängt werden.
* Personalisierungsfelder ermöglichen es Ihnen, Personalisierungselemente zu erstellen, die sich auf Sendungen und nicht auf Empfangende beziehen. Daher ist das Erstellen von Werten möglich, die in Sendungen für eine bestimmte Zielgruppe (Willkommensangebot, Rabatt usw.) verwendet werden können. Sie werden in Adobe Campaign erstellt und über den Link **[!UICONTROL Personalisierungsfelder importieren…]** in den Entwurf importiert.

  ![Wählen Sie das Dialogfeld Personalisierungsfelder mit den Optionen Pack, Gold und Premium aus, das über Personalisierungsfelder importieren geöffnet wurde.](assets/del-outline-perso-field.png)

  Über das Symbol **[!UICONTROL Hinzufügen]** rechts vom Bereich der Liste können in dem Entwurf auch direkt Personalisierungselemente erstellt werden.

  ![Personalisierungsfelder werden in einem Versandentwurf mit eingegebenen Werten und dem Symbol Hinzufügen rechts von der Liste aufgeführt.](assets/add-del-outline-button.png)


### Auswählen eines Versandentwurfs {#select-an-outline}

Sie können für jeden Versand über den Bereich der Extraktionskonfiguration einen Entwurf auswählen, wie im folgenden Beispiel:

![Registerkarte „Briefpost“ eines Versands mit dem Dialogfeld „Versandentwurf auswählen“, in dem die Einheiten B, C und A aufgeführt sind.](assets/select-delivery-outline.png)

Der ausgewählte Entwurf wird dann im unteren Abschnitt des Fensters angezeigt. Er kann über das Symbol rechts im Fenster oder mithilfe der Dropdown-Liste bearbeitet werden:

![Registerkarte „Briefpost“ eines Versands mit hervorgehobenem Feld „Versandentwurf“, auf der Einheit C angezeigt wird.](assets/delivery-outline-selected.png)

Diese Information wird ebenfalls im Tab **[!UICONTROL Zusammenfassung]** des Versands angezeigt:

![Registerkarte Versandzusammenfassung mit einem Pfeil, der auf den Wert des Versandentwurfs, Einheit C, verweist](assets/delivery-outline-in-dashboard.png)

### Extraktionsergebnis {#extraction-result}

In der extrahierten und an den Dienstleister gesendeten Datei werden dem Inhalt der Name des Entwurfs und gegebenenfalls die Eigenschaften (Kosten, Beschreibung usw.) hinzugefügt und zwar entsprechend der Informationen in der mit dem Dienstleister verknüpften Exportvorlage.

Im folgenden Beispiel werden der Titel, die Plankosten sowie die Beschreibung des dem Versand zugeordneten Entwurfs der Extraktionsdatei hinzugefügt.

![Schritt „Zu extrahierende Daten“ der Exportvorlage mit hervorgehobener Ausgabespalte „Bezeichnung“ (Versand/Versandentwurf).](assets/campaign-export-template.png)

Die Exportvorlage muss dem gewählten Dienstleister für den betreffenden Versand zugeordnet sein. Siehe [diesen Abschnitt](providers-stocks-and-budgets.md#create-service-providers-and-their-cost-structures).

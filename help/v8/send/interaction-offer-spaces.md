---
product: Adobe Campaign
title: Campaign Interaction-Angebotsplatzierungen
description: Erfahren Sie, wie Sie Angebotsplatzierungen erstellen
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: ht
source-wordcount: '656'
ht-degree: 100%

---

# Platzierungen erstellen{#creating-offer-spaces}

Der Content des Angebotskatalogs wird in Platzierungen konfiguriert. Standardmäßig kann der Content **[!UICONTROL die folgenden Felder enthalten: Titel]**, **[!UICONTROL Ziel-URL]**, **[!UICONTROL Bild-URL]**, **[!UICONTROL HTML-Inhalt]** und **[!UICONTROL Textinhalt]**. Die Feldsequenz wird in der Angebotsplatzierung konfiguriert.

Als **technischer Administrator** können Sie in der Design-Umgebung Angebotsplatzierungen erstellen. Dazu benötigen Sie Zugriff auf den Unterordner der Platzierung. Nach der Erstellung werden diese Platzierungen bei der Angebotsvalidierung automatisch in die Live-Umgebung dupliziert.

Das HTML-Rendering wird über eine Rendering-Funktion erstellt. Die Reihenfolge der in der Rendering-Funktion definierten Felder muss mit der im Content konfigurierten Sequenz übereinstimmen.

![](assets/offer_space_create_009.png)

Gehen Sie wie folgt vor, um eine neue Platzierung zu erstellen:

1. Klicken Sie in der Liste der Platzierungen auf **[!UICONTROL Neu]**.

   ![](assets/offer_space_create_001.png)

1. Benennen Sie die Platzierung und wählen Sie aus der Dropdown-Liste den E-Mail-Kanal aus.

   ![](assets/offer_space_create_002.png)

1. Aktivieren Sie die Option **[!UICONTROL Einzelmodus zulassen]** .

1. Klicken Sie dann im Bereich **[!UICONTROL Felder des Angebotsinhalts]** auf **[!UICONTROL Hinzufügen]**.

   ![](assets/offer_space_create_003.png)

1. Wählen Sie aus dem **[!UICONTROL Inhalt]**-Knoten unter Berücksichtigung der Reihenfolge folgende Felder aus: **[!UICONTROL Titel]**, **[!UICONTROL Bild-URL]**, **[!UICONTROL HTML-Inhalt]** und schließlich **[!UICONTROL Ziel-URL]**.

   ![](assets/offer_space_create_004.png)

1. Machen Sie jedes Feld zum **[!UICONTROL Pflichtfeld]**.

   >[!NOTE]
   >
   >Diese Option wird in der Vorschau verwendet und macht die Platzierungen bei der Veröffentlichung ungültig, wenn eines der Pflichtfelder des Angebots fehlt. Wenn jedoch ein Angebot bereits auf einer Platzierung live ist, werden diese Kriterien nicht berücksichtigt.

   ![](assets/offer_space_create_005.png)

1. Klicken Sie auf **[!UICONTROL Funktionen bearbeiten...]**, um eine Rendering-Funktion zu erstellen.

   Diese Funktionen dienen der Erzeugung von Angebotsdarstellungen auf einer Platzierung. Dabei sind folgende Formate möglich: HTML oder Text.

   **Hinweis** – Das XML-Format ist auf eingehende Interaktionen beschränkt, die in dieser Produktversion nicht verfügbar sind. [Weitere Informationen](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Gehen Sie auf die Registerkarte **[!UICONTROL HTML-Rendering]** und aktivieren Sie die Option **[!UICONTROL HTML-Rendering-Funktion überschreiben]**.
1. Geben Sie nun Ihre Rendering-Funktion ein.

   ![](assets/offer_space_create_007.png)

## Vorschlagsstatus {#offer-proposition-statuses}

Der Vorschlagsstatus ändert sich entsprechend den Interaktionen mit der Zielpopulation. Das Campaign Interaction-Modul enthält eine Reihe von Werten, die während seines gesamten Lebenszyklus auf den Angebotsvorschlag angewendet werden können. Die Plattform muss so konfiguriert sein, dass sich der Status bei der Erstellung und Annahme des Angebotsvorschlags ändert.

>[!NOTE]
>
>Die Status-Aktualisierung ist ein **asynchroner** Prozess, der vom stündlich ausgelösten Tracking-Workflow ausgeführt wird.

### Liste der Angebotsstatus {#status-list}

Verfügbare Angebotsstatus sind:

* **[!UICONTROL Akzeptiert]**
* **[!UICONTROL Geplant]**
* **[!UICONTROL Erzeugt]**
* **[!UICONTROL Interessant]**
* **[!UICONTROL Unterbreitet]**
* **[!UICONTROL Zurückgewiesen]**

Diese Werte werden nicht standardmäßig angewendet, sie müssen zuvor konfiguriert werden.

>[!NOTE]
>
>Der Status eines Angebotsvorschlags wird automatisch in &quot;Unterbreitet&quot; geändert, wenn das Angebot mit einem Versand verknüpft ist, dessen Status &quot;Gesendet&quot; lautet.

### Angebotsstatus bei Erstellung des Vorschlags {#configuring-the-status-when-the-proposition-is-created}

Wenn ein Angebotsvorschlag **erzeugt** wird, wird sein Status aktualisiert.

Konfigurieren Sie in der Umgebung **[!UICONTROL Design]** für jede Platzierung den Status, der beim Erstellen eines Vorschlags zugewiesen werden soll, entsprechend den Informationen, die Sie in den Angebotsberichten anzeigen möchten.

Gehen Sie dazu wie folgt vor:

1. Gehen Sie auf die Registerkarte **[!UICONTROL Speicherung]** der zu konfigurierenden Platzierung.
1. Wählen Sie den Status aus, der bei der Vorschlagserzeugung zugewiesen werden soll.

   ![](assets/offer_update_status_001.png)

### Angebotsstatus bei Akzeptanz des Vorschlags {#configuring-the-status-when-the-proposition-is-accepted}

Sobald ein Angebotsvorschlag **akzeptiert** wurde, konfigurieren Sie den neuen Vorschlagsstatus mit einem der standardmäßig verfügbaren Werte. Die Aktualisierung wird durchgeführt, sobald ein Empfänger auf einen Link im Angebot klickt.

Gehen Sie dazu wie folgt vor:

1. Gehen Sie auf die Registerkarte **[!UICONTROL Speicherung]** der zu konfigurierenden Platzierung.
1. Wählen Sie den Status aus, den der Vorschlag erhalten soll, nachdem er akzeptiert wurde.

   ![](assets/offer_update_status_002.png)

<!--
**Inbound interaction**

The **[!UICONTROL Storage]** tab lets you define statuses for **proposed** and **accepted** offer propositions only. For inbound interaction, the status of offer propositions should be specified directly in the URL for calling the offer engine, rather than through the interface. This way, you will be able to specify which status to apply in other cases, for example if an offer proposition is rejected.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

For instance, the proposition (identifier **40004**) that matches the **Home insurance** offer displayed on the **Neobank** site contains the following URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

As soon as a visitor clicks the offer, and therefore the URL, the **[!UICONTROL Accepted]** status (value **3**) is applied to the proposition and the visitor is redirected to a new page of the **Neobank** site to take out the insurance contract.

>[!NOTE]
>
>If you want to specify another status in the url (for example if an offer proposition is rejected), use the value corresponding to the desired status. Example: **[!UICONTROL Rejected]** = "5", **[!UICONTROL Presented]** = "1" and so on.
>
>Statuses and their values can be retrieved in the **[!UICONTROL Offer propositions (nms)]** data schema. For more on this, refer to [this page](../../configuration/using/data-schemas.md).

**Outbound interaction**
-->

Sie können den Status **[!UICONTROL Interessant]** automatisch auf einen Angebotsvorschlag anwenden, falls der Versand einen Link enthält. Fügen Sie einfach den Wert **_urlType=&quot;11&quot;** zum Link hinzu:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Angebotsvorschau in der Platzierung {#offer-preview-per-space}

Auf der Registerkarte **[!UICONTROL Vorschau]** können Sie die Angebote anzeigen, die basierend auf einer zuvor ausgewählten Methode für den Empfänger infrage kommen. Beim folgenden Beispiel kommt der Empfänger für drei Angebote per Briefpost infrage.

![](assets/offer_space_overview_002.png)

Sollte kein Angebot für einen Empfänger infrage kommen, ist dies in der Vorschau leicht erkennbar.

![](assets/offer_space_overview_001.png)

<!--
The preview can ignore contexts when they are restricted to a space. This is the case when the interaction schema has been extended to add fields referenced in a space using an inbound channel (for more on this, refer to Extension example.
-->

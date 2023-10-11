---
product: campaign
title: Versand (fortlaufend)
description: Versand (fortlaufend)
feature: Workflows, Channels Activity
role: User
exl-id: e3ad6d92-8d53-4098-90fd-cfed29f2e56e
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: ht
source-wordcount: '374'
ht-degree: 100%

---

# Versand (fortlaufend){#continuous-delivery}



Mit einer Aktion vom Typ **Versand (fortlaufend)** können Sie einem bestehenden Versand Empfänger hinzufügen. Dieser Versandtyp vermeidet, dass Sie jedes Mal einen neuen Versand erstellen müssen: Dieser Modus ist oft effizienter, insbesondere bei Warnungen und Benachrichtigungen mit geringen Volumen, die nach Bedarf gesendet werden.

![](assets/do-not-localize/how-to-video.png) [Funktion im Video kennenlernen](#continuous-delivery-video).

Auf der Ebene der Versandvorlagen können Sie ein Script zur Berechnung der Beschriftung (und des Kampagnenordners) des zugehörigen Versands angeben. Wenn das Script einen Versand berechnet, der noch nicht vorhanden ist, wird er sofort erstellt.

![](assets/edit_diffusion_fil.png)

Dank der Option **[!UICONTROL Fehler verarbeiten]** erscheint eine spezifische Transition, wenn ein Fehler auftritt. In diesem Fall wird die Ausführung des Workflows nicht ausgesetzt, sondern fortgeführt.

Dies gilt für Fehler des Dateisystems (Datei kann nicht verschoben werden, Zugriff auf das Verzeichnis nicht möglich usw.).

Fehler, die aus der Konfiguration der Aktivität resultieren, beispielsweise durch Angabe von ungültigen Werten (z. B. inexistentes Verzeichnis), werden nicht verarbeitet.

## Eingabeparameter {#input-parameters}

* tableName
* schema

Jedes eingehende Ereignis muss eine durch diese Parameter definierte Zielgruppe angeben.

Dies gilt nur, wenn die Option **[!UICONTROL Wird durch das Eingangsereignis angegeben]** angekreuzt wurde.

## Ausgabeparameter {#output-parameters}

* tableName
* schema
* recCount

Anhand der drei Werte lässt sich die durch den wiederkehrenden Versand ermittelte Zielgruppe identifizieren. **[!UICONTROL tableName]** ist der Name der Tabelle, welche die Kennungen der Zielgruppenempfänger enthält, **[!UICONTROL schema]** ist das Schema der Population, (i. d. R. nms:recipient) und **[!UICONTROL recCount]** ist die Anzahl an Elementen in der Tabelle.

Die Transition des Komplements weist die gleichen Parameter auf.

## Einrichten eines Versands (fortlaufend)

In diesem Abschnitt wird beschrieben, wie Sie einen Versand (fortlaufend) einrichten.

Beim **fortlaufenden Versand** können Sie einem bestehenden Versand neue Empfänger hinzufügen, sodass Sie nicht jedes Mal einen neuen Versand erstellen müssen, wenn ein neuer Empfänger hinzugefügt wird. Sie können die kreativen Inhalte direkt im Kampagnen-Workflow aktualisieren, wodurch die Vorlage im Ressourcen-Ordner für Versandvorlagen aktualisiert wird.

Bei einem fortlaufenden Versand wird EIN Versand erstellt. Versandlogs (Broadlog) und Trackinglogs, die auf diesen Versand verweisen, werden bei jeder Ausführung hinzugefügt.

![Versand (fortlaufend)](assets/delivery_continuous.jpg)

## Anleitungsvideo {#continuous-delivery-video}

In diesem Video wird gezeigt, wie Sie einen fortlaufenden Versand mit einer inkrementellen Abfrage konfigurieren.

>[!VIDEO](https://video.tv.adobe.com/v/25039?quality=12)

Weitere Anleitungsvideos zu Campaign finden Sie [hier](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=de){target="_blank"}.

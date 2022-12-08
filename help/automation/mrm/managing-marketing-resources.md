---
product: campaign
title: Marketing-Ressourcen verwalten
description: Erfahren Sie, wie Sie Marketing-Ressourcen verwalten.
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: 399c81276d29622a2161c8c90395df1a38954763
workflow-type: ht
source-wordcount: '1171'
ht-degree: 100%

---

# Marketing-Ressourcen verwalten{#managing-marketing-resources}

Verwenden Sie Adobe Campaign, um die am Lebenszyklus der Kampagne beteiligten Marketing-Ressourcen zu verwalten und zu verfolgen. Bei diesen Marketing-Ressourcen kann es sich um Whitepapers, Datendateien, Logos oder andere Assets handeln, die mit einer Kampagne in Verbindung stehen.

Status, Verlauf und aktuelle Version der über Adobe Campaign verwalteten Marketing-Ressourcen können jederzeit angezeigt werden.

Marketing-Ressourcen werden standardmäßig im Ordner **[!UICONTROL MRM > Marketing-Ressourcen]** des Campaign-Explorers gespeichert.

## Hinzufügen von Marketing-Ressourcen {#adding-a-marketing-resource}

Gehen Sie wie folgt vor, um eine Marketing-Ressource hinzuzufügen:

1. Navigieren Sie zur Registerkarte **[!UICONTROL Kampagnen]** und wählen Sie **[!UICONTROL Marketing-Ressourcen]** aus.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Erstellen]**.
   ![](assets/add-a-mkt-resource.png)
1. Ziehen Sie die Datei in das Fenster „Marketing-Ressource“, um sie zum Campaign-Server hochzuladen. Sie können auch den Link **[!UICONTROL Datei auf den Server laden...]** verwenden.
   ![](assets/mkt-resource-creation.png)

Nach Abschluss des Hochladens wird die Ressource der Liste der verfügbaren Ressourcen hinzugefügt.

## Marketing-Ressourcen verwalten {#manage-marketing-resources}

Nach dem Hochladen ist die Marketing-Ressource für alle Adobe Campaign-Benutzer verfügbar. Sie können sie anzeigen, eine Kopie erstellen, um sie zu ändern, oder die Datei auf dem Server aktualisieren.

![](assets/open-a-marketing-resource.png)

Verwenden Sie die Dropdown-Liste **[!UICONTROL Zugewiesen an]** auf der Registerkarte **[!UICONTROL Bearbeiten]**, um den Benutzer auszuwählen, der für die Ressource verantwortlich ist.

![](assets/assign-a-mkt-resource.png)

Sie können auch die Benutzer oder Benutzergruppen auswählen, die für die Ressourcenvalidierung und die Ressourcenveröffentlichung zuständig sind. Um auf diese Optionen zuzugreifen, klicken Sie auf den Link **[!UICONTROL Erweiterte Parameter]**.

Diese Benutzer werden per E-Mail benachrichtigt, wenn der Ressourcenvalidierungsprozess gestartet wird.

Wenn kein Validierungsverantwortlicher ausgewählt wurde, kann die Ressource **[!UICONTROL nicht]** zur Validierung unterbreitet werden.

Verwenden Sie die Registerkarte **[!UICONTROL Audit]**, um einen Testsendungs-Leser hinzuzufügen und ein Verfügbarkeitsdatum für die Ressource festzulegen. Nach diesem Datum wird sie mit dem Status **[!UICONTROL Überfällig]** angezeigt.

>[!NOTE]
>
>Die Registerkarte **[!UICONTROL Verlauf]** enthält das Protokoll der Downloads und Aktualisierungen der Ressource. Über die Schaltfläche **[!UICONTROL Details]** kann die ausgewählte Version angezeigt werden.
>
>Die Registerkarte **[!UICONTROL Audit]** ermöglicht die Überwachung der an der Ressource vorgenommenen Änderungen: Validierungen, Validierungsablehnungen, Kommentare und Publikationen.

### Ressourcen sperren/entsperren {#locking-unlocking-a-resource}

Nach ihrer Erstellung sind die Ressourcen für die Benutzer im Dashboard der Marketing-Ressourcen verfügbar und sie können bearbeitet und verändert werden.

Wenn ein Benutzer mit der Arbeit an einer Ressource beginnt, empfiehlt es sich, diese zu sperren, damit andere Benutzer sie nicht gleichzeitig ändern können. Die Ressource wird dann reserviert: Sie bleibt verfügbar, kann jedoch von einem anderen Benutzer nicht veröffentlicht oder auf dem Server aktualisiert werden.

Eine Marketing-Ressource kann nur gesperrt werden, wenn sie nicht genehmigt wurde.

Um eine Ressource zu sperren, klicken Sie auf die Ressource und anschließend auf die Schaltfläche **[!UICONTROL Sperren]** im Ressourcen-Dashboard.

![](assets/lock-a-resource.png)


Wenn die Ressource aktualisiert wurde, klicken Sie auf die Schaltfläche **[!UICONTROL Sperren]** im Ressourcen-Dashboard, um sie allen Benutzern wieder verfügbar zu machen.

Folgende Nachricht informiert Benutzer, die auf eine reservierte Ressource zugreifen möchten:

![](assets/mkt-resource-locked.png)

Die Registerkarte **[!UICONTROL Tracking]** gibt den Namen des Benutzers an, der die Ressource gesperrt hat.

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>Nur der Benutzer, der die Ressource gesperrt hat, und solche mit Administrator-Berechtigungen sind befugt, eine gesperrte Ressource zu entsperren.

### Diskussionsforen {#discussion-forums}

An einer Ressource beteiligte Benutzer haben auf der Registerkarte **[!UICONTROL Forum]** die Möglichkeit, Informationen austauschen.

![](assets/mkt-resource-forum.png)

Weitere Informationen finden Sie im Abschnitt [Diskussionsforen](discussion-forums.md).

### Validierungsprozess {#approval-process}

Das erwartete Verfügbarkeitsdatum wird in den Details der Ressource angezeigt, sofern es im Tab **[!UICONTROL Verfolgung]** angegeben wurde. Bei Erreichen des Datums kann der Validierungsprozess im Ressourcen-Dashboard über die Schaltfläche **[!UICONTROL Zur Validierung unterbreiten]** gestartet werden. Der Status der Ressource wechselt zu **[!UICONTROL Validierung in Gang]**.

Um eine Ressource zu genehmigen, klicken Sie auf **[!UICONTROL Ressource validieren]** auf dem Dashboard.

![](assets/mkt-resouce-approve.png)

Berechtigte Benutzer können die Validierung daraufhin akzeptieren oder ablehnen. Diese Aktion kann über den Link in der Benachrichtigungs-E-Mail oder über die Schaltfläche **[!UICONTROL Validieren]** in der Konsole ausgeführt werden.

Im Validierungsfenster kann ein Kommentar eingegeben werden.

![](assets/mkt-resource-approval-confirmation.png)

Navigieren Sie zur Registerkarte **[!UICONTROL Tracking]**, um Genehmigungen zu überprüfen.

>[!NOTE]
>
>Neben dem in jeder Marketing-Ressource bestimmten Validierungsverantwortlichen sind auch Benutzende mit Administrator-Berechtigungen sowie der Ressourcen-Verantwortliche befugt, die jeweilige Ressource zu genehmigen.

### Veröffentlichen von Ressourcen {#publishing-a-resource}

Nach bestätigter Validierung muss die Marketing-Ressource veröffentlicht werden. Der Veröffentlichungsprozess ist separat, den jeweiligen Nutzerbedürfnissen entsprechend zu implementieren. So können Ressourcen beispielsweise auf einem Extranet oder einem beliebigen anderen Server veröffentlicht, bzw. einem externen Dienstleister übermittelt werden usw.

Geben Sie den Zugriff auf eine Ressource frei, indem Sie auf die Schaltfläche **[!UICONTROL Veröffentlichen]** in ihrem Dashboard klicken.

![](assets/mkt-resource-publish.png)

Die Ressourcenveröffentlichung kann auch über einen Workflow automatisiert werden.

Eine Ressource zu veröffentlichen bedeutet, sie verfügbar zu machen, zum Beispiel zur Verwendung in einer Aufgabe. Der eigentliche Vorgang der Veröffentlichung hängt von der Art der Ressource ab: Ein Flyer zum Beispiel kann zum Druck als Datei an einen Dienstleister geschickt oder aber auf einer Webseite online gestellt werden.

Damit Adobe Campaign die Veröffentlichung durchführt, muss ein entsprechender Workflow erstellt und dieser mit der Ressource verbunden werden. Öffnen Sie hierzu das Feld **[!UICONTROL Erweiterte Einstellungen...]** der Ressource und wählen Sie den gewünschten Workflow im Feld **[!UICONTROL Anschlussvorgang]** aus.

![](assets/mkt-resource-post-processing-wf.png)

Der Workflow wird ausgeführt:

* Wenn der Validierungsverantwortliche der Veröffentlichung (oder, falls dieser nicht definiert wurde, der Ressourcen-Verantwortliche) auf **[!UICONTROL Ressource veröffentlichen]** klickt.
* Wenn die Ressource über eine Aufgabe zur Erstellung einer Marketing-Ressource verwaltet wird und die Aufgabe den Status **[!UICONTROL Abgeschlossen]** hat. Zudem muss die Option **[!UICONTROL Marketing-Ressource veröffentlichen]** in der Aufgabe aktiviert worden sein. [Weitere Informationen](creating-and-managing-tasks.md#marketing-resource-creation-task))

Wenn ein Workflow nicht sofort gestartet wird (beispielsweise wenn der Workflow gestoppt), ändert sich der Status der Ressource zu **[!UICONTROL Veröffentlichung ausstehend]**. Nach dem Start des Workflows ändert sich der Status der Ressource in **[!UICONTROL Veröffentlicht]**. Dieser Status berücksichtigt keine möglichen Fehler im Veröffentlichungsprozess. Überprüfen Sie den Status Ihres Workflows, um sicherzustellen, dass er ordnungsgemäß ausgeführt wurde.

## Verknüpfung einer Ressource mit einer Kampagne {#linking-a-resource-to-a-campaign}

### Referenzieren einer Marketing-Ressource {#referencing-a-marketing-resource}

Marketing-Ressourcen können mit Kampagnen verknüpft werden, sofern dieses Feature in der [Kampagnenvorlage](../campaigns/marketing-campaign-templates.md) ausgewählt wurde.

Gehen Sie hierzu im Dashboard der Kampagne zur Registerkarte **[!UICONTROL Bearbeiten > Dokumente > Ressourcen]** und klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine Ressource auszuwählen.

![](assets/link-a-mkt-resource-to-a-campaign.png)

Sie können die Ressourcen nach Status, Art und Ressourcentyp filtern oder einen benutzerdefinierten Filter anwenden.

Verwenden Sie die Schaltfläche **[!UICONTROL Details]**, um die Ressource zu bearbeiten und in der Vorschau anzuzeigen.

### Hinzufügen einer Marketing-Ressource zu einem Versandentwurf {#adding-a-marketing-resource-to-a-delivery-outline}

Marketing-Ressourcen können über Versandentwürfe mit Sendungen verknüpft werden.

Weitere Informationen zu Versandentwürfen finden Sie in [diesem Abschnitt](../campaigns/marketing-campaign-deliveries.md).

Klicken Sie dazu mit der rechten Maustaste auf einen Versandentwurf und wählen Sie **Neu > Ressource** aus.

![](assets/mkt-resource-add-in-del-outline.png)

Geben Sie den Namen des Assets ein und wählen Sie es aus der Dropdown-Liste **Marketing-Ressource** aus.

![](assets/mkt-resource-select-in-del-outline.png)


## Lagerverwaltung {#stock-management}

Sie können eine Marketing-Ressource mit einem oder mehreren Lagern verknüpfen, um den Vorrat zu verwalten und bei unzureichendem Vorrat einen Warnhinweis im Dashboard anzuzeigen.


Gehen Sie wie folgt vor, um eine Marketing-Ressource mit einem Lager zu verknüpfen:

1. Bearbeiten Sie ein Lager oder erstellen Sie ein neues Lager. Weitere Informationen zu Lagern finden Sie in [diesem Abschnitt](../campaigns/providers--stocks-and-budgets.md#stock-management).

1. Fügen Sie eine Lagerposition hinzu und wählen Sie die entsprechende Marketing-Ressource aus.

   ![](assets/mkt-resource-in-a-stock-line.png)

   Bei Bedarf können Sie die ausgewählte Ressource über das Symbol **[!UICONTROL Link bearbeiten]** rechts von der Ressource bearbeiten.

1. Geben Sie den Anfangsbestand sowie den Warnbestand an und speichern Sie.

Das Lager wird auf der Registerkarte **Lager** der Marketing-Ressource angezeigt.

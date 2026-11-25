---
product: campaign
title: Marketing-Kampagnenvorlagen
description: Marketing-Kampagnenvorlagen
feature: Campaigns, Templates
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
TQID: 'https://experienceleague.adobe.com/qmz-Sd1EJmACFfgozVirCHCaeiQN-lGKuxd9-VAPMHs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: baf8e746-117b-5e73-b179-0a83edc0295f
    internal-label: Templates
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 68%
---
# Erstellen und Konfigurieren von Kampagnenvorlagen {#campaign-templates}

Alle Marketing-Kampagnen basieren auf einer Vorlage, in der die Hauptmerkmale und -funktionen gespeichert sind. Campaign verfügt über eine integrierte Vorlage zum Erstellen von Kampagnen. Für diese Vorlage sind alle Funktionen aktiviert: Dokumente, Testadressen, Validierungen, Versandentwürfe usw.

Welche Funktionen verfügbar sind, hängt von Ihren Berechtigungen, Add-ons und der Konfiguration Ihrer Adobe Campaign-Plattform ab.


>[!NOTE]
>
>Um den Navigationsbaum anzuzeigen, klicken Sie auf das Symbol **[!UICONTROL Explorer]** auf der Startseite.

Es wird eine native Vorlage bereitgestellt, mit der Sie eine Kampagne erstellen können, für die keine bestimmte Konfiguration definiert wurde. Sie können Ihre Kampagnenvorlagen erstellen und konfigurieren und dann Kampagnen aus diesen Vorlagen erstellen.

## Erstellen einer Kampagnenvorlage {#create-a-campaign-template}

Gehen Sie wie folgt vor, um eine Kampagnenvorlage zu erstellen:

1. Öffnen Sie den **Explorer** von Campaign und gehen Sie zu **Ressourcen > Vorlagen > Kampagnenvorlagen**.
1. Klicken Sie in der Symbolleiste oberhalb der Vorlagenliste auf **Neu**.

![Liste der Kampagnenvorlagen unter Ressourcen > Vorlagen, wobei die Schaltfläche Neu in der Symbolleiste hervorgehoben ist.](assets/campaign-template-node.png)

Sie können die integrierte Vorlage auch **duplizieren**, um ihre Konfiguration wiederzuverwenden und anzupassen. Klicken Sie dazu mit der rechten Maustaste auf die Vorlage und wählen Sie **Duplizieren**.

1. Geben Sie den Titel der neuen Kampagnenvorlage ein.
1. Klicken Sie auf **Speichern** und öffnen Sie die Vorlage erneut.
1. Definieren Sie auf der Registerkarte **Bearbeiten** die Eigenschaften der Vorlage.
1. Wählen Sie den Link **Erweiterte Kampagnenparameter...**, um einen Workflow zu Ihrer Kampagnenvorlage hinzuzufügen.

   ![Registerkarte „Neue Kampagnenvorlage bearbeiten“ mit hervorgehobenem Link „Erweiterte Kampagnenparameter“.](assets/campaign-template-parameters.png)

1. Ändern Sie den Wert für **Zielgruppenbestimmungen und Workflows** auf **Ja** und bestätigen Sie diesen. Erfahren Sie, wie Sie in [Typologie von Modulen“ Funktionen &#x200B;](#typology-of-enabled-modules).
1. Die Registerkarte **Zielgruppenbestimmungen und Workflows** wird zur Vorlage hinzugefügt. Klicken Sie auf **Workflow hinzufügen...**, geben Sie einen **Titel** ein und klicken Sie auf **OK**.
1. Erstellen Sie Ihren Workflow entsprechend Ihren Anforderungen.

   ![Registerkarte Zielgruppenbestimmungen und Workflows der Vorlage mit einem Workflow, der Abfrage und Liste lesen enthält, die zum E-Mail-Versand führen.](assets/campaign-template-create-wf.png)

1. Klicken Sie auf **Speichern**. Ihre Vorlage kann jetzt zur Erstellung einer neuen Kampagne verwendet werden.

Die unterschiedlichen Registerkarten und Unterregisterkarten der Kampagnenvorlage ermöglichen den Zugriff auf die Einstellungen. Sie werden im Abschnitt [Allgemeine Konfiguration](#general-configuration) beschrieben.

## Auswählen von Modulen {#select-modules}

Über den Link **[!UICONTROL Erweiterte Kampagnenparameter...]** können Sie Aufträge für die auf dieser Vorlage basierenden Kampagnen aktivieren und deaktivieren. Wählen Sie die Funktionen aus, die Sie in den über diese Vorlage erstellten Kampagnen aktivieren möchten.

![Registerkarte „Erweiterte Einstellungen - Konfiguration“ mit einer Liste aller Funktionen mit den Werten „Ja“ oder „Nein“; „Ausgaben und Ziele“ ist „Nein“.](assets/campaign-template-select-modules.png)

Wenn keine Funktion ausgewählt ist, werden die den Prozess betreffenden Elemente (Menüs, Symbole, Optionen, Registerkarten, Unterregisterkarten usw.) nicht in der Benutzeroberfläche der Vorlage oder in den auf dieser Vorlage basierenden Kampagnen angezeigt. Die Registerkarten auf der linken Seite der Kampagnendetails und die verfügbaren Registerkarten entsprechen den in der Vorlage ausgewählten Funktionen. Wenn zum Beispiel die Funktion **Ausgaben und Ziele** nicht aktiviert ist, wird die entsprechende Registerkarte **[!UICONTROL Budget]** in Kampagnen, die auf dieser Vorlage basieren, nicht angezeigt.

Im Kampagnen-Dashboard werden zudem Verknüpfungen zu den Konfigurationsfenstern hinzugefügt. Wenn eine Funktionalität aktiviert ist, besteht über einen Link im Kampagnen-Dashboard direkter Zugriff darauf.

### Konfigurationsbeispiele

* Beispielsweise mit den folgenden Einstellungen:

  ![Erweiterte Einstellungen: Kontrollgruppe, Testadressen und Dokumente auf „Ja“ gesetzt; Genehmigungen, Zielgruppenbestimmungen und Workflows auf „Nein“ gesetzt.](assets/campaign-template-select-functionalities.png)

  Das Kampagnen-Dashboard zeigt Folgendes an:

  ![Kampagnen-Dashboard nur mit den Registerkarten Dashboard und Bearbeiten sowie Links Versand hinzufügen und Dokument hinzufügen.](assets/campaign-template-dashboard-sample-1.png)

  Beachten Sie, dass die Registerkarte **[!UICONTROL Zielgruppenbestimmungen und Workflows]** fehlt.

  Folgende Funktionen stehen zur Verfügung:

  ![Registerkarte „Bearbeiten“ der Kampagne mit den Abschnitten „Eigenschaften“, „Dokumente“ und „Audit“ und ohne „Budget“.](assets/campaign-template-edit-sample-1.png)

  Beachten Sie, dass die Registerkarte **[!UICONTROL Budget]** fehlt.

  Die erweiterten Einstellungen der Kampagne spiegeln diese Konfiguration ebenfalls wider.

  ![Erweiterte Einstellungen in Campaign mit den Registerkarten „Kontrollpopulation“ und „Testadressen“ und „Keine Validierungen“.](assets/campaign-template-parameters-sample-1.png)

  Beachten Sie, dass die Registerkarte **[!UICONTROL Genehmigungen]** nicht verfügbar ist.

* Mit dieser Konfiguration:
  ![Erweiterte Einstellungen: Genehmigungen, Zielgruppenbestimmungen und Workflows, Ausgaben und Ziele auf „Ja“ gesetzt; Andere Funktionen Nein.](assets/campaign-template-dashboard-sample-2.png)

  Das Kampagnen-Dashboard zeigt Folgendes an:

  ![Kampagnen-Dashboard mit der Registerkarte Zielgruppenbestimmungen und Workflows und einem Link zum Hinzufügen eines Versands, aber ohne Link zum Hinzufügen eines Dokuments.](assets/campaign-template-select-functionalities-2.png)

  Beachten Sie, dass die Registerkarte **[!UICONTROL Zielgruppenbestimmungen und Workflows]** verfügbar ist, aber der Link **Dokument hinzufügen** fehlt.

  Folgende Funktionen stehen zur Verfügung:

  ![Registerkarte „Bearbeiten“ mit geöffnetem Abschnitt „Budget“, auf der die zugehörigen Registerkarten „Budget“, „Ziele“ und „Kosten und Ausgaben“ angezeigt werden.](assets/campaign-template-edit-sample-2.png)

  Beachten Sie, dass die Registerkarte **[!UICONTROL Budget]** verfügbar ist.

  Die erweiterten Einstellungen der Kampagne spiegeln diese Konfiguration ebenfalls wider.

  ![Erweiterte Einstellungen mit der Registerkarte Genehmigungen und Vorgangsvalidierungen und ohne die Registerkarten Kontrollpopulation oder Testadressen.](assets/campaign-template-parameters-sample-2.png)

  Beachten Sie, dass die Registerkarte **[!UICONTROL Genehmigungen]** verfügbar ist, aber die Registerkarten **[!UICONTROL Kontrollpopulation]** und **[!UICONTROL Testadressen]** nicht aktiviert sind.


## Typologie von Modulen {#typology-of-enabled-modules}

* **Kontrollgruppe**

  Wenn dieses Modul ausgewählt wird, wird den erweiterten Einstellungen der Vorlage und den auf dieser Vorlage basierenden Kampagnen eine zusätzliche Registerkarte hinzugefügt. Die Konfiguration kann über die Vorlage oder einzeln für jede Kampagne definiert werden. Erfahren Sie mehr über Kontrollgruppen in [Sendungen von Marketing-Kampagnen](marketing-campaign-deliveries.md).

  ![Erweiterte Einstellungen Registerkarte „Kontrollpopulation“ mit aktivierter Option „Kontrollgruppe“ und Link „Bearbeiten“ für die Konfiguration.](assets/template-activate-1.png)


* **Testadressen**

  Wenn dieses Modul ausgewählt wird, wird den erweiterten Einstellungen der Vorlage und den auf dieser Vorlage basierenden Kampagnen eine zusätzliche Registerkarte hinzugefügt. Die Konfiguration kann über die Vorlage oder einzeln für jede Kampagne definiert werden.

  ![Erweiterte Einstellungen Registerkarte Testadressen mit einem Link Testadressen importieren und einer Liste von Testadressen.](assets/template-activate-2.png)

* **Dokumente**

  Wenn dieses Modul ausgewählt wird, wird eine zusätzliche Registerkarte zur Registerkarte **[!UICONTROL Bearbeiten]** der Vorlage und der auf dieser Vorlage basierenden Kampagnen hinzugefügt. Anhänge können für jede Kampagne in der Vorlage oder einzeln hinzugefügt werden. Weitere Informationen zu Dokumenten finden Sie unter [Sendungen von Marketing-Kampagnen](marketing-campaign-deliveries.md).

  ![Dokumente auf der Registerkarte Bearbeiten , auf der die angehängten Dokumente aufgelistet sind, mit den Schaltflächen Hinzufügen, Löschen und Detail.](assets/template-activate-3.png)

* **Versandentwurf**

  Wenn dieses Modul ausgewählt wird, wird dem Tab **[!UICONTROL Dokumente]** der Unter-Tab **[!UICONTROL Versandentwürfe]** hinzugefügt, um für die Kampagne unterschiedliche Versandentwürfe zu erstellen. Weitere Informationen zu Versandentwürfen finden Sie unter [Verwenden von Versandentwürfen](marketing-campaign-assets.md#delivery-outlines).

  ![Unterregisterkarte Versandentwürfe des Abschnitts Dokumente mit einem Link Versandentwurf hinzufügen.](assets/template-activate-4.png)

* **Zielgruppenbestimmungen und Workflows**

  Wenn das Modul **[!UICONTROL Zielgruppenbestimmungen und Workflows]** ausgewählt wird, wird ein Tab zum Erstellen eines oder mehrerer Workflows für Kampagnen hinzugefügt, die auf dieser Vorlage basieren. Workflows können auch basierend auf dieser Vorlage einzeln für jede Kampagne konfiguriert werden.Erfahren Sie mehr über Kampagnen-Workflows in [Sendungen von Marketing-Kampagnen](marketing-campaign-deliveries.md).

  ![Registerkarte Zielgruppenbestimmungen und Workflows mit einem Workflow: Abfrage und Liste lesen, Deduplizierung, dann Versand auf Mobilgeräten.](assets/template-activate-5.png)

  Wenn dieses Modul aktiviert ist, wird die Registerkarte **[!UICONTROL Aufträge]** zu den erweiterten Einstellungen der Kampagne hinzugefügt, um die Reihenfolge der Prozessausführung zu definieren.

* **Validierungen**

  Wenn Sie die **[!UICONTROL Validierungen]** aktivieren, können Sie die zu genehmigenden Prozesse und die für die Genehmigungen zuständigen Personen auswählen. Weitere Informationen zu Validierungen finden Sie unter [Validierungsverantwortliche auswählen](marketing-campaign-approval.md#select-reviewers).

  ![Registerkarte „Erweiterte Einstellungsgenehmigungen“ mit aktivierten Validierungen für Inhalt, Zielgruppe, Budget und Extraktion und zugewiesenen Validierern.](assets/template-activate-6.png)

  Sie können wählen, ob Sie die Prozessvalidierung über die Registerkarte **[!UICONTROL Genehmigungen]** im Abschnitt mit den erweiterten Einstellungen der Vorlagen aktivieren möchten oder nicht.

* **Ausgaben und Budget**

  Wenn dieses Modul ausgewählt wird, wird der Tab **[!UICONTROL Budget]** den Details der Vorlage und der auf dieser Vorlage basierenden Kampagnen hinzugefügt, damit das zugehörige Budget ausgewählt werden kann.

  ![Budgetbereich der Registerkarte „Bearbeiten“ mit zugehörigen Budgetfeldern, Zielen und der Registerkarte „Kosten“ mit Kostenzeilen.](assets/template-activate-7.png)


## Vorlageneigenschaften {#template-properties}

![Registerkarte „Kampagnenvorlage bearbeiten“ mit der Dropdown-Liste „Vorgangstyp“ geöffnet, auf der Eindeutig, Wiederkehrend und Periodisch angezeigt werden.](assets/template-op-type.png)

Bei der Erstellung einer Kampagnenvorlage ist die Angabe folgender Informationen notwendig:

* Geben Sie den **Titel** der Vorlage ein: Der Titel ist obligatorisch und wird als Standardbtitel für alle auf dieser Vorlage basierenden Kampagnen verwendet.
* Wählen Sie die **Kampagnenart** aus der Dropdown-Liste aus. Die in der Dropdown-Liste angebotenen Werte entsprechen den in der Aufzählung **[!UICONTROL natureOp]** gespeicherten Werten.

  Erfahren Sie, wie Sie in Auflistungen verwalten auf [&#x200B; Auflistungen zugreifen &#x200B;](../../v8/config/enumerations.md) sie konfigurieren können.

* Wählen Sie den **Kampagnentyp** aus: einmalig, wiederkehrend oder periodisch. Standardmäßig gelten Kampagnenvorlagen für einmalige Kampagnen. Wiederkehrende und periodische Kampagnen werden im Abschnitt [Erstellen wiederkehrender und periodischer Kampagnen“ &#x200B;](recurring-periodic-campaigns.md).
* Geben Sie die Dauer der Kampagne an. Dies ist der Zeitraum, über den sich die Kampagne erstrecken wird. Wenn Sie eine auf dieser Vorlage basierende Kampagne erstellen, werden das Start- und Enddatum der Kampagne automatisch ausgefüllt.

  Handelt es sich um eine wiederkehrende Kampagne, müssen Start- und Enddatum direkt in der Vorlage angegeben werden.

* Geben Sie das mit der Vorlage **verknüpfte Programm** an: Kampagnen, die auf dieser Vorlage basieren, sind mit dem ausgewählten Programm verknüpft.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.
-->

---
product: campaign
title: Erstellen von Marketing-Kampagnen
description: Erfahren Sie, wie Sie Marketing-Kampagnen erstellen und ausführen.
feature: Campaigns, Cross Channel Orchestration, Programs
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 50%

---

# Erstellen von Programmen und Kampagnen{#create-programs-and-campaigns}

Komponenten für die Kampagnenorchestrierung finden Sie im Abschnitt **[!UICONTROL Kampagnen]** tab: hier können Sie einen Überblick über die Marketingprogramme und -kampagnen und die damit verbundenen Elemente erhalten.

Ein Marketingprogramm besteht aus Kampagnen, die Sendungen, Ressourcen usw. beinhalten. Alle Informationen bezüglich Sendungen, Budgets, Validierungsverantwortlichen und verknüpften Dokumenten werden in der Kampagne zusammengefasst.

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [Entdecken Sie Programme und Kampagnen im Video.](#video)

## Arbeiten mit Programmen und Plänen{#work-with-plan-and-program}

### Hierarchie der Pläne und Programme erstellen {#create-plan-and-program}

Jede Kampagne gehört zu einem Programm, das zu einem Plan gehört. Alle Pläne, Programme und Kampagnen sind über die **[!UICONTROL Kampagnenkalender]** im Menü **Kampagnen** Registerkarte.

Bevor Sie mit der Erstellung Ihrer Kampagnen und Sendungen beginnen, konfigurieren Sie Ihre Ordnerhierarchie für Marketingpläne und -programme.

1. Klicken Sie auf das **Explorer-** Symbol auf der Startseite.
1. Klicken Sie mit der rechten Maustaste auf den Ordner, in dem Sie Ihren Plan erstellen möchten.
1. Wählen Sie **Ordner hinzufügen > Kampagnenverwaltung > Plan** aus.

   ![](assets/create-new-plan-folder.png)

1. Benennen Sie den Plan.
1. Klicken Sie mit der rechten Maustaste auf den neu erstellen Plan und wählen Sie **Eigenschaften...**.
1. Passen Sie im Tab **Allgemein** die Option **Interner Name** an, um bei Package-Exporten Duplikate zu vermeiden.

   ![](assets/plan-properties.png)

1. Wählen Sie **Speichern** aus.
1. Klicken Sie mit der rechten Maustaste auf den neu erstellen Plan und wählen Sie **Programm-Ordner hinzufügen**.

   ![](assets/program-folder.png)

1. Wiederholen Sie die obigen Schritte, um Ihren neuen Programmordner und seinen internen Namen umzubenennen.


### Programm konfigurieren {#edit-a-program}

Zur Konfiguration und Bearbeitung eines Programms stehen die folgenden Tabs zur Verfügung:

* Im Tab **Planung** können Sie den Programmkalender entweder nach Monat, Woche oder Tag angezeigen lassen, indem Sie auf den jeweiligen Tab klicken. Auf dieser Seite können Sie eine Kampagne, ein Programm oder eine Aufgabe erstellen. [Weitere Informationen](#campaign-calendar)

* Über den Tab **Bearbeiten** kann das Programm konfiguriert und verändert werden (Name, Beginn und Ende, Budget, benötigte Dokumente usw.).

   ![](assets/new-program-edit-tab.png)

## Arbeiten mit Kampagnen{#work-with-campaigns}

### Erstellen einer Kampagne {#create-a-campaign}

Sie können eine Kampagne über die Kampagnenliste erstellen. Um diese Ansicht anzuzeigen, wählen Sie die **[!UICONTROL Kampagnen]** im Menü **[!UICONTROL Kampagnen]** Dashboard und klicken Sie auf **[!UICONTROL Erstellen]**.

Im Feld **[!UICONTROL Programm]** wird das Programm ausgewählt, dem die Kampagne zugeordnet werden soll. Diese Information muss angegeben werden.

![](assets/new-campaign-settings.png)

Kampagnen können auch über den Kampagnen- oder Programmkalender erstellt werden. [Weitere Informationen](#campaign-calendar)

Wählen Sie im Fenster zur Kampagnenerstellung die Kampagnenvorlage aus und fügen Sie einen Namen und eine Beschreibung der Kampagne hinzu. Sie können auch das Anfangs- und Enddatum der Kampagne angeben.

Klicken **[!UICONTROL OK]** , um die Kampagne zu erstellen. Er wird dem Programmkalender und der Kampagnenliste hinzugefügt.

Sie können anschließend die gerade erstellte Kampagne bearbeiten und ihre Parameter festlegen. Um diese Kampagne zu öffnen und zu konfigurieren, haben Sie folgende Möglichkeiten:

1. Durchsuchen Sie den Kampagnenkalender, wählen Sie die gewünschte Kampagne aus und klicken Sie auf die Schaltfläche **[!UICONTROL Öffnen]** Link.
1. Durchsuchen Sie die **[!UICONTROL Zeitplan]** im Tab des Programms, wählen Sie die Kampagne aus und öffnen Sie sie.
1. Durchsuchen Sie die Liste der Kampagnen und klicken Sie auf den Namen der zu bearbeitenden Kampagne.

Mit all diesen Aktionen gelangen Sie zum Kampagnen-Dashboard.

![](assets/campaigns-dashboard-approve.png)

In den folgenden Abschnitten erfahren Sie, wie Sie Ihre Kampagne konfigurieren:

* [Sendungen hinzufügen](marketing-campaign-deliveries.md)
* [Verwalten von Assets und Dokumenten](marketing-campaign-assets.md)
* [Zielgruppe erstellen](marketing-campaign-target.md)
* [Einrichten des Validierungsprozesses](marketing-campaign-approval.md)
* [Verwaltung von Lagern und Budgets](providers--stocks-and-budgets.md)


### Bearbeiten von Kampagneneinstellungen {#campaign-settings}

Kampagnen werden über Kampagnenvorlagen erstellt. Sie können wiederverwendbare Vorlagen konfigurieren, für die einige Optionen ausgewählt und andere Einstellungen bereits gespeichert sind.

Für jede Kampagne stehen folgende Funktionen zur Verfügung:

* Referenzdokumente und -ressourcen: Sie können der Kampagne Dokumente zuordnen (Kurzbeschreibung, Bericht, Bilder etc.). Alle Dokumentenformate werden unterstützt. [Weitere Informationen](marketing-campaign-deliveries.md#manage-associated-documents).
* Kosten definieren: Adobe Campaign ermöglicht es, für jede Kampagne Kosteneinträge und Kostenberechnungsstrukturen zu definieren, die bei der Erstellung der Marketingkampagne verwendet werden können. Beispiel: Druckkosten, Nutzung einer externen Agentur, Zimmervermietung usw. [Weitere Informationen](providers--stocks-and-budgets.md#defining-cost-categories).
* Definition von Zielen: Sie können quantifizierbare Ziele für eine Kampagne definieren, z. B. die Anzahl der Abonnenten, das Geschäftsvolumen etc. Diese Informationen werden später in Kampagnenberichten verwendet.
* Verwalten Sie Testadressen und Kontrollgruppen. [Weitere Informationen](marketing-campaign-deliveries.md#defining-a-control-group).
* Verwalten von Genehmigungen: Sie können die zu validierenden Behandlungen auswählen und bei Bedarf die validierenden Benutzer oder Benutzergruppen auswählen. [Weitere Informationen](marketing-campaign-approval.md#checking-and-approving-deliveries).

>[!NOTE]
>
>Um auf die Kampagneneinstellungen zuzugreifen und sie zu aktualisieren, navigieren Sie zu **[!UICONTROL Erweiterte Kampagnenparameter...]** im **[!UICONTROL Bearbeiten]** Registerkarte.

### Überwachen einer Kampagne {#monitor-a-campaign}

Für jede Kampagne werden Vorgänge, Ressourcen und Sendungen in einem Dashboard zentralisiert. Auf dieser Oberfläche können Sie Marketing-Aktionen verwalten und koordinieren.

Mit Adobe Campaign können Sie kollaborative Prozesse zur Erstellung und Genehmigung der verschiedenen Kampagnenschritte einrichten: Validierung von Budget, Zielgruppe, Inhalt usw. Diese Orchestrierung wird im Abschnitt [diesem Abschnitt](marketing-campaign-approval.md).

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>In einer Kampagne verfügbare Komponenten hängen von der Vorlage ab. Die Konfiguration von Kampagnenvorlagen wird im Abschnitt [diesem Abschnitt](marketing-campaign-templates.md#campaign-templates).

Sobald die Kampagne abgeschlossen ist, verwenden Sie die **[!UICONTROL Berichte]** -Link, um auf die Kampagnenberichte zuzugreifen.

![](assets/campaigns-reports-dashboard.png)

## Kampagnenkalender {#campaign-calendar}

Der Kampagnenkalender zeigt alle Programme, Pläne, Kampagnen und Sendungen an.

Um einen Plan, ein Programm, eine Kampagne oder einen Versand zu bearbeiten, navigieren Sie im Kalender zu seinem Namen und verwenden Sie dann die **[!UICONTROL Öffnen]** Link. Er wird dann auf einer neuen Registerkarte angezeigt, wie unten dargestellt:

![](assets/campaign-calendar.png)

Sie haben die Möglichkeit, die im Kampagnenkalender angezeigten Informationen zu filtern. Klicken Sie hierzu auf den Link **[!UICONTROL Filtern]** und wählen Sie die gewünschten Kriterien aus.

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>Wenn Sie nach einem Datum filtern, werden alle Kampagnen angezeigt, deren Startdatum nach dem angegebenen Datum liegt und/oder deren Enddatum vor dem angegebenen Datum liegt. Datumsangaben werden in den Kalender rechts von jedem Feld ausgewählt.

Sie können zur Filterung der angezeigten Elemente auch das Feld **[!UICONTROL Suchen]** verwenden.

Die den Elementen zugeordneten Symbole geben Auskunft über ihren jeweiligen Status: Abgeschlossen, In Gang, In Bearbeitung usw.

Um nur bestimmte Kampagnen anzuzeigen, klicken Sie auf **[!UICONTROL Filtern]** und wählen Sie den Status der gesuchten Kampagnen aus.

![](assets/calendar-filter-options.png)

Beim Durchsuchen des Kalenders können Sie auch ein Programm oder eine Kampagne erstellen.

![](assets/campaign-create-from-calendar.png)

Wenn Sie eine Kampagne im Tab **[!UICONTROL Planung]** eines Programms erstellen, wird die Kampagne dem jeweiligen Programm automatisch hinzugefügt. Das Feld **[!UICONTROL Programm]** wird in diesem Fall ausgeblendet.


## Webschnittstelle verwenden {#use-the-web-interface-}

Sie haben die Möglichkeit, über einen Webbrowser auf die Adobe-Campaign-Konsole zuzugreifen, um alle Kampagnen und ihre Sendungen sowie Berichte und Informationen bezüglich der Profile Ihrer Datenbank einzusehen. Über den Webzugriff können keine Datensätze erstellt werden. Sie können jedoch eingesehen und entsprechend der jeweiligen Benutzerberechtigungen weiterverarbeitet werden. So können beispielsweise Inhalte und Zielgruppen der Kampagnen validiert oder Sendungen unterbrochen werden.

1. Melden Sie sich wie gewohnt über https://`<your instance>:<port>/view/home` an.
1. Über die unterschiedlichen Rubriken besteht Zugriff auf Listen und weitere Navigationselemente.

   ![](assets/web-access-campaigns.png)

Neben dem Navigieren durch und Ansehen von Kampagnen können Sie auch die folgenden Aufgaben ausführen:

* Überwachen von Aktivitäten in einer Instanz
* Teilnahme an Validierungsprozessen, beispielsweise an der Validierung von Versandinhalten
* Durchführen anderer Schnellaktionen, z. B. Pausieren eines Workflows
* Zugriff auf alle Reporting-Funktionen
* Teilnahme an Forumsdiskussionen

Diese Tabelle fasst die Aktionen zusammen, die Sie über einen Browser für Kampagnen durchführen können:

| Seite  | Aktion |
| --- | --- |
| Liste der Kampagnen, Sendungen, Angebote usw. | Löschen von Listenelementen |
| Kampagne | Abbrechen einer Kampagne |
| Versand | Inhalt und Zielgruppe des Versands validieren<br/>Versandinhalt übermitteln<br/>Versand bestätigen<br/>Versand anhalten und stoppen |
| Web-Programm | Web-Programm erstellen<br/>Bearbeiten des Programminhalts und der Eigenschaften<br/>Programminhalt als Vorlage speichern<br/>Programm veröffentlichen |
| Angebot | Inhalt und Eignung des Angebots validieren<br/>Online-Angebot deaktivieren |
| Aufgabe | Aufgabe abschließen<br/>Aufgabe abbrechen |
| Marketing-Ressourcen | Ressource validieren<br/>Ressource sperren und entsperren |
| Kampagnenkit | Kit zur Genehmigung einreichen<br/>Kit genehmigen oder ablehnen<br/>Kit abbrechen |
| Kampagnenbestellung | Bestellung erstellen<br/>Bestellung annehmen oder ablehnen |
| Lager | Lagerposition löschen |
| Angebotssimulation | Simulation starten und stoppen |
| Zielgruppenbestimmungs-Workflow | Workflow starten, pausieren und stoppen |
| Bericht | Aktuelle Daten im Berichtsverlauf speichern |
| Forum | Diskussion hinzufügen<br/>Eine Nachricht in einer Diskussion beantworten<br/>Einer Diskussion folgen und das Abonnement beenden |

### Verwalten von Validierungen

Die Validierung einer Zielgruppe oder eines Versandinhalts kann über den Web-Zugriff erfolgen.

![](assets/web-access-approval.png)

Sie können auch den in den Benachrichtigungsinhalten enthaltenen Link verwenden. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](marketing-campaign-approval.md#checking-and-approving-deliveries).


## Anleitungsvideo {#video}

In diesem Video wird erklärt, wie man einen Marketing-Plan, Programme und Kampagnen erstellt.

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)


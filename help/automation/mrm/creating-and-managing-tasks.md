---
product: campaign
title: Verwaltung von Aufgaben
description: Verwaltung von Aufgaben
feature: Campaigns, Resource Management
role: User
exl-id: 730d1712-53a6-4bf7-9aac-523b06bd0d0a
TQID: 'https://experienceleague.adobe.com/LggpejZ5h1fYPh3efYx2f7x3DEhqVlvPndjgNkNUUCs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: 8d5d4b17-44c6-5e7b-891c-b4277613013d
    internal-label: Resource Management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '3936'
ht-degree: 99%
---
# Aufgaben erstellen und verwalten{#creating-and-managing-tasks}

Mit Adobe Campaign können Aufgaben erstellt und deren gesamter Lebenszyklus direkt im Programm verwaltet werden. Die Programm- und Kampagnenimplementierung kann in Aufgaben unterteilt werden, die Adobe Campaign-Benutzenden oder externen Dienstleistenden zugewiesen sind. Mit diesem Betriebsmodus können Sie eine offene Umgebung für die Zusammenarbeit erstellen, die alle Programmteilnehmenden und externen Teilnehmenden umfasst.

Die Aufgaben können in der Aufgabenliste und über das Dashboard einer Kampagne erstellt, angezeigt und überwacht werden. Anzeige und Nachverfolgung sind darüber hinaus auch in den Zeitplänen des Marketing-Plans, des Programms und der Kampagnen möglich.

Aufgaben sind an eine Kampagne angehängt und können Abhängigkeiten aufweisen, d. h. verknüpfte Aufgaben. Jede Aufgabe verfügt über einen Status, eine Priorität, eine geschätzte Auslastung und zugehörige Kosten.

Alle Aufgaben sind in einer Liste gruppiert, auf die über den Tab **Kampagnen** zugegriffen werden kann. Weitere Informationen hierzu finden Sie unter [Zugriff auf Aufgaben](#accessing-tasks).

Sie können auch im Kalender des Programms, dem sie angehören, angezeigt werden.

![](assets/campaign-calendar.png)

## Zugriff auf Aufgaben {#accessing-tasks}

### Aufgaben anzeigen {#displaying-tasks}

Eine Liste der Aufgaben kann über den Tab **[!UICONTROL Kampagnen]** angezeigt werden.

![](assets/campaign-task-dashboard.png)

Hier werden alle Aufgaben des aktuellen Benutzers aufgeführt.

Weitere Informationen hierzu finden Sie unter [Ausführungsstatus einer Aufgabe](#execution-status-of-a-task) und [Fortschrittsstatus einer Aufgabe ](#progress-status-of-a-task).

### Aufgaben filtern {#filtering-tasks}

Wenn Sie diese Ansicht anzeigen, wird sie automatisch gefiltert, um nur die **aktuelle Benutzeraufgaben** anzuzeigen. Sie können die Aufgaben auch mithilfe der Felder im oberen Bereich des Fensters filtern.

### Aufgaben bearbeiten {#editing-tasks}

Klicken Sie auf eine Aufgabe, um sie zu bearbeiten.

![](assets/edit-a-task.png)

## Neue Aufgabe erstellen {#creating-a-new-task}

Gehen Sie wie folgt vor, um eine Aufgabe zu erstellen:

1. Navigieren Sie zum Link **[!UICONTROL Aufgaben]** in der Registerkarte **[!UICONTROL Kampagnen]** und klicken Sie auf **[!UICONTROL Erstellen]**.

   ![](assets/create-a-task-from-dashboard.png)

1. Geben Sie den Namen der Aufgabe ein und wählen Sie die Kampagne aus, mit der sie verknüpft ist.
1. Legen Sie das Start- und Enddatum fest.
1. Klicken Sie anschließend auf **[!UICONTROL Speichern]**, um die Aufgabe zu erstellen.

   ![](assets/new-task-edit.png)

Aufgaben können zudem über das Dashboard einer Kampagne erstellt werden: In diesem Fall werden sie automatisch der Kampagne zugeordnet, über die sie erstellt wurden.

![](assets/add-a-task-in-a-campaign.png)

Nachdem eine Aufgabe erstellt wurde, wird sie zum Kampagnenkalender, zum Kampagnen-Dashboard und zur Aufgabenliste hinzugefügt. Um eine Aufgabe zu bearbeiten, klicken Sie in der Aufgabenliste auf ihren Namen oder wählen Sie sie im Zeitplan- oder Kampagnen-Dashboard aus und klicken Sie auf **[!UICONTROL Öffnen]**.

Nach der Erstellung können Sie die Aufgabe konfigurieren, indem Sie Folgendes definieren:

* Manager und Teilnehmende. [Weitere Informationen](#manager-and-participants)
* Erstellungsplan. [Weitere Informationen](#execution-schedule)
* Mittelbindungen. [Weitere Informationen](#expenses-and-revenues)

Sie können auch [Validierungsverantwortliche](#reviewers) und [Referenzdokumente](#documents-referenced) hinzufügen.

Der Lebenszyklus einer Aufgabe wird in [diesem Abschnitt](#life-cycle) vorgestellt.

### Verantwortlicher und Teilnehmer {#manager-and-participants}

Die Aufgabe wird standardmäßig dem Benutzer zugewiesen, der sie erstellt hat. Dieser Benutzer wird benachrichtigt, wenn für diese Aufgabe eine Aktion erforderlich ist.

Sie können einen anderen Benutzer aus der Dropdown-Liste **[!UICONTROL Zugewiesen an]** auswählen.

![](assets/task-assigned-to.png)

>[!NOTE]
>
>Die Benutzerverwaltung wird in [diesem Abschnitt](../../v8/start/gs-permissions.md) beschrieben.
>
>Der für eine Aufgabe verantwortliche Benutzer ist als Einziger dazu berechtigt, die Aufgabe zu schließen.

Sie können mehr Benutzer angeben, die an der Ausführung der Aufgabe beteiligt sind. Diese Benutzer dürfen die Aufgabe nicht schließen: sie dürfen nur die ihnen zugewiesene Aufgabe genehmigen.

Gehen Sie wie folgt vor, um Aufgabenbenutzer hinzuzufügen:

1. Klicken Sie auf **[!UICONTROL Ressourcen]** in der Aufgabensymbolleiste.

   ![](assets/add-task-resources.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]** und wählen Sie die betroffenen Benutzer aus.
1. Geben Sie die Nutzungsrate ein: Dies entspricht dem Arbeitsaufwand, der dem Benutzer für die Dauer der Aufgabenausführung zugewiesen wurde. Dieser Satz ist nur ein Hinweis und wird in Prozent ausgedrückt.

   ![](assets/define-operator-task-workload.png)

   Beispiel: Für eine Aufgabe wird eine Erfüllungsplanung von 10 Tagen festgelegt und einem Benutzer eine Auslastung von 50 % zugewiesen. Der Benutzer wird demnach für eine Dauer von 10 Tagen während der Hälfte seiner Arbeitszeit für die Aufgabenerfüllung eingesetzt.

   Sie können für jede Benutzende bzw. jeden Benutzenden einen geplanten sowie einen realen Workload eingeben. Diese Fristen dienen ebenfalls nur zu Informationszwecken.

1. Sie können eine Erinnerung über den Link **[!UICONTROL Erinnerung hinzufügen...]** konfigurieren. Vor dem Enddatum der Aufgabe wird eine E-Mail-Benachrichtigung an alle an der Aufgabe beteiligten Benutzer gesendet.

   ![](assets/task-op-add-a-reminder.png)

1. Sie können auch eine Benachrichtigung senden, bevor die Aufgabe gestartet wird. Um dies einzurichten, wählen Sie das Datum im Feld **[!UICONTROL Erstbenachrichtigung]** aus.
1. Wenn das Enddatum erreicht ist und die Aufgabe nicht geschlossen wird, kann eine Benachrichtigung an den Bevollmächtigten oder die Gruppe von Bevollmächtigten gesendet werden, die in der Dropdown-Liste **[!UICONTROL Zugewiesene Benutzer]** ausgewählt sind.


Über das Benutzer-Dashboard kann dessen Arbeitslast, d.h. seine anderen Aufgaben, eingesehen werden.

![](assets/operator-dashboard.png)

### Aufgabenvalidierung {#reviewers}

Neben den Teilnehmern können Sie auch Benutzer definieren, die die Aufgabe nach Abschluss überprüfen.

Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Aufgabenvalidierung aktivieren]** im unteren Bereich des Fensters **[!UICONTROL Ressourcen]**. Dabei kann es sich um einen einzelnen Benutzer, eine Benutzergruppe oder eine Benutzerliste handeln.

Um eine Benutzerliste zu erstellen, klicken Sie auf den Link **[!UICONTROL Bearbeiten...]** rechts von dem Feld, in dem der erste Validierungsverantwortliche angegeben wird. Fügen Sie nun so viele zusätzliche Benutzer wie nötig hinzu, wie im folgenden Beispiel:

![](assets/enable-task-approval.png)

Im unteren Bereich des Konfigurationsfensters können Sie einen Validierungsplan für die Aufgabe definieren. Standardmäßig haben Validierungsverantwortliche ab dem Unterbreitungsdatum drei Tage Zeit, um die Aufgabe zu genehmigen. Sie können auch eine Erinnerung hinzufügen, die den betroffenen Benutzern automatisch vor Ablauf der Validierungsfrist zugeschickt wird.

Die für die Aufgabe verantwortliche Person kann sich selbst die Genehmigung zuweisen, selbst wenn bereits andere Benutzende hierfür bestimmt wurden. Wenn keine für die Prüfung verantwortliche Person bestimmt wurde, werden die Benachrichtigungen an die verantwortliche Person der Aufgabe gesendet. Alle anderen Adobe Campaign-Benutzenden mit **[!UICONTROL Admin]**-Berechtigungen können die Aufgabe ebenfalls genehmigen. Sie erhalten jedoch keine Benachrichtigungen.

### Referenzierte Dokumente {#documents-referenced}

Sie können einer Aufgabe [Dokumente und Marketing-Ressourcen](managing-marketing-resources.md) hinzufügen.

Um dies durchzuführen:

1. Öffnen Sie die Aufgabe und klicken Sie in der Aufgabensymbolleiste auf das Symbol **[!UICONTROL Dokumente]**.

   ![](assets/add-documents-to-a-task.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]** und wählen Sie das Dokument aus, das Sie Ihrer Aufgabe hinzufügen möchten. Wenden Sie denselben Prozess für Marketing-Ressourcen an.


Referenzierte Dokumente werden den Benachrichtigungen hinzugefügt, die an die an der Aufgabe beteiligten Benutzer gesendet werden. Sie werden auch zum Aufgaben-Dashboard hinzugefügt.

![](assets/s_ncs_user_task_notification_documents.png)

### Planung {#execution-schedule}

Der Gültigkeitszeitraum einer Aufgabe wird in den Feldern **[!UICONTROL Start]** und **[!UICONTROL Ende]** angegeben. Die geplante Belastung drückt den Workload aus, der während des Zeitraums ausgeführt werden soll. Sie wird in Tagen oder Stunden angegeben.

>[!NOTE]
>
>Der Lebenszyklus einer Aufgabe wird im Abschnitt [Lebenszyklus](#life-cycle) beschrieben.

Im Feld **[!UICONTROL Bereits aufgewendete Zeit]** kann der Fortschritt der Arbeitslast im Vergleich zum geplanten Zeitaufwand manuell aktualisiert werden. Die Angabe erfolgt ebenfalls in Stunden oder Tagen.

![](assets/s_ncs_user_task_percentage_done_enter.png)

Der in Prozent ausgedrückte **[!UICONTROL Fortschrittsstatus]** der Aufgabe wird automatisch entsprechend den von den beteiligten Benutzenden ausgeführten Aufgaben aktualisiert. Er kann manuell eingegeben werden.

Der Fortschritt wird im Aufgaben-Dashboard angezeigt.

![](assets/s_ncs_user_task_percentage_done_from_dashboard.png)

Die gleiche Information ist auch dem Kampagnen-Dashboard zu entnehmen.

![](assets/s_ncs_user_task_percentage_done_from_op.png)

Wenn das Enddatum der Erfüllungsplanung erreicht und die Aufgabe nicht beendet ist, ist die Aufgabe **[!UICONTROL Überfällig]**. Außerdem wird eine Warnmeldung angezeigt, die die Benutzenden informiert.

Weitere Informationen hierzu finden Sie unter [Fortschritt einer Aufgabe](#progress-status-of-a-task).

### Ausgaben und Einnahmen {#expenses-and-revenues}

Für jede Aufgabe können Sie zugehörige Ausgaben und prognostizierten Umsatz definieren. Diese werden berechnet und dann in der Kampagne konsolidiert, der die Aufgabe zugeordnet ist.

Klicken Sie zur Angabe dieser Informationen auf das Symbol **[!UICONTROL Ausgaben und Einnahmen]** in der Menüleiste der Aufgabe.

![](assets/s_ncs_user_task_edit_costs.png)

Standardmäßig entspricht das belastete Budget dem Budget der Kampagne, der die Aufgabe zugeordnet ist. Es wird in den Aufgabendetails angezeigt.

>[!NOTE]
>
>Weitere Informationen zu Ausgaben und Budgets finden Sie in [diesem Abschnitt](../campaigns/providers-stocks-and-budgets.md#cost-commitment--calculation-and-charging).

In diesem Fenster können Sie auch die zu erreichenden Ziele definieren. Ziele werden in Form von prognostizierten Umsätzen für die Aufgabe ausgedrückt.

### Dienstleister {#service-providers}

Auch die Beteiligung externer Dienstleister an der Aufgabenverwaltung kann verzeichnet werden.

Öffnen Sie hierzu die Aufgabeneigenschaften und wählen Sie den entsprechenden Dienstleister aus. Die mit dem Dienstleister verbundenen Kostenkategorien werden automatisch im mittleren Abschnitt des Fensters aufgelistet.

Wählen Sie die im Zusammenhang mit der Aufgabe anfallenden Kostenkategorien aus. Geben Sie hierzu den Kostentyp an und fügen Sie gegebenenfalls einen zu belastenden Betrag hinzu.

![](assets/s_ncs_user_task_edit_simple_costs_tab.png)

>[!NOTE]
>
>Die Verwaltung und Kontrolle von Budgets und Kosten wird im Abschnitt [Kosten kontrollieren](controlling-costs.md) beschrieben.

Jeder ausgewählte Dienstleister wird im Aufgaben-Dashboard angezeigt.

![](assets/s_ncs_user_task_supplier_view.png)

### Überfällige Aufgaben {#late-tasks}

Eine Aufgabe ist überfällig, wenn sie ihr Enddatum erreicht hat, ohne dass sich ihr Status in **[!UICONTROL Abgeschlossen]** geändert hat. Standardmäßig wird niemand gewarnt, wenn eine Aufgabe überfällig ist. Sie können den Versand einer Benachrichtigungs-E-Mail konfigurieren: Alle Benutzenden können benachrichtigt werden, selbst wenn sie nicht an der Aufgabe beteiligt sind.

Wählen Sie im Bereich **[!UICONTROL Ressourcen]** die gewünschte Person im Feld **[!UICONTROL Zuweisung]** aus. Um mehrere Personen zu benachrichtigen, wählen Sie eine Benutzergruppe aus.

![](assets/mrm_task_alert_if_late.png)

### Erstbenachrichtigungen {#initial-notifications}

Wenn Sie eine Aufgabe erstellen oder verändern, deren Beginn in der Zukunft liegt, bietet Adobe Campaign die Möglichkeit, den Verantwortlichen der Aufgabe zum gegebenen Zeitpunkt per E-Mail zu informieren.

![](assets/mrm_task_first_notif.png)

Wenn die Aufgabe, die Sie erstellen, zeitlich weit entfernt liegt, kann der Versand der Benachrichtigungs-E-Mail für einen Zeitpunkt kurz vor dem Beginn der Aufgabe terminiert werden. Wenn die Aufgabe zum Beispiel erst in einem Monat beginnt, können Sie die verantwortliche Person für die Aufgabe eine Woche vor dem Beginn benachrichtigen.

Verwenden Sie zur Programmierung dieser E-Mail das Feld **[!UICONTROL Erstbenachrichtigung]** im **[!UICONTROL Ressourcen]**-Fenster.

![](assets/mrm_task_alert_before.png)

* Für Aufgaben in Kampagnen sind Datum und Uhrzeit genau festzulegen.
* Für Aufgaben in Kampagnenvorlagen wird der Benachrichtigungszeitpunkt in Form des zeitlichen Abstands vom Startdatum der Aufgabe angegeben (wenn Sie beispielsweise 2T im Feld **[!UICONTROL Erstbenachrichtigung]** eingeben, wird die E-Mail 2 Tage vor Beginn der Aufgabe gesendet).

Auch wenn eine Benachrichtigung terminiert wurde, schlägt Adobe Campaign beim Speichern der Aufgabe vor, sofort eine Benachrichtigung zu senden. Sie können sich für ein sofortiges Senden entscheiden. Die terminierte Benachrichtigung wird dadurch nicht ersetzt.

### Mit einem Programm verknüpfte Aufgabe {#task-linked-to-a-program}

Aufgaben können auch direkt in einem Programm erstellt werden, um Aktionen zu verwalten, die die globale Organisation und keine bestimmte Kampagne betreffen (beispielsweise eine Besprechung über die nächsten Kampagnen innerhalb eines Programms). Die Aufgabe wird in der Programmplanung angezeigt.

Um eine direkt mit einem Programm verknüpfte Aufgabe zu erstellen, gehen Sie wie folgt vor:

1. Öffnen Sie die Programmplanung: Wählen Sie hierzu auf der Startseite **[!UICONTROL Kampagnen > Durchsuchen > Andere Optionen > Programme]**. Die Programmplanung öffnet sich rechts im Fenster.
1. Klicken Sie im Kalender auf das gewünschte Programm. Es erscheint ein Fenster mit der Beschreibung des Programms.
1. Klicken Sie in diesem Fenster auf **[!UICONTROL Öffnen]**. Die Programmplanung wird geöffnet.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** rechts über dem Kalender und wählen Sie **[!UICONTROL Aufgabe hinzufügen]** aus.

![](assets/mrm_task_create_from_prg.png)

### Verfügbarkeit der Benutzer {#operator-availability}

Im Aufgaben-Dashboard zeigt ein Symbol neben dem Namen des Benutzers an, dass er während des von der Aufgabe abgedeckten Zeitraums bereits an einer anderen Aufgabe oder einem anderen Ereignis arbeitet. Die Aufgabe, für die der Benutzer verantwortlich ist oder an der er beteiligt ist, wird im Feld **[!UICONTROL Zugeordneter Benutzer]** oder im Feld **[!UICONTROL Ressourcen]** der Aufgabe angezeigt.

![](assets/mrm_task_alert_operator_busy.png)

### Aufgabe in einem Workflow {#task-in-a-workflow}

Die Nutzung einer **[!UICONTROL Aufgabe]** in einem Kampagnenworkflow ermöglicht zwei unterschiedliche Szenarien, abhängig davon, ob die Aufgabe validiert wurde oder nicht.

![](assets/mrm_task_in_workflow.png)

Die **[!UICONTROL Aufgabe]**-Aktivität befindet sich im Tab **[!UICONTROL Steuerung]** der Kampagnenworkflows.

## Aufgabenarten {#types-of-task}

Bei der Aufgabenerstellung über eine Kampagne können Sie spezifische Aufgaben erstellen. Der Aufgabentyp wird in der ausgewählten Vorlage definiert.

![](assets/s_ncs_user_task_select_template.png)

Folgende Arten von Aufgaben können geplant werden:

* [Kontrollaufgaben](#control-tasks),
* [Gruppierungsaufgaben](#grouping-task),
* [Gruppierungsaufgaben](#grouping-task),
* [Benachrichtigungsaufgaben](#notification-task).

>[!NOTE]
>
>**[!UICONTROL Kontrollaufgaben]** und **[!UICONTROL Gruppierungsaufgaben]** können **nur** über das Kampagnen-Dashboard erstellt werden.\
>Sie werden in der Aufgabenübersicht des ihnen zugeordneten Benutzers angezeigt. Siehe [Zugriff auf Aufgaben](#accessing-tasks).

### Kontrollaufgaben {#control-tasks}

**[!UICONTROL Kontrollaufgaben]** sind mit der Validierung eines Versands verbunden. Diese beinhaltet die Targeting-, Inhalts-, Extraktionsdatei-, Budget- und BAT-Validierung.

![](assets/s_ncs_user_task_new_control.png)

Die erstellte Aufgabe wird dem Kampagnen-Dashboard hinzugefügt.

![](assets/s_ncs_user_task_edit_from_board.png)

Von hier aus kann die Aufgabe konfiguriert und bearbeitet werden.

### Aufgaben zur Erstellung von Marketing-Ressourcen {#marketing-resource-creation-task}

Eine Aufgabe zur Erstellung von Marketing-Ressourcen kann zur Erstellung und Veröffentlichung von Marketing-Ressourcen verwendet werden. Wenn Sie eine Ressource über eine Aufgabe verwalten und nicht über die Ressource selbst, können Sie:

* den Erstellungsprozess der Ressource von einer Kampagne aus steuern;
* den Erstellungsprozess der Ressource in einem Kalender verfolgen;
* die Erstellungsplanung der Ressource verwalten (Erinnungen, Benachrichtigungen);
* die mit der Erarbeitung der Ressource verbundenen Kosten erfassen und kontrollieren;
* die Ressource über die Aufgabe validieren und veröffentlichen (sofern die entsprechende Option aktiviert ist).

#### Zusammenspiel von Aufgaben und ihnen zugeordneten Ressourcen {#interaction-between-the-task-and-its-linked-resource}

Die Aufgabe zur Erstellung von Marketing-Ressourcen interagiert mit der zugeordneten Ressource. Dies bedeutet:

* Die Erarbeitungsplanung einer Ressource und die mit ihr verbundenen Kosten werden über die Aufgabe verwaltet, der sie zugordnet ist.
* Die Benutzer können wie gewohnt mit der Ressource weiterarbeiten (sie down- und uploaden, sperren und entsperren), ohne dass sich dies auf die Aufgabe auswirkt.
* Eine Ressource kann über die Aufgabe validiert und veröffentlicht werden: Wenn die Option **[!UICONTROL Marketing-Ressource veröffentlichen]** aktiviert ist, wird die Ressource mit Abschluss der Aufgabe automatisch validiert und veröffentlicht. Wenn die Option nicht aktiviert ist, interagieren die Aufgabe und die Ressource nicht: Das Bearbeiten von einem Element hat keine Auswirkungen auf das andere.

  Sie können eine Reihe miteinander verbundener Aufgaben verwenden, um einen vollständigen Validierungszyklus festzulegen. Überprüfen Sie die Option **[!UICONTROL Marketing-Ressource veröffentlichen]** nur für die letzte Aufgabe: Alle Aufgaben müssen abgeschlossen sein, damit die Ressource veröffentlicht werden kann. Wenn Sie außerdem eine untergeordnete Marketing-Ressourcenaufgabe erstellen, wird die Ressource automatisch in der untergeordneten Aufgabe ausgewählt.

  * **Über die Ressource**: Wenn die Ressource validiert oder zur Validierung unterbreitet wird, hat dies keinerlei Auswirkung auf die Aufgabe.
  * **Über die Aufgabe**: Wenn die Option **[!UICONTROL Marketing-Ressource veröffentlichen]** für die Aufgabe aktiviert ist, wird die Ressource bei Abschluss der Aufgabe automatisch validiert und veröffentlicht (siebe oben). Wenn die Option nicht aktiviert ist, interagieren die Aufgabe und die Ressource nicht: Das Bearbeiten von einem Element hat keine Auswirkungen auf das andere.

#### Aufgabe zur Erstellung einer Marketing-Ressource konfigurieren {#configuring-a-marketing-resource-creation-task}

Die Prüfung der Aufgabe und die des Inhalts der Ressource müssen nicht durch die gleiche Person erfolgen. Wenn die Option **[!UICONTROL Marketing-Ressource veröffentlichen]** aktiviert wurde (siehe unten), ist die Prüferin bzw. der Prüfer der Aufgabe berechtigt, den Inhalt der Ressource zu validieren, da beim Abschluss der Aufgabe die Ressource automatisch validiert wird. Wenn keine Prüferin und kein Prüfer bestimmt ist, fällt die Validierung der verantwortlichen Person der Aufgabe zu.

![](assets/mrm_task_asset_creation.png)

Definieren Sie im Feld **[!UICONTROL Marketing-Ressource]** die Ressource, die Sie über diese Aufgabe verwalten möchten. Sie haben folgende Möglichkeiten:

* eine bereits existierende Ressource auszuwählen. Die Dropdown-Liste schlägt alle Ressourcen mit dem Status **[!UICONTROL In Bearbeitung]** vor.
* eine Ressource zu erstellen. Klicken Sie hierzu auf das Symbol **[!UICONTROL Verknüpftes Element auswählen]** und anschließend auf das Symbol **[!UICONTROL Erstellen]**.

Die Option **[!UICONTROL Marketing-Ressource veröffentlichen]** ermöglicht die automatische Veröffentlichung einer Ressource: Wenn die Aufgabe **[!UICONTROL Abgeschlossen]** ist, ändert sich der Status der Ressource automatisch in **[!UICONTROL Veröffentlicht]**, auch wenn diese weder validiert noch zur Validierung unterbreitet wurde. Dies gilt auch dann, wenn der Validierer der Aufgabe nicht dem Validierer des Ressourceninhalts entspricht.

Die Schaltfläche **[!UICONTROL Ressource veröffentlichen]** ist verfügbar und der Validierer für die Veröffentlichung der Ressource erhält eine Benachrichtigungs-E-Mail, die ihn darüber informiert, dass die Ressource zur Veröffentlichung bereit ist. Auf der Registerkarte **[!UICONTROL Bearbeiten > Tracking]** werden die Überprüfung und Veröffentlichung durch den Aufgabenvalidierer angezeigt. Wenn ein Nachbearbeitungs-Workflow für Ressourcen definiert wurde, wird er jetzt ausgeführt.

![](assets/mrm_resource_audit_tab.png)

### Gruppenaufgabe {#grouping-task}

**[!UICONTROL Gruppierungsaufgaben]** ermöglichen es, die Verwaltung des Fortschritts und der Validierung verschiedener Aufgaben zu synchronisieren.

Gruppierungsaufgaben haben weder Ausgaben noch mit ihnen verbundene Ressourcen.

Alle zu einer Gruppierungsaufgabe gruppierten Aufgaben können in einem eigenen Dashboard angezeigt werden. In diesem kann die Liste an Aufgaben so gefiltert werden, dass nur diejenigen angezeigt werden, die Sie interessieren.

Gruppierungsaufgaben verfügen über einen Link, der die Erstellung von enthaltenen Aufgaben erleichtert.

Um innerhalb einer Gruppierungsaufgabe direkt weitere Aufgaben zu erstellen, klicken Sie im Kampagnen-Dashboard auf die Schaltfläche **[!UICONTROL Aufgabe hinzufügen]**.

![](assets/mrm_task_grouped_create.png)

Eine bereits erstellte Aufgabe kann einer Gruppierungsaufgabe über das Feld **[!UICONTROL Gruppiert mit]** im Fenster **[!UICONTROL Eigenschaften]** der zu gruppierenden Aufgabe zugeordnet werden.

![](assets/s_ncs_user_task_group_with.png)

### Benachrichtigungsaufgaben {#notification-task}

Mit Benachrichtigungsaufgaben können Sie den Versand von E-Mails (an Benutzende, Benutzergruppen, Dienstleister usw.) planen. Auf diese Weise können Sie Erinnerungen planen, um beispielsweise jemanden zu benachrichtigen, dass eine Kampagne bald beendet wird, oder Dokumente senden, bevor eine Kampagne gestartet wird, damit die Benutzenden sie vorbereiten können. So können Sie die Kommunikation innerhalb der Kampagne oder des Programms nachverfolgen und die durchgeführten Aktionen im Auge behalten.

#### Lebenszyklus {#life-cycle}

Benachrichtigungsaufgaben erfordern keine Validierung. Ihr Lebenszyklus ist daher einfacher als der einer Standardaufgabe:

![](assets/mrm_task_notif_lifecycle.png)

Eine Benachrichtigungsaufgabe kann folgende Status haben:

* **[!UICONTROL Geplant]**, wenn die E-Mail noch nicht versandt wurde;
* **[!UICONTROL Gestartet]**, wenn die E-Mail versandt, das Enddatum jedoch noch nicht erreicht ist;
* **[!UICONTROL Abgeschlossen]**, wenn das Enddatum erreicht ist.

#### Konfiguration {#configuration}

![](assets/mrm_task_notif_dashboard.png)

Bei der Erstellung müssen folgende Elemente der Aufgabe eingegeben werden:

* **[!UICONTROL Zugewiesen an]**: Der Benutzer oder die Benutzergruppe, der/die die E-Mail erhalten wird. Wenn Sie die Aufgabe nach dem Versand der E-Mail neu zuordnen, wird die E-Mail nicht an die neu zugeordnete Benutzerin bzw. den neu zugeordneten Benutzer versandt (hierzu muss die Aufgabe neu initialisiert und ihr Startdatum geändert werden).
* **Startdatum der Aufgabe**: Datum, an dem die Benachrichtigungs-E-Mail gesendet wird. Dieses Datum muss zum Zeitpunkt der Aufgabenspeicherung in der Zukunft liegen.
* **Enddatum der Aufgabe**: Datum, an dem der Aufgabenstatus zu **[!UICONTROL Abgeschlossen]** geändert wird. Standardmäßig entspricht das Enddatum dem Startdatum. Allerdings können Sie der Aufgabe bei Bedarf eine Dauer zuweisen und so die Zeit angeben, über die die Benutzerin bzw. der Benutzer für die Ausführung innerhalb des Zeitplans verfügt.
* **[!UICONTROL Beschreibung]**: Der hier eingegebene Text erscheint im Hauptteil der Benachrichtigungs-E-Mail.

  ![](assets/mrm_task_notif_dashboard_msg.png)

Sie können der Aufgabe und der Benachrichtigungs-E-Mail einen Anhang hinzufügen. Klicken Sie hierzu auf das Symbol **[!UICONTROL Dokumente]** in der Symbolleiste in der rechten oberen Ecke.

## Lebenszyklus {#life-cycle-1}

### Relationen zwischen Aufgaben {#links-between-tasks}

Mit der Schaltfläche **[!UICONTROL Eigenschaften]** in den Aufgaben können Sie die Verknüpfungen zwischen Aufgaben in einer Kampagne definieren. Sie können Aufgaben mithilfe einer Gruppenaufgabe in Unteraufgaben aufteilen (siehe [Gruppierung von Aufgaben ](#linked-tasks)) oder Abhängigkeiten zwischen den Aufgaben definieren (siehe [Abhängigkeit von Aufgaben](#grouping-tasks)).

#### Gruppierung von Aufgaben {#linked-tasks}

Verwenden Sie das Feld **[!UICONTROL Verknüpfte Aufgabe]**, um Aufgaben einer Gruppierungsaufgabe zuzuordnen. Siehe [Aufgabenarten](#types-of-task).

Im folgenden Beispiel wird die Validierung der Zielgruppenbestimmung in vier Unteraufgaben aufgeteilt.

![](assets/s_ncs_user_task_linked_tasks.png)

Jede Unteraufgabe ist eine Standardaufgabe, die mit der Hauptaufgabe verknüpft ist.

![](assets/s_ncs_user_task_depends_on.png)

#### Gruppenaufgaben {#grouping-tasks}

Verwenden Sie das Feld **[!UICONTROL Abhängig von]**, um die Erfüllung einer Aufgabe von der einer anderen abhängig zu machen.

![](assets/s_ncs_user_task_group_with.png)

Die Abhängigkeit zwischen den Aufgaben wird mithilfe von Pfeilen im Kampagnen-Dashboard dargestellt.

![](assets/s_ncs_user_task_dependencies_from_board.png)

Bei gruppierten Aufgaben weist Adobe Campaign der untergeordneten Aufgabe automatisch das Enddatum der übergeordneten Aufgabe als Startdatum zu. Wenn beispielsweise eine Aufgabe **Einladung erstellen** am 15. Oktober um 15:30 Uhr endet, beginnt die untergeordnete Aufgabe **Einladungs-E-Mail senden** am 15. Oktober um 15:30 Uhr.

Wenn Sie darüber hinaus das Ende einer übergeordneten Aufgabe nach hinten verschieben, hat dies möglicherweise Auswirkungen auf die untergeordneten Aufgaben, und zwar auf jene mit dem Status **[!UICONTROL Geplant]**, deren Startdatum vor dem neuen Enddatum der übergeordneten Aufgabe liegt. Die Dauer der Aufgabe bleibt unverändert. Wenn das Startdatum einer untergeordneten Aufgabe nach dem neuen Enddatum der übergeordneten Aufgabe liegt, ist die untergeordnete Aufgabe nicht betroffen.

**Beispiel**

Eine übergeordnete Aufgabe, deren Ende für den 9. Oktober um 17 Uhr geplant ist, hat zwei untergeordnete Aufgaben: Aufgabe A und Aufgabe B. Der Beginn von Aufgabe A ist für den 10. Oktober um 14 Uhr, der von Aufgabe B für den 12. Oktober um 8 Uhr geplant.

Verschieben wir nun die übergeordnete Aufgabe, sodass sie am 11. Oktober um 13 Uhr endet. Dadurch wird nur der Beginn von Aufgabe A auf den 11. Oktober um 13 Uhr verschoben.

![](assets/mrm_task_parent_postpones_child.png)

### Ausführungsstatus einer Aufgabe {#execution-status-of-a-task}

Aufgabenstatus können in der Aufgabenübersicht angezeigt werden. Der Ausführungsstatus einer Aufgabe wird automatisch entsprechend den Benutzeraktionen aktualisiert.

Eine Aufgabe kann folgende Status haben: **[!UICONTROL Geplant]**, **[!UICONTROL Gestartet]**, **[!UICONTROL Abgeschlossen]**, **[!UICONTROL Abgebrochen]**, **[!UICONTROL Validierung ausstehend]** und **[!UICONTROL Abgelehnt]**.

* Wenn das Startdatum einer Aufgabe bei deren Erstellung in der Zukunft liegt, lautet ihr Status **[!UICONTROL Geplant]**. Dieser Status wird bis zum Startdatum beibehalten.
* Nach dem Start ist die Aufgabe **[!UICONTROL In Bearbeitung]**. Wenn die verantwortliche Person die Aufgabe schließt, ändert sie sich zu **[!UICONTROL Abgeschlossen]**.
* Wurde eine Prüferin oder ein Prüfer bestimmt, erhält die Aufgabe den Status **[!UICONTROL Validierung ausstehend]**, sobald sie von der verantwortlichen Person geschlossen wird und bis sie durch die Prüferin bzw. den Prüfer validiert wird. Wenn die Prüferin bzw. der Prüfer die Aufgabe ablehnt, hat sie den Status **[!UICONTROL Abgelehnt]**.
* Eine Aufgabe kann von ihrem Verantwortlichen über das Aufgaben-Dashboard oder die **[!UICONTROL Aufgabenübersicht]** durch Klick auf die Schaltfläche **[!UICONTROL Abbrechen]** abgebrochen werden.
* Um eine Aufgabe zu planen, geben Sie ein in der Zukunft liegendes Startdatum ein. Danach können Sie eine erste Benachrichtigung an die Adobe Campaign-Benutzenden senden, die an der Durchführung der Aufgabe beteiligt sind. Siehe [Vollständiger Lebenszyklus einer Aufgabe](#complete-task-life-cycle).

>[!NOTE]
>
>* Der Status der Aufgabe wird automatisch aktualisiert.
>* Aufgaben, die nicht geschlossen wurden, werden auch nach Abschluss des Gültigkeitszeitraums in der Liste der laufenden Aufgaben angezeigt. Benutzende werden durch eine Warnung darauf hingewiesen, dass die Aufgabe überfällig ist.
>

### Fortschritt einer Aufgabe {#progress-status-of-a-task}

Zusätzlich zum Ausführungsstatus weist die Aufgabe einen Fortschrittsstatus auf: **[!UICONTROL Überfällig]**, **[!UICONTROL Zu validieren]**, **[!UICONTROL Heute zu erledigen]** und **[!UICONTROL Diese Woche zu erledigen]**. Diese Informationen werden automatisch entsprechend dem Aufgabenzeitplan eingegeben.

Sie können die Liste der Aufgaben nach Erfüllungs- oder Fortschrittstatus filtern.

Weitere Informationen hierzu finden Sie unter [Zugriff auf Aufgaben ](#accessing-tasks).

### Vollständiger Lebenszyklus einer Aufgabe {#complete-task-life-cycle}

Im Folgenden werden die Etappen des vollständigen Zyklus einer Aufgabe dargestellt, für die der Verantwortliche beteiligte und validerende Benutzer festgelegt hat.

1. Die verantwortliche Person erstellt die Aufgabe und gibt die verschiedenen Felder ein. Weitere Informationen hierzu finden Sie unter [Neue Aufgabe erstellen](#creating-a-new-task).

   Bei Erstellung und Änderung einer **in der Zukunft geplanten** Aufgabe (das Startdatum der Aufgabe darf noch nicht erreicht sein) können der Verantwortliche sowie alle Beteiligten per E-Mail über die Planung einer neuen Aufgabe informiert werden.

   ![](assets/s_ncs_user_task_planed_send_message.png)

   Um diese erste Benachrichtigung zu senden, klicken Sie auf **[!UICONTROL Ja]**. Diese Benachrichtigung enthält Details über die nächste Aufgabe, ihren Inhalt sowie die Anzahl der bis zur Deadline verbleibenden Tage.

   Eine in der Zukunft geplante Aufgabe erhält bei ihrer Erstellung den Status **[!UICONTROL Geplant]**.

1. Wenn das Startdatum der Aufgabe erreicht ist, werden die verantwortliche Person und die Beteiligten mit einer E-Mail hiervon in Kenntnis gesetzt. Der Status ändert sich in **[!UICONTROL In Bearbeitung]**.
1. Wenn ein Beteiligter seinen Teil der Aufgabe abgeschlossen hat, kann er die Aufgabe auf zweierlei Weisen erfüllen:

   * über die Benachrichtigungs-E-Mail;
   * im Dashboard der Aufgabe über die Client-Konsole oder die Web-Schnittstelle.

     ![](assets/s_ncs_user_task_start_rea.png)

1. Nach jeder neuen Validierung wird der Fortschritt der Aufgabe automatisch aktualisiert.

   ![](assets/s_ncs_user_task_percentage_done_op.png)

1. Der validierende Benutzer wird jedes Mal per E-Mail benachrichtigt, wenn ein Benutzer einen dem validierenden Benutzer zugewiesenen Abschnitt fertigstellt.

   Er kann den Fortschritt der Aufgabe im Aufgaben-Dashboard verfolgen.

   ![](assets/s_ncs_user_task_follow_from_dashboard.png)

1. Wenn der Verantwortliche die Aufgabe als abgeschlossen erachtet, kann er sie entweder über die Benachrichtigungs-E-Mail, die er zu Beginn der Aufgabe erhalten hat, über die Client-Konsole oder über die Web-Schnittstelle schließen.

   ![](assets/s_ncs_user_task_console_ressource_validation.png)

   >[!NOTE]
   >
   >Die verantwortliche Person kann die Aufgabe jederzeit schließen, auch wenn noch Validierungen fehlen. Der Fortschrittsstatus ändert sich automatisch in 100 %.

1. Die Aufgabe erhält damit den Status **[!UICONTROL Zu validieren]** und der Validierer wird benachrichtigt.

   Sie genehmigen die Aufgabe über die Benachrichtigungs-E-Mail, die Client-Konsole oder die Web-Schnittstelle.

   Er kann das Kampagnen-Dashboard zur Validierung nutzen:

   ![](assets/s_ncs_user_task_console_validation.png)

   Er kann die Aufgabe auch direkt über deren Validierungsschaltfläche validieren:

   ![](assets/s_ncs_user_task__validation.png)

   >[!NOTE]
   >
   >Die Aufgabe erhält den Status **[!UICONTROL Zu validieren]** nur, wenn die Option **[!UICONTROL Aufgabenvalidierung aktivieren]** im **[!UICONTROL Ressourcen]**-Fenster der Aufgabe aktiviert wurde.\
   >Wenn der Validierer die Aufgabe ablehnt, wird ihr Status zu **[!UICONTROL Abgelehnt]** und der Aufgabenzyklus beginnt automatisch von vorn.

1. Der Aufgabenstatus ändert sich in **[!UICONTROL Abgeschlossen]**. Alle beteiligten Personen erhalten eine Benachrichtigung.

   >[!NOTE]
   >
   >Nach Abschluss einer Aufgabe kann ihr Lebenszyklus von der verantwortlichen Person neu initialisiert werden. Öffnen Sie hierzu die Aufgabe und klicken Sie auf den Link **[!UICONTROL Aufgabe zurücksetzen, um sie erneut auszuführen…]** unten im Dashboard.

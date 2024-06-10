---
product: campaign
title: Audit-Protokoll
description: Erfahren Sie, wie Sie Ihre Instanz mit dem Audit-Protokoll von Campaign überwachen.
feature: Audit Trail, Monitoring, Workflows
exl-id: 6a937575-42d4-4dc5-8168-43c25bb2cde6
source-git-commit: b4b361a4aabd1b33554166c2638989b99a02baec
workflow-type: ht
source-wordcount: '650'
ht-degree: 100%

---

# Audit-Protokoll{#audit-trail}

Die Funktion **[!UICONTROL Audit-Protokoll]** in Adobe Campaign bietet eine detaillierte Aufzeichnung aller Änderungen, die an wichtigen Entitäten in Ihrer Instanz vorgenommen wurden. Dies sind typischerweise Änderungen, die den reibungslosen Betrieb der Instanz wesentlich beeinflussen. Es dient als Echtzeit-Protokoll und erfasst eine detaillierte Liste von Aktionen und Ereignissen, sobald sie auftreten.

>[!NOTE]
>
>Adobe Campaign prüft keine Änderungen an Benutzerrechten, Vorlagen, Personalisierungen oder Kampagnen.\
>Das Audit-Protokoll kann nur von Admins der Instanz verwaltet werden.

+++ Weitere Informationen über die verfügbaren Entitäten im Audit-Protokoll

* **Schema-Audit-Protokoll**: ermöglicht es Ihnen, die Änderungen an Ihren Schemata zu untersuchen und zu identifizieren, wer diese Änderungen vorgenommen hat und wann sie vorgenommen wurden.

  Detaillierte Informationen zu Schemata finden Sie auf [Seite](../dev/schemas.md).

* Das **Workflow-Audit-Protokoll** verfolgt alle Aktionen im Zusammenhang mit Ihren Workflows, einschließlich:

   * Starten
   * Aussetzen
   * Stoppen
   * Neu starten
   * Bereinigen, was der Aktion „Verlauf bereinigen“ entspricht
   * Simulieren, was der Aktion „Starten“ im Simulationsmodus entspricht
   * Wecken, was der Aktion „Vorgezogene Ausführung der ausstehenden Aufgaben“ entspricht
   * Unbedingter Stopp

  Weiterführende Informationen zu Workflows finden Sie auf [dieser Seite](../../automation/workflow/about-workflows.md).

  Weiterführende Informationen zur Überwachung Workflows finden Sie im [entsprechenden Abschnitt](../../automation/workflow/monitor-workflow-execution.md).

* Das **Audit-Protokoll für Optionen** ermöglicht Ihnen die Überprüfung der Aktivitäten und der letzten Änderungen an Ihren Optionen.

  Weiterführende Informationen zu Optionen finden Sie auf [dieser Seite](https://experienceleague.adobe.com/de/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* Das **Audit-Protokoll für den Versand** ermöglicht Ihnen die Überprüfung der Aktivitäten und der letzten Änderungen an Ihren Sendungen.

  Weiterführende Informationen zu Sendungen finden Sie auf [dieser Seite](../start/create-message.md).

* **Externes Konto** ermöglicht Ihnen die Überprüfung von Änderungen an externen Konten, die von technischen Prozessen wie technischen Workflows oder Kampagnen-Workflows verwendet werden.

  Weiterführende Informationen zu „Externes Konto“ finden Sie auf [dieser Seite](../config/external-accounts.md).

* **Versand-Mapping** ermöglicht es Ihnen, Aktivitäten und kürzlich an Ihren Versand-Mappings vorgenommene Änderungen zu überwachen.

  Weiterführende Informationen zu „Versand-Mapping“ finden Sie auf [dieser Seite](../audiences/target-mappings.md).

* **Web-Anwendung** ermöglicht Ihnen das Überprüfen von Änderungen an Web-Formularen in Campaign V8, die zum Erstellen von Seiten mit Eingabe- und Auswahlfeldern verwendet werden und die Daten aus der Datenbank enthalten können.

  Weiterführende Informationen zu „Web-Anwendung“ finden Sie auf [dieser Seite](../dev/webapps.md).

* **Angebot** ermöglicht es Ihnen, die Aktivitäten und letzten Änderungen an Ihren Angeboten zu überprüfen.

  Weiterführende Informationen zu „Angebot“ finden Sie auf [dieser Seite](../interaction/interaction.md).

* **Operator** ermöglicht es Ihnen, Aktivitäten und Änderungen zu überwachen, die vor Kurzem an Ihren Operatoren vorgenommen wurden.

  Weiterführende Informationen zu Benutzerinnen und Benutzern finden Sie auf [dieser Seite](../interaction/interaction-operators.md).

+++

## Zugriff auf das Audit-Protokoll {#accessing-audit-trail}

So greifen auf das **[!UICONTROL Audit-Protokoll]** Ihrer Instanz zu:

1. Greifen Sie auf das Menü **[!UICONTROL Explorer]** Ihrer Instanz zu.

1. Wählen Sie unter dem Menü **[!UICONTROL Administration]** die Option **[!UICONTROL Audit]** und dann **[!UICONTROL Audit-Protokoll]** aus.

   ![](assets/audit-trail-1.png)

1. Das Fenster **[!UICONTROL Audit-Protokoll]** wird mit der Liste Ihrer Entitäten geöffnet. Adobe Campaign prüft die Aktionen zum Erstellen, Bearbeiten und Löschen für Ihre unterschiedlichen Entitäten.

   Wählen Sie eine der Entitäten aus, um mehr über die letzten Änderungen zu erfahren.

1. Im Fenster **[!UICONTROL Audit-Entität]** erhalten Sie detailliertere Informationen zu der ausgewählten Entität, z. B.:

   * **[!UICONTROL Typ]**: Workflow, Optionen, Sendungen oder Schemata.
   * **[!UICONTROL Entität]**: Interner Name Ihrer Aktivitäten.
   * **[!UICONTROL Geändert von]**: Benutzername der Person, die diese Entität zuletzt geändert hat.
   * **[!UICONTROL Aktion]**: Letzte Aktion, die für diese Entität ausgeführt wurde, entweder „Erstellt“, „Geändert“ oder „Gelöscht“.
   * **[!UICONTROL Änderungsdatum]**: Datum der letzten Aktion, die an dieser Entität durchgeführt wurde.

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>Die Aufbewahrungsfrist für **[!UICONTROL Auditlogs]** ist standardmäßig auf 180 Tage festgelegt. Dieser Wert kann im Bereitstellungsassistenten geändert werden.

## Aktivieren/Deaktivieren des Audit-Protokolls {#enable-disable-audit-trail}

Das Audit-Protokoll kann für eine bestimmte Aktivität einfach aktiviert oder deaktiviert werden, beispielsweise wenn Sie Speicherplatz in der Datenbank sparen möchten.

Gehen Sie dabei folgendermaßen vor:

1. Greifen Sie auf das Menü **[!UICONTROL Explorer]** Ihrer Instanz zu.

1. Wählen Sie unter dem Menü **[!UICONTROL Administration]** die Option **[!UICONTROL Plattform]** und dann **[!UICONTROL Optionen]** aus.

1. Wählen Sie je nach zu aktivierender/deaktivierender Entität eine der folgenden Optionen aus:

   * Für Workflow: **[!UICONTROL XtkAudit_Workflows]**
   * Für Schemata: **[!UICONTROL XtkAudit_DataSchema]**
   * Für Optionen: **[!UICONTROL XtkAudit_Option]**
   * Für Sendungen: **[!UICONTROL XtkAudit_Delivery]**
   * Für externes Konto: **[!UICONTROL XtkAudit_ExtAccount]**
   * Für Versand-Mapping: **[!UICONTROL XtkAudit_DeliveryMapping]**
   * Für Web-Anwendung: **[!UICONTROL XtkAudit_WebApp]**
   * Für Angebot: **[!UICONTROL XtkAudit_Offer]**
   * Für Operator: **[!UICONTROL XtkAudit_Operator]**
   * Für jede Entität: **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. Ändern Sie den **[!UICONTROL Wert]** in „1“, wenn Sie die Entität aktivieren möchten, oder in „0“, wenn Sie sie deaktivieren möchten.

   ![](assets/audit-trail-4.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

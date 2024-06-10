---
product: campaign
title: Verwalten von Workflow-Berechtigungen
description: Erfahren Sie, wie Sie Workflow-Berechtigungen verwalten.
feature: Workflows, Permissions
role: Admin
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: ht
source-wordcount: '336'
ht-degree: 100%

---

# Verwalten von Workflow-Berechtigungen{#managing-rights}



Adobe-Campaign-Benutzer, die nicht über Administratorrechte verfügen, müssen die entsprechenden Rechte eingeräumt werden, um Workflows erstellen, ausführen und ändern zu können.

Benutzer, die mit Workflows arbeiten, müssen Zugriff haben auf die Ordner und Unterordner, die die in den verschiedenen Aktivitäten verwendeten Daten enthalten (Empfänger, Empfängerlisten, Abonnements, Sendungen etc.).

Des Weiteren müssen Sie über die spezifischen Berechtigungen verfügen, die den von den Workflows ausgeführten Aktionen entsprechen (Import von Empfängern, Zugriff auf Dateien, Fusion, Ausführung von SQL-Scripts etc.).

Die Verwaltung der Benutzenden sowie ihrer Berechtigungen wird in [diesem Abschnitt](../../v8/start/gs-permissions.md) erläutert.

## Benutzergruppen {#operator-groups-wf}

Folgende Benutzergruppen sind im Zusammenhang mit Workflows von Bedeutung:

* Die Gruppe **[!UICONTROL Workflow-Ausführung]** ermöglicht es, die Ausführung und Genehmigung von Zielgruppen-Workflows zu steuern. Die spezifische Berechtigung WORKFLOW wird den Benutzenden dieser Gruppe zugeordnet. Sie ist für alle Aktionen in Workflows erforderlich, zusätzlich zu den Zugriffsrechten auf die Datendateien. Standardmäßig hat die Gruppe **[!UICONTROL Workflow-Ausführung]** schreibgeschützten Zugriff auf standardmäßige Zielgruppen-Workflow-Dateien und Workflow-Vorlagen. Benutzende in dieser Gruppe haben auch Lese- und Schreibzugriff auf die Datei der ausstehenden Validierungen.
* Die Gruppe **[!UICONTROL Workflow-Verantwortliche]** ermöglicht den Benutzern die Verwaltung der Workflow-Validierungen.
* Die Benutzer der Gruppe **[!UICONTROL Kampagnenverantwortliche Benutzer]** haben Zugriff auf Kampagnen-Workflows.

## Spezifische Berechtigungen {#named-rights}

Nur die spezifische Berechtigung WORKFLOW bezieht sich auf Workflows: Sie ermöglicht die Erstellung, den Start und das Anhalten von Workflows. Leserechte für die Workflow-Datei sind erforderlich, damit die spezifische Berechtigung angewendet werden kann. Für Zielgruppen-Workflows ist außerdem der Lesezugriff auf den Ordner **[!UICONTROL Profile und Zielgruppen]** erforderlich.

## Workflow-Ausführungskonto {#workflow-execution-account}

Das Ausführungskonto eines Workflows wird auf Niveau der Vorlage definiert. Das Ausführungskonto ermöglicht die direkte Zuordnung der Rechte zum Workflow, unabhängig vom Adobe-Campaign-Benutzer, der die Ausführung startet. Standardmäßig wird jeder Workflow mit den Rechten des Benutzers ausgeführt, der ihn gestartet hat.

Gehen Sie zur Zuordnung eines Ausführungskontos zu einem Workflow in die Liste der Workflow-Vorlagen und klicken Sie mit der rechten Maustaste auf die dem Workflow entsprechende Vorlage. Verwenden Sie die Option **[!UICONTROL Aktionen > Ausführungskonto ändern...]** und wählen Sie das zu verwendende Konto aus.

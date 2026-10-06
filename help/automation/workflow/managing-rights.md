---
product: campaign
title: Verwalten von Workflow-Berechtigungen
description: Erfahren Sie, wie Sie Workflow-Berechtigungen verwalten.
feature: Workflows, Permissions
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
TQID: 'https://experienceleague.adobe.com/xZwqhzyDbDM309Q-WNpYoD-BvWiJmaTVHsmf50ywAJk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 100%
---
# Verwalten von Workflow-Berechtigungen{#managing-rights}



Adobe Campaign-Benutzer, die nicht über Administratorrechte verfügen, müssen die entsprechenden Rechte eingeräumt werden, um Workflows erstellen, ausführen und ändern zu können.

Benutzer, die mit Workflows arbeiten, müssen Zugriff haben auf die Ordner und Unterordner, die die in den verschiedenen Aktivitäten verwendeten Daten enthalten (Empfänger, Empfängerlisten, Abonnements, Sendungen etc.).

Des Weiteren müssen Sie über die spezifischen Berechtigungen verfügen, die den von den Workflows ausgeführten Aktionen entsprechen (Import von Empfängern, Zugriff auf Dateien, Fusion, Ausführung von SQL-Scripts etc.).

Die Verwaltung der Benutzenden sowie ihrer Berechtigungen wird in [diesem Abschnitt](../../v8/start/gs-permissions.md) erläutert.

## Benutzergruppen {#operator-groups-wf}

Folgende Benutzergruppen sind im Zusammenhang mit Workflows von Bedeutung:

* Die Gruppe **[!UICONTROL Workflow-Ausführung]** ermöglicht es, die Ausführung und Validierung von Zielgruppenbestimmungs-Workflows zu steuern. Die Berechtigung WORKFLOW wird den Benutzenden dieser Gruppe zugeordnet. Sie ist für alle Aktionen in Workflows erforderlich, zusätzlich zu den Zugriffsrechten auf die Datendateien. Standardmäßig hat die Gruppe **[!UICONTROL Workflow-Ausführung]** schreibgeschützten Zugriff auf standardmäßige Zielgruppen-Workflow-Dateien und Workflow-Vorlagen. Benutzende in dieser Gruppe haben auch Lese- und Schreibzugriff auf die Datei der ausstehenden Validierungen.
* Die Gruppe **[!UICONTROL Workflow-Verantwortliche]** ermöglicht den Benutzern die Verwaltung der Workflow-Validierungen.
* Die Benutzer der Gruppe **[!UICONTROL Kampagnenverantwortliche Benutzer]** haben Zugriff auf Kampagnen-Workflows.

## Spezifische Berechtigungen {#named-rights}

Nur die spezifische Berechtigung WORKFLOW gilt speziell für Workflows: Damit können Sie Workflows erstellen, starten und stoppen. Leserechte für die Workflow-Datei sind erforderlich, damit die spezifische Berechtigung angewendet werden kann. Für Zielgruppen-Workflows ist außerdem der Lesezugriff auf den Ordner **[!UICONTROL Profile und Zielgruppen]** erforderlich.

## Workflow-Ausführungskonto {#workflow-execution-account}

Sie können das Ausführungskonto konfigurieren, das auf Workflow-Vorlagenebene verwendet werden soll. Das Ausführungskonto ermöglicht die direkte Zuordnung der Berechtigungen zum Workflow, unabhängig von den Adobe Campaign-Benutzenden, die die Ausführung starten. Standardmäßig werden alle Workflows mit den Berechtigungen der benutzenden Person ausgeführt, der sie gestartet hat.

Gehen Sie zur Zuordnung eines Ausführungskontos zu einem Workflow in die Liste der Workflow-Vorlagen und klicken Sie mit der rechten Maustaste auf die dem Workflow entsprechende Vorlage. Verwenden Sie die Option **[!UICONTROL Aktionen > Ausführungskonto ändern...]** und wählen Sie das zu verwendende Konto aus.

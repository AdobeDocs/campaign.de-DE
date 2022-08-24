---
product: campaign
title: Verwalten von Workflow-Berechtigungen
description: Erfahren Sie, wie Sie Workflow-Berechtigungen verwalten.
feature: Workflows
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Verwalten von Workflow-Berechtigungen{#managing-rights}



Adobe-Campaign-Benutzer, die nicht über Administratorrechte verfügen, müssen die entsprechenden Rechte eingeräumt werden, um Workflows erstellen, ausführen und ändern zu können.

Benutzer, die mit Workflows arbeiten, müssen Zugriff haben auf die Ordner und Unterordner, die die in den verschiedenen Aktivitäten verwendeten Daten enthalten (Empfänger, Empfängerlisten, Abonnements, Sendungen etc.).

Des Weiteren müssen Sie über die spezifischen Berechtigungen verfügen, die den von den Workflows ausgeführten Aktionen entsprechen (Import von Empfängern, Zugriff auf Dateien, Fusion, Ausführung von SQL-Scripts etc.).

Weitere Informationen zur Verwaltung von Benutzern und Berechtigungen finden Sie in diesem Dokument.

## Benutzergruppen {#operator-groups-wf}

Folgende Benutzergruppen sind im Zusammenhang mit Workflows von Bedeutung:

* Die Gruppe **[!UICONTROL Workflow-Ausführung]** dient der Ausführungs- und Validierungskontrolle von Zielgruppen-Workflows. Die Benutzer dieser Gruppe verfügen automatisch über die spezifische Berechtigung WORKFLOW. Diese ist neben den Datenzugriffsrechten Vorraussetzung für alle Workflow-bezogenen Aktionen. Die Gruppe **[!UICONTROL Workflow-Ausführung]** verfügt standardmäßig über Lesezugriff auf die Standard-Ordner der Zielgruppen-Workflows und der Workflow-Vorlagen. Die Benutzer dieser Gruppen haben des Weiteren Lese- und Schreibzugriff auf den Ordner der ausstehenden Validierungen.
* Die Gruppe **[!UICONTROL Workflow-Supervisoren]** ermöglicht den Benutzern die Verwaltung der Workflow-Validierungen.
* Die Benutzer der Gruppe **[!UICONTROL Kampagnenverantwortliche Benutzer]** haben Zugriff auf Kampagnen-Workflows.

## Spezifische Berechtigungen {#named-rights}

Nur die spezifische Berechtigung WORKFLOW bezieht sich ausschließlich auf die Bearbeitung von Workflows. Sie berechtigt zu Erstellung, Start und Stopp von Workflows. Voraussetzung ist, dass die entsprechenden Benutzer mindestens über einen Lesezugriff auf den Workflow-Ordner verfügen. Für Zielgruppen-Workflows ist außerdem der Lesezugriff auf den Ordner **[!UICONTROL Profile und Zielgruppen]** erforderlich.

## Workflow-Ausführungskonto {#workflow-execution-account}

Das Ausführungskonto eines Workflows wird auf Niveau der Vorlage definiert. Das Ausführungskonto ermöglicht die direkte Zuordnung der Rechte zum Workflow, unabhängig vom Adobe-Campaign-Benutzer, der die Ausführung startet. Standardmäßig wird jeder Workflow mit den Rechten des Benutzers ausgeführt, der ihn gestartet hat.

Gehen Sie wie folgt vor, um einem Workflow ein Ausführungskonto zuzuordnen: Gehen Sie in die Liste der Workflow-Vorlagen und klicken Sie mit der rechten Maustaste auf die dem Workflow entsprechende Vorlage. Verwenden Sie die Option **[!UICONTROL Aktionen > Ausführungskonto ändern...]** und wählen Sie das zu verwendende Konto aus.

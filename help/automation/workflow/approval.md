---
product: campaign
title: Validierung
description: Validierung
feature: Workflows, Approvals
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9e57d21c-ce16-448d-97f1-8c6844acb37b
TQID: 'https://experienceleague.adobe.com/wmqV-ZCTwYaGQHTxIZ3iZpv9cTR4TrGDtXuV-YfF1Io'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ce296ecd-3d06-45ab-83c3-37214e8ce31c
    internal-label: Approvals
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 100%
---
# Validierung{#approval}



Eine Aufgabe des Typs **Validierung** erfordert die Beteiligung einer Benutzerin bzw. eines Benutzers. Der Benutzerin bzw. dem Benutzer wird eine Aufgabe zugewiesen, auf die per E-Mail, über die in der E-Mail-Nachricht verknüpfte Web-Seite oder über die Konsole reagiert werden kann.

## Aufgabenzuweisung {#task-assignment}

Standardmäßig wird die Validierung einer Benutzergruppe zugewiesen. Diese Gruppe repräsentiert eine Rolle, z. B. „Gruppe für Newsletter-Inhalte“ oder „Zielgruppenbestimmungsgruppe für Newsletter“. Alle Benutzenden in der Gruppe können antworten, es wird jedoch nur die erste Antwort berücksichtigt (außer eine mehrfache Validierung ist erforderlich).

Bei Bedarf kann die Validierung auch einem einzelnen oder durch die Verwendung von Filtern mehreren Benutzern zugewiesen werden.

* Zur Auswahl eines einzelnen Benutzers ist im Feld **[!UICONTROL Zuweisungstyp]** die Option **[!UICONTROL Benutzer]** zu wählen. Wählen Sie dann aus der Dropdown-Liste des Felds **[!UICONTROL Zuweisung]** den gewünschten Benutzer aus.

  ![](assets/s_advuser_validation_box_assign.png)

  >[!CAUTION]
  >
  >Nur der ausgewählte Benutzer verfügt über die Berechtigung zur Validierung der Aufgabe.

* Es besteht die Möglichkeit, eine Abfrage zu erstellen, um die für die Validierung verantwortlichen Benutzenden zu filtern. Wählen Sie hierzu im Feld **[!UICONTROL Zuweisungstyp]** die Option **[!UICONTROL Filter]** aus und klicken Sie auf den Link **[!UICONTROL Erweiterte Parameter…]**, um die Filterkriterien zu definieren, wie im unten stehendem Beispiel dargestellt:

  ![](assets/s_advuser_validation_box_filter.png)

Im Fall einer einfachen Validierung, wird die der Wahl des Benutzers entsprechende Transition aktiviert und die Aufgabe abgeschlossen. Andere Benutzer können nun die Aufgabe nicht mehr validieren.

Im Fall einer mehrfachen Validierung werden Transitionen entsprechend der Auswahl jeder Benutzerin bzw. jedes Benutzers aktiviert. Die Aufgabe wird abgeschlossen, sobald alle Benutzenden der Gruppe reagiert haben, oder wenn die Aufgabe abgelaufen ist.

Diese Aktivität betrifft nicht den gesamten Workflow, andere Aufgaben können parallel ausgeführt werden.

Eine Benutzerin bzw. ein Benutzer kann die ihr bzw. ihm zugewiesenen Aufgaben über die Client-Konsole genehmigen. Benutzer bzw. Benutzerinnen mit Administratorrechten können die Aufgaben, die einem Benutzer bzw. einer Benutzerin zugewiesen sind, anzeigen und löschen, aber nicht darauf antworten.

Änderungen in Bezug auf die Titel oder den Nachrichten-Textkörper der Aktivität haben keinen Einfluss auf laufende Aufgaben. Sollten jedoch die möglichen Antworten geändert werden, werden die neuen Optionen automatisch in den laufenden Aufgaben übernommen.

Auf **Validierungsaufgaben** kann im Knoten **[!UICONTROL Administration > Betreibung > Automatisch erstellte Objekte > Ausstehende Validierungen]** zugegriffen werden. Aus dieser Ansicht heraus gelangen die Benutzer direkt in die verschiedenen Validierungsformulare.

![](assets/s_advuser_validation_from_console.png)

## Eigenschaften {#properties}

In der an die prüfenden Personen gesendeten Nachricht können Personalisierungsvariablen verwendet werden. Diese können entweder in den Nachrichtentitel oder den Textkörper eingefügt werden.

![](assets/edit_validation.png)

Das Feld **[!UICONTROL Titel]** enthält den Titel der Nachricht und stellt den Betreff der gesendeten E-Mail-Nachricht dar. Sowohl beim Titel als auch beim Nachrichtentext handelt es sich um JavaScript-Vorlagen. Daher können sie Werte enthalten, die entsprechend dem Kontext des Workflows berechnet wurden.

Im unteren Bereich des Editors können Sie die Liste der möglichen Antworten definieren. Zu jeder Antwort gehört eine Transition. Der Name ist die interne Kennung und der Titel ist der Text, der in der Auswahlliste angezeigt wird.

Klicken Sie auf den Link **[!UICONTROL Erweiterte Parameter…]**, um die Versandvorlage für die Benachrichtigung der Benutzenden auszuwählen. Die Standardvorlage (interner Name „notifyAssignee“) übernimmt den Titel und den Nachrichteninhalt und fügt einen Link zur Web-Seite hinzu, über die geantwortet werden kann.

Diese Vorlage kann angepasst werden, um das Nachrichten-Layout zu personalisieren, es wird jedoch empfohlen, sie zu kopieren. Der Zielgruppenbestimmungsmechanismus (externe Datei, Zielgruppen-Mapping) darf nicht geändert werden, da er für die ordnungsgemäße Funktionsweise von Benachrichtigungen erforderlich ist.

Ein Validierungsbeispiel finden Sie im Abschnitt [Validierungen definieren](define-approvals.md).

## Ausgabeparameter {#output-parameters}

* **[!UICONTROL response]**

  Kommentar zur Antwort

* **[!UICONTROL responseOperator]**

  Kennung der Person, die geantwortet hat. Dieses Feld ist ein numerischer Wert, aber ein Feld mit einer **[!UICONTROL Zeichenfolge]**.

---
product: campaign
title: Lokale Validierung
description: Lokale Validierung
feature: Workflows, Approvals
role: User
exl-id: 172b6827-ddfc-4c6e-87c9-eb49e73ab3ab
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 100%

---

# Lokale Validierung{#local-approval}

Im Rahmen eines Zielgruppen-Workflows ermöglicht die Aktivität **[!UICONTROL Lokale Validierung]** die Formalisierung eines Validierungsprozesses, der die Überprüfung der ausgewählten Empfänger vor Absendung der Kampagne sicherstellt.

![](assets/local_validation_0.png)

>[!CAUTION]
>
>Zur Verwendung dieser Funktion benötigen Sie das Modul Distributed Marketing (Campaign-Option). Bitte prüfen Sie Ihren Lizenzvertrag.

Ein Beispiel für die Aktivität **[!UICONTROL Lokale Validierung]** mit einer Verteilungsvorlage finden Sie unter [Lokale Validierung verwenden](local-approval-activity.md).

Benennen Sie zunächst die Aktivität und kreuzen Sie die **[!UICONTROL Auszuführende Aktion]** an:

![](assets/local_validation_1.png)

* Wählen Sie die Option **[!UICONTROL Benachrichtigung zur Zielgruppenvalidierung]**, um die Verantwortlichen der Lokalstellen zur Validierung ihrer jeweiligen Empfängerliste aufzufordern.

* **Inkrementelle Abfrage**: erlaubt es, eine Abfrage auszuführen und deren Ausführung zu planen. Siehe Abschnitt [Inkrementelle Abfrage](incremental-query.md).

  ![](assets/local_validation_intro_3.png)

## Benachrichtigung zur Zielgruppenvalidierung {#target-approval-notification}

Bei Verwendung dieser Option ist die Aktivität **[!UICONTROL Lokale Validierung]** im Anschluss an die Zielgruppenbestimmung und vor der Versandaktivität zu platzieren:

![](assets/local_validation_2.png)

In diesem Fall sind folgende Felder zu konfigurieren:

![](assets/local_validation_3.png)

* **[!UICONTROL Verteilungskontext]**: Wählen Sie die Option **[!UICONTROL In der Transition angegeben]**, wenn Sie eine Aktivität vom Typ **[!UICONTROL Aufspaltung]** zur Begrenzung der Zielpopulation verwenden. In diesem Fall wird die Verteilungsvorlage in die Aufspaltungsaktivität eingegeben. Wenn Sie die Zielpopulation nicht begrenzt möchten, wählen Sie die Option **[!UICONTROL Explizit]** aus und geben Sie im Feld **[!UICONTROL Datenverteilung]** die Verteilungsvorlage an.

  Weitere Informationen zum Erstellen einer Datenverteilungsvorlage finden Sie unter [Anzahl an Datensätzen in Teilmengen durch Datenverteilung begrenzen](split.md#limiting-the-number-of-subset-records-per-data-distribution).

* **[!UICONTROL Validierungsverwaltung:]**

   * Wählen Sie die Versandvorlage und den Betreff für die E-Mail-Benachrichtigung aus. Eine Standardvorlage ist verfügbar: **[!UICONTROL Benachrichtigung bezüglich lokaler Validierungen]**. Sie können auch eine Beschreibung hinzufügen, die oberhalb der Empfängerlisten in den Validierungs- und Feedback-Benachrichtigungen erscheint.
   * Geben Sie den **[!UICONTROL Validierungstyp]** an, d. h. die Validierungsdeadline (Datum oder Abstand vom Unterbreitungsdatum). Zum angegebenen Zeitpunkt wird die Ausführung des Workflows fortgesetzt. Nicht validierte Empfänger werden von der Zielgruppe ausgeschlossen. Nach Absendung der Benachrichtigungen wechselt die Aktivität in den Wartezustand bis die Lokalstellen-Verantwortlichen die Empfänger validiert haben oder der Validierungszeitraum abgelaufen ist.

     >[!NOTE]
     >
     >Wenn nicht anders angegeben, wartet die Aktivität drei Tage.

     Sie können auch eine oder mehrere Erinnerungen hinzufügen, um die lokalen Validierungsverantwortlichen vor Ablauf der Frist zu erinnern. Klicken Sie dazu auf den Link **[!UICONTROL Erinnerung hinzufügen]**.

* **[!UICONTROL Komplement]**: Kreuzen Sie die Option **[!UICONTROL Komplement erzeugen]** an, um eine zweite Ergebnismenge mit allen nicht validierten Empfängern zu erzeugen.

  >[!NOTE]
  >
  >Standardmäßig ist diese Option deaktiviert.

## Versandreaktionen-Bericht {#delivery-feedback-report}

In diesem Fall wird die **[!UICONTROL Lokale Validierung]** im Anschluss an die Versandaktion platziert:

![](assets/local_validation_4.png)

Folgende Angaben sind erforderlich:

![](assets/local_validation_workflow_4.png)

* Wählen Sie die Option **[!UICONTROL In der Transition angegeben]** aus, wenn der Versand in einer vorangehenden Aktivität eingegeben wurde. Wählen Sie **[!UICONTROL Explizit]** aus, um den Versand in der lokalen Validierungsaktivität anzugeben.
* Wählen Sie die Versandvorlage und den Betreff der Benachrichtigungs-E-Mail aus. Es gibt eine Standardvorlage: **[!UICONTROL Benachrichtigung bezüglich lokaler Validierungen]**.

## Beispiel: Workflow-Versand validieren {#example--approving-a-workflow-delivery}

Dieses Beispiel zeigt, wie Sie einen Validierungsprozess für einen Workflow-Versand einrichten. Weitere Informationen zum Erstellen von Versand-Workflows finden Sie im Abschnitt [Beispiel: Versand-Workflow](delivery.md#example--delivery-workflow).

Der Benutzerin bzw. dem Benutzer bieten sich zwei verschiedene Möglichkeiten, um einen Versand zu genehmigen: entweder über die in der E-Mail-Nachricht verlinkte Web-Seite oder über die Client-Konsole.

* Validierung über Webzugriff

  Die an die zuvor gewählte Benutzergruppe gesandte Benachrichtigung ermöglicht die Validierung der Versandzielgruppe. Die Benachrichtigung enthält den in der Vorlage definierten Text, wobei der JavaScript-Ausdruck durch den berechneten Wert (hier &#39;574&#39;) ersetzt wird.

  Um den Versand zu genehmigen, klicken Sie auf den entsprechenden Link und melden sich bei der Client-Konsole von Adobe Campaign an.

  ![](assets/new-workflow-valid-webaccess.png)

  Kreuzen Sie die gewünschte Antwort an und klicken Sie auf **[!UICONTROL Absenden]**.

  ![](assets/new-workflow-valid-webaccess-confirm.png)

* Genehmigung über die Client-Konsole

  Im Navigationsbaum enthält der Knoten **[!UICONTROL Administration > Betreibung > Automatisch erstellte Objekte > Ausstehende Validierungen]** die Liste der vom aktuellen Benutzer zu validierenden Aufgaben. Doppelklicken Sie auf die entsprechende Zeile, um die Validierung vorzunehmen.

![](assets/new-workflow-7.png)

**** Kreuzen Sie die gewünschte Antwort an und klicken Sie auf **[!UICONTROL Validieren]**. Ein Pop-up bestätigt Ihnen, dass die Antwort gespeichert wurde.

Wenn Sie nach einigen Sekunden zum Workflow-Diagramm zurückkehren, stellt es sich wie folgt dar:

![](assets/new-workflow-8.png)

Der Workflow hat die Aufgabe **[!UICONTROL Versand bearbeiten]** ausgeführt, d. h. der zuvor erstellte Versand wurde gestartet, und der Workflow wurde erfolgreich abgeschlossen.

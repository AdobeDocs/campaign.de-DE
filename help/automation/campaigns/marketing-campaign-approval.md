---
product: campaign
title: Einrichten und Verwalten des Genehmigungsprozesses
description: Erfahren Sie, wie Sie Genehmigungen von Marketing-Kampagnen verwalten.
feature: Approvals, Campaigns
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 56%

---

# Einrichten und Verwalten des Validierungsprozesses {#approval-marketing-campaigns}

Die Methoden und Personen, die an der Erstellung und Genehmigung von Marketingkampagnen beteiligt sind, sind für jede Organisation spezifisch. Der Kampagnengenehmigungsprozess umfasst die Koordinierung mehrerer Interessengruppen: Digital-Marketing-Experten, Versand-Manager, Content-Manager und externe Eigentümer wie Partner oder Lieferanten.

Mit Adobe Campaign können Sie einen Validierungsfluss für Ihre Kampagnen einrichten und Benutzer darüber informieren, wenn eine Aktion erforderlich ist. Sie können Validierungen für jeden Schritt eines Versands definieren: Zielgruppenbestimmung, Inhalt, Budget, Extraktion und Testversand. Wenn Ihre Kampagnensendungen die verschiedenen Validierungsschritte durchlaufen, erstellt Adobe Campaign einen Verlauf der Änderungen und Abmeldungen, einschließlich Feedback, Kommentaren, Änderungsanforderungen und Kommentaren.

Die Adobe Campaign-Benutzer, die als validierungsverantwortliche Benutzer benannt wurden, erhalten eine Benachrichtigungsanfrage.


Benutzer können die Validierung auf verschiedene Weise vornehmen:

* Aus der Benachrichtigungsmeldung. Über den Link in der E-Mail erhält der Benutzer über einen Webbrowser Zugriff auf Campaign. Nach der Verbindung kann der Validierer den Inhalt validieren oder nicht.
   ![](assets/approval-content-email.png)

* Wählen Sie im Kampagnen-Dashboard aus.
   ![](assets/approval-from-dashboard.png)

* Im Versand-Dashboard.
   ![](assets/approval-from-delivery-dashboard.png)

Benutzer können über das Validierungsfenster auf die Kampagne und den Versand zugreifen. Sie können auch einen Kommentar eingeben.

![](assets/approval-target-confirm.png)

Sobald ein Benutzer die Validierung durchführt, werden die Informationen in den Kampagnen- und Versand-Dashboards sowie in den Logs angezeigt.

![](assets/approvals-from-delivery.png)

Die Informationen sind auch in den Validierungslogs des Versands und im Validierungsprotokoll der Kampagne verfügbar. Auf diese Protokolle kann über die **[!UICONTROL Bearbeiten > Audit > Genehmigungen]** Registerkarten.

![](assets/approval-logs.png)


## Validierungen aktivieren{#enable-approvals}

Validierungsbenachrichtigungen werden an die Benutzer gesendet, die von jedem Prozess betroffen sind, für den die Validierung aktiviert wurde.

Sie können für die Kampagnenvorlage, für jede Kampagne einzeln oder für einen Versand aktiviert werden.

Alle Prozesse, für die eine Validierung erforderlich ist, werden in der Kampagnenvorlage über die  **[!UICONTROL Eigenschaften]** > **[!UICONTROL Erweiterte Kampagnenparameter...]** > **[!UICONTROL Genehmigungen]** Registerkarte. Auf dieser Registerkarte werden validierungsverantwortliche Benutzer oder Gruppen von Validierungsverantwortlichen ausgewählt. Sie erhalten Benachrichtigungen, es sei denn, diese Option ist nicht aktiviert. [Weitere Informationen](#approving-processes).

Diese Einstellungen können für jede mit dieser Vorlage erstellte Kampagne sowie für jeden Versand einzeln überschrieben werden. Durchsuchen Sie die **[!UICONTROL Eigenschaften]** -Schaltfläche des Versands, dann die **[!UICONTROL Genehmigungen]** Registerkarte.

Im nachfolgenden Beispiel wird der Inhalt des Briefpost-Versands nicht zur Validierung unterbreitet:

![](assets/approval-not-enabled.png)


>[!CAUTION]
>
>Vergewissern Sie sich, dass die Validierungsverantwortlichen über die **erforderlichen Berechtigungen** zur Validierung verfügen und dass ihre Sicherheitszone korrekt definiert ist. [Weitere Informationen](#selecting-reviewers).

Der Validierungsprozess für Sendungen wird im Abschnitt [diesem Abschnitt](#review-and-approve-deliveries).

## Auswahl von Validierungsverantwortlichen {#select-reviewers}

Für jeden Validierungstyp werden die für die Validierung verantwortlichen Benutzer oder Benutzergruppen aus der Dropdown-Liste im Versand ausgewählt. Weitere Benutzer können mit dem Link **[!UICONTROL Bearbeiten...]** hinzugefügt werden. In diesem Fenster können Sie auch die Validierungs-Deadline bearbeiten. Standardmäßig haben Überprüfer drei Tage ab dem Sendedatum Zeit, um einen Prozess zu genehmigen. Verwenden Sie zum Hinzufügen einer automatischen Erinnerung die **[!UICONTROL Erinnerung hinzufügen]** Link.

![](assets/add-reviewers.png)

Wenn kein validierungsverantwortlicher Benutzer angegeben wird, ist der Kampagneninhaber für die Validierungen verantwortlich und erhält die Benachrichtigungen. Der Kampagneninhaber wird im Feld **[!UICONTROL Bearbeiten > Eigenschaften]** Tab der Kampagne:

![](assets/campaign-owner.png)

Alle anderen Adobe Campaign-Operatoren mit **[!UICONTROL Administrator]** -Berechtigungen können auch Aufträge genehmigen, erhalten jedoch keine Benachrichtigungen.

>[!NOTE]
>
>Standardmäßig kann der Kampagnenverantwortliche die Validierung nicht durchführen oder den Versand starten, wenn Validierungsverantwortliche festgelegt wurden. Als Adobe Campaign-Administrator können Sie dieses Verhalten ändern und es den Kampagneninhabern ermöglichen, Sendungen zu genehmigen/zu starten, indem Sie die **NmsCampaign_Activate_OwnerConfirmation** Option, auf **1**.


Wenn eine Liste von Validierungsverantwortlichen definiert ist, wird ein Auftrag validiert, wenn ein Validierer ihn genehmigt hat. Der Validierungslink ist dann nicht mehr in den Kampagnen- und Versand-Dashboards verfügbar. Wenn das Senden von Benachrichtigungen aktiviert ist und ein anderer Validierungsverantwortlicher auf den Validierungs-Link in der Benachrichtigung klickt, wird ihm mitgeteilt, dass ein anderer Validierungsverantwortlicher den Vorgang bereits validiert hat.

![](assets/delivery-target-already-approved.png)


## Prüfen und Validieren von Sendungen {#review-and-approve-deliveries}

Für jede Kampagne können Sie die Versandzielgruppe validieren. [Versandinhalt](#approving-content) und Kosten. Die für die Validierung zuständigen Adobe Campaign-Benutzer können per E-Mail benachrichtigt werden und eine Validierung über die Konsole oder eine Internet-Verbindung annehmen oder ablehnen. [Weitere Informationen](#approving-processes).

Bei Briefpost-Versand können Adobe Campaign-Benutzer die Extraktionsdatei vor der Übermittlung an den Router einsehen. Bei Bedarf haben sie die Möglichkeit, das Format zu verändern und die Extraktion erneut zu starten. [Weitere Informationen](#approve-an-extraction-file).

Sobald diese Validierungsphasen beendet sind, kann der Versand gestartet werden. [Weitere Informationen](marketing-campaign-deliveries.md#starting-a-delivery).

>[!NOTE]
>
>Prozesse, die eine Validierung erfordern, werden in der Kampagnenvorlage ausgewählt. [Weitere Informationen](marketing-campaign-templates.md).

### Schritte zur Validierung eines Versands {#approving-processes}

Die zu validierenden Etappen werden im Dashboard der Kampagne angezeigt (über die Konsole oder die Webschnittstelle). Sie werden auch in der Versandverfolgungstabelle und im Versand-Dashboard angezeigt.

![](assets/delivery-approval-actions.png)

Folgende Validierungsvorgänge stehen für Kampagnensendungen zur Verfügung:

* **Validierung von Zielgruppe, Inhalt und Budget**

   Wenn die **[!UICONTROL Zielgruppenvalidierung aktivieren]**, **[!UICONTROL Inhaltsvalidierung aktivieren]** oder **[!UICONTROL Budgetvalidierung aktivieren]** werden im Fenster der Validierungseinstellungen ausgewählt, die entsprechenden Links werden im Kampagnen- und Versand-Dashboard angezeigt.

   ![](assets/template-activate-6.png)

   >[!NOTE]
   >
   >Die Budgetvalidierung ist nur verfügbar, wenn die Zielgruppenvalidierung im Fenster der Validierungseinstellungen aktiviert ist. Der Link zur Budgetvalidierung wird erst nach der Zielgruppenanalyse angezeigt.

   Wenn die Optionen **[!UICONTROL Inhaltsbearbeitung zuweisen]** oder **[!UICONTROL Externe Inhaltsvalidierung]** im Fenster der Validierungseinstellungen ausgewählt sind, werden im Dashboard die entsprechenden Links **[!UICONTROL Inhalt unterbreiten]** und **[!UICONTROL Externe Inhaltsvalidierung]** angezeigt.

   Die Inhaltsvaldiierung ermöglicht den Zugriff auf die durchgeführtenTestsendungen.

* **Validierung der Extraktion (Briefpost)**

   Wenn die Option **[!UICONTROL Extraktionsvalidierung aktivieren]** im Fenster der Validierungseinstellungen ausgewählt ist, muss die Extraktionsdatei validiert werden, bevor der Router benachrichtigt werden kann.

   Die **[!UICONTROL Datei genehmigen]** ist in den Kampagnen- und Versand-Dashboards verfügbar.

   ![](assets/approve-file-preview.png)

   Sie können die Ausgabedatei vor der Validierung in der Vorschau anzeigen. Die Vorschau der Extraktionsdatei zeigt nur ein Datenbeispiel. Die gesamte Datei wird nicht geladen.

* **Validierung der Sendungen**

   Die **[!UICONTROL Individuelle Validierung jedes zugeordneten Versands aktivieren]** wird für einen primären Versand verwendet, der mit sekundären Sendungen verknüpft ist. Standardmäßig ist diese Option nicht aktiviert, sodass eine Gesamtvalidierung des Hauptversands durchgeführt werden kann. Wenn diese Option aktiviert ist, muss jeder Versand einzeln validiert werden.

   ![](assets/enable-ind-approval.png)


>[!NOTE]
>
>Wenn in einem Zielgruppen-Workflow während der Nachrichtenvorbereitung ein Konfigurationsfehler auftritt, wird die **[!UICONTROL Nachrichtenvorbereitung neu starten]** -Link wird im Dashboard angezeigt. Korrigieren Sie den Fehler und verwenden Sie diesen Link, um die Nachrichtenvorbereitung unter Umgehung der Zielbestimmung neu zu starten.


### Validieren eines Inhalts {#approve-content}

>[!CAUTION]
>
>Zur Validierung eines Inhalts ist ein Testversandzyklus obligatorisch. Mit Testsendungen können Sie die Anzeige von Informationen sowie Personalisierungsdaten validieren und die Funktionsfähigkeit von Links überprüfen.
>
>Die im Folgenden beschriebenen Funktionen für die Inhaltsvalidierung beziehen sich auf den Testversand.

Es ist möglich, einen Validierungszyklus für Inhalte zu konfigurieren. Wählen Sie dazu im Fenster mit den Validierungseinstellungen die Option **[!UICONTROL Inhaltsvalidierung aktivieren]**. Die Inhaltsvalidierung gliedert sich in folgende Schritte:

1. Nach der Erstellung eines neuen Versands klickt der Kampagnenverantwortliche auf den Link **[!UICONTROL Inhalt unterbreiten]** im Kampagnen-Dashboard, um den Zyklus der Inhaltsvalidierung zu starten.

   >[!NOTE]
   >
   >Wenn im Fenster der Validierungseinstellungen die Option **[!UICONTROL Testversand aktivieren]** (für einen E-Mail-Versand) oder die Option **[!UICONTROL Testversandvalidierung]** (für einen Briefpost-Versand) aktiviert ist, erfolgt der Testversand automatisch.

1. Der Inhaltsverantwortliche wird daraufhin per E-Mail benachrichtigt und entscheidet, ob er den Inhalt validiert oder nicht:

   * über die Benachrichtigungs-E-Mail: Die Benachrichtigungs-E-Mail enthält einen Link zu den bereits durchgeführten Testsendungen und gegebenenfalls zu einer Darstellung der Nachricht für die verschiedenen Webmails, falls die **Zustellbarkeit** -Add-on für diese Instanz aktiviert ist.

   * über die Konsole oder die Webschnittstelle, in der Versandverfolgung oder dem Kampagnen- oder Versand-Dashboard. Im Kampagnen-Dashboard kann die Liste der durchgeführten Testsendungen durch Öffnen des Links **[!UICONTROL Inbox Rendering...]** angezeigt werden. Klicken Sie auf das Symbol **[!UICONTROL Details]** rechts von der Liste, um ihren Inhalt anzuzeigen.

1. Der Kampagnenverantwortliche wird per E-Mail benachrichtigt, ob der Inhalt validiert wurde oder nicht. Der Kampagnenverantwortliche kann zu jedem Zeitpunkt den Zyklus der Inhaltsvaldierung neu starten. Öffnen Sie hierzu den Link oberhalb der Zeile **[!UICONTROL Inhaltsstatus]** im Kampagnen-Dashboard (auf Ebene des Versands) und klicken Sie auf **[!UICONTROL Inhaltsvalidierung zurücksetzen, um sie erneut durchzuführen]**.

#### Inhaltsbearbeitung zuweisen {#assign-content-editing}

Diese Option ermöglicht die Bestimmung eines Verantwortlichen für die Inhaltsbearbeitung, zum Beispiel einen Webmaster. Wenn die Option **[!UICONTROL Inhaltsbearbeitung zuweisen]** im Fenster der Validierungseinstellungen aktiviert ist, werden zwischen der Versanderstellung und dem Benachrichtigungsversand an den Inhaltsverantwortlichen mehrere Validierungsetappen hinzugefügt:

1. Nach Erstellung eines neuen Versands klickt der Kampagnenverantwortliche auf den Link **[!UICONTROL Inhaltsbearbeitung unterbreiten]** im Kampagnen-Dashboard, um den Inhaltsbearbeitungszyklus zu starten.

1. Der Verantwortliche der Inhaltsbearbeitung erhält daraufhin eine E-Mail, die ihn über die Inhaltsfreigabe informiert.

1. Er kann sich dann mit der Konsole verbinden, um den Versand zu öffnen und diesen mittels eines vereinfachten Assistenten zu bearbeiten, der die Änderung des Betreffs, der HTML- und Textinhalte sowie die Durchführung von Testsendungen ermöglicht.

   >[!NOTE]
   >
   >Wenn im Fenster der Validierungseinstellungen die Option **[!UICONTROL Testversand aktivieren]** (für einen E-Mail-Versand) oder die Option **[!UICONTROL Testversandvalidierung]** (für einen Briefpost-Versand) aktiviert ist, erfolgt der Testversand automatisch.

1. Nach Beendigung der Bearbeitung kann der Verantwortliche der Inhaltsbearbeitung den Inhalt zur Verfügung stellen.

   Dazu können sie Folgendes verwenden:

   * die **[!UICONTROL Verfügbare Inhalte]** in der Adobe Campaign-Konsole.
   * den Link in der Benachrichtigung.
Der Benutzer kann der Validierung einen Kommentar hinzufügen, bevor er den Inhalt dem Kampagnenverantwortlichen unterbreitet.
Über die Benachrichtigungs-E-Mail kann der Kampagnenverantwortliche den ihm unterbreiteten Inhalt akzeptieren oder ablehnen.

#### Externe Inhaltsvalidierung {#external-content-approval}

Diese Option ermöglicht die Bestimmung eines externen Inhaltsverantwortlichen, der die Darstellung (z. B. die Kohärenz der Kommunikation der Marke oder die angekündigten Tarife) des Versands validiert. Wenn die Option **[!UICONTROL Externe Inhaltsvalidierung]** im Fenster der Validierungseinstellungen aktiviert ist, werden zwischen der Inhaltsvalidierung durch den Inhaltsverantwortlichen und dem Benachrichtigungsversand an den Kampagnenverantwortlichen mehrere Validierungsetappen hinzugefügt:

1. Der externe Inhaltsverantwortliche wird per E-Mail benachrichtigt, sobald der Inhalt intern validiert wurde und die externe Validierung erfolgen muss.
1. Die Benachrichtigungs-E-Mail enthält Links zu den Testsendungen, die der Überprüfung der Darstellung des Versandinhalts dienen, und eine Schaltfläche, über die der Versandinhalt validiert oder abgelehnt werden kann.

Diese Links sind nur verfügbar, wenn eine oder mehrere Testsendungen durchgeführt wurden. Die Darstellung des Versandinhalts kann andernfalls nur über die Konsole oder die Webschnittstelle überprüft werden.

### Validieren einer Extraktionsdatei {#approve-an-extraction-file}

Für Offline-Sendungen erzeugt Adobe Campaign eine Extraktionsdatei, die, je nach Konfiguration, dem Router übermittelt wird. Der Inhalt der Datei hängt von der verwendeten Exportvorlage ab.

Sobald Inhalt, Zielgruppe und Budget validiert sind, erhält der Versand den Status **[!UICONTROL Extraktion ausstehend]**, bis der Extraktions-Workflow für Kampagnen gestartet wird.

Wenn das Datum der Extraktionsanfrage erreicht ist, wird die Extraktionsdatei erstellt und der Versandstatus wird zu **[!UICONTROL Datei zu validieren]**.

Sie können den Inhalt der Extraktionsdatei ansehen, indem Sie auf ihren Titel klicken. Über die verschiedenen Links im Dashboard haben Sie zudem die Möglichkeit, die Datei zu validieren oder bei Bedarf ihr Format zu verändern und die Extraktion erneut durchzuführen.

Nachdem die Datei validiert wurde, können Sie die Benachrichtigungs-E-Mail an den Router senden. [Weitere Informationen](marketing-campaign-deliveries.md#start-an-offline-delivery).

## Validierungsmodi {#approval-modes}

Vorgänge können im Kampagnen-Dashboard, im Versand-Tracking-Tab, im Versand-Dashboard oder in der an die Validierer gesendeten E-Mail-Benachrichtigung validiert werden.

### Im Dashboard genehmigen {#approval-via-the-dashboard}

Klicken Sie auf den entsprechenden Link im Kampagnen-Dashboard, um einen Auftrag über die Konsole oder die Webschnittstelle zu validieren.

Beispielsweise nach Ausführung der Versandanalyse:

1. Auswählen **[!UICONTROL Validierung der Zielgruppenbestimmung]**.

![](assets/target-validation-from-console.png)

1. Überprüfen Sie im Popup-Fenster die zu validierenden Informationen.
1. Wählen Sie **[!UICONTROL Akzeptieren]** oder **[!UICONTROL Ablehnen]** und erfassen Sie gegebenenfalls einen Kommentar. Dieser Kommentar wird in den Validierungslogs angezeigt.
1. Bestätigen Sie Ihre Auswahl mit der **[!UICONTROL Zielgruppenvalidierung]** Schaltfläche.

![](assets/confirm-validation-from-console.png)


Wenn ein Vorgang bereits von einem anderen Benutzer validiert wurde, ist der Validierungslink nicht mehr verfügbar.

Wenn ein Prozess abgelehnt wurde, werden die Informationen im Versand-Dashboard wie folgt angezeigt:

![](assets/target-approval-rejected.png)


### Aus den Benachrichtigungen validieren {#approval-via-notification-messages}

So genehmigen Sie einen Auftrag über die [Benachrichtigungsinhalt](#notifications):

1. Klicken Sie auf den Link in der Benachrichtigung.
1. Bei Adobe Campaign anmelden.
1. Überprüfen Sie die zu genehmigenden Informationen.
1. Wählen Sie **[!UICONTROL Akzeptieren]** oder **[!UICONTROL Ablehnen]** und erfassen Sie gegebenenfalls einen Kommentar.
1. Validieren. Ihre Auswahl und Ihr Kommentar werden in den Validierungslogs angezeigt.

>[!NOTE]
>
>Wenn der Vorgang Warnungen erzeugt hat, erscheint in der Benachrichtigung ein Warnhinweis.

### Validierung verfolgen{#approval-tracking}

In der Benutzeroberfläche sind Validierungsprotokolle verfügbar:

* Im Validierungsprotokoll der Kampagne: **[!UICONTROL Genehmigungen]** Unterregisterkarte des **[!UICONTROL Bearbeiten > Audit]** tab:

   ![](assets/approval-tracking-from-campaign.png)

* Im Versandlog der Kampagne: **[!UICONTROL Sendungen]** Unterregisterkarte des **[!UICONTROL Bearbeiten > Audit]** tab:

   ![](assets/approval-tracking-from-campaign-deliveries.png)

* Der Validierungsstatus eines jeden Versands kann durch Klick auf die Schaltfläche **[!UICONTROL Protokolle ausblenden/anzeigen]** der **[!UICONTROL Zusammenfassung]** Registerkarte.

   ![](assets/approval-tracking-delivery-dashboard.png)

* Auf diese Informationen kann auch über die **[!UICONTROL Audit > Validierungen]** im Tab jedes Versands:

   ![](assets/approval-tracking-delivery-tab.png)

>[!NOTE]
>
>Nachdem ein Benutzer einen Auftrag genehmigt oder abgelehnt hat, können die anderen validierungsverantwortlichen Benutzer ihn nicht mehr ändern.

### Automatische/manuelle Genehmigungen {#automatic-and-manual-approval}

Wenn bei der Erstellung eines Zielgruppen-Workflows die Validierung automatisch erfolgt (Standardmodus), zeigt Adobe Campaign den Validierungslink an oder sendet eine Benachrichtigung, sobald eine Validierung erforderlich ist.

Um den Validierungsmodus (manuell oder automatisch) auszuwählen, klicken Sie auf die Schaltfläche **[!UICONTROL Bearbeiten > Eigenschaften]** auf der Kampagnen- oder Kampagnenvorlage ein und klicken Sie auf **[!UICONTROL Erweiterte Kampagnenparameter...]** und schließlich **[!UICONTROL Genehmigungen]** Registerkarte.
par
![](assets/approval-mode.png)

>[!NOTE]
>
>Der Validierungsmodus gilt für alle Sendungen der Kampagne.

Die manuelle Validierung hingegen verhindert bei der Erstellung eines Zielgruppen-Workflows die automatische Generierung von Validierungslinks und den automatischen Versand von Benachrichtigungen. Im Dashboard der Kampagne wird daraufhin der Link **[!UICONTROL Zielgruppe zur Validierung unterbreiten]** verfügbar, um die Validierung manuell zu starten.

Über eine Bestätigungsnachricht können die Validierungen der ausgewählten Prozesse für diesen Versand erlaubt werden.

Daraufhin werden die Validierungsschaltflächen im Dashboard der Kampagne (für diesen Versand), im Dashboard des Versands sowie in der Versandverfolgung angezeigt. Wenn die Benachrichtigungen aktiviert wurden, werden diese parallel versendet.

Diese Art der Validierungsaktivierung ermöglicht es, die Zielbestimmungsrecherchen zu bearbeiten, ohne die validierenden Benutzer fälschlicherweise zu benachrichtigen.

## Benachrichtigungen {#notifications}

Benachrichtigungen sind spezifische E-Mails, die den validierungsverantwortlichen Benutzern gesendet werden, um diese über auf Validierung wartende Prozesse zu informieren. Der in der Nachricht enthaltene Link führt zu einer Webschnittstelle, in der sich der Benutzer identifizieren muss. Nach der Anmeldung kann er die betreffenden Elemente einsehen, den Prozess validieren oder nicht und seine Entscheidung mit einem Kommentar begründen.

Der Inhalt der E-Mail-Benachrichtigungen kann angepasst werden. Siehe [Inhalt der Benachrichtigungen](#notification-content).

### Aktivieren/Deaktivieren von Benachrichtigungen {#enabling-disabling-notification}

Benachrichtigungs-E-Mails werden automatisch versendet, wenn die Validierung des entsprechenden Prozesses in der Kampagnenvorlage, der Kampagne selbst oder dem betreffenden Versand aktiviert wurde. Die Benachrichtigungen können jedoch auch deaktiviert werden, um nur Validierungen über die Konsole zu erlauben.

Bearbeiten Sie hierzu das Validierungsfenster der Kampagne oder der Kampagnenvorlage ( **[!UICONTROL Bearbeiten > Eigenschaften]** > **[!UICONTROL Erweiterte Kampagnenparameter...]** > **[!UICONTROL Genehmigungen]** und wählen Sie **[!UICONTROL Benachrichtigungsversand nicht aktivieren]**.

![](assets/enable-disable-notifications.png)

### Inhalt der Benachrichtigungen {#notification-content}

Der Benachrichtigungsinhalt wird in der Vorlage **[!UICONTROL Validierungsbenachrichtigung bezüglich einer Marketingkampage]** festgelegt. Sie können im Ordner **[!UICONTROL Administration > Kampagnen > Vorlagen technischer Sendungen]** des Adobe Campaign-Explorers darauf zugreifen.

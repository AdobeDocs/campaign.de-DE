---
title: Quarantäneverwaltung in Campaign
description: Quarantäneverwaltung in Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1380'
ht-degree: 73%

---

# Quarantäne {#quarantine-management}

Adobe Campaign verwaltet für Online-Kanäle (E-Mail, SMS, Push-Benachrichtigung) eine Liste von unter Quarantäne gestellten Adressen. Teilweise werden E-Mails von Providern automatisch als Spam eingestuft, wenn die Anzahl ungültiger Adressen zu hoch ist. Durch die Quarantäne können Sie also vermeiden, von diesen Providern auf eine Blockierungsliste gesetzt zu werden. Zusätzlich helfen Ihnen Quarantänen, die Kosten des SMS-Versands zu senken, indem fehlerhafte Telefonnummern aus den Sendungen ausgeschlossen werden.

Wenn die Adresse oder Telefonnummer von Empfängern in Quarantäne ist, werden diese während der Versandanalyse von der Zielgruppe ausgeschlossen: Dann können Sie diesen Kontakten keine Marketing-Nachrichten, einschließlich automatisierter Workflow-E-Mails, senden. Sind diese in Quarantäne befindlichen Adressen auch in Listen enthalten, werden sie beim Versand an diese Listen ausgeschlossen. Eine E-Mail-Adresse kann unter Quarantäne gestellt werden, wenn beispielsweise das Postfach voll ist, die E-Mail-Adresse nicht existiert oder der E-Mail-Server nicht verfügbar ist.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

## Quarantäne versus Blockierungsliste

**Quarantäne** gilt nur für eine **E-Mail-Adresse**, eine **Telefonnummer** oder ein **Geräte-Token**, aber nicht für das Profil selbst. Wenn beispielsweise ein Profil mit einer in Quarantäne befindlichen E-Mail-Adresse eine neue Adresse angibt, kann es erneut in Versandzielgruppen aufgenommen werden. Wenn zwei Profile dieselbe Telefonnummer haben, sind beide betroffen, wenn die Nummer unter Quarantäne gestellt wird. Die unter Quarantäne gestellten Adressen oder Telefonnummern werden in den [Ausschlusslogs](#delivery-quarantines) (für einen Versand) oder in der [Quarantäneliste](#non-deliverable-bounces) (für die gesamte Plattform) angezeigt.

>[!NOTE]
>
>Wenn Empfängerinnen oder Empfänger Ihre Nachricht als Spam melden oder auf eine SMS mit einem Schlüsselwort wie „STOP“ antworten, wird ihre Adresse oder Telefonnummer als **[!UICONTROL Auf die Blockierungsliste gesetzt]** unter Quarantäne gestellt. Die jeweiligen Profile werden entsprechend aktualisiert.

Auf die Blockierungsliste setzen Profile können sich jedoch auch **{**} auf der ****-Seite befinden, wie etwa nach einer Abmeldung (Opt-out) für einen bestimmten Kanal: Dies bedeutet, dass sie nicht mehr in den Versand eingeschlossen sind. Hat ein Profil auf der Blockierungsliste für den E-Mail-Kanal zwei E-Mail-Adressen, werden folglich beide Adressen vom Versand ausgeschlossen. Im Abschnitt **[!UICONTROL Nicht mehr kontaktieren]** der Registerkarte **[!UICONTROL Allgemein]** des Profils können Sie überprüfen, ob sich ein Profil auf der Blockierungsliste für einen oder mehrere Kanäle befindet. [Weitere Informationen](../audiences/view-profiles.md)

>[!NOTE]
>
>Abgemeldete Empfänger über die [ „mailto“ List-Unsubscribe-Methode ](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"} nicht unter Quarantäne gestellt. Sie haben das Abonnement für den [Service](../start/subscriptions.md), der mit dem Versand verknüpft ist, oder werden an die Blockierungsliste gesendet (sichtbar im Abschnitt **[!UICONTROL Nicht mehr kontaktieren]** des Profils), wenn für den Versand kein Service definiert wurde.

<!--For the mobile app channel, device tokens are quarantined.-->

## Warum eine E-Mail, eine Telefonnummer oder ein Gerät unter Quarantäne gestellt wird {#quarantine-reason}

Adobe Campaign verwaltet die Quarantäne je nach Art des Versandfehlers und seiner Ursache. Die Fehler und deren Ursache werden während der Qualifizierung der Fehlermeldungen zugewiesen. [Auf dieser Seite](delivery-failures.md) erfahren Sie mehr über die Verwaltung von fehlgeschlagenen Sendungen.

Es können zwei Typen von Fehlern erfasst werden:

* **Hardbounce**: Die E-Mail-Adresse, die Telefonnummer oder das Gerät wird sofort unter Quarantäne gestellt.
* **Softbounce**: Softbounces erhöhen den Fehlerzähler und können E-Mail-Adressen, Telefonnummern oder Geräte-Token unter Quarantäne stellen. Campaign unternimmt [weitere Zustellversuche](delivery-failures.md#retries): Wenn der Fehlerzähler den Grenzwert erreicht, wird die E-Mail-Adresse, die Telefonnummer oder das Geräte-Token unter Quarantäne gestellt. [Weitere Informationen](delivery-failures.md#retries).

Bei Adressen in Quarantäne zeigt das Feld **[!UICONTROL Fehlerursache]** an, was die Quarantäne ausgelöst hat. [Weitere Informationen](#non-deliverable-bounces).


Wenn ein Benutzer eine E-Mail als Spam kennzeichnet, wird die Nachricht automatisch an ein von Adobe verwaltetes technisches Postfach weitergeleitet. Die E-Mail-Adresse des Benutzers wird dann automatisch unter Quarantäne gestellt und der Status in **[!UICONTROL Auf Blockierungsliste]** geändert. Der Status bezieht sich ausschließlich auf die Adresse, und das Profil wird nicht auf die Blockierungsliste gesetzt, sodass der Empfänger nach wie vor SMS-Nachrichten und Push-Benachrichtigungen erhält. Im [Handbuch zu Best Practices beim Versand](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=de#feedback-loops){target="_blank"} erfahren Sie mehr über Feedback-Schleifen.

>[!NOTE]
>
>Bei der Quarantänefunktion in Adobe Campaign wird die Groß-/Kleinschreibung beachtet. Achten Sie darauf, E-Mail-Adressen in Kleinbuchstaben zu importieren, damit sie später nicht erneut verwendet werden.

## Verwaltung von Softbounces {#soft-error-management}

Im Gegensatz zu Hardbounces senden Softbounces eine Adresse nicht sofort in Quarantäne, sondern erhöhen stattdessen einen Fehlerzähler. Wenn der Fehlerzähler den Grenzwert erreicht, wird die Adresse unter Quarantäne gestellt. Weitere Informationen zu weiteren Zustellversuchen und Fehlertypen finden Sie unter [ von fehlgeschlagenen Sendungen ](delivery-failures.md).

Der Fehlerzähler wird erneut initialisiert, wenn der letzte signifikante Fehler vor mehr als 10 Tagen aufgetreten ist. Der Status der Adresse wird auf **[!UICONTROL Gültig]** gesetzt und mithilfe des Workflows **[!UICONTROL Datenbankbereinigung]** wird die Adresse aus der Quarantäneliste gelöscht. [Weitere Informationen zu technischen Workflows](../config/workflows.md#technical-workflows).

## Zugriff auf unter Quarantäne gestellte E-Mail-Adressen {#access-quarantined-addresses}

Die in Quarantäne befindlichen Adressen können für einen bestimmten Versand oder für die gesamte Plattform angezeigt werden.

### Quarantänen für einen Versand{#delivery-quarantines}

E-Mail-Adressen in Quarantäne werden während der Versandvorbereitung in den Versand-Logs des Versand-Dashboards aufgeführt.

Die **[!UICONTROL Versandzusammenfassung]** gibt Aufschluss über die Anzahl der Adressen in Quarantäne in der Zielgruppe für jeden Versand. Sie zeigt insbesondere

* die Adressen, die bei der Versandanalyse ausgeschlossen wurden,
* die Adressen, die infolge des Versands neu unter Quarantäne gestellt wurden.

Weitere Informationen zu Versandberichten finden Sie in [diesem Abschnitt](../reporting/gs-reporting.md).

### Nicht zustellbare und Bounce-Adressen{#non-deliverable-bounces}

Um die Liste der in Quarantäne befindlichen Adressen **für die gesamte Plattform** anzuzeigen, können Campaign-Administratoren zu **[!UICONTROL Administration > Kampagnenverwaltung > Unzustellbarkeitsverwaltung > Adressen unzustellbarer Sendungen]** gehen. In diesem Abschnitt werden unter Quarantäne gestellte Elemente für die Kanäle **E-Mail**, **SMS** und **Push-Benachrichtigungen** aufgeführt.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Die Anzahl der Quarantänen steigt mit der Zeit. Wenn man beispielsweise davon ausgeht, dass eine E-Mail-Adresse eine Lebensdauer von etwa drei Jahren hat und die Empfängertabelle pro Jahr um 50 % wächst, lässt sich der Quarantänezuwachs wie folgt berechnen:
>
>Ende 1. Jahr: (1 &#42; 0,33) / (1 + 0,5) = 22 %.
>
>Ende 2. Jahr: ((1,22 &#42; 0,33) + 0,33) / (1,5 + 0,75) = 32,5 %.

Darüber hinaus zeigt der integrierte Bericht **[!UICONTROL Fehler und Bounces]** der im Abschnitt **Berichte** dieser Startseite verfügbar ist, Informationen zu den in Quarantäne befindlichen E-Mail-Adressen, zu den aufgetretenen Fehlertypen und zur Verteilung von Fehlern nach Domain. Sie können Daten nach einem bestimmten Versand filtern oder diesen Bericht nach Bedarf anpassen.

Weitere Informationen zu Bounce-Adressen finden Sie im [Handbuch mit den Best Practices zur Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=de){target="_blank"}.

### E-Mail-Adresse in Quarantäne {#quarantined-recipient}

Sie können den Status der E-Mail-Adresse jedes Empfängers aufrufen.

Wählen Sie dazu das Empfängerprofil aus und klicken Sie auf die Registerkarte **[!UICONTROL Sendungen]**. Sie können für alle Sendungen an diesen Empfänger feststellen, ob beispielsweise die Adresse fehlerhaft war, während der Analyse unter Quarantäne gestellt wurde usw.

Sie können für jeden Ordner mit dem integrierten Filter **[!UICONTROL E-Mail-Adresse in Quarantäne]** nur die Empfänger anzeigen, deren E-Mail-Adresse unter Quarantäne steht (siehe unten):

![](assets/quarantine-filter.png)


## Entfernen einer Adresse aus der Quarantäne {#remove-a-quarantined-address}

### Automatische Aktualisierungen {#unquarantine-auto}

Adressen, die bestimmte Bedingungen erfüllen, werden durch den integrierten Workflow der **[!UICONTROL Datenbankbereinigung]** automatisch aus der Quarantäneliste gelöscht.

In den folgenden Fällen werden die Adressen automatisch aus der Quarantäneliste entfernt:

* Adressen mit dem Status **[!UICONTROL Fehlerhaft]** werden nach einem erfolgreichen Versand aus der Quarantäneliste entfernt.
* Adressen mit dem Status **[!UICONTROL Fehlerhaft]** werden aus der Quarantäneliste entfernt, wenn der letzte Softbounce mehr als 10 Tage zurückliegt. Weitere Informationen zum Umgang mit Softbounces finden Sie in [diesem Abschnitt](#soft-error-management).
* Adressen mit dem Status **[!UICONTROL Fehlerhaft]**, die mit dem Fehler **[!UICONTROL Postfach voll]** zurückkommen, werden nach 30 Tagen aus der Quarantäneliste entfernt.

Ihr Status ändert sich dann in **[!UICONTROL Gültig]**.

>[!CAUTION]
>
>Empfänger mit einer Adresse in **[!UICONTROL Quarantäne]** oder dem Status **[!UICONTROL Auf Blockierungsliste]** werden niemals entfernt, auch wenn sie eine E-Mail erhalten.

### Manuelle Aktualisierungen {#unquarantine-manual}

Bei Bedarf können Sie eine Adresse auch manuell aus der Quarantäneliste entfernen. Um eine Adresse manuell aus der Quarantäne zu entfernen, können Sie im Knoten **[!UICONTROL Administration > Kampagnen-Management > Unzustellbarkeitsverwaltung > Adressen unzustellbarer Sendungen]** ihren Status in **[!UICONTROL Gültig]** ändern.

![](assets/tech-quarantine-status.png)

### Massenaktualisierungen {#unquarantine-bulk}

Möglicherweise müssen Sie in bestimmten Situationen Massenaktualisierungen auf der Quarantäneliste durchführen, z. B. bei einem ISP-Ausfall, bei dem E-Mails fälschlicherweise als Bounces gekennzeichnet werden, da sie ihrem Empfänger nicht erfolgreich zugestellt werden können.

So führen Sie eine Massenaktualisierung durch:

1. Erstellen eines Workflows und Hinzufügen einer Abfrage in der Quarantänetabelle (**[!UICONTROL nms:address]**), um betroffene Empfänger zu filtern
2. Verwenden Sie Abfragebedingungen, um Adressen zu identifizieren, die nicht in Quarantäne gestellt werden sollen, z. B.:
   * **E-Mail-Domain (@domain)** ist gleich den betroffenen ISP-Domains
   * **Aktualisierungsstatus (@lastModified)** innerhalb des Zeitrahmens des Ausfalls
   * **Status (@status)** entspricht Quarantänestatus
3. Fügen Sie die Aktivität **[!UICONTROL Daten aktualisieren]** hinzu, um den Adressenstatus auf &quot;**[!UICONTROL &quot;]**

Die Adressen werden dann durch den Workflow **[!UICONTROL Datenbankbereinigung“ automatisch aus der Quarantäneliste entfernt]** können in zukünftige Sendungen aufgenommen werden.

## Verwandte Themen

* [Fehlgeschlagene Sendungen verstehen](delivery-failures.md) - Erfahren Sie mehr über die verschiedenen Arten von fehlgeschlagenen Sendungen und darüber, wie Campaign mit Bounces umgeht.
* [Sendungen überwachen](delivery-dashboard.md) - Auf Versandlogs zugreifen und die Versandleistung überwachen
* [Best Practices beim Versand](../start/delivery-best-practices.md) - Best Practices für die Aufrechterhaltung einer guten Zustellbarkeit und das Vermeiden von Quarantänen


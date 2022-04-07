---
title: Quarantäneverwaltung in Campaign
description: Funktionsweise der Quarantäneverwaltung in Adobe Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 36%

---

# Quarantänen {#quarantine-management}

Adobe Campaign verwaltet eine Liste von Adressen in Quarantäne für Online-Kanäle (E-Mail, SMS, Push-Benachrichtigung). Einige Internet-Anbieter betrachten E-Mails automatisch als Spam, wenn die Anzahl ungültiger Adressen zu hoch ist. Durch die Quarantäne können Sie also vermeiden, von diesen Providern auf eine Blockierungsliste gesetzt zu werden. Zusätzlich helfen Ihnen Quarantänen, die Kosten des SMS-Versands zu senken, indem fehlerhafte Telefonnummern aus dem Versand ausgeschlossen werden.

Wenn ihre Adresse oder Telefonnummer in Quarantäne ist, werden Empfänger während der Versandanalyse von der Zielgruppe ausgeschlossen: Sie können diesen Kontakten keine Marketingnachrichten, einschließlich automatisierter Workflow-E-Mails, senden. Sind diese Adressen in Quarantäne auch in Listen enthalten, werden sie beim Versand an diese Listen ausgeschlossen. Eine E-Mail-Adresse kann unter Quarantäne gestellt werden, wenn beispielsweise das Postfach voll ist, die Adresse nicht existiert oder der E-Mail-Server nicht verfügbar ist.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**Quarantäne** gilt nur für **Adresse**, **Telefonnummer** oder **Geräte-Token**, aber nicht zum Profil selbst. Wenn beispielsweise ein Profil mit einer in Quarantäne befindlichen E-Mail-Adresse eine neue Adresse angibt, kann es erneut in Versandzielgruppen aufgenommen werden. Wenn zwei Profile dieselbe Telefonnummer haben, sind beide betroffen, wenn die Nummer unter Quarantäne gestellt wird. Die unter Quarantäne gestellten Adressen oder Telefonnummern werden in den [Ausschlusslogs](#delivery-quarantines) (für einen Versand) oder in der [Quarantäneliste](#non-deliverable-bounces) (für die gesamte Plattform) angezeigt.

Auf der anderen Seite können Profile auf der **Blockierungsliste** wie nach einer Abmeldung (Opt-out) für einen bestimmten Kanal: Dies bedeutet, dass sie nicht mehr von irgendwelchen Personen angesprochen werden. Wenn also ein Profil auf der Blockierungsliste für den E-Mail-Kanal zwei E-Mail-Adressen hat, werden beide Adressen vom Versand ausgeschlossen. Im Bereich **[!UICONTROL Nicht mehr kontaktieren]** der Registerkarte **[!UICONTROL Allgemein]** des Profils können Sie überprüfen, ob sich ein Profil auf der Blockierungsliste für einen oder mehrere Kanäle befindet. [Weitere Informationen](../audiences/view-profiles.md).

>[!NOTE]
>
>Wenn Empfänger Ihre Nachricht als Spam melden oder auf eine SMS mit einem Schlüsselwort wie &quot;STOP&quot; antworten, wird ihre Adresse oder Telefonnummer unter Quarantäne gestellt als **[!UICONTROL Auf die Blockierungsliste gesetzt]**. Ihr Profil wird entsprechend aktualisiert.
>
> E-Mail-Adressen werden für den E-Mail-Kanal unter Quarantäne gestellt. Für den Mobile-App-Kanal werden Geräte-Token unter Quarantäne gestellt. Für den SMS-Kanal werden Telefonnummern unter Quarantäne gestellt.

## Warum wird eine E-Mail, ein Telefon oder ein Gerät unter Quarantäne gestellt? {#quarantine-reason}

Adobe Campaign verwaltet die Quarantäne je nach Art des fehlgeschlagenen Versands und seinem Grund. Diese werden während der Qualifizierung der Fehlermeldungen zugewiesen. Erfahren Sie mehr über die Verwaltung von fehlgeschlagenen Sendungen [auf dieser Seite](delivery-failures.md).

Es können zwei Typen oder Fehler erfasst werden:

* **Hardbounce**: die E-Mail-Adresse, die Telefonnummer oder das Gerät sofort unter Quarantäne gestellt werden.
* **Softbounce**: Softbounces erhöhen den Fehlerzähler und können E-Mails, Telefonnummern oder Geräte-Token unter Quarantäne stellen. Kampagnenleistung [retries](delivery-failures.md#retries).: Wenn der Fehlerzähler den Grenzwert erreicht, wird die Adresse, Telefonnummer oder das Geräte-Token unter Quarantäne gestellt. [Weitere Informationen](delivery-failures.md#retries).


Bei Adressen in Quarantäne zeigt das Feld **[!UICONTROL Fehlerursache]** an, was die Quarantäne ausgelöst hat. [Weitere Informationen](#identifying-quarantined-addresses-for-the-entire-platform).


Wenn ein Benutzer eine E-Mail als Spam kennzeichnet, wird die Nachricht automatisch an ein von Adobe verwaltetes technisches Postfach weitergeleitet. Die E-Mail-Adresse des Benutzers wird dann automatisch unter Quarantäne gestellt und der Status in **[!UICONTROL Auf Blockierungsliste]** geändert. Der Status bezieht sich ausschließlich auf die Adresse und das Profil wird nicht auf die Blockierungsliste gesetzt, sodass der Empfänger nach wie vor SMS-Nachrichten und Push-Benachrichtigungen erhält. Erfahren Sie mehr über Feedback-Schleifen im [Handbuch zu Best Practices beim Versand](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=de#feedback-loops).

>[!NOTE]
>
>Bei der Quarantänefunktion in Adobe Campaign wird die Groß-/Kleinschreibung beachtet. Achten Sie darauf, E-Mail-Adressen in Kleinbuchstaben zu importieren, damit sie später nicht erneut verwendet werden.

## Zugriff auf unter Quarantäne gestellte Adressen {#access-quarantined-addresses}

Die in Quarantäne befindlichen Adressen können für einen bestimmten Versand oder für die gesamte Plattform angezeigt werden.

### Quarantänen für einen Versand{#delivery-quarantines}

Quarantäne-Adressen werden während der Versandvorbereitung in den Versandlogs des Versand-Dashboards aufgeführt.

Bei jedem Versand können Sie auch die **[!UICONTROL Versandzusammenfassung]** Bericht: Er zeigt die Anzahl der Adressen in Quarantäne in der Versandzielgruppe an und zeigt Folgendes an:

* die Adressen, die bei der Versandanalyse ausgeschlossen wurden,
* die Adressen, die infolge des Versands neu unter Quarantäne gestellt wurden.

### Nicht zustellbare und Bounce-Adressen{#non-deliverable-bounces}

So zeigen Sie die Liste der in Quarantäne befindlichen Adressen an **für die gesamte Plattform**, können Campaign-Administratoren zu  **[!UICONTROL Administration > Campaign Management > Unzustellbarkeitsverwaltung > Adressen unzustellbarer Sendungen]**. In diesem Abschnitt werden unter Quarantäne gestellte Elemente für **email**, **SMS** und **Push-Benachrichtigung** Kanäle.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Die Anzahl der Quarantänen steigt mit der Zeit. Wenn man beispielsweise davon ausgeht, dass eine E-Mail-Adresse eine Lebensdauer von etwa drei Jahren hat und dass die Empfängertabelle pro Jahr um 50 % wächst, lässt sich der Quarantänezuwachs wie folgt berechnen:
>
>Ende von Jahr 1: 1&#42;0,33)/(1+0,5) = 22 %.
>
>Ende von Jahr 2: (1,22)&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Darüber hinaus wird die **[!UICONTROL Fehler und Bounces]** nativer Bericht, verfügbar über **Berichte** enthält Informationen zu den in Quarantäne befindlichen Adressen, zu den aufgetretenen Fehlertypen und zur Verteilung von Fehlern nach Domain. Sie können Daten nach einem bestimmten Versand filtern oder diesen Bericht nach Bedarf anpassen.

Erfahren Sie mehr über Bounce-Adressen in der [Best Practices für die Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=de)

### E-Mail-Adresse in Quarantäne {#quarantined-recipient}

Sie können den Status der E-Mail-Adresse jedes Empfängers nachschlagen.

Wählen Sie dazu das Empfängerprofil aus und klicken Sie auf die Schaltfläche **[!UICONTROL Sendungen]** Registerkarte. Bei allen Sendungen an diesen Empfänger können Sie feststellen, ob die Adresse fehlgeschlagen ist, während der Analyse unter Quarantäne gestellt wurde usw.

Für jeden Ordner können Sie nur die Empfänger anzeigen, deren E-Mail-Adresse unter Quarantäne steht, wobei die Variable **[!UICONTROL E-Mail-Adresse in Quarantäne]** integrierter Filter, wie unten dargestellt:

![](assets/quarantine-filter.png)


## Entfernen einer Adresse aus der Quarantäne {#remove-a-quarantined-address}

Adressen, die bestimmten Bedingungen entsprechen, werden automatisch von der Quarantäneliste gelöscht **Datenbankbereinigung** integrierter Workflow.

In den folgenden Fällen werden die Adressen automatisch aus der Quarantäneliste entfernt:

* Adressen mit dem Status **[!UICONTROL Fehlerhaft]** werden nach einem erfolgreichen Versand aus der Quarantäneliste entfernt.
* Adressen mit dem Status **[!UICONTROL Fehlerhaft]** werden aus der Quarantäneliste entfernt, wenn der letzte Softbounce mehr als 10 Tage zurückliegt. Weitere Informationen zum Umgang mit Softbounces finden Sie in [diesem Abschnitt](#soft-error-management).
* Adressen mit dem Status **[!UICONTROL Fehlerhaft]**, die mit dem Fehler **[!UICONTROL Postfach voll]** zurückkommen, werden nach 30 Tagen aus der Quarantäneliste entfernt.

Ihr Status ändert sich dann in **[!UICONTROL Gültig]**.

>[!CAUTION]
>
>Empfänger mit einer Adresse in **[!UICONTROL Quarantäne]** oder dem Status **[!UICONTROL Auf Blockierungsliste]** werden niemals entfernt, auch wenn sie eine E-Mail erhalten.

Sie können eine Adresse auch manuell aus der Quarantäneliste entfernen. Um eine Adresse aus der Quarantäne zu nehmen, haben Sie folgende Möglichkeiten:

* Ändern Sie den Status in **[!UICONTROL Gültig]** von **[!UICONTROL Administration > Campaign Management > Unzustellbarkeitsverwaltung > Adressen unzustellbarer Sendungen]** Knoten.

   ![](assets/tech-quarantine-status.png)

* Ändern Sie den Status in **[!UICONTROL Auf die Zulassungsliste gesetzt]**: in diesem Fall bleibt die Adresse auf der Quarantäneliste, sie wird jedoch systematisch als Ziel ausgewählt, auch wenn ein Fehler auftritt.

>[!CAUTION]
>
>Wenn Sie eine Adresse aus der Quarantäneliste entfernen, starten Sie den erneuten Versand an diese Adresse. Dies kann erhebliche Auswirkungen auf Ihre Zustellbarkeit und IP-Reputation haben, was letztendlich dazu führen kann, dass Ihre IP-Adresse oder Versanddomäne blockiert wird. Gehen Sie besonders vorsichtig vor, wenn Sie erwägen, eine Adresse aus der Quarantäne zu nehmen. Wenn Sie Hilfe benötigen, wenden Sie sich an den Support von Adobe.

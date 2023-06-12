---
title: Testprofile in Campaign erstellen
description: Erfahren Sie, wie Sie in Adobe Campaign Testprofile erstellen und verwalten.
feature: Audiences, Profiles
role: User
level: Beginner
source-git-commit: 19c42bcd2a96173f3d33e3e259192107b5e64c6c
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 52%

---

# Testprofile erstellen und verwalten {#create-test-profiles}

## Was ist eine Testadresse? {#gs-seeds}

Testprofile werden als Testadressen erstellt. Sie werden verwendet, um Empfänger anzusprechen, die nicht den definierten Zielgruppenkriterien entsprechen. Mit Testadressen können Sie Personalisierung und Rendering vor dem Versand durch Testsendungen in der Vorschau ansehen und testen.

Die Testadressen bieten folgende Vorteile:

* Ersetzen von Feldern durch Daten aus Empfängerprofilen (Zufallsauswahl): Auf diese Weise können Sie beispielsweise nur die E-Mail-Adresse im Bereich Testadressen eingeben und Campaign die anderen Felder des Profils automatisch ausfüllen lassen. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=en){target="_blank"}.
* Bei Workflows mit Datamanagement-Funktionen können die im Versand genutzten zusätzlichen Daten auf Ebene der Testadressen angegeben werden, um den entsprechenden Wert zu erzwingen. Auf diese Weise umgeht man die zufällige Wertersetzung.
* Testadressen werden in den folgenden Versandstatistikberichten grundsätzlich nicht berücksichtigt: **[!UICONTROL Klicks]**, **[!UICONTROL Öffnungen]**, **[!UICONTROL Abmeldungen]**.

Testadressen werden entweder durch Importieren zur Versandzielgruppe hinzugefügt oder direkt im Versand oder der Kampagne erstellt.

>[!NOTE]
>
>Testadressen werden nicht in der Empfängertabelle, sondern in einer separaten Tabelle erstellt. Wenn Sie die Empfängertabelle um neue Daten erweitern, müssen Sie die Testadressen-Tabelle ebenfalls um die gleichen Daten erweitern. Andernfalls werden erweiterte Felder für Testadressen nicht berücksichtigt.
>
>Ein Beispiel für die Erweiterung der Testadressen-Tabelle finden Sie unter [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.



## Erstellen von Testadressen

Testadressen werden nicht über Standardprofile und -ziele verwaltet, sondern in einem dedizierten Knoten des Adobe Campaign-Explorer: **[!UICONTROL Ressourcen > Kampagnenverwaltung > Testadressen]**. Sie können Unterordner erstellen, um die Testadressen zu organisieren.

Adobe Campaign bietet auch die Möglichkeit, Testadressenvorlagen zu erstellen, die in Sendungen oder Kampagnen importiert und deren spezifischen Bedürfnissen angepasst werden. Weitere Informationen finden Sie unter [Erstellen von Testadressenvorlagen](#creating-seed-address-templates).

### Definieren von Adressen {#defining-addresses}

Gehen Sie wie folgt vor, um Testadressen zu erstellen:

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Neu]** oberhalb der Testadressenliste.
1. Füllen Sie im Tab **[!UICONTROL Empfänger]** die jeweiligen Felder aus. Die verfügbaren Felder entsprechen den Standardfeldern in den Profilen der Versandempfänger (nms:recipient table): Name, Vorname, E-Mail etc.

   >[!NOTE]
   >
   >Für die Bezeichnung der Adresse werden automatisch die von Ihnen definierten Vor- und Nachnamen verwendet.
   >
   >Bei der Erstellung einer Testadresse müssen nicht alle Felder einer jeden Registerkarte ausgefüllt werden. Fehlende Personalisierungselemente werden bei der Versandanalyse nach dem Zufallsprinzip eingetragen.

1. Im **[!UICONTROL Adressfelder]** Geben Sie die Werte ein, die in den Versandlogs während der Analysephase im **[!UICONTROL nms:broadLog]** Tabelle.

1. Geben Sie im Tab **[!UICONTROL Zusätzliche Daten]** die Personalisierungsdaten an, die in mit Data Management-Workflows erstellten Sendungen verwendet werden und die durch einen spezifischen Wert ersetzt werden sollen.

   Stellen Sie sicher, dass zusätzliche Zielgruppendaten mit einem Alias definiert wurden, der mit &quot;@&quot;im **[!UICONTROL Anreicherung]** Workflow-Aktivität. Andernfalls können Sie sie nicht richtig mit Ihren Testadressen in Ihrer Versandaktivität verwenden.

### Testadressenvorlagen erstellen {#creating-seed-address-templates}

Sie können Adressenvorlagen erstellen, die für jeden Versand importiert und geändert werden können. Der Prozess entspricht dem bei der Definition einer neuen Testadresse. Der einzige Unterschied besteht darin, dass Testadressenvorlagen-Adressen in einem Ordner vom Typ &quot;Vorlage&quot; gespeichert werden müssen.

### Testadressen für den Briefpost-Versand {#direct-mail-seed-addresses}

Für [Briefpost-Sendungen](../send/direct-mail.md), werden Testadressen während der Extraktion hinzugefügt und im Ausgabedokument gemischt.

Bei Briefsendungen muss das Format der Extraktionsdatei folgende Bedingungen erfüllen:

* Keine Verwendung der Option **[!UICONTROL Gruppierungen verwalten (GROUP BY + HAVING)]**.

* Wenn Kollektionselemente extrahiert werden, enthalten diese Felder einen leeren Wert für die Testadressen, es sei denn, die **[!UICONTROL Einzelne Zeile (erfahrener Benutzer)]** ausgewählt ist.

## Testadressen in einem Versand hinzufügen{#seed-addresses-in-a-delivery}

Wählen Sie zum Hinzufügen spezifischer Testadressen für einen Versand den Link **[!UICONTROL An]** und danach den Tab **[!UICONTROL Testadressen]** aus.

Drei Einfügemodi stehen zur Verfügung:

1. Geben Sie einzelne Testadressen ein.  Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und füllen Sie die Adressfelder aus. Dies ist für jede zu erstellende Adresse zu wiederholen.

1. Import [Testadressenvorlagen](#creating-seed-address-template) und passen sie an Ihre Bedürfnisse an. Klicken Sie auf den Link **[!UICONTROL Testadressenvorlagen importieren...]** und wählen Sie den die Vorlagen enthaltenden Ordner.

   Bei Bedarf können Sie nun die Adressfelder anpassen, indem Sie entweder darauf doppelklicken oder **[!UICONTROL Details...]** auswählen.

1. Erstellen Sie eine Bedingung, um die einzufügenden Kontrolladressen dynamisch auszuwählen. Klicken Sie auf den Link **[!UICONTROL Dynamische Bedingung bearbeiten...]** und geben Sie dann die Auswahlkriterien für die Testadressen an. Sie können beispielsweise alle in einem bestimmten Ordner enthaltenen Adressen oder die zu einer bestimmten Abteilung Ihres Unternehmens gehörigen Testadressen auswählen.

   Ein Beispiel dafür finden Sie unter [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

Bei Briefsendungen können Sie die Art der Adresseneinfügung in die Extraktionsdatei anpassen. Standardmäßig werden sie der Sortierreihenfolge der Ausgabedatei entsprechend eingeordnet. Sie haben jedoch die Möglichkeit, sie am Anfang oder am Ende der Datei bzw. zufällig inmitten der Empfänger der Hauptzielgruppe einzufügen.

## Testadressen in eine Kampagne einfügen {#seed-addresses-in-a-campaign}

Um Testadressen auf Kampagnenniveau in die Zielgruppe einzuschließen, wählen Sie den Tab **[!UICONTROL Bearbeiten]** aus.

Klicken Sie auf **[!UICONTROL Erweiterte Kampagnenparameter...]** und dann **[!UICONTROL Testadressen]** Registerkarte. Die aus der Kampagne hinzugefügten Testadressen werden zur Zielgruppe jedes Versands in der Kampagne hinzugefügt.

## Testadressen und benutzerdefinierte Tabelle {#using-an-external-recipient-table}

Wenn es sich bei der Versandtabelle um eine externe Tabelle handelt, müssen Sie zusätzliche Konfigurationen vornehmen. Die **[!UICONTROL nms:seedmember]** -Schema erweitert werden. Den Testadressen wird ein Tab hinzugefügt, um die entsprechenden Felder zu definieren

Geben Sie in diesem Fall die Testadressen-Daten direkt in den jeweiligen Feldern des entsprechenden Tabs auf Ebene des Versands ein oder importieren Sie Adressenvorlagen.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->


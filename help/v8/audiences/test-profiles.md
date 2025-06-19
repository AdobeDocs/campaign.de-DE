---
title: Erstellen von Testprofilen in Campaign
description: Erfahren Sie, wie Sie in Adobe Campaign Testprofile erstellen und verwalten.
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: ht
source-wordcount: '974'
ht-degree: 100%

---

# Erstellen und Verwalten von Testprofilen {#create-test-profiles}

## Was ist eine Testadresse? {#gs-seeds}

Testprofile werden als Testadressen erstellt. Sie werden verwendet, um Empfänger und Empfängerinnen anzusprechen, die nicht den definierten Zielgruppenkriterien entsprechen. Mit Testadressen können Sie Personalisierung und Rendering vor dem Versand durch Testsendungen in der Vorschau ansehen und testen.

Die Testadressen bieten die folgenden Vorteile:

* Ersetzen fehlender Werte durch Empfängerdaten aus der Zielgruppe (Zufallsauswahl). So ist es beispielsweise möglich, in Testadressen nur die E-Mail-Adresse anzugeben und die anderen Felder automatisch von Campaign aus dem Profil ausfüllen zu lassen. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=de){target="_blank"}.
* Bei Workflows mit Datamanagement-Funktionen können die im Versand genutzten zusätzlichen Daten auf Ebene der Testadressen angegeben werden, um den entsprechenden Wert zu erzwingen. Auf diese Weise umgeht man die zufällige Wertersetzung.
* Testadressen werden in den folgenden Versandstatistikberichten grundsätzlich nicht berücksichtigt: **[!UICONTROL Klicks]**, **[!UICONTROL Öffnungen]**, **[!UICONTROL Abmeldungen]**.

Testadressen werden entweder durch Importieren zur Versandzielgruppe hinzugefügt oder direkt im Versand oder der Kampagne erstellt.

>[!NOTE]
>
>Testadressen werden nicht in der Empfängertabelle, sondern in einer separaten Tabelle erstellt. Wenn Sie die Empfängertabelle um neue Daten erweitern, müssen Sie die Testadressen-Tabelle ebenfalls um die gleichen Daten erweitern. Andernfalls werden erweiterte Felder für Testadressen nicht berücksichtigt.
>
>Ein Beispiel für die Erweiterung der Testadressen-Tabelle finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=de){target="_blank"}.

## Erstellen von Testadressen

Testadressen werden nicht über Standardprofile und Zielgruppen verwaltet, sondern in einem eigenen Knoten des Adobe Campaign Explorers: **[!UICONTROL Ressourcen > Kampagnen-Management > Testadressen]**. Sie können Unterordner erstellen, um die Testadressen zu organisieren.

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

1. Geben Sie auf der Registerkarte **[!UICONTROL Adressfelder]** die Werte ein, die während der Analysephase in die Versandlogs in der Tabelle **[!UICONTROL nms:broadLog]** eingefügt werden sollen.

1. Geben Sie im Tab **[!UICONTROL Zusätzliche Daten]** die Personalisierungsdaten an, die in mit Data Management-Workflows erstellten Sendungen verwendet werden und die durch einen spezifischen Wert ersetzt werden sollen.

   Stellen Sie sicher, dass in der Workflow-Aktivität **[!UICONTROL Anreicherung]** zusätzliche Zielgruppendaten mit einem Alias definiert wurden, der mit „@“ beginnt. Andernfalls können Sie sie nicht richtig mit Ihren Testadressen in Ihrer Versandaktivität verwenden.

### Erstellen von Adressenvorlagen {#creating-seed-address-templates}

Sie können Adressenvorlagen erstellen, die für jeden Versand importiert und geändert werden können. Der Vorgang ist derselbe wie bei der Definition einer neuen Testadresse. Der einzige Unterschied besteht darin, dass Adressen von Testadressenvorlagen in einem Ordner vom Typ „Vorlage“ gespeichert werden müssen.

### Testadressen für die Briefpost-Sendungen {#direct-mail-seed-addresses}

Für die [Briefpost-Sendungen](../send/direct-mail.md) werden Testadressen während der Extraktion hinzugefügt und im Ausgabedokument unter die restlichen Informationen gemischt.

Bei Briefsendungen muss das Format der Extraktionsdatei folgende Bedingungen erfüllen:

* Keine Verwendung der Option **[!UICONTROL Gruppierungen verwalten (GROUP BY + HAVING)]**.

* Bei der Extraktion von Sammlungselementen bleiben die entsprechenden Felder für Testadressen leer, es sei denn, die Option **[!UICONTROL Nur eine Zeile (Expertenmodus)]** wurde ausgewählt.

## Hinzufügen von Testadressen zu einem Versand{#seed-addresses-in-a-delivery}

Wählen Sie zum Hinzufügen spezifischer Testadressen für einen Versand den Link **[!UICONTROL An]** und danach den Tab **[!UICONTROL Testadressen]** aus.

Drei Einfügemodi stehen zur Verfügung:

1. Eingabe einzelner Testadressen.  Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** und füllen Sie die Adressfelder aus. Dies ist für jede zu erstellende Adresse zu wiederholen.

1. Importieren Sie [Vorlagen von Testadressen](#creating-seed-address-template) und passen Sie sie an Ihre Bedürfnisse an. Klicken Sie auf den Link **[!UICONTROL Testadressenvorlagen importieren...]** und wählen Sie den die Vorlagen enthaltenden Ordner.

   Bei Bedarf können Sie nun die Adressfelder anpassen, indem Sie entweder darauf doppelklicken oder **[!UICONTROL Details...]** auswählen.

1. Erstellen Sie eine Bedingung zur dynamischen Auswahl der einzufügenden Testadressen. Klicken Sie auf den Link **[!UICONTROL Dynamische Bedingung bearbeiten...]** und geben Sie dann die Auswahlkriterien für die Testadressen an. Sie können beispielsweise alle in einem bestimmten Ordner enthaltenen Adressen oder die zu einer bestimmten Abteilung Ihres Unternehmens gehörigen Testadressen auswählen.

   Ein Beispiel dafür finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=de){target="_blank"}.

Bei Briefsendungen können Sie die Art der Adresseneinfügung in die Extraktionsdatei anpassen. Standardmäßig werden sie der Sortierreihenfolge der Ausgabedatei entsprechend eingeordnet. Sie haben jedoch die Möglichkeit, sie am Anfang oder am Ende der Datei bzw. zufällig inmitten der Empfänger der Hauptzielgruppe einzufügen.

## Hinzufügen von Testadressen in einer Kampagne {#seed-addresses-in-a-campaign}

Um Testadressen auf Kampagnenniveau in die Zielgruppe einzuschließen, wählen Sie den Tab **[!UICONTROL Bearbeiten]** aus.

Klicken Sie auf den Link **[!UICONTROL Erweiterte Kampagnenparameter...]** und anschließend auf die Registerkarte **[!UICONTROL Testadressen]**. Die auf diese Weise angegebenen Testadressen werden bei jedem Versand dieser Kampagne zur Zielgruppe hinzugefügt.

## Testadressen und benutzerdefinierte Tabelle {#using-an-external-recipient-table}

Wenn es sich bei der Versandtabelle um eine externe Tabelle handelt, müssen Sie zusätzliche Konfigurationen vornehmen. Das Schema **[!UICONTROL nms:seedmember]** muss erweitert werden. Es wird eine Registerkarte zu den Testadressen hinzugefügt, um die entsprechenden Felder zu definieren

Geben Sie in diesem Fall die Testadressen direkt in den jeweiligen Feldern der entsprechenden Registerkarte auf Ebene des Versands ein oder importieren Sie die Adressenvorlagen.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->

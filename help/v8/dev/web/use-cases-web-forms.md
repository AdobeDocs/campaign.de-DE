---
product: campaign
title: 'Anwendungsbeispiele: Web-Formulare'
description: 'Anwendungsbeispiele: Web-Formulare'
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 7aa4646d-1325-47c2-b553-6fe375c48973
TQID: 'https://experienceleague.adobe.com/Zw-cfoQrq1PAe-swZ7gvMNyTb4ciCMF2kdT7fN2zLsg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 61%
---
# Anwendungsbeispiele: Web-Formulare{#use-cases-web-forms}



## Abonnement-Formular mit zweifacher Bestätigung erstellen {#create-a-subscription--form-with-double-opt-in}

Wenn Sie Informationsdienste anbieten, müssen sich Empfangende für den Empfang aller verknüpften Nachrichten anmelden. Um unsachgemäße Kommunikation zu vermeiden und sicherzustellen, dass die empfangende Person sich absichtlich angemeldet hat, empfehlen wir, eine Anmeldebestätigungsanfrage zu senden, um ein doppeltes Opt-in zu erstellen. Das Abonnement wird erst wirksam, wenn die Person auf den in der Bestätigungsnachricht enthaltenen Link klickt.

Es wird von folgendem Szenario ausgegangen:

1. Ein Newsletter-Abonnement soll auf einer Website erstellt werden, die ein Kontrollkästchen enthält, über das die Anmeldung für einen temporären Dienst möglich ist. Dieser Dienst ermöglicht den Versand von Bestätigungsnachrichten zu Abonnements.
1. Der Versand einer Abonnementbestätigung soll mit einer Versandvorlage erstellt werden, die mit einem Web-Formular verknüpft ist. Dieses enthält den Bestätigungs-Link, mit dem das Formular zur Newsletter-Anmeldung aufgerufen und eine Validierungsnachricht für die Anmeldung angezeigt wird.

### Schritt 1: Erstellen von Informationsdiensten {#step-1---creating-information-services}

1. Erstellen Sie den Dienst für die Newsletter-Anmeldung für Ihre Empfangenden. Weitere Informationen zur Erstellung eines Newsletters finden Sie [in diesem Abschnitt](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/about-services-and-subscriptions){target="_blank"}.

   ![Dialogfeld „Service“ für den wöchentlichen Newsletter-Service mit den Feldern „Titel“, „Interner Name“, „E-Mail-Typ“ und „Newsletter-Modus“.](assets/s_ncs_admin_survey_double-opt-in_sample_1.png)

1. Erstellen Sie einen zweiten Informationsdienst, einen temporären Dienst, der mit einer Versandvorlage verknüpft ist, um Nachrichten zur Anmeldebestätigung zu versenden.

   ![Dashboard des temporären Dienstes (temp_service) mit E-Mail-Typ, Newsletter-Modus und Ordner.](assets/s_ncs_admin_survey_double-opt-in_sample_1c.png)

### Schritt 2: Erstellen von Bestätigungsnachrichten {#step-2---creating-confirmation-messages}

Bestätigungsnachrichten werden über eine spezielle Versandvorlage gesendet, die im temporären Dienst referenziert ist.

1. Wählen Sie im **[!UICONTROL Explorer]** die Option **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]** aus.
1. Erstellen Sie eine Versandvorlage zum Senden der Anmeldebestätigung.
1. Wählen Sie in den **[!UICONTROL E-Mail-Parametern]** die Schaltfläche **[!UICONTROL An]** aus, um die Versandvorlage mit dem Abonnement-Zielgruppen-Mapping anstelle der Empfänger zu verbinden.

   ![Wählen Sie das Dialogfeld Ziel in der Versandvorlage aus, wobei das Zielgruppen-Mapping Abonnements :subscriptionnms) ausgewählt ist.](assets/s_ncs_admin_survey_double-opt-in_sample_1d.png)

1. Da die Empfänger dieses Versands ihre Zustimmung nicht bestätigt haben, befinden sie sich immer noch auf der Blockierungsliste der Datenbank. Damit sie diese Nachricht erhalten, müssen Sie Sendungen autorisieren, die auf dieser Vorlage basieren, um Empfänger auf der Blockierungsliste anzusprechen.

   Verwenden Sie dazu den Tab **[!UICONTROL Ausschlüsse]**.

1. Wählen Sie den Link **[!UICONTROL Bearbeiten...]** aus und deaktivieren Sie die Option **[!UICONTROL Empfänger ausschließen, die nicht mehr kontaktiert werden möchten]**.

   <!-- ![](assets/s_ncs_admin_survey_double-opt-in_sample_4d.png)-->

   >[!IMPORTANT]
   >
   >Diese Option darf nur in diesem Kontext deaktiviert werden.

1. Passen Sie Ihren Versand an und fügen Sie den Bestätigungs-Link in den Nachrichteninhalt ein. Über diesen Link können Sie auf das Web-Formular zugreifen, um Anmeldebestätigungen aufzuzeichnen.

   ![Bestätigungs-E-Mail im Versand-Editor mit einem Personalisierungsfeld Vorname und einem Link Hier klicken](assets/s_ncs_admin_survey_double-opt-in_sample_1b.png)

1. Verknüpfen Sie mithilfe des DCE Ihre URL mit dem Web-Formular. Da das Web-Formular noch nicht erstellt wurde, ersetzen Sie den entsprechenden Wert unmittelbar bei seiner Erstellung.

   ![Hypertextverknüpfungsbereich mit dem Feld Web-Anwendung, noch leer, für den Link Hier klicken in der Bestätigungs-E-Mail.](assets/s_ncs_admin_survey_double-opt-in_sample_3.png)

1. Verbinden Sie abschließend diese Vorlage mit dem zuvor erstellten temporären Dienst.

   ![Registerkarte „Bearbeitung“ des temporären Services, auf der der Bestätigungsversand im Feld Abonnement ausgewählt ist.](assets/s_ncs_admin_survey_double-opt-in_sample_3c.png)

### &#x200B;3. Schritt: Erstellung des Anmeldeformulars {#step-3---creating-the-subscription-form}

Das Webformular ermöglicht sowohl die Anmeldung der Empfänger als auch die Anmeldebestätigung.

Der Webformular-Workflow umfasst die folgenden Aktivitäten:

![Web-Formular-Workflow: Vorausfüllen, Testen und dann Leere E-Mail führt zu Skript-Blockierungsliste, Abonnement, Speicherung, Ende.](assets/s_ncs_admin_survey_double-opt-in_sample_4c.png)

Gehen Sie dazu wie folgt vor:

1. Erstellen Sie ein Webformular und wählen Sie die Vorlage **[!UICONTROL Newsletter-Anmeldung (subNewsletter)]** aus.

   ![Dialogfeld „Neue Web-Anwendung“ mit ausgewählter Vorlage „Newsletter-Abonnement (Unter-Newsletter)“.](assets/s_ncs_admin_survey_double-opt-in_sample_5a.png)

1. Im Tab **[!UICONTROL Bearbeiten]** muss der vorhandene Workflow konfiguriert werden, da eine Bestätigungsnachricht an die Empfänger, die sich anmelden möchten, hinzugefügt werden soll.

   Doppelklicken Sie dazu auf die Aktivität **[!UICONTROL Vorausfüllen]** und konfigurieren Sie sie wie folgt.

   ![Dialogfeld „Aktivität vorausfüllen“ mit im Formular referenzierten Daten automatisch laden und „Vorausfüllen überspringen“, wenn keine ID ausgewählt ist.](assets/s_ncs_admin_survey_double-opt-in_sample_5b.png)

   Wenn die Benutzerin bzw. der Benutzer über den Link in der Bestätigungsnachricht auf dieses Formular zugreift, werden die Profilinformationen geladen. Wenn der Zugriff auf das Web-Formular über eine Seite der Website erfolgt, werden keine Informationen geladen.

1. Fügen Sie eine **[!UICONTROL Test]**-Aktivität zu Ihrem Workflow hinzu.

   ![Web-Formular-Workflow mit einer Test -Aktivität, die in einer E-Mail verzweigt, die leer zu Abonnement, Speicherung und Ende ist.](assets/s_ncs_admin_survey_double-opt-in_sample_6e.png)

   Die Aktivität **[!UICONTROL Test]** kann sich auf die Empfänger-E-Mail beziehen. Konfigurieren Sie sie in diesem Fall wie folgt:

   ![Testen Sie den Aktivitätszweig-Editor mit der Bedingung, @email nicht leer ist.](assets/s_ncs_admin_survey_double-opt-in_sample_6d.png)

1. Fügen Sie zwei **[!UICONTROL Script]**-Aktivitäten zu Ihrem Workflow hinzu.

   ![Web-Formular-Workflow mit einer Script-Aktivität in jedem Zweig der Testaktivität.](assets/s_ncs_admin_survey_double-opt-in_sample_6f.png)

   Die erste **[!UICONTROL Script]**-Aktivität fügt Empfänger auf der Blockierungsliste hinzu, bis sie ihr Abonnement für den Newsletter bestätigt haben. Der Inhalt muss wie folgt aussehen:

   ```javascript
   ctx.recipient.@blackList=1
   ```

   ![Script zur Blockierungsliste des Scripts ctx.recipient.@blackList=1.](assets/s_ncs_admin_survey_double-opt-in_sample_6bbis.png)

   Mit der zweiten **[!UICONTROL Script]**-Aktivität werden Sendungen an die Benutzer genehmigt. Außerdem werden diese zum Newsletter angemeldet. Die letzten beiden Zeilen des Skripts ermöglichen es Ihnen, Ihre Empfänger vom temporären Ordner in einen anderen Ordner zu übertragen und mit vorhandenen Profilen abzustimmen, sobald sie das Abonnement bestätigt haben.

   ```javascript
   ctx.recipient.@blackList=0
   nms.subscription.Subscribe("INTERNAL_NAME_OF_THE_NEWSLETTER", ctx.recipient, false)
   ctx.recipient.folder = <folder name="nmsRootRecipient"/>
   nms.subscription.Unsubscribe("TEMP", ctx.recipient)
   ```

   >[!NOTE]
   >
   >Die Partition **[!UICONTROL Temp]** kann auch regelmäßig mit einem Workflow bereinigt werden.

   ![Zweite Script-Aktivität mit den Skript-Zeilen „unblocklist“, „subscribe“, „folder“ und „unsubscribe“.](assets/s_ncs_admin_survey_double-opt-in_sample_6b.png)

1. Doppelklicken Sie auf die **[!UICONTROL Abonnement]**-Aktivität, um das Anmeldeformular anzupassen und eine Checkbox mit dem zuvor erstellten temporären Dienst zu verbinden.

   ![Seiteneditor mit dem Kontrollkästchen „Einverständnis“, das mit dem temporären Dienst im Feld Dienst verknüpft ist.](assets/s_ncs_admin_survey_double-opt-in_sample_5c.png)

1. Konfigurieren Sie die Aktivität **[!UICONTROL Speicherung]**, um die auf der Formularseite eingegebenen Informationen zu speichern.

   Mit dieser Aktivität können Sie Empfängerprofile in einem speziellen temporären Ordner erstellen. Damit können Sie sie von den Profilen in der Datenbank trennen, denen Nachrichten gesendet werden können.

   ![Dialogfeld „Speicheraktivität“ mit als Erstellungsordner festgelegtem temporären Ordner.](assets/s_ncs_admin_survey_double-opt-in_sample_5g.png)

   >[!NOTE]
   >
   >Es dürfen keine Abstimmoptionen definiert werden.

1. Fügen Sie zwei **[!UICONTROL Ende]**-Aktivitäten hinzu, um dem Benutzer eine Nachricht anzuzeigen.

   Die zweite **[!UICONTROL Ende]**-Aktivität enthält die Bestätigungsnachricht, sobald die Anmeldung abgeschlossen ist.

   ![Der Dialog „Aktivität beenden“ mit der Meldung „Ihr Abonnement ist abgeschlossen“. In Kürze erhalten Sie unseren Newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_5h.png)

1. Nachdem das Webformular erstellt und konfiguriert wurde, können Sie es in der Versandvorlage referenzieren, um Bestätigungsnachrichten zu senden.

   ![Bestätigungsversand mit dem Link Hier klicken , der auf die Anmeldung zum Newsletter mit Double-Opt-in-Webanwendung verweist.](assets/s_ncs_admin_survey_double-opt-in_sample_7b.png)

### Schritt 4: Veröffentlichung und Testen des Formulars {#step-4---publishing-and-testing-the-form}

Sie können jetzt das Formular veröffentlichen, damit die Benutzer darauf zugreifen können.

![Dashboard der Webanwendung mit der Schaltfläche Veröffentlichen und der Meldung, dass die Anwendung veröffentlicht werden muss, damit der Zugriff online möglich ist.](assets/s_ncs_admin_survey_double-opt-in_sample_8b.png)

Die Anmeldung zum Newsletter beinhaltet die folgenden Schritte:

1. Der Benutzer der Website loggt sich in der Anmeldeseite ein und validiert das Formular.

   ![Newsletter-Anmeldeformular in einem Browser mit ausgefülltem Namen und ausgefüllter E-Mail, aktiviertem Einverständnisfeld und der Schaltfläche „Abonnieren“.](assets/s_ncs_admin_survey_double-opt-in_sample_8c.png)

   Eine Nachricht in seinem Browser informiert ihn, dass seine Anfrage eingegangen ist.

   ![Browser-Endseite, auf der angegeben wird, dass die Anfrage registriert wurde und eine Meldung folgt.](assets/s_ncs_admin_survey_double-opt-in_sample_8d.png)

   Der Benutzer wird zum **[!UICONTROL Temp]**-Ordner der Adobe Campaign-Datenbank hinzugefügt; sein Profil wird auf die Blockierungsliste gesetzt, bis er seine Anmeldung über die E-Mail bestätigt.

   ![Ordner der temporären Empfänger mit dem ausgewählten neuen Profil und der Option Nicht mehr kontaktieren (alle Kanäle).](assets/s_ncs_admin_survey_double-opt-in_sample_8f.png)

1. Er erhält eine Bestätigungsnachricht mit einem Link zur Abonnement-Bestätigung.

   ![Bestätigungs-E-Mail für die Anmeldung mit einem Link Hier klicken, um die Newsletter-Anmeldung zu bestätigen.](assets/s_ncs_admin_survey_double-opt-in_sample_8e.png)

1. Wenn er auf diesen Link klickt, wird in seinem Browser die Bestätigungsseite angezeigt.

   ![Browser-Seite mit dem Titel Glückwunsch! Bestätigung, dass das Abonnement jetzt aktiv ist.](assets/s_ncs_admin_survey_double-opt-in_sample_8.png)

   Das Benutzerprofil wird in Adobe Campaign aktualisiert:

   * Es befindet sich nicht mehr auf der Blockierungsliste
   * und wurde zum Informationsdienst angemeldet.

     ![Empfängerprofil wurde aktualisiert, und der Kontakt wurde nicht mehr gelöscht und das Newsletter-Filmabonnement wurde aufgelistet.](assets/s_ncs_admin_survey_double-opt-in_sample_9.png)

## Je nach den ausgewählten Werten unterschiedliche Optionen anzeigen {#displaying-different-options-depending-on-the-selected-values}

Im folgenden Beispiel wird die Person aufgefordert, einen Fahrzeugtyp auszuwählen. Je nach ausgewähltem Typ können die verfügbaren Fahrzeugkategorien angezeigt werden. Das bedeutet, dass die in der rechten Spalte angezeigten Elemente von der Auswahl der Person abhängen:

![Seite zur Fahrzeugauswahl mit der Dropdown-Liste „Fahrzeugtyp“ auf „Auswählen“.](assets/s_ncs_admin_survey_condition_sample0.png)

* Wenn der Benutzer &quot;Personenfahrzeug&quot; auswählt, werden die Kategorien &quot;Kompakt&quot; und &quot;Minivan&quot; angezeigt.

  ![Seite zur Fahrzeugauswahl mit ausgewähltem Personenkraftwagen, auf der die Optionen „Standard“ und „Kompakt“ angezeigt werden.](assets/s_ncs_admin_survey_condition_sample2.png)

* Wenn der Benutzer &quot;Nutzfahrzeug&quot; auswählt, wird in einer Dropdown-Liste eine Auswahl angeboten.

  ![Seite zur Fahrzeugauswahl mit ausgewähltem fahrendem LKW und einer Dropdown-Liste von Fahrzeugtypen.](assets/s_ncs_admin_survey_condition_sample1.png)

In diesem Beispiel wird der Fahrzeugtyp nicht in der Datenbank gespeichert. Die Dropdown-Liste ist wie folgt konfiguriert:

![Typ des Autos Kombinationsfeld Eigenschaften mit den Werten Auswählen, Persönliches Auto und Beweglicher LKW.](assets/s_ncs_admin_survey_condition_config1.png)

Diese Information wird in einer lokalen Variable gespeichert.

Die bedingte Anzeige in der rechten Spalte wird in Containern konfiguriert:

![Dialogfeld „Speicherung“ mit ausgewählter Option „Variable“ für das Feld „Fahrzeugtyp“](assets/s_ncs_admin_survey_condition_config1bis.png)

* Bedingte Sichtbarkeit der Felder für ein Personenfahrzeug:

  ![Sichtbedingung auf dem Personal-Car-Container: Art des Autos entspricht dem Personal-Car.](assets/s_ncs_admin_survey_condition_config2.png)

* Bedingte Sichtbarkeit der Felder für ein Nutzfahrzeug:

  ![Sichtbedingung am LKW-/Transporter-Container: Fahrzeugtyp entspricht dem fahrenden LKW.](assets/s_ncs_admin_survey_condition_config3.png)

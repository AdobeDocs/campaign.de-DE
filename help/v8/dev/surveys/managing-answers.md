---
product: campaign
title: Antworten verwalten
description: Erfahren Sie, wie Sie Umfrageantworten verwalten
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 0b5dc602-e16f-4bf1-bd8f-352e0bc78996
TQID: 'https://experienceleague.adobe.com/-xjK3nxUc4Lz-mWyVoUbbIJ8HQvyLRInYk-w8zYLYE4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 74%
---
# Antworten verwalten{#managing-answers}

>[!AVAILABILITY]
>
>Für Campaign-FFDA[Bereitstellungen sind keine Umfragen &#x200B;](../../architecture/enterprise-deployment.md).



## Erfasste Antworten speichern {#storing-collected-answers}

Zusätzlich zu den Standard-Speichermodi, die für alle Webformulare in Adobe Campaign bereitstehen (Datenbankfeld und lokale Variable), ist bei Umfragen auch die dynamische Erweiterung des Datenmodells mithilfe archivierter Felder möglich.

>[!CAUTION]
>
>Diese Option ist nur für Web-Anwendungen vom Typ **Umfrage** verfügbar. Sie wird nicht für andere Arten von Web-Formularen angeboten.

### In einem archivierten Feld speichern {#storing-in-an-archived-field}

Es ist einfach, die Datenvorlage zu erweitern, indem neue Speicherorte hinzugefügt werden, um die in Umfragen bereitgestellten Antworten zu speichern. Wählen Sie dazu bei der Erstellung des Eingabefelds die Option **[!UICONTROL Antworten auf eine Frage speichern]** aus. Klicken Sie auf **[!UICONTROL Neues Feld...]** und geben Sie seine Eigenschaften an:

![Dialogfeld „Speicherung“ mit „Antworten auf eine Frage speichern“ und dem Dialogfeld „Neues archiviertes Feld erstellen“ für ein Vertragsfeld ausgewählt.](assets/s_ncs_admin_survey_new_space.png)

Geben Sie den Titel und den Namen des Felds ein und wählen Sie den Typ des Felds aus: Text, boolesch, ganze Zahl oder Dezimalzahl, Datum etc.

Über den ausgewählten Feldtyp lassen sich auch die von den Benutzern eingegebenen Daten definieren. Bei **Text**-Feldern können Sie eine Einschränkung (Groß-/Kleinschreibung, Format) oder einen Link zu einer vorhandenen Aufzählung hinzufügen, um eine Auswahl zu erzwingen.

Um eine Einschränkung hinzuzufügen, wählen Sie sie aus der Dropdown-Liste aus. Es gibt zwei Arten von Einschränkungen:

1. Groß- und Kleinschreibung von Buchstaben

   Die eingegebenen Informationen können im Feld in den folgenden Formaten gespeichert werden: nur Großbuchstaben, nur Kleinbuchstaben oder erster Buchstabe großgeschrieben. Diese Einschränkung erfordert nicht, dass Benutzende die Daten im ausgewählten Format eingeben, aber der im Feld eingegebene Inhalt wird beim Speichern umgewandelt.

1. Datenformat

Wenn dieses Feld in einer Liste verwendet wird, können die Werte der Aufzählung automatisch in der Wertetabelle über den Link **[!UICONTROL Datenbankverbindung über der Liste der Werte]** oberhalb der Werteliste abgerufen werden.

Sie können beispielsweise eine Dropdown-Liste erstellen, aus der der Benutzer seine Muttersprache auswählen kann. Das entsprechende archivierte Feld kann mit der Aufzählung **Sprache** verknüpft werden, die eine Liste von Sprachen enthält:

![Dialogfeld „Neues archiviertes Feld erstellen“ mit ausgewählter Sprachaufzählung und hervorgehobenem Symbol „Link bearbeiten“.](assets/s_ncs_admin_survey_database_values_2b.png)

Mit dem Symbol **[!UICONTROL Link bearbeiten]** rechts neben dem Feld können Sie den Inhalt dieser Aufzählung bearbeiten:

![Auflistungssprachen-Editor (Sprache) mit den Werten Englisch, Französisch und Deutsch.](assets/s_ncs_admin_survey_database_values_2c.png)

Im Tab **[!UICONTROL Allgemein]** des Felds können Sie über den Link **[!UICONTROL Werteliste aus der Datenbank übernehmen]** automatisch die angebotene Liste der Titel eingeben.

![Dropdown-Feld Registerkarte Allgemein , Initialisieren Sie die Liste der Werte aus dem Datenbank-Link, der die Sprachkennzeichnungen ausfüllt.](assets/s_ncs_admin_survey_database_values_2.png)

**Beispiel**: Die Verträge eines Empfängers sollen gemeinsam in einem Feld gespeichert werden.

Um verschiedene Arten von Verträgen gemeinsam in einem Feld zu speichern, erstellen Sie ein Eingabefeld vom Typ **[!UICONTROL Text]** und wählen Sie die Option **[!UICONTROL Antworten auf eine Frage speichern]** aus.

Klicken Sie auf **[!UICONTROL Neues Feld...]** und geben Sie die Feldeigenschaften ein. Wählen Sie die Option **[!UICONTROL Mehrfachwerte]** aus, um die Speicherung mehrerer Werte zu ermöglichen.

![Dialogfeld „Neues archiviertes Feld für Verträge erstellen“ mit ausgewählter Option „Mehrere Werte“.](assets/s_ncs_admin_survey_storage_multi_ex1.png)

Erstellen Sie für die anderen Verträge Eingabefelder und speichern Sie die Daten im selben archivierten Feld.

![Speicherdialogfeld und Feldauswahl, die ein Eingabefeld mit dem archivierten Feld „Verträge“ verknüpfen.](assets/s_ncs_admin_survey_storage_multi_ex2.png)

Wenn Benutzer die Umfrage validieren, werden ihre Antworten im Feld **[!UICONTROL Verträge]** gespeichert.

In unserem Beispiel betrifft das die folgenden Antworten:

![Vertragsbefragungsseite mit vier Vertragsfeldern ausgefüllt mit den Werten M, L, T und V.](assets/s_ncs_admin_survey_storage_multi_ex3.png)

Die vier eingegebenen Verträge werden im Profil des Benutzers gespeichert.

Die Verträge können im Tab **[!UICONTROL Antworten]** der Umfrage aufgerufen werden, indem die entsprechenden Spalten angezeigt werden.

![Registerkarte „Antworten“ mit Antworten mit den Spalten „Contrat_1“ bis „Contrat_4“, in denen die Werte von Antworten mit mehreren Werten angezeigt werden.](assets/s_ncs_admin_survey_storage_multi_ex4.png)

Sie können Empfänger auch auf der Basis ihrer Antworten filtern, sodass nur die für Sie interessanten Benutzer angezeigt werden. Erstellen Sie dazu einen Zielgruppen-Workflow unter Verwendung der Box **[!UICONTROL Umfrageantworten]**.

![Zielgruppenbestimmungs-Workflow mit der Aktivität Umfrageantworten , die aus der Zielgruppenbestimmungspalette in das Diagramm gezogen wurde.](assets/s_ncs_admin_survey_read_responses_wf.png)

Erstellen Sie Ihre Abfrage basierend auf den Profilen, die Sie abrufen möchten. Im folgenden Beispiel können Sie Profile mit mindestens zwei Verträgen einschließlich eines Vetrags des Typs A für die Abfrage auswählen.

![Aktivität „Umfrageantworten“ und ihr Abfrage-Dialogfeld, das nach Contract_1 gleich E und Contract_2 gleich R filtert](assets/s_ncs_admin_survey_read_responses_edit.png)

Die bereitgestellten Antworten für jedes Formular können in Feldern oder Titeln verwendet werden. Verwenden Sie die folgende Syntax für Inhalte, die in einem archivierten Feld gespeichert sind:

```html
<%= ctx.webAppLogRcpData.name of the archived field %
```

>[!NOTE]
>
>Die Syntax für andere Feldtypen wird in [diesem Abschnitt](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/data/query/query-editor){target="_blank"} (Dokumentation zu Campaign v8) beschrieben.

### Speichereinstellungen {#storage-settings}

Sie können Antworten auf Umfragen im XML-Format archivieren. Auf diese Weise können Sie eine Rohkopie der gesammelten Antworten speichern, was bei übermäßiger Standardisierung der Daten in einer Einzelauflistung nützlich sein kann. [Weitere Informationen](publish-track-and-use-collected-data.md#standardizing-data)

>[!CAUTION]
>
>Die Archivierung von Rohantworten wirkt sich auf den erforderlichen Speicherplatz aus. Verwenden Sie diese Option mit Bedacht.

Gehen Sie dazu wie folgt vor:

* Öffnen Sie die Umfrageeigenschaften über die Schaltfläche **[!UICONTROL Eigenschaften]** im Tab **[!UICONTROL Bearbeiten]**.
* Wählen Sie den Link **[!UICONTROL Erweiterte Parameter]** aus und aktivieren Sie die Option **[!UICONTROL Kopie der Originalantworten speichern]**.

![Dialogfeld „Erweiterte Parameter der Web-Anwendung“ mit ausgewählter Option Kopie der unbearbeiteten Antworten speichern.](assets/s_ncs_admin_survey_xml_archive_option.png)

Sie können sie standardmäßig für alle Umfragen aktivieren (diese Option wird bei der Veröffentlichung der Umfrage angewendet). Erstellen Sie dazu die Option **[!UICONTROL NmsWebApp_XmlBackup]** und weisen Sie den Wert **[!UICONTROL 1]** zu, wie unten gezeigt:

![Optionsknoten in Administration, Platform mit der Option „NmsWebApp_XmlBackup“, erstellt mit dem Wert 1.](assets/s_ncs_admin_survey_xml_global_option.png)

## Verwaltung der Punktzahl {#score-management}

Sie können den auf den Formularseiten bereitgestellten Optionen eine Punktzahl zuweisen. Punktzahlen können nur mit geschlossenen Fragen verknüpft werden: Kontrollkästchen, Wert aus einer Dropdown-Liste, Abonnement usw.

![Kombinationsfeld Registerkarte „Allgemein“ mit Werten auf der Treuekarte „Standard“ für VIP mit einer Bewertungsspalte von 2,00 bis 10,00.](assets/s_ncs_admin_survey_score_create.png)

Die Punkte werden kumuliert und auf dem Server gespeichert, wenn die Seite bestätigt wird, d. h. wenn der Benutzer auf die Schaltfläche **[!UICONTROL Weiter]** oder **[!UICONTROL Beenden]** klickt.

>[!NOTE]
>
>Sie können dafür positive oder negative sowie ganzzahlige oder nicht-ganzzahlige Werte verwenden.

Die Punktzahl kann in Tests oder Scripts verwendet werden.

>[!CAUTION]
>
>Die Punktzahl kann nicht in den Sichtbarkeitsbedingungen für Felder verwendet werden, die sich auf derselben Seite befinden. Sie kann jedoch auf nachfolgenden Seiten verwendet werden.

* Um Punkte in Tests einzubeziehen, verwenden Sie in der Test-Berechnungsformel wie unten gezeigt das Feld **[!UICONTROL Punktzahl]**:

  ![Testen Sie die Aktivität mit einer Bedingung für einen Wert größer als 6, indem Sie das Feld Score im Kontextdokument auswählen.](assets/s_ncs_admin_survey_score_in_a_test.png)

* Sie können die Punktzahl in einem Script verwenden.

**Beispiel**: Berechnen Sie eine Punktzahl und verwenden Sie sie als Bedingung für die Anzeige der nächsten Seite:

* In einer Umfrage können Sie Benutzern mithilfe der Auswahl für die nächste Seite unterschiedliche Punktzahlen entsprechend dem in der Dropdown-Liste ausgewählten Wert zuweisen.

  ![Dropdown-Feld der Klassenstufen, Vorschule bis College, mit Werten von 2,00 bis 7,00.](assets/s_ncs_admin_survey_score_exa.png)

* Diese Punktzahl kann abhängig von der ausgewählten Option mit einem zweiten Wert kombiniert werden:

  ![Multiple-Choice-Feld Sie sind… mit einem Elternteil von 7,00 und einem Schüler von 2,00,](assets/s_ncs_admin_survey_score_exb.png)

* Wenn der Benutzer die Schaltfläche **[!UICONTROL Weiter]** auswählt, werden die beiden Werte addiert.

  ![Begrüßungsseite mit Junior High in der Level-Liste ausgewählt und der Parent-Option unter Status ausgewählt.](assets/s_ncs_admin_survey_score_exe.png)

* Auf die anzuzeigende Seite können entsprechend der Punktzahl Bedingungen angewendet werden. Dies wird wie folgt konfiguriert:

  ![Testaktivität mit der Bedingung „Verzweigung bearbeiten“: Score größer als 7,00.](assets/s_ncs_admin_survey_score_exd.png)

  ![Die Testaktivität wird zu Stufe 1 weitergeleitet, wenn der Score unter 7 liegt, zu Stufe 2, wenn er gleich 7 ist, und zu Stufe 3 über 7.](assets/s_ncs_admin_survey_score_exg.png)

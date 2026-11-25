---
product: campaign
title: Beispiele für verteiltes Marketing
description: Beispiele für verteiltes Marketing
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 7825426b-c9e4-49e9-840c-dc6d6d836fbe
TQID: https://experienceleague.adobe.com/fCNtLvuBs2xnlBx-Eu-6AIDkle5YpR0z9pecVRJJbQA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 80%
---
# Beispiele für verteiltes Marketing{#distributed-marketing-samples}


## Erstellen einer lokalen Kampagne (Formular) {#creating-a-local-campaign--by-form-}

Die Web-Schnittstelle vom Typ **Standardformular** erfordert die Verwendung einer **Web-Anwendung**. Je nach Konfiguration kann diese Web-Anwendung jeden Typ definierter personalisierter Elemente enthalten. Sie können beispielsweise Links vorschlagen, um die Zielgruppe, das Budget, den Inhalt usw. über dedizierte APIs auszuwerten.

>[!NOTE]
>
>Die in diesem Beispiel verwendete Web-Anwendung ist keine Web-Anwendung, die in Adobe Campaign vorkonfiguriert vorhanden ist. Um ein Formular in einer Kampagne zu verwenden, müssen Sie die dedizierte Web-Anwendung erstellen.

Klicken Sie beim Erstellen der Kampagnenvorlage auf das Symbol **[!UICONTROL Zoom]** in der Option **[!UICONTROL Web-Schnittstelle]** des Links **[!UICONTROL Erweiterte Kampagnenparameter...]**, um auf Details der Web-Anwendung zuzugreifen.

![Erweiterte Einstellungen, Registerkarte „Verteiltes Marketing“: Feld in der Web-Benutzeroberfläche mit hervorgehobenem Symbol „Link bearbeiten“.](assets/mkg_dist_local_op_form1.png)

>[!NOTE]
>
>Die Konfiguration der Webanwendung kann nur in der Kampagnenvorlage vorgenommen werden.

Wählen Sie im Tab **[!UICONTROL Bearbeiten]** die Aktivität **Kampagnenbestellung** aus und öffnen Sie sie, um auf ihren Inhalt zuzugreifen.

![Workflow der Web-Anwendung, bei dem die Seitenaktivität „Kampagnenbestellung“ geöffnet wurde, um den Inhalt anzuzeigen.](assets/mkg_dist_web_app1.png)

Im vorliegenden Beispiel enthält die Aktivität **Kampagnenbestellung**:

* Felder, die von der Lokalstelle bei der Bestellung angegeben werden;

  ![Felder der Kampagnenbestellseite (Kontaktdatum, bevorzugter Kanal, Alterssegment, Bild, Nachricht) und ihr Web-Formular.](assets/mkg_dist_web_app2.png)

* Links, die der Lokalstelle die Auswertung der Kampagne ermöglichen (z. B. Zielgruppe, Budget, Inhalt etc.);

  ![Auswerten der Zielgruppenbestimmung, Auswerten des Budgets und Auswerten der Links für Inhalte auf der Seite und im Web-Formular.](assets/mkg_dist_web_app3.png)

* Scripts, die die Berechnung und Anzeige der Ergebnisse der vorhergehenden Auswertungen ermöglichen.

  ![Seitenstruktur mit Hervorhebung von Zielgruppenbestimmungsergebnis, Budgetergebnis und Inhaltsergebniselementen.](assets/mkg_dist_web_app4.png)

Im vorliegenden Beispiel werden die folgenden APIs verwendet:

* Zur Zielgruppenauswertung:

  ```
  var res = nms.localOrder.EvaluateTarget(ctx.localOrder);
  ```

* Zur Budgetauswertung:

  ```
  var res = nms.localOrder.EvaluateDeliveryBudget(ctx.@deliveryId, NL.XTK.parseNumber(ctx.@compt));
  ```

* Zur Inhaltsauswertung:

  ```
  var res = nms.localOrder.EvaluateContent(ctx.localOrder, ctx.@deliveryId, "html", resSeed.@id);
  ```

## Erstellen einer partizipativen Kampagne (mit Zielgruppenvalidierung) {#creating-a-collaborative-campaign--by-target-approval-}

### Einleitung {#introduction}

Sie sind Marketing-Führungskraft für eine große Modemarke, die über einen Online-Shop und mehrere Geschäfte in den USA verfügt. Zum Frühlingsanfang möchten Sie Ihre besten Kundinnen und Kunden von einem Sonderangebot profitieren lassen – 50 % Rabatt auf alle Kleider in Ihrem Katalog.

Dieses Angebot soll nur den Kunden unterbreitet werden, die seit Jahresbeginn für mehr als 300 € in einer Ihrer Filialen eingekauft haben.

Sie entschließen sich daher, mithilfe der Distributed-Marketing-Option eine partizipative Kampagne mit Zielgruppenvalidierung zu erstellen: Diese ermöglicht es Ihnen, die zuvor beschriebenen besten Kunden Ihrer Filialen je nach Region auszuwählen und ihnen das entsprechende Angebot zukommen zu lassen.

Der erste Teil des Beispiels stellt die Perspektive der Lokalstellen dar: Sie erhalten bei der Erstellung der Kampagne eine Benachrichtigungs-E-Mail, über die sie die Kampagne konfigurieren, auswerten und bestellen können.

Der zweite Teil detailliert, wie diese Kampagnenart von der Zentralstelle erstellt wird.

Zusammenfassend sind folgende Etappen zu durchlaufen:

**Lokalstellenseitig**

1. Rufen Sie über die Benachrichtigung bezüglich der Erstellung der Kampagne die von der Zentralstelle ausgewählte Kontaktliste auf.
1. Wählen Sie die gewünschten Kontakte aus und validieren Sie Ihre Teilnahme an der Kampagne.

**Zentralstellenseitig**

1. Erstellen Sie eine **[!UICONTROL Datenverteilung]**.
1. Erstellen Sie die partizipative Kampagne.
1. Veröffentlichen Sie die Kampagne.

### Teilnehmende Lokalstellen {#local-entity-side}

1. Die zur Teilnahme an der Kampagne ausgewählten Lokalstellen erhalten per E-Mail eine Benachrichtigung.

   ![E-Mail zur Zielgruppenvalidierung mit dem Link Zugriff auf Ihre Kontaktliste und Zielgruppenbestimmung validieren.](assets/mkg_dist_use_case_target_valid8.png)

1. Über den in der Benachrichtigung enthaltenen Link **[!UICONTROL Kontaktliste aufrufen und Zielgruppenbestimmung validieren]** hat die Lokalstelle per Web-Schnittstelle Zugriff auf die Liste ihrer für die Kampagne ausgewählten Kontakte.

   ![Web-Seite der Zielgruppenvalidierung mit den Kontrollkästchen der Zielgruppenkontakte und der Schaltfläche Zielgruppe validieren.](assets/mkg_dist_use_case_target_valid9.png)

1. Die Lokalstelle entnimmt der Liste die Kontakte, die vor Kurzem bereits ein ähnliches Angebot erhalten haben.

   ![Target-Validierungsseite mit drei nicht aktivierten Kontakten und einem Kommentar, der die Löschungen erklärt.](assets/mkg_dist_use_case_target_valid10.png)

Nach den Validierungen kann die Kampagne automatisch beginnen.

### Zuständige Zentralstelle {#central-entity-side}

#### Erstellen einer Datenverteilungs-Aktivität {#creating-a-data-distribution-activity}

1. Zur Einrichtung einer partizipativen Kampagne (mit Zielgruppenvalidierung) müssen Sie zunächst eine **[!UICONTROL Datenverteilungs-Aktivität]** erstellen. Klicken Sie dafür im Ordner **[!UICONTROL Ressourcen > Kampagnenverwaltung > Datenverteilung]** des Campaign-Explorers auf das Symbol **[!UICONTROL Neu]**.

   ![Registerkarte „Allgemein“ der Datenverteilung: Zielgruppendimension, Verteilungsfeld, Herkunft, Zuweisungstyp Lokalstelle.](assets/mkg_dist_use_case_target_valid3.png)

1. Geben Sie im Tab **[!UICONTROL Allgemein]** folgende Parameter an:

   * die **[!UICONTROL Zielgruppendimension]**. Die **Datenverteilung** erfolgt hier für die **Empfänger**.
   * den **[!UICONTROL Verteilungstyp]** Sie können eine **Feste Größe** oder eine **Größe in Prozent** auswählen.
   * den **[!UICONTROL Zuweisungstyp]**. Wählen Sie die Option **Lokalstelle**.
   * den **[!UICONTROL Verteilungstyp]** Das Feld **[!UICONTROL Herkunft (@origin)]** aus der Empfängertabelle ermöglicht es hier, die Relation zwischen Kontakt und Lokalstelle zu identifizieren.
   * Das Feld **[!UICONTROL Validierungsspeicherung]**. Wählen Sie die Option **Lokale Validierung eines Empfängers**.

1. Geben Sie im Tab **[!UICONTROL Aufschlüsselung]** folgende Parameter an:

   * den **[!UICONTROL Wert des Verteilungsfelds]**, der den an der vorgesehenen Kampagne beteiligten Lokalstellen entspricht;
   * den **[!UICONTROL Titel]** der Lokalstelle;
   * die **[!UICONTROL Größe]** (fest oder in Prozent). Der **Standardwert 0** bewirkt eine Auswahl aller mit der jeweiligen Lokalstelle in Verbindung stehender Empfänger.

   ![Registerkarte Datenverteilung Aufschlüsselung mit den Werten der Ost-, Nord-, Süd- und West-Verteilung und den Lokalstellen.](assets/mkg_dist_use_case_target_valid4.png)

1. Speichern Sie die neue Datenverteilung.

#### Erstellen einer partizipativen Kampagne {#creating-a-collaborative-campaign}

1. Erstellen Sie vom Ordner **[!UICONTROL Kampagnenverwaltung > Kampagnen]** des Campaign-Explorers aus eine neue **[!UICONTROL partizipative Kampagne (mit Zielgruppenvalidierung)]**.
1. Erstellen Sie auf der Registerkarte **[!UICONTROL Zielgruppenbestimmungen und Workflows]** einen Workflow für die Kampagne. Dieser muss eine Aktivität vom Typ **Aufspaltung** enthalten, deren **[!UICONTROL Begrenzung der Anzahl von Datensätzen]** durch die **[!UICONTROL Datenverteilung]** festgelegt wird.

   ![Begrenzung der Anzahl der aufgeteilten Datensätze auf Durch Datenverteilung mithilfe der Lokalstellen-Verteilung auf festgelegt.](assets/mkg_dist_use_case_target_valid5.png)

1. Fügen Sie eine Aktivität **[!UICONTROL Lokale Validierung]** hinzu, in der Sie folgende Parameter festlegen können:

   * den Inhalt der Benachrichtigung, die die Lokalstellen erhalten;
   * die Validierungserinnerung;
   * die erwartete Bearbeitung der Kampagne.

   ![Lokale Validierungsaktivität: Zielgruppenvalidierungsbenachrichtigung, Validierungstyp, Vorlage und Beschreibung für Lokalstellen.](assets/mkg_dist_use_case_target_valid7.png)

1. Speichern Sie die Kampagne.

#### Veröffentlichen der Kampagne {#publishing-the-campaign}

Fügen Sie nun über den Tab **[!UICONTROL Kampagnen]** ein **Kampagnenkit** hinzu.

1. Wählen Sie **[!UICONTROL Referenzkampagne]**. Auf der Registerkarte **[!UICONTROL Bearbeiten]** des Kits können Sie den **[!UICONTROL Validierungsmodus]** für Ihre Kampagne wählen:

   * Im Modus **Manuell** nehmen die Lokalstellen an der Kampagne teil, wenn Sie die Einladung der Zentralstelle akzeptieren. Sie können bei Bedarf die vorausgewählten Kontakte löschen. Eine Validierung der Kampagnenteilnahme durch eine vorgesetzte Person ist zwingend erforderlich.
   * Im Modus **Automatisch** sind die Lokalstellen verpflichtet, an der Kampagne teilzunehmen, sofern sie sich nicht manuell abmelden. Sie können Kontakte löschen, ohne dass eine Genehmigung erforderlich ist.

   ![Dialogfeld Kampagnenkit-Erstellung , wobei die Referenzkampagne und das Feld Validierungsmodus auf Manuell gesetzt sind.](assets/mkg_dist_use_case_target_valid.png)

1. Im Tab **[!UICONTROL Beschreibung]** können Sie eine Beschreibung der Kampagne hinzufügen und Dokumente anhängen, die den Lokalstellen übermittelt werden.

   ![Registerkarte „Kampagnenkit-Beschreibung“ mit Paketbeschreibung und Liste der beigefügten Dokumente.](assets/mkg_dist_use_case_target_valid1.png)

1. Validieren Sie das Kit und starten Sie den Workflow, um das Kit zu veröffentlichen und es für die Lokalstellen in der Kampagnenkit-Liste zur Verfügung zu stellen.

   ![Paket-Dashboard mit der Schaltfläche Paket genehmigen , das den Status in Bearbeitung anzeigt.](assets/mkg_dist_use_case_target_valid2.png)

## Erstellen einer partizipativen Kampagne (Formular) {#creating-a-collaborative-campaign--by-form-}

### Einleitung {#introduction-1}

Sie sind zuständig für das Marketing einer großen Make-up-Marke, die einen Online-Shop und mehrere Geschäfte in den gesamten USA hat. Um Ihr Lager zu räumen, möchten Sie ein Sonderangebot für zwei unterschiedliche Kundenkategorien erstellen: Die erste Kategorie enthält alle Personen, die älter als 30 sind und Produkte für reifere Haut angeboten bekommen sollen. Die zweite Kategorie enthält Personen unter 30 Jahren, die Angebote für Produkte erhalten sollen, die für unreine oder normale Haut geeignet sind.

Sie entschließen sich daher, mithilfe der Option „Dezentrales Marketing“ eine kollaborative Kampagne mit Formular zu erstellen. Diese ermöglicht es Ihnen, die Kundinnen und Kunden der unterschiedlichen Filialen nach Altersgruppen auszuwählen. Diese Personen erhalten einen E-Mail-Versand mit einem speziellen Angebot, das entsprechend ihrer Altersgruppe personalisiert wurde.

Der erste Teil des Beispiels stellt die Perspektive der Lokalstellen dar: Sie erhalten bei der Erstellung der Kampagne eine Benachrichtigungs-E-Mail, über die sie die Kampagne konfigurieren, auswerten und bestellen können.

Der zweite Teil detailliert, wie diese Kampagnenart von der Zentralstelle erstellt wird.

Zusammenfassend sind folgende Etappen zu durchlaufen:

**Lokalstellenseitig**

1. Rufen Sie über die Benachrichtigung bezüglich der Erstellung der Kampagne das Online-Formular auf.
1. Passen Sie die lokal Kampagne an, indem Sie Zielgruppe, Inhalt und Versandumfang angeben.
1. Evaluieren Sie die lokale Anpassung und überarbeiten Sie sie, sofern notwendig.
1. Validieren Sie Ihre Teilnahme.
1. Der Manager (der Lokal- oder Zentralstelle) genehmigt Konfiguration und Teilnahme.

**Zentralstellenseitig**

1. Erstellen Sie die partizipative Kampagne.
1. Konfigurieren Sie die **[!UICONTROL Erweiterten Kampagnenparameter...]** so, wie Sie es für eine lokale Kampagne tun würden.
1. Konfigurieren Sie den Kampagnen- sowie den Versand-Workflow wie für eine lokale Kampagne.
1. Aktualisieren Sie das Webformular.
1. Erstellen und veröffentlichen Sie das Kampagnenkit.

### Teilnehmende Lokalstellen {#local-entity-side-1}

1. Die zur Teilnahme an der Kampagne ausgewählten Lokalstellen werden per E-Mail über die Veröffentlichung der Kampagne benachrichtigt.

   ![Registrierung für die Kampagnen-E-Mail mit dem Link Für die Kampagne registrieren für Lokalstellen.](assets/mkg_dist_use_case_form_7.png)

1. Jede Lokalstelle füllt das personalisierte Formular aus und:

   * wertet Zielgruppe und Budget aus,
   * überprüft die Vorschau des Versandinhalts,
   * validiert ihre Teilnahme.

     ![Web-Formular für Kampagnenbestellungen mit Auswertungs-Links, einer Bildvorschau und der Schaltfläche „Validieren“.](assets/mkg_dist_use_case_form_8.png)

1. Der für die Validierung der Bestellungen verantwortliche Benutzer genehmigt die Teilnahme.

   ![Seite zur Validierung von Kampagnenbestellungen mit Bestelldetails, Bestellkommentar und der Schaltfläche Validieren.](assets/mkg_dist_use_case_form_9.png)

### Zuständige Zentralstelle {#central-entity-side-1}

1. Um eine partizipative Kampagne mit Formular zu erstellen, muss zunächst eine Referenzkampagne mithilfe der Vorlage **Partizipative Kampagne (Formular) (opCollaborativeByForm)** erstellt werden.

   ![Dialogfeld „Neue Marketing-Kampagne“ mithilfe der Vorlage Partizipative Kampagne (Formular) .](assets/mkg_dist_use_case_form_1.png)

1. Klicken Sie auf der Registerkarte **[!UICONTROL Bearbeiten]** der Kampagne auf den Link **[!UICONTROL Erweiterte Kampagnenparameter...]**, um die Kampagne wie eine lokale Kampagne zu konfigurieren. Siehe [Erstellung einer lokalen Kampagne (Standardformular)](#creating-a-local-campaign--by-form-).

   ![Erweiterte Einstellungen, Registerkarte „Verteiltes Marketing“: Partizipatives Marketing, Formularebene konfigurierbar, Standardwerte.](assets/mkg_dist_use_case_form_2.png)

1. Konfigurieren Sie den Kampagnen-Workflow und das Webformular. Siehe [Erstellung einer lokalen Kampagne (Standardformular)](#creating-a-local-campaign--by-form-).
1. Erstellen Sie das Kampagnenkit. Geben Sie hierbei die Ausführungsplanung sowie die betroffenen Lokalstellen an.

   ![Dialogfeld Kampagnenkit mit Referenz-Kampagnen, Ausführungsplanung, Fristen und Liste der lokalen Entitäten.](assets/mkg_dist_use_case_form_3.png)

1. Schließen Sie die Konfiguration des Kits mit der Auswahl des Validierungsmodus im Tab **[!UICONTROL Bearbeiten]** ab.

   ![Dropdown-Liste „Genehmigungsmodus“ mit manuellen und automatischen Optionen.](assets/mkg_dist_use_case_form_4.png)

1. Erfassen Sie bei Bedarf auf der Registerkarte **[!UICONTROL Beschreibung]** nähere Hinweise zu der geplanten Kampagne. Diese Beschreibung ist in der Benachrichtigung enthalten, die die Lokalstellen bei der Veröffentlichung des Kits erhalten. An dieser Stelle können dem Kampagnenkit zudem relevante Dokumente angehängt werden.

   ![Registerkarte „Paketbeschreibung“ mit der Option Benachrichtigungs-E-Mail, Nachricht für die Lokalstelle und angehängte Dokumente.](assets/mkg_dist_use_case_form_5.png)

1. Validieren Sie das Kit, um es in der Kampagnenkit-Liste zu veröffentlichen.

   ![Schaltfläche Paket genehmigen öffnen Sie das Dialogfeld Aktion im Paket mit den Optionen Akzeptieren und Ablehnen.](assets/mkg_dist_use_case_form_6.png)

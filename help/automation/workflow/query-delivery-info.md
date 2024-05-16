---
product: campaign
title: Abfrage zu Versandinformationen
description: Erfahren Sie, wie Sie Versandinformationen abfragen können
feature: Query Editor
role: User
exl-id: d11a1992-c07b-4133-8f0a-65f1b7552a99
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1552'
ht-degree: 73%

---

# Abfragen von Informationen zum Versand {#querying-delivery-information}



## Anzahl der Klicks für einen bestimmten Versand {#number-of-clicks-for-a-specific-delivery}

In diesem Beispiel wird die Anzahl der Klicks von Empfängern in einem bestimmten Zeitraum gesucht. Die Klicks werden in den Trackinglogs der Empfänger gespeichert. Letztere werden über die E-Mail-Adresse identifiziert. Diese Abfrage basiert auf der Tabelle **[!UICONTROL Trackinglogs der Empfänger]**.

* Welche Tabelle soll ausgewählt werden?

  Die Trackinglogs der Empfänger (**[!UICONTROL nms:trackingLogRcp]**)

* Felder, die als Ausgabespalten verwendet werden sollen?

  Primärschlüssel (mit Zählung) und E-Mail

* Nach welchen Kriterien werden die Informationen gefiltert?

  Nach einem Zeitraum und einem Element im Versandtitel

Gehen Sie für dieses Beispiel wie folgt vor:

1. Öffnen Sie das **[!UICONTROL generische Abfragetool]** und wählen Sie das Schema **[!UICONTROL Trackinglogs der Empfänger]** aus.

   ![](assets/query_editor_tracklog_05.png)

1. Im **[!UICONTROL Zu extrahierende Daten]** -Fenster erstellen, erstellen wir ein Aggregat, um Informationen zu sammeln. Fügen Sie dazu den Primärschlüssel hinzu (der sich über dem **[!UICONTROL Trackinglogs der Empfänger]** element): Die Anzahl der Trackinglogs wird hierdurch ermittelt. **[!UICONTROL Primärer Schlüssel]** -Feld. Der bearbeitete Ausdruck **[!UICONTROL x=count(Primärschlüssel)]**. Dabei wird die Summe der verschiedenen Trackinglogs mit einer einzelnen E-Mail-Adresse verknüpft.

   Gehen Sie dazu wie folgt vor:

   * Verwenden Sie die Schaltfläche **[!UICONTROL Hinzufügen]** rechts neben den **[!UICONTROL Ausgabespalten]**. Wählen Sie im Fenster **[!UICONTROL Formeltyp]** die Option **[!UICONTROL Formel von einem Ausdruck ausgehend erstellen]** und danach **[!UICONTROL Weiter]** aus. Verwenden Sie im Fenster **[!UICONTROL Feldauswahl]** die Option **[!UICONTROL Erweiterte Auswahl]**.

     ![](assets/query_editor_tracklog_06.png)

   * Verwenden Sie im Fenster **[!UICONTROL Formeltyp]** eine Aggregatfunktion. In diesem Fall ist das die Zählung des Primärschlüssels.

     Wählen Sie im Abschnitt **[!UICONTROL Aggregat]** die Option **[!UICONTROL Aggregatfunktionen]** und klicken Sie auf **[!UICONTROL Zählung]**.

     ![](assets/query_editor_nveau_18.png)

     Klicken Sie auf **[!UICONTROL Weiter]**.

   * Wählen Sie nun das Feld **[!UICONTROL Primärschlüssel (@id)]** aus. Die Ausgabespalte **[!UICONTROL count(Primärschlüssel)]** wurde konfiguriert.

     ![](assets/query_editor_nveau_19.png)

1. Wählen Sie das andere Feld aus, das in der Ausgabespalte angezeigt werden soll. Im **[!UICONTROL Verfügbare Felder]** -Spalte, öffnen Sie die **[!UICONTROL Empfänger]** Knoten und wählen Sie **[!UICONTROL Email]**. Dies führt zur Zuordnung eines jeden Trackinglogs zum entsprechenden Empfänger.********

   ![](assets/query_editor_nveau_20.png)

1. Konfigurieren Sie die Spaltensortierung so, dass die aktivsten Empfänger (mit den meisten Trackinglogs) zuerst angezeigt werden. Überprüfen **[!UICONTROL Ja]** im **[!UICONTROL Absteigende Sortierung]** Spalte.

   ![](assets/query_editor_nveau_64.png)

1. Im folgenden Schritt können Sie die Abfrageergebnisse weiter einschränken und beispielsweise aus allen Logs jene herausfiltern, die unter 15 Tage alt sind und deren Sendungen sich auf eine Gartenausstellung beziehen.

   Gehen Sie dazu wie folgt vor:

   * Konfigurieren Sie einen Datenfilter. Wählen Sie dazu **[!UICONTROL Filterbedingungen]** und danach **[!UICONTROL Weiter]** aus.

     ![](assets/query_editor_nveau_22.png)

   * Drei Filterbedingungen sind erforderlich, um die Ergebnisse wie gewünscht einzuschränken: zwei Datumsfilter zur Eingrenzung des Zeitraums zwischen 15 Tagen vor dem aktuellen Datum und 1 Tag vor dem aktuellen Datum sowie eine weitere Bedingung, um nur Logs bezüglich bestimmter Sendungen zu erfassen.

     Im **[!UICONTROL Zielelement]** konfigurieren Sie das Datum, ab dem Trackinglogs berücksichtigt werden sollen. Wählen Sie **[!UICONTROL Hinzufügen]** aus. Eine Bedingungszeile wird angezeigt. Bearbeiten Sie die **[!UICONTROL Ausdruck]** durch Klicken auf die **[!UICONTROL Ausdruck bearbeiten]** -Funktion. Im **[!UICONTROL Feld auswählen]** auswählen **[!UICONTROL Datum (@logDate)]**.

     ![](assets/query_editor_nveau_23.png)

     Wählen Sie die **[!UICONTROL größer als]** Operator. Im **[!UICONTROL Wert]** Spalte, klicken **[!UICONTROL Ausdruck bearbeiten]** und in der **[!UICONTROL Formeltyp]** auswählen **[!UICONTROL Datumsfunktionen]**. Schließlich in **[!UICONTROL Aktuelles Datum minus n Tage]**, geben Sie &quot;15&quot;ein.

     Klicken Sie auf **[!UICONTROL Beenden]**.

     ![](assets/query_editor_nveau_24.png)

   * Zur Suche nach dem Enddatum der gewünschten Trackingperiode ist eine weitere Bedingungszeile erforderlich. **** Im **[!UICONTROL Ausdruck]** Spalte, wählen **[!UICONTROL Datum (@logDate)]** erneut.

     Wählen Sie die **[!UICONTROL kleiner als]** Operator. Im **[!UICONTROL Wert]** Spalte, klicken **[!UICONTROL Ausdruck bearbeiten]**. Gehen Sie zur Datumsverarbeitung zum **[!UICONTROL Formeltyp]** Fenster, geben Sie &quot;1&quot;ein in **[!UICONTROL Aktuelles Datum minus n Tage]**.

     Klicken Sie auf **[!UICONTROL Beenden]**.

     ![](assets/query_editor_nveau_65.png)

     Der gewünschte Zeitraum wurde konfiguriert. In der dritten Filterbedingung gilt es, nur einen bestimmten Versand zu berücksichtigen.

   * Klicken Sie auf **[!UICONTROL Hinzufügen]** -Funktion, um eine weitere Filterbedingung zu erstellen. Im **[!UICONTROL Ausdruck]** Spalte, klicken **[!UICONTROL Ausdruck bearbeiten]**. Im **[!UICONTROL Feld auswählen]** auswählen **[!UICONTROL Titel]** im **[!UICONTROL Versand]** Knoten.

     Klicken Sie auf **[!UICONTROL Beenden]**.

     ![](assets/query_editor_nveau_66.png)

     Gesucht wird ein Versand zum Thema &quot;Gartenausstellung&quot;. Wählen Sie den Operator **[!UICONTROL enthält]** und geben Sie im Feld **[!UICONTROL Wert]** &quot;Garten&quot; ein, wenn Sie sich nicht an den genauen Versandtitel erinnern können.

     ![](assets/query_editor_nveau_25.png)

1. Da in unserem Beispiel keine spezielle Formatierung erforderlich ist, können Sie im Fenster **[!UICONTROL Datenformatierung]** direkt auf **[!UICONTROL Weiter]** klicken.
1. Klicken Sie nun im **[!UICONTROL Datenvorschau]**-Fenster auf **[!UICONTROL Datenvorschau starten]**, um die Anzahl an Trackinglogs für jeden Versandempfänger abzurufen.

   Die Trackinglogs werden wie gewünscht in absteigender Reihenfolge angezeigt.

   ![](assets/query_editor_tracklog_04.png)

   Die höchste Loganzahl für einen Benutzer beträgt bei diesem Versand 8. 20 verschiedene Benutzer haben die E-Mail dieses Versands geöffnet oder auf einen Link geklickt.

## Empfänger, die keine Nachricht geöffnet haben {#recipients-who-did-not-open-any-delivery}

In diesem Beispiel möchten wir Empfänger herausfiltern, die in den letzten sieben Tagen keine E-Mail geöffnet haben.

Gehen Sie wie folgt vor:

1. Ziehen Sie eine **[!UICONTROL Abfrage]** in den Workflow-Arbeitsbereich und öffnen Sie sie.
1. Wählen Sie **[!UICONTROL Abfrage bearbeiten]** aus und wählen Sie für die Zielgruppen- und Filterdimension die Option **[!UICONTROL Empfänger]** aus.

   ![](assets/query_recipients_1.png)

1. Wählen Sie **[!UICONTROL Filterbedingungen]** und danach **[!UICONTROL Weiter]** aus.
1. Verwenden Sie die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie **[!UICONTROL Trackinglogs]** aus.
1. Wählen Sie für den **[!UICONTROL Operator]** des **[!UICONTROL Trackinglogs]**-Ausdrucks **[!UICONTROL Nicht wie]** aus.

   ![](assets/query_open_1.png)

1. Fügen Sie einen weiteren Ausdruck hinzu. Wählen Sie in der **[!UICONTROL URL]**-Kategorie die Option **[!UICONTROL Typ]** aus.
1. Wählen Sie dann für den **[!UICONTROL Operator]** die Option **[!UICONTROL Gleich]** und für den **[!UICONTROL Wert]** die Option **[!UICONTROL Offen]** aus.

   ![](assets/query_open_2.png)

1. Fügen Sie einen weiteren Ausdruck hinzu und wählen Sie **[!UICONTROL Datum]** aus. Der **[!UICONTROL Operator]** sollte **[!UICONTROL Später als]** sein.

   ![](assets/query_open_3.png)

1. Um als Wert die letzten sieben Tage festzulegen, wählen Sie im Feld **[!UICONTROL Wert]** die Schaltfläche **[!UICONTROL Ausdruck bearbeiten]** aus.
1. Wählen Sie in der Kategorie **[!UICONTROL Funktion]** die Option **[!UICONTROL Aktuelles Datum abzüglich n Tage]** aus und fügen Sie die gewünschte Anzahl der Tage ein. In unserem Fall sind das die letzten sieben Tage.

   ![](assets/query_open_4.png)

Ihre ausgehende Transition wird Empfänger enthalten, die in den letzten sieben Tagen keine E-Mail geöffnet haben.

Wenn Sie hingegen Empfänger filtern möchten, die mindestens eine E-Mail geöffnet haben, sollte Ihre Abfrage wie folgt lauten. Beachten Sie, dass in diesem Fall die **[!UICONTROL Filterdimension]** auf **[!UICONTROL Trackinglogs (Empfänger)]** gesetzt werden sollte.

![](assets/query_open_5.png)

## Empfänger, die einen Versand geöffnet haben {#recipients-who-have-opened-a-delivery}

Im folgenden Beispiel erfahren Sie, wie Sie alle Profile auswählen können, die in den vergangenen zwei Wochen einen Versand geöffnet haben.

1. Verwenden Sie Trackinglogs, um Profile auszuwählen, die einen Versand geöffnet haben. sie werden in einer verknüpften Tabelle gespeichert: Wählen Sie zunächst diese Tabelle in der Dropdown-Liste der **[!UICONTROL Filterdimension]** wie unten gezeigt:

   ![](assets/s_advuser_query_sample1.0.png)

1. Wählen Sie aus der Liste der Einschränkungsfilter die Filterbedingungen aus und klicken Sie auf die Schaltfläche **[!UICONTROL Ausdruck bearbeiten]**. Markieren Sie nun im Knoten der Trackinglogs das Feld **[!UICONTROL Datum]**.

   ![](assets/s_advuser_query_sample1.1.png)

   Klicken Sie auf **[!UICONTROL Beenden]**, um die Auswahl zu bestätigen.

   Um nur die Trackinglogs der letzten 14 Tage abzurufen, müssen Sie den Operator **[!UICONTROL Größer als]** wählen.

   ![](assets/s_advuser_query_sample1.4.png)

   Klicken Sie in der **[!UICONTROL Wert]**-Spalte wiederum auf **[!UICONTROL Ausdruck bearbeiten]**, um die Formel zur Datumsberechnung zu definieren. Kreuzen Sie die Option **[!UICONTROL Aktuelles Datum abzüglich n Tage]** an und geben Sie 15 ein.

   ![](assets/s_advuser_query_sample1.5.png)

   Klicken Sie auf **[!UICONTROL Beenden]** Schaltfläche des Formelfensters. Klicken Sie im Filterfenster auf die Schaltfläche **[!UICONTROL Vorschau]** , um die Targeting-Kriterien zu überprüfen.

   ![](assets/s_advuser_query_sample1.6.png)

## Verhalten der Empfänger nach einem Versand filtern {#filtering-recipients--behavior-folllowing-a-delivery}

In einem Workflow ermöglichen die Aktivitäten **[!UICONTROL Abfrage]** und **[!UICONTROL Aufspaltung]** die Auswahl eines Verhaltens, das auf einen früheren Versand folgt. Diese Auswahl erfolgt mithilfe des Filters **[!UICONTROL Versandempfänger]**.

* Ziel des Beispiels

  In einem Versand-Workflow gibt es mehrere Möglichkeiten des weiteren Vorgehens nach einem ersten E-Mail-Kontakt. Diese werden über die Aktivität **[!UICONTROL Aufspaltung]** gesteuert.

* Kontext

  Ein Versand zum Thema &quot;Sommersport-Angebote&quot;. Vier Tage nach dem Versand werden zwei weitere Sendungen geschaltet: &quot;Wassersport-Angebote&quot; und ein Erinnerungsschreiben bezüglich des ersten Sommersport-Angebots.

  Der Versand &quot;Wassersport-Angebote&quot; richtet sich an Empfänger, die in der ersten E-Mail auf Inhalte zum Thema Wassersport geklickt haben. Diese Klicks zeugen vom Interesse der Empfänger. Ähnliche Angebote könnten daher ebenfalls für diese Interessenten infrage kommen. Empfänger hingegen, die die &quot;Sommersport-Angebote&quot;-E-Mail nicht angeklickt haben, bekommen dieselben Angebote wie zuvor.

Die folgenden Schritte zeigen die Konfiguration der **[!UICONTROL Aufspaltung]** unter Berücksichtigung von zwei Verhaltensmustern:

1. Ziehen Sie die Aktivität **[!UICONTROL Aufspaltung]** in den Workflow. Sie steuert die Zuordnung der Empfänger des ersten Versands zu einer der zwei folgenden Sendungen. Dies geschieht in Abhängigkeit vom Verhalten der Empfänger infolge des ersten Versands.

   ![](assets/query_editor_ex_09.png)

1. Öffnen Sie die **[!UICONTROL Aufspaltung]** ankreuzen. Im **[!UICONTROL Allgemein]** Geben Sie einen Titel ein: **Aufspaltung nach Verhalten** beispielsweise.

   ![](assets/query_editor_ex_04.png)

1. Konfigurieren Sie im Tab **[!UICONTROL Teilmengen]** die erste Verzweigung der Aufspaltung. Nennen Sie diesen Zweig beispielsweise &quot;**Haben geklickt**&quot;.
1. Wählen Sie die **[!UICONTROL Filterbedingung für die Eingangspopulation hinzufügen]** -Option. Klicks **[!UICONTROL Bearbeiten]**.
1. Doppelklicken Sie im Fenster **[!UICONTROL Zielgruppen- und Filterdimension]** auf den Filter **[!UICONTROL Versandempfänger]**.

   ![](assets/query_editor_ex_05.png)

1. Wählen Sie im **[!UICONTROL Zielelement]**-Fenster das auf diesen Zweig zutreffende Verhalten: **[!UICONTROL Empfänger, die geklickt haben (E-Mail)]**.

   Kreuzen Sie unterhalb die Option **[!UICONTROL Von der Transition festgelegter Versand]** an. Hierdurch werden automatisch alle vom ersten Versand angesprochenen Empfänger abgerufen.

   Die Empfänger dieses Zweigs bekommen also den Versand &quot;Wassersport-Angebote&quot;.

   ![](assets/query_editor_ex_08.png)

1. Definieren Sie die zweite Verzweigung. Dieser Zweig enthält die Folgenachrichten-E-Mail mit demselben Inhalt wie der erste Versand. Navigieren Sie zu **[!UICONTROL Untergruppen]** Registerkarte und klicken Sie auf **[!UICONTROL Hinzufügen]** , um es zu erstellen.

   ![](assets/query_editor_ex_06.png)

1. Eine weitere Unterregisterkarte wird angezeigt. Benennen Sie es &quot;**Klicks nicht**&quot;.
1. Klicks **[!UICONTROL Filterbedingung für die Eingangspopulation hinzufügen]**. Klicken Sie anschließend auf **[!UICONTROL Bearbeiten...]**.

   ![](assets/query_editor_ex_07.png)

1. Doppelklicken Sie im Fenster **[!UICONTROL Zielgruppen- und Filterdimension]** auf den Filter **[!UICONTROL Versandempfänger]**.
1. Im **[!UICONTROL Zielelement]** auswählen, wählen Sie die **[!UICONTROL Empfänger, die nicht geklickt haben (E-Mail)]** Verhalten. Wählen Sie die **[!UICONTROL Von der Transition festgelegter Versand]** -Option, wie für den letzten Zweig angezeigt.

   Die Konfiguration der **[!UICONTROL Aufspaltung]** ist abgeschlossen.

   ![](assets/query_editor_ex_03.png)

Folgende Empfängerverhalten wurden standardmäßig in der Anwendung hinterlegt:

* **[!UICONTROL Alle Empfänger,]**
* **[!UICONTROL Empfänger, denen die Nachricht erfolgreich zugestellt wurde,]**
* **[!UICONTROL Empfänger, die geöffnet oder geklickt haben (E-Mail),]**
* **[!UICONTROL Empfänger, die geklickt haben (E-Mail),]**
* **[!UICONTROL Empfänger, denen die Nachricht nicht zugestellt werden konnte,]**
* **[!UICONTROL Empfänger, die weder geöffnet noch geklickt haben (E-Mail),]**
* **[!UICONTROL Empfänger, die nicht geklickt haben (E-Mail).]**

  ![](assets/query_editor_ex_02.png)

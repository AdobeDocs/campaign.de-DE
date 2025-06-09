---
title: Erstellen von Filtern in Adobe Campaign
description: Erfahren Sie, wie Sie Ihre Daten filtern und Filter in Campaign speichern können.
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: ht
source-wordcount: '1708'
ht-degree: 100%

---

# Erstellen und Verwalten von Filtern{#create-filters}

Beim Filtern von Daten wird ein kleinerer Teil Ihrer Datenmenge ausgewählt, nämlich nur die Einträge, die bestimmten Kriterien entsprechen. Diese Untergruppe wird für bestimmte Aktionen (Aktualisierungen, Erstellung von Zielgruppen) oder Analysen verwendet.

Beim Durchsuchen von Campaign über den **[!UICONTROL Explorer]** werden die Daten in Listen angezeigt. Sie können vorhandene integrierte Filter verwenden, um auf eine bestimmte Untergruppe dieser Daten zuzugreifen: Beispielsweise Adressen in Quarantäne, nicht kontaktierte Empfänger, eine bestimmte Altersgruppe oder das Erstellungsdatum.

Sie können auch eigene Filter erstellen, diese zur späteren Verwendung speichern oder für andere Campaign-Benutzer freigeben.

Die Filterkonfiguration ermöglicht die **[!UICONTROL dynamische]** Auswahl von Daten aus einer Liste. Bei Änderung der Daten werden die gefilterten Daten aktualisiert.

>[!NOTE]
>
>Die Konfigurationseinstellungen der Benutzeroberfläche werden lokal auf Geräteebene definiert. Manchmal kann es notwendig sein, diese Daten zu bereinigen, insbesondere wenn Probleme beim Aktualisieren von Daten auftreten. Verwenden Sie dazu das Menü **[!UICONTROL Datei > Lokalen Cache löschen]**.

Die folgenden Filtertypen sind in Adobe Campaign verfügbar:

## Vordefinierte Filter{#predefined-filters}

Vordefinierte Filter sind über den Button **Filter** oberhalb jeder Liste verfügbar.

Für die Profile sind beispielsweise die folgenden integrierten Filter verfügbar:

![](assets/built-in-filters.png)

Sie können im Knoten **[!UICONTROL Profile und Zielgruppen > Vordefinierte Filter]** des Explorers auf die Filterdetails zugreifen.

>[!NOTE]
>
>Für alle anderen Datenlisten werden vordefinierte Filter im Knoten **[!UICONTROL Administration > Konfiguration > Vordefinierte Filter]** gespeichert.

Wählen Sie einen Filter aus, um dessen Definition anzuzeigen.

![](assets/predefined-filter-list.png)

Verwenden Sie die letzte Registerkarte, um die gefilterten Daten in der Vorschau anzuzeigen.

![](assets/built-in-filter-preview.png)


Integrierte vordefinierte Filter sind:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Abfrage</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Haben geöffnet<br /> </td> 
   <td> Auswahl der Empfänger, die einen Versand geöffnet haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Haben geöffnet aber nicht geklickt<br /> </td> 
   <td> Auswahl der Empfänger, die den angegebenen Versand geöffnet, aber keinen Link angeklickt haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inaktive Empfänger<br /> </td> 
   <td> Auswahl der Empfänger, die seit der angegebenen Anzahl an Monaten keinen Versand geöffnet haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Letzte Aktivität nach Gerätetyp<br /> </td> 
   <td> Auswahl der Empfänger, die unter Verwendung eines Geräts vom Typ X den Versand Y in den letzten Z Tagen angeklickt oder geöffnet haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Letzte Aktivität nach Gerätetyp (Tracking)<br /> </td> 
   <td> Auswahl der Empfänger, die unter Verwendung eines Geräts vom Typ X den Versand Y in den letzten Z Tagen angeklickt oder geöffnet haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nicht kontaktierte Empfänger<br /> </td> 
   <td> Auswahl der Empfänger, die seit X Monaten nicht über den Kanal Y kontaktiert wurden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sehr aktive Empfänger<br /> </td> 
   <td> Auswahl der Empfänger, die in den letzten X Monaten mindestens Y Mal geklickt haben.<br /> </td> 
  </tr> 
  <tr> 
 <td> E-Mail-Adresse, die auf die Blockierungsliste gesetzt wurde<br /> </td> 
    <td> Wählt Empfänger aus, deren E-Mail-Adresse sich auf der Blockierungsliste befindet.<br/> </td>
  </tr> 
  <tr> 
   <td> E-Mail-Adresse in Quarantäne<br /> </td> 
   <td> Auswahl der Empfänger, deren E-Mail-Adresse in Quarantäne ist.<br /> </td> 
  </tr> 
  <tr> 
   <td> Im Ordner mehrfach enthaltene E-Mail-Adressen<br /> </td> 
   <td> Auswahl der Empfänger, deren E-Mail-Adresse mehrfach im zugrunde liegenden Ordner enthalten ist.<br /> </td> 
  </tr> 
  <tr> 
   <td> Haben weder geöffnet noch geklickt<br /> </td> 
   <td> Auswahl der Empfänger, die den angegebenen Versand weder geöffnet noch darin auf einen Link geklickt haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Neue Empfänger (Tage)<br /> </td> 
   <td> Auswahl der Empfänger, die in den letzten X Tagen erstellt wurden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Neue Empfänger (Minuten)<br /> </td> 
   <td> Auswahl der Empfänger, die in den letzten X Minuten erstellt wurden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Neue Empfänger (Monate)<br /> </td> 
   <td> Auswahl der Empfänger, die in den letzten X Monaten erstellt wurden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Abonnement<br /> </td> 
   <td> Auswahl der Empfänger, die den angegebenen Dienst abonniert haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Klicks auf eine spezifische URL<br /> </td> 
   <td> Auswahl der Empfänger, die im Versand X auf die URL Y geklickt haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Verhalten im Anschluss an einen Versand<br /> </td> 
   <td> Auswahl der Empfänger, die nach Erhalt des Versands X mit dem Verhalten Y reagiert haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Erstellungsdatum<br /> </td> 
   <td> Auswahl der Empfänger, die im Zeitraum von vor X bis Y Monaten (jeweils aktuelles Datum abzüglich n Monate) erstellt wurden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Liste<br /> </td> 
   <td> Auswahl der Empfänger, die der angegebenen Liste angehören.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Anzahl an Klicks<br /> </td> 
   <td> Auswahl der Empfänger, die in den letzten X Monaten zwischen Y und Z Mal in Sendungen geklickt haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Anzahl an empfangenen Nachrichten<br /> </td> 
   <td> Auswahl der Empfänger, die über den angegebenen Kanal in den letzten X Monaten zwischen Y und Z Nachrichten erhalten haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Anzahl an Öffnungen<br /> </td> 
   <td> Auswahl der Empfänger, die in den letzten X Monaten zwischen Y und Z Sendungen geöffnet haben.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Name oder E-Mail<br /> </td> 
   <td> Auswahl der Empfänger nach Nachname oder E-Mail-Adresse.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nach Altersgruppen<br /> </td> 
   <td> Auswahl der Empfänger im Alter von X bis Y Jahren.<br /> </td> 
  </tr> 
 </tbody> 
</table>


### Standardfilter{#default-filters}

In den Feldern oberhalb jeder Liste können Sie den **vordefinierten Standardfilter** für diese Liste verwenden. Für die Empfängerliste können Sie standardmäßig nach dem Namen und der E-Mail-Adresse filtern.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>Das Zeichen **%** ersetzt alle Zeichenfolgen. Geben Sie beispielsweise `%@gmail.com` im E-Mail-Feld ein, um alle Profile mit einer Gmail-Adresse anzuzeigen. Geben Sie `%@L` im Nachnamenfeld ein, um alle Profile mit &quot;L&quot; im Nachnamen anzuzeigen.

Um den Standardfilter für eine Empfängerliste zu ändern, gehen Sie zum Knoten **[!UICONTROL Profile und Zielgruppen > Vordefinierte Filter]**.

Standardfilter für andere Datentypen werden im Verzeichnisknoten **[!UICONTROL Administration > Konfigurationen > Vordefinierte Filter]** konfiguriert.

Gehen Sie wie folgt vor:

1. Wählen Sie den Filter aus, der als Standardfilter dienen soll.
1. Klicken Sie auf den Tab **[!UICONTROL Parameter]** und kreuzen Sie die Option **[!UICONTROL Standardfilter für den verbundenen Dokumenttyp]** an.

   ![](assets/change-default-filter.png)

1. Deaktivieren Sie diese Option für den aktuellen vordefinierten Filter.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, um den Filter anzuwenden.
1. Gehen Sie zum Ordner &quot;Empfänger&quot; und klicken Sie auf den Button **[!UICONTROL Diesen Filter entfernen]** rechts neben dem aktuellen Filter: Der neue Standardfilter ist verfügbar.
   ![](assets/updated-default-filter.png)


## Schnellfilter{#quick-filters}

Verwenden und kombinieren Sie **Schnellfilter**, um Filter für bestimmte Felder zu definieren.

Nach dem Hinzufügen werden die Schnellfilterfelder nacheinander über der Datenliste angezeigt. Sie können unabhängig voneinander gelöscht werden.

Schnellfilter sind für jeden Benutzer und jede Benutzerin spezifisch und werden bei jeder Cache-Leerung der Client-Konsole erneut initialisiert.

Wenn Sie einen Filter wiederverwenden müssen, erstellen Sie einen **erweiterten Filter** und speichern Sie ihn. [Weitere Informationen](#advanced-filters).

Gehen Sie wie folgt vor, um einen **Schnellfilter** zu erstellen:

1. Klicken Sie mit der rechten Maustaste auf das Feld, nach dem Sie die Daten filtern möchten, und wählen Sie die Option **[!UICONTROL Nach diesem Feld filtern]** aus.

   ![](assets/quick-filter-on-this-field.png)

   Die Standard-Filterfelder werden oberhalb der Liste angezeigt.

   ![](assets/quick-filter-above-list.png)

1. Wählen Sie die Filteroptionen aus.
1. Verwenden Sie bei Bedarf das graue Symbol rechts neben einem Filter, um ihn zu entfernen.
1. Sie können Filter kombinieren, um Ihre Suche weiter einzuengen.

   ![](assets/add-filter-above-the-list.png)


Wenn Sie nach einem Feld filtern müssen, das im Formular nicht vorhanden ist, fügen Sie es in die Spalten ein und filtern Sie nach dieser Spalte. Gehen Sie dazu wie folgt vor,

1. Klicken Sie auf das Symbol **[!UICONTROL Liste konfigurieren]**.

   ![](assets/configure-list.png)

1. Wählen Sie die anzuzeigende Spalte aus, z. B. das Alter der Empfänger, und klicken Sie auf **Ok**.

   ![](assets/add-age-column.png)

1. Klicken Sie anschließend mit der rechten Maustaste in der Empfängerliste auf die Spalte **Alter** und wählen Sie **[!UICONTROL Nach dieser Spalte filtern]** aus.

   ![](assets/age-filter-on-this-column.png)

   Nun können Sie die Filteroptionen bezüglich des Alters auswählen. Fügen Sie einen weiteren Altersfilter hinzu, um einen Bereich zu definieren.

   ![](assets/filter-on-age.png)

## Erweiterte Filter{#advanced-filters}

Kombinieren Sie in **Erweiterte Filter** komplexe Kriterien. Verwenden Sie diese Filter, um eine komplexe Abfrage oder eine Kombination von Abfragen Ihrer Daten zu erstellen. Diese Filter können gespeichert und für andere Campaign-Benutzer freigegeben werden.

### Erstellen eines erweiterten Filters{#create-adv-filters}

Um einen **erweiterten Filter** zu erstellen, klicken Sie auf den Button **[!UICONTROL Filter]** und wählen Sie **[!UICONTROL Erweiterte Filter...]** aus.

![](assets/adv-filter.png)

Alternativ können Sie mit der rechten Maustaste in die Liste der zu filternden Daten klicken und **[!UICONTROL Erweiterte Filter...]** auswählen.

Definieren Sie die Filterbedingungen. Im folgenden Beispiel filtern Sie nach Empfängern, deren Kundennummer nicht mit NL beginnt und die in Paris oder Los Angeles leben.

1. Klicken Sie auf das Symbol **[!UICONTROL Ausdruck bearbeiten]** der Spalte **[!UICONTROL Ausdruck]**.

   ![](assets/edit-exp.png)

1. Wählen Sie das Feld aus, nach dem gefiltert werden soll.
1. Wählen Sie in der Dropdown-Liste den anzuwendenden Operator aus.

   ![](assets/select-operator.png)

1. Geben Sie dann in der Spalte **[!UICONTROL Wert]** den Vergleichswert an. Sie können mehrere Filter kombinieren, um Ihre Abfrage zu verfeinern. Um eine Filterbedingung hinzuzufügen, klicken Sie auf **[!UICONTROL Hinzufügen]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >Mithilfe der Pfeile in der Symbolleiste können Sie die Ausdrücke hierarchisch gliedern oder die Reihenfolge der Ausdrücke der Abfrage ändern.

1. Es stehen drei Operatoren zur Kombination von Ausdrücken zur Verfügung: **Und**, **Oder**, **Außer**. Klicken Sie auf den Pfeil, um zu **Oder** zu wechseln.

   ![](assets/select-or-operator.png)

1. Klicken Sie auf **[!UICONTROL OK]**, um den Filter zu erstellen und ihn auf die aktuelle Liste anzuwenden.

Der angewendete Filter wird oberhalb der Liste angezeigt.

![](assets/adv-filter-link.png)

Um diesen Filter zu bearbeiten oder zu ändern, klicken Sie oberhalb der Liste auf den Link mit der Beschreibung in Blau.


### Speichern eines erweiterten Filters{#save-adv-filters}

Erweiterte Filter können als [vordefinierter Filter](#predefined-filters) gespeichert werden, sodass Sie sie wiederverwenden und für andere Campaign-Benutzer freigeben können.

Gehen Sie wie folgt vor, um einen erweiterten Filter zu speichern:

1. Klicken Sie auf die Beschreibung des Filters, um ihn zu bearbeiten.
1. Klicken Sie auf **[!UICONTROL Als Filter speichern]** rechts oben im Fenster.

   ![](assets/save-as-filter.png)

1. Geben Sie einen Namen für diesen Filter ein und speichern Sie ihn.

   ![](assets/application-filter-save.png)

Der Filter wird zu den [vordefinierten Filtern](#predefined-filters) hinzugefügt. Er kann von diesem Knoten aus aktualisiert werden.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>Sie können einen Tastaturbefehl für Ihren Filter hinzufügen, um ihn über Ihre Tastatur zu aktivieren.



Dieser Filter ist auch in den vordefinierten Filtern der Empfängerliste verfügbar.

![](assets/access-to-new-predefined-filter.png)



### Verwenden eines Filters, um ein Segment zu definieren {#filter-as-segment}

Sie können Filter verwenden und kombinieren, um ein Segment der Zielpopulation zu erstellen.

Nach dem Speichern sind erweiterte Filter verfügbar, wenn Sie die Zielpopulation einer Nachricht im Abschnitt **[!UICONTROL Benutzerfilter]** auswählen.

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Verwenden Sie die Option **[!UICONTROL Empfänger von diesem Segment ausschließen]**, um nur Kontakte auszuwählen, die nicht den Filterkriterien entsprechen.


### Verwenden von Funktionen zum Erstellen erweiterter Filter{#use-functions-adv-filters}

Verwenden Sie Funktionen zur Definition des Inhalts des Filters, um erweiterte Filterfunktionen auszuführen. Der Editor für erweiterte Filter nutzt alle Funktionen des Campaign-Abfragetools.

In diesen Beispielen erfahren Sie, wie Sie erweiterte Abfragen erstellen:

* Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"} erfahren Sie, wie Sie einfache Empfängerattribute für Ihr Targeting verwenden können.
* Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=de){target="_blank"} erfahren Sie, wie Sie nach Empfängern filtern können, die in den letzten 7 Tagen nicht kontaktiert wurden.
* Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/create-a-filter.html?lang=de){target="_blank"} erfahren Sie, wie Sie eine Liste der Benutzer abrufen können, die nach aktiven Konten gefiltert werden können.
* Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=de){target="_blank"} erfahren Sie, wie Sie eine Zielgruppe für Geburtstags-E-Mails erstellen können.


### Erweiterte Parameter für vordefinierte Filter {#param-for-data-filters}

Für vordefinierte Filter sind erweiterte Parameter verfügbar. Um darauf zuzugreifen, gehen Sie zur Registerkarte **[!UICONTROL Parameter]** des Filters.

* Um den Filter standardmäßig für alle Listen anzuzeigen, die auf diesem Dokumenttyp basieren, wählen Sie die Option **[!UICONTROL Standardfilter für diesen Dokumenttyp]** aus.

  Beispielsweise wird der Filter **[!UICONTROL Nach Name oder Login]** auf Benutzer angewendet. Die Option &quot;Standardfilter für diesen Dokumenttyp&quot; ist angekreuzt, der Filter wird daher systematisch für alle Benutzerlisten vorgeschlagen.

* Um einen Filter für alle Campaign-Benutzer verfügbar zu machen, wählen Sie die  Option **[!UICONTROL Mit anderen Benutzern geteilter Filter]** aus.

* Um ein Formular zur Auswahl der Filterkriterien zu definieren, wählen Sie die Option **[!UICONTROL Nutzung eines Formulars zur Parametereingabe]** aus. Dieses Formular muss in der Registerkarte **[!UICONTROL Formular]** im XML-Format eingegeben werden. Zum Beispiel zeigt der integrierte vordefinierte Filter **[!UICONTROL Empfänger, die geöffnet haben]**, der in der Empfängerliste verfügbar ist, ein Filterfeld an, mit dem Sie den Versand auswählen können, für den der Filter gilt.

![](assets/predefined-filters-parameters.png)


* Über den Link **[!UICONTROL Erweiterte Parameter]** können Sie zusätzliche Einstellungen definieren.

   * Sie können eine SQL-Tabelle mit dem Filter verknüpfen, um ihn für alle Bearbeiter freizugeben, die die Tabelle gemeinsam nutzen.
   * Um zu verhindern, dass Benutzer den Filter überschreiben, wählen Sie die Option **[!UICONTROL Filter nicht weiter einschränken]** aus. Diese Option ist beispielsweise für die Filter &quot;Versandempfänger&quot; und &quot;Empfänger von Sendungen eines bestimmten Ordners&quot; aktiv, die im Versand-Assistenten verfügbar sind. Diese Filter können nicht überschrieben werden.

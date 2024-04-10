---
product: campaign
title: Hinzufügen eines berechneten Felds vom Typ "Aufzählung"
description: Erfahren Sie, wie Sie ein berechnetes Feld vom Typ "Aufzählung" hinzufügen
feature: Workflows, Data Management
role: User
exl-id: 4fe2ae81-faa6-4777-a332-70c451bca75b
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 67%

---

# Hinzufügen eines berechneten Felds vom Typ &quot;Aufzählung&quot; {#adding-an-enumeration-type-calculated-field}

In der folgenden Abfrage wird ein **[!UICONTROL berechnetes Auflistungsfeld]** hinzugefügt. In der Ergebnisanzeige soll eine Spalte erzeugt werden, die das Geschlecht der Empfänger anzeigt: männlich (1), weiblich (2) oder unbestimmt (0).

* Welche Tabelle soll ausgewählt werden?

  Die Empfängertabelle (nms:recipient)

* Felder, die als Ausgabespalten verwendet werden sollen?

  Nachname, Vorname, Geschlecht

* Nach welchen Kriterien sind die Informationen zu filtern?

  Nach der Sprache der Empfänger

Gehen Sie wie folgt vor:

1. Öffnen Sie das **[!UICONTROL generische Abfragetool]** und wählen Sie die Empfängertabelle (nms:recipient).
1. Wählen Sie im Fenster **[!UICONTROL Zu extrahierende Daten]** die Felder **[!UICONTROL Nachname]**, **[!UICONTROL Vorname]** und **[!UICONTROL Geschlecht]**.

   ![](assets/query_editor_nveau_73.png)

1. In diesem Beispiel ist keine **[!UICONTROL Sortierung]** erforderlich. Sie können somit direkt auf **[!UICONTROL Weiter]** klicken.
1. Wählen Sie dann im **[!UICONTROL Datenfilter]**-Fenster die Option **[!UICONTROL Filterbedingungen]**.
1. Konfigurieren Sie im Fenster **[!UICONTROL Zielelement]** eine Bedingung, die als Ergebnis alle deutschsprachigen Empfänger ausgibt.

   ![](assets/query_editor_nveau_74.png)

1. Klicken Sie dann im Fenster **[!UICONTROL Datenformatierung]** auf die Schaltfläche **[!UICONTROL Berechnetes Feld hinzufügen]**.

   ![](assets/query_editor_nveau_75.png)

1. Wählen Sie im Feld **[!UICONTROL Typ]** des Fensters **[!UICONTROL Definition eines berechneten Export-Feldes]** die Option **[!UICONTROL Auflistungen]** aus.

   Definieren Sie die Spalte, auf die das neue berechnete Feld verweisen muss. Wählen Sie dazu die **[!UICONTROL Geschlecht]** Spalte im Dropdown-Menü der **[!UICONTROL Quellspalte]** Feld: Die Zielwerte stimmen mit den **[!UICONTROL Geschlecht]** Spalte.

   ![](assets/query_editor_nveau_76.png)

   Konfigurieren Sie **Quellwert** und **Zielwert**. Der Zielwert erleichtert die Lesbarkeit des Abfrageergebnisses, d. h. des Geschlechts der Empfänger (0, 1 oder 2).

   Klicken Sie für jedes Quell- und Zielwertpaar auf **[!UICONTROL Hinzufügen]** rechts oberhalb der **[!UICONTROL Liste der Auflistungswerte]**:

   * Geben Sie bei **[!UICONTROL Quellwert]** in neue Zeilen jeweils die dem Geschlecht entsprechenden Zahlenwerte ein (0, 1 und 2).
   * Geben Sie bei **[!UICONTROL Zielwert]** die den Zahlen entsprechende Bedeutung ein: &quot;Unbestimmt&quot; bei &quot;0&quot;, &quot;Männlich&quot; bei &quot;1&quot; und &quot;Weiblich&quot; bei &quot;2&quot;.

   Kreuzen Sie die Option **[!UICONTROL Quellwert]** beibehalten an und

   klicken Sie auf **[!UICONTROL OK]**, um die Konfiguration des berechneten Felds abzuschließen.

   ![](assets/query_editor_nveau_77.png)

1. Klicken Sie im Fenster **[!UICONTROL Datenformatierung]** auf **[!UICONTROL Weiter]**.
1. Nun können Sie die **[!UICONTROL Datenvorschau starten]**.

   Die berechnete Spalte zeigt an, welchem Geschlecht die drei Werte 0, 1 und 2 entsprechen:

   * 0 für &quot;Unbestimmt&quot;
   * 1 für &quot;Männlich&quot;
   * 2 für &quot;Weiblich&quot;

   ![](assets/query_editor_nveau_78.png)

   Wenn Sie z. B. in das Feld „Geschlecht 2“ nicht eingeben **[!UICONTROL Liste der Auflistungswerte]** und die **[!UICONTROL Warnung erzeugen und fortfahren]** Funktion des **[!UICONTROL In anderen Fällen]** Wenn das Feld ausgewählt ist, wird ein Warnprotokoll angezeigt. Dieses Protokoll gibt an, dass Geschlecht „2“ (Weiblich) nicht eingegeben wurde. Er wird in der **[!UICONTROL Beim Export generierte Logs]** Feld des Datenvorschau-Fensters.

   ![](assets/query_editor_nveau_79.png)

   Nehmen wir ein anderes Beispiel und sagen, dass der Auflistungswert „2“ nicht eingegeben wurde. Wählen Sie die **[!UICONTROL Fehler erzeugen und Zeile ablehnen]** Funktion: Alle Empfänger mit „Geschlecht 2“ melden Anomalien und die anderen Informationen in der Zeile (Vor- und Nachname usw.) wird nicht exportiert. Ein Fehlerprotokoll wird in der **[!UICONTROL Beim Export generierte Logs]** Feld des Datenvorschau-Fensters. Dieses Protokoll gibt an, dass der Auflistungswert „2“ nicht eingegeben wurde.

   ![](assets/query_editor_nveau_80.png)

---
product: campaign
title: Verwenden von Aggregaten
description: Machen Sie sich mit der Verwendung von Aggregaten vertraut
feature: Workflows
exl-id: 7522f449-341e-4aef-8c1e-c49e13809c08
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 89%

---

# Verwenden von Aggregaten{#using-aggregates}



Ziel des folgenden Anwendungsbeispiels ist es, die zuletzt zur Datenbank hinzugefügten Empfänger zu identifizieren.

Hierfür wird das Datum der Empfängererstellung in der Datenbank mit dem letzten bekannten Datum, an dem ein Empfänger erstellt wurde, mithilfe eines Aggregats verglichen. Auf diese Weise werden alle an diesem Datum erstellten Empfänger abgerufen.

Die Konfiguration eines Empfängerfilters vom Typ **Erstellungsdatum = max (Erstellungsdatum)** ist mithilfe des folgenden Workflows möglich:

1. Abrufen von Datenbankempfängern mithilfe einer einfachen Abfrage. Weitere Informationen zu diesem Schritt finden Sie unter [Abfragen erstellen](query.md#creating-a-query).
1. Berechnung des letzten bekannten Empfängererstellungs-Datums mit der Aggregatfunktion **max (Erstellungsdatum)**.
1. Zuordnung der Empfänger zum Ergebnis des Aggregats im selben Schema.
1. Filterung der Empfänger mithilfe des Aggregats im bearbeiteten Schema.

![](assets/datamanagement_usecase_1.png)

## 1. Schritt: Berechnung des Aggregats {#step-1--calculating-the-aggregate-result}

1. Erstellen Sie eine Abfrage. Ziel ist die Berechnung des letzten bekannten Erstellungsdatums aus allen in der Datenbank enthaltenen Empfängern. Die Abfrage enthält somit keinen Filter.
1. Klicken Sie auf den Link **[!UICONTROL Daten hinzufügen...]**.
1. Wählen Sie in den aufeinanderfolgenden Fenstern die Optionen **[!UICONTROL Daten in Relation mit der Filterdimension]** und **[!UICONTROL Daten der Filterdimension]**.
1. In der **[!UICONTROL Hinzuzufügende Daten]** eine Spalte hinzufügen, die den Höchstwert für die **Erstellungsdatum** Feld in der Empfängertabelle. Sie können den Ausdruckseditor verwenden oder eingeben **max(@created)** Direkt in ein Feld im **[!UICONTROL Ausdruck]** Spalte. Klicken Sie dann auf die Schaltfläche **[!UICONTROL beenden]** Schaltfläche.

   ![](assets/datamanagement_usecase_2.png)

1. Klick **[!UICONTROL Zusätzliche Daten bearbeiten]** dann **[!UICONTROL Erweiterte Parameter…]**. Überprüfen Sie die **[!UICONTROL Automatisches Hinzufügen der Primärschlüssel der Zielgruppendimension deaktivieren]** Option.

   Diese Option ermöglicht es, nicht alle Empfänger als Ergebnis auszugeben und nur die Daten beizubehalten, die explizit hinzugefügt wurden. Hier handelt es sich um das Datum, an dem zuletzt ein Empfänger erstellt wurde.

   Lassen Sie die Option **[!UICONTROL Dubletten löschen (DISTINCT)]** angekreuzt.

## 2. Schritt: Verknüpfung von Empfängern und Aggregat {#step-2--linking-the-recipients-and-the-aggregation-function-result}

Verwenden Sie die Schema-Bearbeitung, um die auf Empfänger bezogene Abfrage mit der zur Berechnung eines Aggregats dienenden Abfrage zu verknüpfen.

1. Wählen Sie als Hauptmenge die Abfrage bezüglich der Empfänger aus.
1. Fügen Sie im **[!UICONTROL Relationen]**-Tab eine neue Relation hinzu und konfigurieren Sie sie wie folgt:

   * Wählen Sie das temporäre Schema des Aggregats aus. Die Daten dieses Schemas werden zur Hauptmenge hinzugefügt.
   * Aktivieren Sie die Option **[!UICONTROL Einfachen Join verwenden]**, um das Ergebnis des Aggregats zu jedem Empfänger der Hauptmenge zuzuordnen.
   * Geben Sie schließlich an, dass es sich bei der Relation um eine **[!UICONTROL 1:1-Relation]** handelt.

   ![](assets/datamanagement_usecase_3.png)

Auf diese Weise wird das Ergebnis des Aggregats mit jedem einzelnen der Empfänger verknüpft.

## 3. Schritt: Filterung der Empfänger mithilfe des Aggregats  {#step-3--filtering-recipients-using-the-aggregate-}

Nach Erzeugung der Relation sind die Empfänger und das Aggregat Teil desselben temporären Schemas. Dadurch ist es nun möglich, einen Filter auf das Schema anzuwenden, der den Vergleich zwischen dem Erstellungsdatum der Empfänger und dem letzten Erstellungsdatum (durch das Aggregat berechnet) vornimmt. Hierzu wird eine Aufspaltung verwendet.

1. Wählen Sie im **[!UICONTROL Allgemein]**-Tab **Empfänger** als Zielgruppendimension und **Schema-Bearbeitung** als Filterdimension aus (um das Schema der eingehenden Transition zu filtern).
1. Gehen Sie in den **[!UICONTROL Teilmengen]**-Tab, kreuzen Sie die Option **[!UICONTROL Filterbedingung für die Eingangspopulation hinzufügen]** an und klicken Sie auf **[!UICONTROL Bearbeiten...]**.
1. Setzen Sie im Ausdruckseditor das Erstellungsdatum der Empfänger mit dem vom Aggregat berechneten Datum gleich.

   Datumsfelder werden in der Datenbank in der Regel auf die Millisekunde genau gespeichert. Die Datumsangaben müssen daher auf den ganzen Tag ausgedehnt werden, um nicht nur die Empfänger abzurufen, die in derselben Millisekunde erstellt wurden.

   Im Ausdruckseditor steht hierzu die Funktion **ToDate** zur Verfügung, die Datumsangaben mit Uhrzeit in einfache Daten konvertiert.

   Folgende Ausdrücke sind also für die Bedingung erforderlich:

   * **[!UICONTROL Ausdruck]**: `toDate([target/@created])`.
   * **[!UICONTROL Wert`toDate([datemax/expr####])`]**, wobei expr#### dem in der Aggregatabfrage definierten Aggregat entspricht.

   ![](assets/datamanagement_usecase_4.png)

Das Ergebnis der Aufspaltung entspricht somit den am selben Tag wie die letzte bekannte Erstellung erstellten Empfängern.

Sie haben die Möglichkeit, im Anschluss weitere Aktivitäten wie beispielsweise ein Listen-Update oder einen Versand im Workflow-Diagramm zu platzieren.

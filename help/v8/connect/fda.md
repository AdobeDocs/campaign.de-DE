---
title: Arbeiten mit Campaign und externen Datenbanken (FDA)
description: Erfahren Sie, wie Sie mit Campaign und externen Datenbanken arbeiten
feature: Federated Data Access
role: Admin
level: Beginner, Intermediate
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 100%

---

# Federated Data Access (FDA){#gs-fda}

Verwenden Sie den FDA-Connector (Federated Data Access), um Campaign mit einer oder mehreren **externen Datenbanken** zu verbinden und darin gespeicherte Informationen zu verarbeiten, ohne die Daten in Ihrer Campaign Cloud-Datenbank zu beeinflussen. Sie können dann auf externe Daten zugreifen, ohne die Struktur der Adobe Campaign-Daten zu verändern.

![](../assets/do-not-localize/speech.png) Benutzende von Managed Cloud Services können [Adobe kontaktieren](../start/campaign-faq.md#support), um ihre externe(n) Datenbank(en) mit Campaign zu verbinden.


>[!NOTE]
>
>* Kompatible Datenbanken für Federated Data Access sind in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) aufgeführt.
>
>* Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) ist ein spezielles externes Konto verfügbar, über das die Kommunikation zwischen der lokalen Campaign-Datenbank und der Snowflake-Cloud-Datenbank verwaltet werden kann. Dieses externe Konto wird von Adobe für Sie eingerichtet und **darf nicht** geändert werden.
>



## Best Practices und Einschränkungen

Die FDA-Option unterliegt den Einschränkungen des von Ihnen verwendeten Drittanbieter-Datenbanksystems.

Beachten Sie außerdem die folgenden Einschränkungen und Best Practices:

* Die FDA-Option wird zur Bearbeitung der Daten in externen Datenbanken im Batch-Modus in Workflows verwendet. Um Leistungsprobleme zu vermeiden, wird nicht empfohlen, das FDA-Modul im Kontext von Einzeloperationen zu verwenden, etwa Personalisierung, Interaktion oder Echtzeit-Messaging.

* Vermeiden Sie möglichst Vorgänge, bei denen sowohl Adobe Campaign als auch die externe Datenbank zum Einsatz kommen. Gehen Sie dazu folgendermaßen vor:

   * Exportieren Sie die Adobe Campaign-Datenbank in die externe Datenbank und führen Sie die Aktionen nur in der externen Datenbank aus. Importieren Sie danach die Ergebnisse wieder in Adobe Campaign.

   * Rufen Sie die Daten aus der externen Adobe Campaign-Datenbank ab und führen Sie die Aktionen lokal durch.
   Wenn Sie Ihre Sendungen unter Verwendung von Daten der externen Datenbank personalisieren möchten, rufen Sie die entsprechenden Daten über einen Workflow ab und stellen Sie sie in einer temporären Tabelle bereit. Personalisieren Sie dann Ihren Versand mit den Daten aus der temporären Tabelle. Bereiten Sie die Personalisierung von Nachrichten in einem speziellen Workflow vor, indem Sie die Option **[!UICONTROL Personalisierungsdaten mit einem Workflow vorbereiten]** verwenden, die auf der Registerkarte **[!UICONTROL Analyse]** der Versandeigenschaften verfügbar ist. Diese Option ermöglicht es, im Zuge der Versandanalyse automatisch einen Workflow zu erstellen und auszuführen, welcher alle auf eine Zielgruppe bezogenen Daten in einer temporären Tabelle speichert (insbesondere Daten aus verknüpften Tabellen einer externen Datenbank).

   >[!CAUTION]
   >
   >Diese Option verbessert die Leistung beim Ausführen des Personalisierungsschritts erheblich.


## Verwenden von externen Daten in einem Workflow

Campaign verfügt über mehrere Workflow-Aktivitäten, die Sie für die Interaktion mit Daten in Ihrer/Ihren externen Datenbank(en) verwenden können:

* **Filter für externe Daten** – Verwenden Sie die Aktivität **[!UICONTROL Abfrage]**, um externe Daten hinzuzufügen und sie in den definierten Filterkonfigurationen zu verwenden.

* **Erstellen von Teilmengen** - Verwenden Sie die Aktivität **[!UICONTROL Aufspaltung]**, um Teilmengen zu erstellen. Sie können externe Daten verwenden, um die zu verwendenden Filterkriterien zu definieren.

* **Externe Datenbank laden** – Verwenden Sie die externen Daten in der Aktivität **[!UICONTROL Laden (DBMS)]**.

* **Informationen und Links hinzufügen** – Verwenden Sie die Aktivität **[!UICONTROL Anreicherung]**, um der Arbeitstabelle des Workflows zusätzliche Daten und einer externen Tabelle Links hinzuzufügen. In diesem Kontext können Daten aus einer externen Datenbank verwendet werden.

Sie können aus allen oben aufgeführten Workflow-Aktivitäten auch direkt eine Verbindung zu einer externen Datenbank für eine temporäre Verwendung definieren. In diesem Fall handelt es sich um eine lokale externe Datenbank, die nur innerhalb des aktuellen Workflows verwendet werden kann.

>[!CAUTION]
>
>Diese Art der Konfiguration darf nur temporär zur Sammlung von Daten verwendet werden. Die Konfiguration externer Konten sollte für jede andere Verwendung bevorzugt werden.

Beispielsweise können Sie in der Aktivität **[!UICONTROL Abfrage]** eine temporäre Verbindung zu einer externen Datenbank wie folgt definieren:

1. Öffnen Sie die Aktivität und klicken Sie auf **[!UICONTROL Daten hinzufügen...]**
1. Wählen Sie die Option **[!UICONTROL Externe Daten]** aus.
1. Wählen Sie die Option **[!UICONTROL Datenquelle lokal definieren]**
1. Wählen Sie aus der Dropdown-Liste die Zieldatenbank-Engine aus. Geben Sie den Namen des Servers und die Authentifizierungsparameter ein. Geben Sie auch den Namen der externen Datenbank an.
1. Wählen Sie die Tabelle aus, in der die Daten gespeichert sind. Sie können den Namen der Tabelle direkt in das entsprechende Feld eingeben oder auf das Bearbeiten-Symbol klicken, um eine Liste mit Datenbanktabellen zu öffnen.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]**, um ein oder mehrere Abstimmungsfelder zwischen den Daten der externen Datenbank und den Daten in der Adobe Campaign-Datenbank zu definieren. Über die Symbole **[!UICONTROL Ausdruck bearbeiten]** der Option **[!UICONTROL Remote-Feld]** und **[!UICONTROL Lokales Feld]** erhalten Sie Zugriff auf die Liste mit den Feldern einer jeden Tabelle.
1. Spezifizieren Sie nötigenfalls eine Filterbedingung und den Datensortierungsmodus.
1. Wählen Sie zusätzlich in der externen Datenbank zu sammelnden Daten aus. Doppelklicken Sie dazu auf die Felder, die Sie hinzufügen möchten, damit sie in den **[!UICONTROL Ausgabespalten]** angezeigt werden.
1. Klicken Sie zur Bestätigung der Konfiguration auf **[!UICONTROL Beenden]**.

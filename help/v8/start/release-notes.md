---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 34%

---

# Aktuelle Version{#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **aktuellen Campaign v8-Version** aufgelistet.

## Version 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#download-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

_27. Januar 2023_

**Verbesserungen**

* Fehlerkorrektur - Es wurde ein Synchronisierungsproblem mit Versandindikatoren zwischen dem Marketing-Server und dem Mid-Sourcing-Server behoben. (NEO-50724) <!--OKKKK-->
* Fehlerkorrektur - Beim Export von Workflows tritt jetzt kein Fehler mehr auf. (NEO-50555) <!--OKKKK-->
* Fehlerkorrektur - Es wurde ein Problem beim Erweitern eines zuvor erweiterten Schemas behoben. (NEO-49118) <!--OKKKK-->
* Fehlerkorrektur - Bei der Verwendung von zwei Anreicherungsaktivitäten mit derselben Kennung in der Linkdefinition tritt jetzt kein Fehler mehr auf. (NEO-48851)
* Fehlerkorrektur - bei der Versandvorbereitung treten jetzt keine Fehler mehr auf. Die Versandvorbereitung konnte fehlschlagen, wenn die Anzahl der zu bearbeitenden potenziellen Angebote zu hoch war. Das zweite Problem trat auf, wenn die Bild-URLs als URLs definiert wurden, die in einem Textformat-Versand verfolgt werden sollen. (NEO-48807) <!--OKKKK-->
* Fehlerkorrektur - Workflow-Fehler werden jetzt nicht mehr dadurch verursacht, dass der im externen Konto definierte Warehouse-Name für Nicht-FFDA-Konten von einem Workflow überschrieben wird. (NEO-43209) <!--OKKKK-->
* Verbesserte Sicherheit für Webanwendungen, um DDoS-Angriffe zu verhindern. (NEO-50757) <!--OKKKK-->
* Die Verwaltung konsolidierter Tracking-Daten wurde im **[!UICONTROL Konsolidiertes Tracking]** (nms:trackingStats) FFDA-Tabelle, um Duplikate zu vermeiden. (NEO-46409)
* Fehlerkorrektur - In Workflow-Abfragen tritt bei der Verwendung von `enableIf` in einer logischen Operatorbedingung. Die vorherige logische Bedingung wurde überschrieben. (NEO-45815)  <!--OKKKK-->
* Die Erstellung aktiver Profile wurde im Abrechnungs-Workflow optimiert, um die Leistung zu verbessern. (NEO-47658) <!--OKKKK-->
* Fehlerkorrektur: Beim HTML-Dateiimport tritt jetzt kein Fehler mehr auf, wenn Bildknoten (img) URLs mit Personalisierungsfeldern enthalten. (NEO-48396)
* Es wurde ein Problem mit Snowflake (allen Implementierungen) bei der Verwendung des Sortierparameters in einer **Aufspaltung** Workflow-Aktivität. (NEO-45899) <!--OKKKK-->
* Fehlerkorrektur: Jetzt tritt kein Fehler mehr auf, wenn ein Benutzer bzw. eine Benutzerin mit Lesezugriffsrechten für den Ordner &quot;nmsDeliveryMapping&quot; versucht, eine Kampagne oder einen Workflow auszuführen. (NEO-48230)
* Fehlerkorrektur: Bei umfangreichem HTML-Code in der HTML-Tabelle eines Versands tritt jetzt kein Leistungsproblem mehr auf. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Fehlerkorrektur - Benutzer können jetzt die **Ausgewählte Zeilen zusammenführen** Workflow-Option. (NEO-48488)
* Fehlerkorrektur - Im Snowflake-FDA-Connector werden Datensätze jetzt nicht mehr gelöscht, wenn während der Anreicherung die Option &quot;Einfache Verknüpfung mit Kardinalität 0 oder 1&quot; verwendet wird. (NEO-48737)
* Die verbleibenden Verweise auf die log4j-Bibliothek wurden aus der Campaign-Installation unter Windows entfernt. (NEO-44851)
* Fehlerkorrektur: Beim Hinzufügen des Indikators **Empfänger, die geöffnet haben** (estimatedRecipientOpen) zu den Zusatzdaten einer **Abfrage**-Workflow-Aktivität tritt kein Fehler mehr auf. (NEO-46665)
* Die Verwaltung von Tracking-URLs in Workflows mit mehreren Sendungen wurde verbessert, um die Leistung zu verbessern. (NEO-50894) <!--OKKKK-->
* Fehlerkorrektur - Die Replikation von Schemas, die Xtkfolder verwenden, schlägt jetzt nicht mehr fehl. (NEO-46787) <!--OKKKK-->
* Fehlerkorrektur - Die benutzerdefinierte Spalte &quot;lastModified&quot; wird jetzt in der NmsSubscription-Tabelle abgelegt. (NEO-48402)

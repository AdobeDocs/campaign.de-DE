---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 44743e585119e8cd81a8fcc9b4d667c25c0d438e
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 100%

---

# Aktuelle Version{#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **aktuellen Campaign v8-Version** aufgelistet.

## Version 8.4.5 {#release-8-4-5}

_3. April 2023_

**Patches**

* Fehlerkorrektur – Wenn mehrere Genehmigungs-Workflows auf denselben Zeitplan eingestellt sind, gibt es keine Einschränkung aufgrund von doppelten Schlüsseln mehr. (NEO-48968)
* Fehlerkorrektur – Das Stilattribut des Body-Tags wird jetzt beim Hochladen eines Bildes im Digital Content Editor (DCE) nicht mehr geändert, nachdem der durch NEO-54474 (8.4.4) eingeführte Regressionsfehler behoben wurde. (NEO-57697)
* Fehlerkorrektur – Beim Exportieren von Daten über einen CRM-Connector tritt jetzt kein Fehler mehr auf, wenn der Primärschlüssel der temporären Tabelle als „long“ anstelle von „uuid“ definiert ist. (NEO-54153)
* Fehlerkorrektur – Es kommt jetzt nicht mehr zu Fehlern bei Paket-Export, FDA über HTTP und Reporting, nachdem der in 8.4.1 eingeführte Regressionsfehler behoben wurde. (NEO-57731)
* Fehlerkorrektur – Der Versandstatus für Sendungen mit negativen IDs wird jetzt korrekt aktualisiert, nachdem der in Version 8.3.8 eingeführte Regressionsfehler behoben wurde. (NEO-54675)
* Fehlerkorrektur – Beim Importieren von Daten mit dem Big Query Connector tritt jetzt kein Problem mehr mit booleschen Feldern auf (NEO-49181).

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

## Version 8.4.4 {#release-8-4-4}

_8. März 2023_

**Sicherheitsverbesserung**

* Um die Sicherheit zu verbessern, wurde Tomcat von Version 8.5.81 auf 8.5.85 aktualisiert. (NEO-50530)

**Patches**

* Das Scrollen in der Registerkarte **Bearbeiten** des Digital Content Editor (DCE) ist jetzt problemlos möglich. (NEO-54474)
* Bei der Replikation stürzt der Webserver jetzt nicht mehr ab. (NEO-53670)


>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.


## Version 8.4.3 {#release-8-4-3}


_27. Januar 2023_

**Verbesserungen**

* Fehlerkorrektur: Es wurde ein Synchronisierungsproblem von Versandindikatoren zwischen dem Marketing-Server und dem Mid-Sourcing-Server behoben. (NEO-50724) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das beim Export eines Workflows zu einem Fehler führen konnte. (NEO-50555) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem beim Erweitern eines zuvor erweiterten Schemas behoben. (NEO-49118) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem bei der Verwendung von zwei Anreicherungsaktivitäten mit derselben Kennung in der Link-Definition behoben. (NEO-48851)
* Fehlerkorrektur: Es wurden zwei Fehler bei der Versandvorbereitung behoben. Die Versandvorbereitung konnte fehlschlagen, wenn die Anzahl der bearbeiteten potenziellen Angebote zu hoch war. Das zweite Problem trat auf, wenn die Bild-URLs als URLs definiert waren, die in einem Versand im Textformat nachverfolgt werden sollten. (NEO-48807) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das zu Workflow-Fehlern führen konnte, wodurch der im externen Konto definierte Warehouse-Name für Nicht-FFDA-Konten von einem Workflow überschrieben werden konnte. (NEO-43209) <!--OKKKK-->
* Fehlerkorrektur: Verbesserte Sicherheit für Webanwendungen, um DDoS-Angriffe zu verhindern. (NEO-50757) <!--OKKKK-->
* Fehlerkorrektur: Die Verwaltung konsolidierter Tracking-Daten wurde in der FFDA-Tabelle für **[!UICONTROL konsolidiertes Tracking]** (nms:trackingStats) verbessert, um Duplikate zu vermeiden. (NEO-46409)
* Fehlerkorrektur: Ein Problem mit dem logischen Operator in Workflow-Abfragen bei der Verwendung von `enableIf` in einer logischen Operator-Bedingung wurde behoben. Die vorherige logische Bedingung wurde überschrieben. (NEO-45815)  <!--OKKKK-->
* Fehlerkorrektur: Die Erstellung aktiver Profile wurde im Abrechnungs-Workflow optimiert, um die Leistung zu verbessern. (NEO-47658) <!--OKKKK-->
* Fehlerkorrektur: Beim HTML-Dateiimport tritt jetzt kein Fehler mehr auf, wenn Bildknoten (img) URLs mit Personalisierungsfeldern enthalten. (NEO-48396)
* Fehlerkorrektur: Es wurde ein Problem bei der Verwendung des Sortierparameters in der Workflow-Aktivität **Aufspaltung** bei Snowflake (alle Bereitstellungen) behoben. (NEO-45899) <!--OKKKK-->
* Fehlerkorrektur: Jetzt tritt kein Fehler mehr auf, wenn ein Benutzer bzw. eine Benutzerin mit Lesezugriffsrechten für den Ordner &quot;nmsDeliveryMapping&quot; versucht, eine Kampagne oder einen Workflow auszuführen. (NEO-48230)
* Fehlerkorrektur: Bei umfangreichem HTML-Code in der HTML-Tabelle eines Versands tritt jetzt kein Leistungsproblem mehr auf. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das Benutzende davon abhielt, die Workflow-Option **Ausgewählte Zeilen zusammenführen** zu verwenden. (NEO-48488)
* Fehlerkorrektur: Es wurde ein Problem im Snowflake FDA-Connector behoben, das dazu führte, dass Einträge bei Verwendung der Option &quot;Einfache Relation mit Kardinalität 0 oder 1&quot; während der Anreicherung gelöscht wurden. (NEO-48737)
* Die verbleibenden Verweise auf die log4j-Bibliothek wurden aus der Campaign-Installation unter Windows entfernt. (NEO-44851)
* Fehlerkorrektur: Beim Hinzufügen des Indikators **Empfänger, die geöffnet haben** (estimatedRecipientOpen) zu den Zusatzdaten einer **Abfrage**-Workflow-Aktivität tritt kein Fehler mehr auf. (NEO-46665)
* Fehlerkorrektur: Die Verwaltung von Tracking-URLs wurde in Workflows mit mehreren Sendungen verbessert, um die Leistung zu verbessern. (NEO-50894) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das zum Scheitern der Replikation von Schemata führen konnte, die Xtkfolder verwenden. (NEO-46787) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, dass dazu führen konnte, dass die benutzerdefinierte Spalte &quot;lastModified&quot; in der NmsSubscription-Tabelle gelöscht wurde. (NEO-48402)


>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

---
title: Frühzeitige Versionshinweise zu Campain v8
description: Frühzeitige Veröffentlichung von Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# Frühzeitige Versionshinweise {#e-new-release}

Auf dieser Seite werden Verbesserungen und Fehlerbehebungen beschrieben, die in der nächsten Version von Campaign v8 enthalten sein werden. Dieser Inhalt kann ohne vorherige Ankündigung bis zum Veröffentlichungsdatum geändert werden. Die offiziellen Versionshinweise finden Sie auf dieser [Seite](../start/release-notes.md).

## Version 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#download-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

_7. Oktober 2022_

**Verbesserungen**

* Es wurde ein Problem behoben, das sich auf die Statusaktualisierungen des Versandlogs auf der MID-Instanz auswirkte, wenn die Option &quot;FeatureFlag_GZIP_Compression&quot; aktiviert war. (NEO-49183)
* Der technische Workflow **Datenbankbereinigung** kann jetzt auch für benutzerdefinierte Staging-Schemata verwendet werden. (NEO-48974)
* Fehlerkorrektur – Sendungen bleiben jetzt nicht mehr im Status **Ausstehend**, wenn das Kontaktdatum erreicht ist. (NEO-48079, NEO-48251)
* Die Stabilität bei der Verarbeitung ungültiger XML-Zeichenfolgen während SOAP-Aufrufen wurde verbessert. (NEO-48027)
* Fehlerkorrektur – Die Versandanalyse ist jetzt während des Ausschlusses von auf die Blockierungsliste gesetzten Empfängern nicht mehr verlangsamt, wenn die Zielgruppe aus einer großen Mengen von Empfängern besteht. (NEO-48019)
* Um einen zu langsamen Testversand an Testadressen zu verhindern, werden nun alle aufeinanderfolgenden Replikationen von Testempfängern und -empfängerinnen zu einer einzigen Replikationsanfrage zusammengefasst. (NEO-44844)
* Es wurde ein Problem behoben, das zu Personalisierungsproblemen beim Versand von SMS-Nachrichten über einen externen Versandmodus führte. (NEO-46415)
* Es wurde ein Problem behoben, bei dem ein Fehler angezeigt wurde, wenn die Vorschau eines Versands in einem archivierten Ereignis des Message Centers aufgerufen wurde. (NEO-43620)
* Es wurde ein Problem in Workflows behoben, das dazu führen konnte, dass Dateien auf dem Server nicht aktualisiert wurden, wenn die Aktivität **Laden (Datei)** verwendet wurde. Der Prozess wurde bei 100 % angehalten, aber nie beendet. (NEO-47269)
* Fehlerkorrektur – Jetzt werden keine unnötigen Versandkontingente mehr erstellt, wenn für den Versand Kalender- und Aufspaltungsmodi verwendet werden. (NEO-48634)
* Es wurde ein Leistungsproblem bei der Verwendung von auf Kalendern basierenden Schüben behoben. (NEO-48451)
* Fehlerkorrektur – Im Bildschirm der Versandliste wird jetzt nach der Erstellung eines neuen Zielgruppen-Mappings für ein benutzerdefiniertes Schema keine Fehlermeldung mehr angezeigt. (NEO-49237)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr auf, wenn ein Versand während des MTA-Prozesses eine bestimmte Größe erreicht. (NEO-46097)
* Es wurde ein Problem behoben, das verhinderte, dass Trackinglogs Daten über den Browser des Empfängers zurückgaben. (NEO-46612)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr während des Postupgrades in japanischen Umgebungen auf. (NEO-46640)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr bei der Verwendung der **Abfrage**-Aktivität und der Filterung einer Tabelle auf. Wenn ein Spaltenname das Wort &quot;Update&quot; enthielt, kam es zu einem Kompilierungsfehler mit einer ungültigen Kennung und folgender Meldung: &quot;Anzahl der Zeilen aktualisiert&quot;. (NEO-46485)
* Es wurde ein Problem behoben, das verhinderte, dass der technische Workflow **[!UICONTROL Staging-Daten replizieren]** (ffdaReplicateStagingData) gestoppt wurde, selbst wenn während seiner Ausführung ein Fehler auftrat. (NEO-46280)
* Fehlerkorrektur – Jetzt gehen keine Daten mehr verloren, wenn der Staging-Workflow fehlerhaft ist und die Aufbewahrungsfrist vollständig abgelaufen ist. (NEO-48975)
* Es wurde ein Problem behoben, das bei der Eingabe von Daten in die Snowflake-Cloud-Datenbank mithilfe der Campaign-Aktivität **Abfrage** und **Datenquelle ändern** auftrat: Der Prozess schlug fehl, wenn ein umgekehrter Schrägstrich in den Daten vorhanden war. Die Quellzeichenfolge wurde nicht escaped, wodurch die Daten von Snowflake nicht korrekt verarbeitet wurden. (NEO-45549)

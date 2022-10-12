---
title: Frühe Versionshinweise zu Campaign v8
description: Frühe Campaign v8-Version
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 43%

---

# Vorzeitige Versionshinweise {#e-new-release}

Auf dieser Seite werden Verbesserungen und Fehlerbehebungen beschrieben, die in der nächsten Campaign v8-Version enthalten sind. Dieser Inhalt kann bis zum Veröffentlichungsdatum ohne vorherige Ankündigung geändert werden. Die offiziellen Versionshinweise finden Sie in diesem [page](../start/release-notes.md).

## Version 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> Die Aktualisierung der Client Console ist obligatorisch. Informationen zum Aktualisieren der Client-Konsole finden Sie in diesem [page](../start/connect.md#download-ac-console).

_7. Oktober 2022_

**Verbesserungen**

* Es wurde ein Problem behoben, das sich auf die Statusaktualisierungen des Versandlogs auf der MID-Instanz auswirkte, wenn die Option &quot;FeatureFlag_GZIP_Compression&quot; aktiviert war. (NEO-49183)
* Die **Datenbankbereinigung** Der technische Workflow verarbeitet jetzt auch benutzerdefinierte Staging-Schemata. (NEO-48974)
* Fehlerkorrektur - Sendungen bleiben jetzt nicht mehr im **Ausstehend** Status, auch wenn das Kontaktdatum erreicht wurde. (NEO-48079, NEO-48251)
* Verbesserte Stabilität bei der Verarbeitung ungültiger XML-Zeichenfolgen während SOAP-Aufrufen. (NEO-48027)
* Fehlerkorrektur - Die Versandanalyse wird jetzt beim Ausschließen auf die Blockierungsliste gesetzt Empfänger bei der Zielgruppenbestimmung für große Mengen von Empfängern nicht mehr verlangsamt. (NEO-48019)
* Um eine Langsamkeit beim Testversand an Testadressen zu vermeiden, werden alle aufeinander folgenden Replikationen von Testmitgliedern nun in einer Replikationsanforderung gruppiert. (NEO-44844)
* Es wurde ein Problem behoben, das zu Personalisierungsproblemen beim Versand von SMS-Nachrichten über einen externen Versandmodus führte. (NEO-46415)
* Es wurde ein Problem behoben, bei dem ein Fehler angezeigt wurde, wenn die Vorschau eines Versands in einem archivierten Ereignis des Message Centers aufgerufen wurde. (NEO-43620)
* Es wurde ein Problem in Workflows behoben, das dazu führen konnte, dass Dateien auf dem Server nicht aktualisiert wurden, wenn die Aktivität **Laden (Datei)** verwendet wurde. Der Prozess wurde bei 100 % angehalten, aber nie beendet. (NEO-47269)
* Fehlerkorrektur - jetzt werden keine unnötigen Versandteile mehr erstellt, wenn der Versand Kalender- und Aufspaltungsmodi verwendet. (NEO-48634)
* Es wurde ein Leistungsproblem bei der Verwendung kalendartiger Schübe behoben. (NEO-48451)
* Fehlerkorrektur - Im Bildschirm der Versandliste wird jetzt nach der Erstellung eines neuen Zielgruppen-Mappings für ein benutzerdefiniertes Schema keine Fehlermeldung mehr angezeigt. (NEO-49237)
* Fehlerkorrektur - jetzt tritt kein Fehler mehr auf, wenn ein Versand während des MTA-Prozesses eine bestimmte Größe erreicht. (NEO-46097)
* Es wurde ein Problem behoben, das verhinderte, dass Trackinglogs Daten über den Browser des Empfängers zurückgaben. (NEO-46612)
* Es wurde ein Problem beim Postupgrade in japanischen Umgebungen behoben. (NEO-46640)
* Es wurde ein Problem bei der Verwendung der **Abfrage**-Aktivität und der Filterung einer Tabelle behoben. Wenn ein Spaltenname das Wort &quot;Aktualisieren&quot;enthielt, trat ein Kompilierungsfehler mit einer ungültigen Kennung und der folgenden Meldung auf: &quot;Anzahl der Zeilen aktualisiert&quot;. (NEO-46485)
* Es wurde ein Problem behoben, das verhinderte, dass der technische Workflow **[!UICONTROL Staging-Daten replizieren]** (ffdaReplicateStagingData) gestoppt wurde, selbst wenn während seiner Ausführung ein Fehler auftrat. (NEO-46280)
* Fehlerkorrektur - Jetzt gehen keine Daten mehr verloren, wenn der Staging-Workflow fehlerhaft ist und die Aufbewahrungsfrist vollständig abgelaufen ist. (NEO-48975)
* Es wurde ein Problem behoben, das bei der Eingabe von Daten in die Snowflake-Cloud-Datenbank mithilfe der Campaign-Aktivität **Abfrage** und **Datenquelle ändern** auftrat: Der Prozess schlug fehl, wenn ein umgekehrter Schrägstrich in den Daten vorhanden war. Die Quellzeichenfolge wurde nicht escaped, wodurch die Daten von Snowflake nicht korrekt verarbeitet wurden. (NEO-45549)

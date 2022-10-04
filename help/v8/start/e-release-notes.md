---
title: Frühe Versionshinweise zu Campaign v8
description: Frühe Campaign v8-Version
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: acb3223a9a70179ea1cb3a126ef17cf5e234b4ba
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 5%

---

# Vorzeitige Versionshinweise {#e-new-release}

Auf dieser Seite werden Verbesserungen und Fehlerbehebungen beschrieben, die in der nächsten Campaign v8-Version enthalten sind.

>[!CAUTION]
>
> Dieser Inhalt kann bis zum Veröffentlichungsdatum ohne vorherige Ankündigung geändert werden. Die offiziellen Versionshinweise finden Sie in diesem [page](../start/release-notes.md).

## Version 8.3.9 {#release-8-3-9}

_7. Oktober 2022_

**Verbesserungen**

* Fehlerkorrektur - Die Statusaktualisierungen des Versandlogs auf der MID-Instanz werden jetzt nicht mehr beeinträchtigt, wenn die Option FeatureFlag_GZIP_Compression aktiviert ist. (NEO-49183)
* Die **Datenbankbereinigung** Der technische Workflow verarbeitet jetzt auch benutzerdefinierte Staging-Schemata. (NEO-48974)
* Fehlerkorrektur - Sendungen bleiben jetzt nicht mehr im **Ausstehend** Status, auch wenn das Kontaktdatum erreicht wurde. (NEO-48079, NEO-48251)
* Verbesserte Stabilität bei der Verarbeitung ungültiger XML-Zeichenfolgen während SOAP-Aufrufen. (NEO-48027)
* Fehlerkorrektur - Die Versandanalyse wird jetzt beim Ausschließen auf die Blockierungsliste gesetzt Empfänger bei der Zielgruppenbestimmung für große Mengen von Empfängern nicht mehr verlangsamt. (NEO-48019)
* Um eine Langsamkeit beim Testversand an Testadressen zu vermeiden, werden alle aufeinander folgenden Replikationen von Testmitgliedern nun in einer Replikationsanforderung gruppiert. (NEO-44844)
* Fehlerkorrektur - Personalisierungsprobleme treten jetzt nicht mehr auf, wenn SMS-Nachrichten im externen Versandmodus gesendet werden. (NEO-46415)
* Fehlerkorrektur - Jetzt wird kein Fehler mehr angezeigt, wenn versucht wird, einen Versand in einem archivierten Message Center-Ereignis in der Vorschau anzuzeigen. (NEO-43620)
* Fehlerkorrektur - In Workflows werden Dateien jetzt auf dem Server aktualisiert, wenn die **Laden (Datei)** Aktivität. Der Prozess wurde zu 100 % gestoppt, endete aber nie. (NEO-47269)
* Fehlerkorrektur - jetzt werden keine unnötigen Versandteile mehr erstellt, wenn der Versand Kalender- und Aufspaltungsmodi verwendet. (NEO-48634)
* Es wurde ein Leistungsproblem bei der Verwendung kalendartiger Schübe behoben. (NEO-48451)
* Fehlerkorrektur - Im Bildschirm der Versandliste wird jetzt nach der Erstellung eines neuen Zielgruppen-Mappings für ein benutzerdefiniertes Schema keine Fehlermeldung mehr angezeigt. (NEO-49237)
* Fehlerkorrektur - jetzt tritt kein Fehler mehr auf, wenn ein Versand während des MTA-Prozesses eine bestimmte Größe erreicht. (NEO-46097)
* Fehlerkorrektur - Trackinglogs können jetzt Daten im Zusammenhang mit dem Browser des Empfängers zurückgeben. (NEO-46612)
* Es wurde ein Problem beim Postupgrade in japanischen Umgebungen behoben. (NEO-46640)
* Es wurde ein Problem bei der Verwendung der **Abfrage** Aktivität und Filterung einer Tabelle. Wenn ein Spaltenname das Wort &quot;Aktualisieren&quot;enthielt, trat ein Kompilierungsfehler mit einer ungültigen Kennung und der folgenden Meldung auf: &quot;Anzahl der Zeilen aktualisiert&quot;. (NEO-46485)
* Fehlerkorrektur - Die **[!UICONTROL Replizieren von Staging-Daten]** Der technische Workflow (ffdaReplicateStagingData) kann selbst dann angehalten werden, wenn bei der Ausführung ein Fehler aufgetreten ist. (NEO-46280)
* Fehlerkorrektur - Jetzt gehen keine Daten mehr verloren, wenn der Staging-Workflow fehlerhaft ist und die Aufbewahrungsfrist vollständig abgelaufen ist. (NEO-48975)
* Fehlerkorrektur - Beim Einfügen von Daten in eine Snowflake Cloud-Datenbank mit einer Campaign tritt jetzt kein Fehler mehr auf **Abfrage** und eine **Datenquelle ändern** Aktivität: Der Prozess schlug fehl, wenn in den Daten ein umgekehrter Schrägstrich vorhanden ist. Die Quellzeichenfolge wurde nicht maskiert und die Daten wurden auf dem Snowflake nicht korrekt verarbeitet. (NEO-45549)

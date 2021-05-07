---
solution: Campaign
product: Adobe Campaign
title: Funktionsmatrix von Campaign Classic v7 - Kampagne v8
description: Unterschiede zwischen Campaign Classic v7 und Kampagne v8 verstehen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: e1308398e5a33f2ad9659ad632aeb05af9916e69
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 4%

---

# Campaign Classic v7 - Kampagne v8-Funktionen{#gs-matrix}


Als bestehender Campaign Classic v7-Nutzer sollten Sie keine größeren Störungen in der Interaktion mit Adobe Campaign erwarten. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten sichtbar sind.

Wichtige Änderungen:

* Segmente bis zu 200-mal schneller erstellen

* Erhöhen Sie die Geschwindigkeit des Versands

* Echtzeit-Berichte

Beachten Sie als Campaign Classic, dass die meisten Campaign Classic v7-Funktionen mit Kampagne v8 verfügbar sind, mit Ausnahme eines kleinen Satzes, der in [diesem Abschnitt](#gs-removed) aufgeführt ist. Andere werden in zukünftigen Versionen erscheinen. [Mehr dazu](#gs-unavailable-features)


## Produktkonfigurationsänderungen

### Kampagne und [!DNL Snowflake] {#ac-gs-snowflake}

Die Cloud-Datenspeicherung wird in [!DNL Snowflake] ausgeführt: Ein neues Externe Konto stellt die Verbindung zur Cloud-Datenbank sicher. [Weitere Informationen](#ac-gs-snowflake).

Dies ist ein grundlegender Wandel in der Softwarearchitektur. Daten sind jetzt remote und die Kampagne führt die gesamten Daten, einschließlich Profilen, zusammen. Kampagne-Prozesse skalieren jetzt von Targeting bis zur Ausführung von Meldungen: Datenerfassung, Segmentierung, Targeting, Abfragen und Versand werden jetzt in der Regel in Minuten ausgeführt.

Diese neue Version löst die ganze Herausforderung der Skalierung und bewahrt dabei den gleichen Grad an Flexibilität und Erweiterbarkeit. Die Anzahl der Profil ist nahezu unbegrenzt, und die Datenspeicherung kann verlängert werden.

Ein neues integriertes **Externe Konto** ist der vollständigen FDA gewidmet. Dies ist der Kern der Cloud-Datenbankverbindung. Wir empfehlen, so zu gehen, wie es ist.

Für alle integrierten Schemas/Tabellen, die in der Cloud-Datenbank verschoben oder repliziert werden müssen, ist eine integrierte Schema-Erweiterung unter dem Namensraum **xxl** verfügbar.

Diese Erweiterungen enthalten alle erforderlichen Änderungen, um integrierte Schema aus der lokalen Kampagne in die Cloud-Datenbank zu verschieben und ihre Struktur entsprechend anzupassen: neue UUID, aktualisierte Links usw.[!DNL Snowflake]

>[!CAUTION]
>
> Kundendaten werden nicht in der lokalen Kampagne gespeichert. Daher müssen benutzerdefinierte Tabellen in der Cloud-Datenbank erstellt werden.


### Datenreplikation

Ein spezieller Arbeitsablauf für technische Arbeitsabläufe behandelt die Replikation von Tabellen, die auf beiden Seiten vorhanden sein müssen (Kampagne der lokalen Datenbank und Cloud-Datenbank). Dieser Workflow wird stündlich ausgelöst und basiert auf einer neuen integrierten JavaScript-Bibliothek.

>[!NOTE]
>
> Es wurden mehrere Replikationsrichtlinien erstellt, die auf der Größe der Tabelle (XS, XL usw.) basieren.
> Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, andere werden eine vollständige Aktualisierung durchlaufen.


[Weitere Informationen zur Datenreplikation](../config/replication.md)

### ID-Management

Kampagne v8-Objekte verwenden jetzt eine **Universally Unique ID (UUID)**, die die Identifizierung von Daten durch unbegrenzte eindeutige Werte ermöglicht.

Bitte beachten Sie, dass diese ID zeichenfolgenbasiert und nicht sequenziell ist.

### Vereinfachte Wartung

Kampagne-Benutzer müssen keine Datenbankexperten sein: Es besteht kein Bedarf mehr an komplexen Datenbankwartungsvorgängen oder komplexer Tabellenindizierung.

## Temporäre nicht verfügbare Funktionen{#gs-unavailable-features}

Bitte beachten Sie, dass in dieser ersten Version noch einige Funktionen nicht verfügbar sind, z.B.:

* Verwaltung von Marketing-Ressourcen
* Dezentrales Marketing
* Inbound Angebot Management (Interaktionsmodul)
* Kampagnenoptimierung (Campaign Optimization)
* Reaktionsverwaltung
* Hybrid-/lokale Bereitstellungsmodelle

## Entfernte Funktionen{#gs-removed}

Um mit dem neuen Architektur- und Bereitstellungsmodell der Kampagne v8 in Einklang zu stehen, sind einige historische Campaign Classic v7-Funktionen in Kampagne v8 nicht mehr verfügbar.

* Coupons
* Webtracking
* Umfragen
* Social Marketing
* ACS Connector (Prime-Angebot)


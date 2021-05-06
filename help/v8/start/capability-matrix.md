---
solution: Campaign Classic
product: campaign
title: Funktionsmatrix von Campaign Classic v7 - Kampagne v8
description: Unterschiede zwischen Campaign Classic v7 und Kampagne v8 verstehen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 3%

---

# Campaign Classic v7 - Kampagne v8-Funktionen{#gs-matrix}


Als bestehender Campaign Classic-v7-Nutzer sollten Sie jede große Störung in der Art und Weise erwarten, wie Sie normalerweise mit Adobe Campaign spielen. Die meisten Änderungen sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und Konfigurationsschritten sichtbar sind.

Wichtige Änderungen:

* Segmente bis zu 200-mal schneller erstellen

* Erhöhen Sie die Geschwindigkeit des Versands

* Echtzeit-Berichte

Beachten Sie als Campaign Classic, dass die meisten Campaign Classic v7-Funktionen mit Kampagne v8 verfügbar sind, mit Ausnahme eines kleinen Satzes, der in [diesem Abschnitt](#gs-removed) aufgeführt ist. Andere werden in zukünftigen Versionen erscheinen. [Mehr dazu](#gs-unavailable-features)


## Produktkonfigurationsänderungen

### Kampagne und [!DNL Snowflake] {#ac-gs-snowflake}

Die Cloud-Datenspeicherung wird in [!DNL Snowflake] ausgeführt: Ein neues Externe Konto stellt die Verbindung zur Cloud-Datenbank sicher. [Weitere Informationen](#ac-gs-snowflake).

Dies ist ein grundlegender Wandel in der Softwarearchitektur. Daten sind jetzt remote: Die Kampagne führt die gesamten Daten, einschließlich Profilen, zusammen. Der Kampagne-Prozess wird jetzt von Ende zu Ende skaliert, vom Targeting zur Ausführung des Versands: Die Datenerfassung, Segmentierung, Targeting, Abfragen und die Ausführung des Versands werden jetzt in wenigen Minuten ausgeführt.

Diese neue Version löst die ganze Herausforderung der Skalierung und hält dabei den gleichen Grad an Flexibilität und Erweiterbarkeit. Die Anzahl der Profil ist nahezu unbegrenzt, und die Datenspeicherung kann verlängert werden.

Ein neues integriertes **Externe Konto** ist der vollständigen FDA gewidmet. Dies ist der Kern der Cloud-Datenbankverbindung. Wir empfehlen, so zu gehen, wie es ist.

Für alle integrierten Schemas/Tabellen, die in die Cloud-Datenbank verschoben oder repliziert werden müssen, ist unter Namensraum **xxl** eine integrierte Schema-Erweiterung verfügbar. Was die Schema-Erweiterung angeht, wird der neue XXL-Namensraum für jede neue OOTB-Konfiguration wie JavaScript, JSSP usw. verwendet.

Diese Erweiterungen enthalten alle erforderlichen Änderungen, um integrierte Schema von der lokalen Kampagne in die Cloud-Datenbank zu verschieben und ihre Struktur entsprechend anzupassen: neue UUID, aktualisierte Links usw.[!DNL Snowflake]

>[!CAUTION]
>
> Kundendaten werden nicht in der lokalen Kampagne gespeichert. Daher müssen benutzerdefinierte Tabellen in der Cloud-Datenbank erstellt werden.


### Datenreplikation

Ein spezieller Arbeitsablauf für technische Arbeitsabläufe behandelt die Replikation von Tabellen, die auf beiden Seiten vorhanden sein müssen (Kampagne der lokalen Datenbank und Cloud-Datenbank). Dieser Workflow wird stündlich ausgelöst und basiert auf einer neuen integrierten JavaScript-Bibliothek.

>[!NOTE]
>
> Es wurden mehrere Replikationsrichtlinien erstellt, die auf der Größe der Tabelle (XS, XL usw.) basieren.
> Einige Tabellen werden in Echtzeit repliziert, während andere stündlich erstellt werden. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, während andere vollständig aktualisiert werden.


[Weitere Informationen zur Datenreplikation](../config/replication.md)

### ID-Management

Kampagne v8-Objekte verwenden jetzt **Universally Unique ID (UUID)**, was unbegrenzte eindeutige Werte zur Identifizierung von Daten impliziert.

Bitte beachten Sie, dass diese ID zeichenfolgenbasiert und nicht sequenziell ist.

### Vereinfachte Wartung

Kampagne-Benutzer müssen keine Datenbankexperten sein: keine lange Workflows oder komplexe Tabellenindizierung mehr zu pflegen.

## Temporäre nicht verfügbare Funktionen{#gs-unavailable-features}

Bitte beachten Sie, dass einige Funktionen in dieser ersten Version nicht verfügbar sind, aber bald veröffentlicht werden, z.B.:

* Verwaltung von Marketing-Ressourcen
* Dezentrales Marketing
* Inbound-Nachrichten im Angebot-Management (Interaktionsmodul)
* Kampagnenoptimierung (Campaign Optimization)
* Reaktionsverwaltung
* Social Marketing mit Twitter
* Hybrid-/lokale Bereitstellungsmodelle

## Entfernte Funktionen{#gs-removed}

Zur Anpassung an neue Architektur- und Bereitstellungsmodelle der Kampagne v8 stehen in Kampagne v8 einige historische Campaign Classic v7-Funktionen nicht zur Verfügung.

* Coupons
* Webtracking
* Umfragen
* Social Marketing mit Facebook
* ACS Connector (Prime-Angebot)
* Microsoft SQL-Datenbank
* Oracle-Datenbank

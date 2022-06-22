---
title: Bekannte Probleme in Campaign v8
description: Bekannte Probleme in der neuesten Campaign-Version
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# Bekannte Probleme{#known-issues}

Auf dieser Seite werden bekannte Probleme aufgelistet, die in der Variablen **neueste Version von Campaign v8**. Darüber hinaus werden Einschränkungen von Campaign v8 aufgelistet [auf dieser Seite](known-limitations.md).


>[!NOTE]
>
>Adobe veröffentlicht diese Liste bekannter Probleme nach eigenem Ermessen. Er basiert auf der Anzahl der Kundenberichte, der Schwere und der Verfügbarkeit der Problemumgehung. Wenn ein Problem, auf das Sie stoßen, nicht aufgelistet ist, entspricht es möglicherweise nicht den Kriterien für die Veröffentlichung auf dieser Seite.

## Problem mit der Datenquelle-Aktivität ändern {#issue-1}

### Beschreibung

Die **Datenquelle ändern** -Aktivität schlägt beim Übertragen von Daten aus der lokalen Campaign-Datenbank in die Snowflake-Cloud-Datenbank fehl. Beim Wechsel der Richtung kann die Aktivität Probleme verursachen.

### Reproduktionsschritte

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Hinzufügen einer **Abfrage** und eine **Datenquelle ändern** Aktivität.
1. Definieren Sie eine Abfrage im **email**, was eine Zeichenfolge ist.
1. Führen Sie den Workflow aus und klicken Sie mit der rechten Maustaste auf die Transition, um die Population anzuzeigen: die E-Mail-Datensätze werden ersetzt durch `****`.
1. Überprüfen Sie die Workflow-Protokolle: die **Datenquelle ändern** -Aktivität interpretiert diese Datensätze als numerische Werte.

### Problemumgehung

Damit die Daten von der Snowflake Cloud-Datenbank in die Campaign-Datenbank und zurück in Snowflake übertragen werden, müssen Sie zwei verschiedene **Datenquelle ändern** Aktivitäten.

### Interner Verweis

Referenz: NEO-45549


## Die Aktivität Laden (Datei) konnte die Datei nicht auf den Server hochladen {#issue-2}

### Beschreibung

Der Datei-Upload auf den Campaign-Server stoppt bei 100 % Fortschritt, endet jedoch nie.

### Reproduktionsschritte

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Hinzufügen einer **Laden (Datei)** und konfigurieren Sie sie.
1. Wählen Sie die **Auf Server hochladen** -Option.
1. Wählen Sie die Datei auf Ihrem lokalen Computer aus.
1. Klicken **Hochladen**

### Problemumgehung

Kein(e)

### Interner Verweis

Referenz: NEO-47269
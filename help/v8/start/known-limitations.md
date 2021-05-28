---
solution: Campaign v8
product: Adobe Campaign
title: Bekannte Einschränkungen in Campaign v8
description: Bekannte Einschränkungen
feature: Übersicht
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 583a8f6a03b00e1eafa6d408c9949e60a6f8158d
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# Bekannte Einschränkungen

Bekannte Einschränkungen identifizieren Funktionen, Architekturen oder Prozesse, die von dieser Version des Produkts nicht unterstützt werden oder nicht ordnungsgemäß mit dem Produkt interagieren. Überprüfen Sie diese Einschränkungen sorgfältig.

Für Adobe Campaign v8 bestehen die folgenden Einschränkungen:

* Adobe Campaign v8 ist nicht für On-Premise-/Hybrid-Bereitstellungen verfügbar - nur als Adobe Managed Cloud Service veröffentlicht
* Bestehende Kunden können nicht von einer bestehenden Adobe Campaign-Umgebung auf Adobe Campaign v8 migrieren
* Keine bidirektionale Datenreplikation: Die Replikation erfolgt nur über die lokale Campaign-Datenbank in die Cloud-Datenbank
* Die in diesem Abschnitt](capability-matrix.md#gs-unavailable-features) aufgelisteten Funktionen sind im aktuellen Build von Campaign v8 nicht verfügbar.[
* Einige nicht verfügbare oder entfernte Funktionen sind weiterhin in der Benutzeroberfläche sichtbar
* Die Mechanismen für die Anmeldung (Opt-in) und Abmeldung (Opt-out) sowie die mobile Registrierung sind asynchrone Prozesse. Anforderungen werden stündlich über einen spezifischen technischen Workflow verarbeitet. [Mehr dazu](../config/replication.md#tech-wf)
* ID-Verwaltung - Duplikate - zur Bestätigung + Details
* LINE - zur Bestätigung + Details
* Latenz - zur Bestätigung + Details



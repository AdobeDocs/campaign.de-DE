---
product: Adobe Campaign
title: Bekannte Einschränkungen in Campaign v8
description: Bekannte Einschränkungen
feature: Übersicht
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 08c1f2fbe79845fe54670e25ac4a63ab65517513
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 3%

---

# Bekannte Einschränkungen

Bekannte Einschränkungen identifizieren Funktionen, Architekturen oder Prozesse, die von dieser Version des Produkts nicht unterstützt werden oder nicht ordnungsgemäß mit dem Produkt interagieren. Überprüfen Sie diese Einschränkungen sorgfältig.

Für Adobe Campaign v8 bestehen die folgenden Einschränkungen:

* Adobe Campaign v8 ist nicht für On-Premise-/Hybridbereitstellungen verfügbar, sondern nur als Adobe Managed Cloud Service.
* Bestehende Kunden können nicht von einer bestehenden Adobe Campaign-Umgebung auf Adobe Campaign v8 migrieren
* Keine bidirektionale Datenreplikation: Die Replikation erfolgt nur über die lokale Campaign-Datenbank in die Cloud-Datenbank
* Die in diesem Abschnitt](capability-matrix.md#gs-unavailable-features) aufgelisteten Funktionen sind im aktuellen Campaign v8-Build nicht verfügbar.[
* Einige nicht verfügbare oder entfernte Funktionen sind weiterhin in der Benutzeroberfläche sichtbar
* Die Mechanismen für die Anmeldung (Opt-in) und Abmeldung (Opt-out) sowie die mobile Registrierung sind asynchrone Prozesse. Anforderungen werden stündlich über einen spezifischen technischen Workflow verarbeitet. [Mehr dazu](../config/replication.md#tech-wf)
* Duplikate müssen von Endbenutzern manuell verarbeitet werden. [Mehr dazu](../dev/keys.md)
* LINE - zur Bestätigung + Details
* Latenz - zur Bestätigung + Details

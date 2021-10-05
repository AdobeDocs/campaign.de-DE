---
title: Bekannte Einschränkungen in Campaign v8
description: Bekannte Einschränkungen
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---

# Bekannte Einschränkungen

Bekannte Einschränkungen betreffen Funktionen, Architekturen oder Prozesse, die von dieser Version des Produkts nicht unterstützt werden oder nicht ordnungsgemäß mit dem Produkt interagieren. Überprüfen Sie diese Einschränkungen sorgfältig.

Für Adobe Campaign v8 bestehen die folgenden Einschränkungen:

* Adobe Campaign v8 ist nicht für On-Premise-/Hybridbereitstellungen verfügbar, sondern ausschließlich als Adobe Managed Cloud Service.
* Bestehende Kunden können nicht von einer bestehenden Adobe Campaign-Umgebung auf Adobe Campaign v8 migrieren.
* Keine bidirektionale Datenreplikation: Die Replikation erfolgt nur über die lokale Campaign-Datenbank in die Cloud-Datenbank.
* Die [in diesem Abschnitt](capability-matrix.md#gs-unavailable-features) aufgelisteten Funktionen sind im aktuellen Build von Campaign v8 nicht verfügbar.
* Einige nicht verfügbare oder entfernte Funktionen sind weiterhin in der Benutzeroberfläche sichtbar.
* Die Mechanismen für die Anmeldung (Opt-in) und Abmeldung (Opt-out) sowie die Mobile-Registrierung sind asynchrone Prozesse. Anfragen werden stündlich über einen speziellen technischen Workflow verarbeitet. [Weitere Informationen](../config/replication.md#tech-wf)
* Duplikate müssen von Endbenutzern manuell korrigiert werden. [Weitere Informationen](../dev/keys.md)
* Adobe Campaign v8 bietet keine Unterstützung für erweiterten Durchsatz in API- und Web-Anwendungen. Wenden Sie sich bei besonderen Anforderungen an Adobe, um Beratung zu erhalten.

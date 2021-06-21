---
product: Adobe Campaign
title: Bekannte Einschränkungen in Campaign v8
description: Bekannte Einschränkungen
feature: Übersicht
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 87%

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
* Adobe Campaign v8 unterstützt keinen erweiterten Durchsatz in API- und Webanwendungen. Wenden Sie sich bei besonderen Bedürfnissen an die Adobe, um Beratung zu erhalten.



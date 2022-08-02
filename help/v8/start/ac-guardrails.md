---
title: Schutzmechanismen in Campaign v8
description: Schutzmechanismen in Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---

# Produkt-Schutzmechanismen{#guardrails}

Berechtigungen, Produktbeschränkungen und Leistungs-Schutzmechanismen finden Sie auf der [Produktbeschreibungsseite zu Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

Unten finden Sie zusätzliche Schutzmechanismen und Einschränkungen bei der Verwendung von [!DNL Adobe Campaign].

Schutzmechanismen und Einschränkungen betreffen Funktionen, Architekturen oder Prozesse, die von dieser Version des Produkts nicht unterstützt werden oder nicht ordnungsgemäß mit dem Produkt interagieren. Überprüfen Sie diese Einschränkungen sorgfältig.

* Adobe Campaign v8 ist nicht für On-Premise-/Hybridbereitstellungen verfügbar, sondern ausschließlich als Adobe Managed Cloud Service
* Bestehende Kunden können nicht von einer bestehenden Adobe Campaign-Umgebung zu Adobe Campaign v8 migrieren.
* Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) wird keine bidirektionale Datenreplikation bereitgestellt: Die Replikation erfolgt nur von der lokalen Campaign-Datenbank in die Cloud-Datenbank.
* Die [in diesem Abschnitt](v7-to-v8.md#gs-unavailable-features) aufgelisteten Funktionen sind im aktuellen Build von Campaign v8 nicht verfügbar.
* Einige nicht verfügbare oder entfernte Funktionen sind weiterhin in der Benutzeroberfläche sichtbar.
* Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) sind Mechanismen zur Anmeldung (Opt-in-) und zur Abmeldung (Opt-out) sowie die Mobile-Registrierung asynchrone Prozesse. Anfragen werden stündlich über einen speziellen technischen Workflow verarbeitet. [Weitere Informationen](../architecture/replication.md#tech-wf)
* Duplikate müssen von Endbenutzern manuell korrigiert werden. [Weitere Informationen](../architecture/keys.md)
* Adobe Campaign v8 unterstützt keinen erweiterten Durchsatz in API- und Web-Anwendungen. Wenden Sie sich bei besonderen Anforderungen an Adobe, um Beratung zu erhalten.
* Das Optimierungsmodul von Adobe Campaign berücksichtigt keine geplanten Sendungen in Drucktypologieregeln. Weitere Informationen finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/pressure-rules.html?lang=de).
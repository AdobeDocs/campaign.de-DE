---
title: Schutzmechanismen in Campaign v8
description: Schutzmechanismen in Campaign v8
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 100%

---

# Produkt-Schutzmechanismen{#guardrails}

Berechtigungen, Produktbeschränkungen und die Performance betreffende Leitplanken finden Sie auf der [Produktbeschreibungsseite zu Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Unten finden Sie zusätzliche Schutzmechanismen und Einschränkungen bei der Verwendung von [!DNL Adobe Campaign].

Schutzmechanismen und Einschränkungen betreffen Funktionen, Architekturen oder Prozesse, die von dieser Version des Produkts nicht unterstützt werden oder nicht ordnungsgemäß mit dem Produkt interagieren. Überprüfen Sie diese Einschränkungen sorgfältig.

* Adobe Campaign v8 ist nicht für On-Premise-/Hybridbereitstellungen verfügbar, sondern ausschließlich als Adobe Managed Cloud Service
* Für Bestandskundinnen und -kunden ist keine automatische Migration auf Adobe Campaign v8 verfügbar
* Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) wird keine bidirektionale Datenreplikation bereitgestellt: Die Replikation erfolgt nur von der lokalen Campaign-Datenbank in die Cloud-Datenbank.
* Die [in diesem Abschnitt](v7-to-v8.md#gs-unavailable-features) aufgelisteten Funktionen sind im aktuellen Build von Campaign v8 nicht verfügbar.
* Einige nicht verfügbare oder entfernte Funktionen sind weiterhin in der Benutzeroberfläche sichtbar.
* Im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) sind Mechanismen zur Anmeldung (Opt-in-) und zur Abmeldung (Opt-out) sowie die Mobile-Registrierung asynchrone Prozesse. Anfragen werden stündlich über einen speziellen technischen Workflow verarbeitet. [Weitere Informationen](../architecture/replication.md#tech-wf)
* Im Kontext einer [Enterprise-Bereitstellung (FFDA)](../architecture/enterprise-deployment.md) müssen Duplikate von Endbenutzerinnen und -benutzern manuell verarbeitet werden. [Weitere Informationen](../architecture/keys.md)
* Adobe Campaign v8 unterstützt keinen erweiterten Durchsatz in API- und Web-Anwendungen. Wenden Sie sich bei besonderen Anforderungen an Adobe, um Beratung zu erhalten.
* Im Kontext einer [Enterprise-Bereitstellung (FFDA)](../architecture/enterprise-deployment.md) berücksichtigt das Adobe Campaign Campaign Optimization-Modul geplante Sendungen nicht in Drucktypologieregeln. Weitere Informationen auf [dieser Seite](../../automation/campaign-opt/pressure-rules.md)
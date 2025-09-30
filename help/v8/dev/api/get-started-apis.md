---
title: Erste Schritte mit Campaign REST-APIs
description: Erstellen Sie Integrationen und bauen Sie Ihr eigenes Ökosystem, indem Sie Campaign mit einer Reihe von Technologien verbinden.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: 115b7b6824f3736e03f9fb87898f1264f9bab636
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 43%

---

# Erste Schritte mit Campaign REST-APIs {#get-started-apis}

Mit den Campaign REST-APIs können Sie **Integrationen erstellen** für Adobe Campaign erstellen und **Ihr eigenes Ökosystem**, indem Sie Adobe Campaign mit dem von Ihnen verwendeten Technologiebereich verbinden.

>[!AVAILABILITY]
>
>* Diese Funktion ist nur bei Bedarf für alle [Campaign FDA-Umgebungen](../../architecture/fda-deployment.md) verfügbar. Sie ist **nicht** für [Enterprise (FFDA)-Bereitstellungen verfügbar](../../architecture/enterprise-deployment.md). Wenden Sie sich für Zugriff an den Adobe-Support.
>
>* Bevor Sie API-Aufrufe ausführen, überprüfen Sie bitte die Volumenbeschränkungen in Ihrer Lizenzvereinbarung. Weitere Informationen hierzu finden Sie in der [Adobe Campaign v8-Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.


Mit den Adobe Campaign REST-APIs erhalten Sie Zugriff auf die folgenden Funktionen:

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="Bedingungen" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Profile</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="Bedingungen" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Dienste und Abonnements</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="Bedingungen" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Benutzerdefinierte Ressourcen</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="Bedingungen" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Workflows</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="Bedingungen" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Transaktionsnachrichten</a></p></td>
</tr></table>

Um die Campaign REST-APIs verwenden zu können, benötigen Sie ein Adobe I/O-Konto. Dies ist ein notwendiger erster Schritt zum Kennenlernen der API-Funktionen.
Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](setting-up-api-access.md).

Die APIs, die wir bereitstellen, basieren auf **Standardkonzepten** mit einer REST-Schnittstelle und JSON-Payloads.

Alle Endpunkte werden in dieser Dokumentation ausführlich mit den allgemeinen Begriffen beschrieben, die Sie für die Bearbeitung der API kennen sollten, sowie mit der vollständigen API-Referenz, Code-Beispielen und Schnellstartanleitungen. Alle Beispiele arbeiten mit Postman; Sie können aber auch Ihren bevorzugten REST-Client nutzen.


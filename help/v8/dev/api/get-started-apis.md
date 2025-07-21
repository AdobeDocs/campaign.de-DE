---
title: Erste Schritte mit Campaign REST-APIs
description: Erstellen Sie Integrationen und bauen Sie Ihr eigenes Ökosystem, indem Sie Campaign mit einer Reihe von Technologien verbinden.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: ea51863bdbc22489af35b2b3c81259b327380be4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 47%

---

# Erste Schritte mit Campaign REST-APIs {#get-started-apis}

>[!AVAILABILITY]
>
>Diese Funktion ist nur bei Bedarf für alle Campaign FDA-Umgebungen verfügbar. Sie **nicht** für Campaign FFDA-Bereitstellungen verfügbar. Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um Zugriff zu erhalten.

>[!CAUTION]
>
>Bevor Sie API-Aufrufe ausführen, überprüfen Sie bitte die Volumenbeschränkungen in Ihrer Lizenzvereinbarung. Weiterführende Informationen hierzu finden Sie auf dieser [Seite](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

Mit den Campaign REST-APIs können Sie **Integrationen erstellen** für Adobe Campaign erstellen und **Ihr eigenes Ökosystem**, indem Sie Adobe Campaign mit dem von Ihnen verwendeten Technologiebereich verbinden.

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

Wenn etwas fehlt oder fehlerhaft erscheint, fragen Sie bitte die [Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community).

---
title: Integrierte Packages
description: Erfahren Sie, was integrierte Pakete in Campaign v8 sind, wie sie sich von benutzerdefinierten Datenpaketen unterscheiden und welche verfügbar sind
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 9f70a309a882347a0df658d00c47127f31d28eb9
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 16%
---
# Integrierte Packages {#built-in-packages}

Integrierte Pakete (auch als Standardpakete bezeichnet) enthalten die Funktionen von Adobe Campaign. In Campaign v8 installiert Adobe diese Packages und verwaltet sie für Sie. Sie müssen sie nicht installieren.

## Integrierte Pakete und benutzerdefinierte Pakete {#built-in-vs-custom}

Campaign verwendet zwei Arten von Paketen. Stellen Sie sicher, dass Sie mit dem richtigen arbeiten.

| | Integrierte Packages | Benutzerdefinierte Pakete |
|---|---|---|
| Zweck | Stellen Sie die Campaign-Funktionen wie Kanäle, Integrationen und Add-ons bereit. | Exportieren und importieren Sie Ihre eigenen Konfigurationen und Daten, z. B. aus einer Staging- in eine Produktionsumgebung. |
| Wer verwaltet sie? | Adobe installiert und verwaltet sie. Mit Managed Cloud Services können Sie installierte integrierte Pakete nicht ändern. | Sie erstellen, exportieren und importieren sie. |
| Weitere Informationen | Diese Seite. | [Arbeiten mit Datenpaketen](../dev/packages.md) |

## Überprüfen der installierten Pakete {#check-installed-packages}

Um zu überprüfen, welche integrierten Pakete in Ihrer Instanz installiert sind, navigieren Sie zu **[!UICONTROL Administration > Konfiguration > Paketverwaltung > Installierte Pakete]**. Sie können sie auch in der Instanzüberwachung des Control Panels anzeigen. Weitere Informationen finden Sie unter [Übersicht über die Kampagnenüberwachung](../start/monitor.md#monitor-instance).

Wenn Sie ein nicht für Sie bereitgestelltes Paket oder Add-on benötigen, wenden Sie sich an die Adobe-Kundenunterstützung oder Ihren Adobe Transition Manager.

## Liste der integrierten Packages {#list-of-built-in-packages}

In der folgenden Tabelle sind die integrierten Packages aufgeführt. Die Verfügbarkeit der einzelnen Pakete hängt von Ihrer Lizenzvereinbarung und Ihrem Bereitstellungsmodell ab.

| Package | Beschreibung |
|---|---|
| Versand | Überwacht Sendungen und Probleme beim Versand von Nachrichten. [Weitere Informationen](../start/monitor.md) |
| Marketing-Kampagnen (Campaign) | Definiert, optimiert, führt aus und analysiert Kommunikations- und Marketing-Kampagnen. [Weitere Informationen](../start/campaigns.md) |
| Marketing-Ressourcen (MRM) | Steuert Marketing-Aktionen im kollaborativen Modus mit Verwaltung und Verfolgung von Aufgaben, Budgets und Marketing-Ressourcen. [Weitere Informationen](../../automation/mrm/about-marketing-resource-management.md) |
| Angebotsmodul (interaction) | Reagiert in Echtzeit während einer Interaktion mit einem Kontakt, indem ein oder mehrere angepasste Angebote gemacht werden. [Weitere Informationen](../interaction/interaction.md) |
| Soziale Netzwerke (Social-Media-Marketing) | Synchronisiert Adobe Campaign mit X (früher Twitter). [Weitere Informationen](../connect/ac-tw.md) |
| Kontrolle und Ausführung von Transaktionsnachrichten (Message Center) | Verwaltet Trigger-Nachrichten, die von Ereignissen in Informationssystemen generiert wurden, mit höherer Verfügbarkeit und besserem Lastmanagement. [Weitere Informationen](../send/transactional.md) |
| LINE-Kanal | Sendet Sendungen über den LINE-Kanal. [Weitere Informationen](../send/line/line.md) |
| Direkt-Mail-Kanal | Sendet Sendungen über den Briefpostkanal. [Weitere Informationen](../send/direct-mail.md) |
| Mobile-Kanal (SMS) | Sendet Sendungen über den mobilen Kanal (SMS), einschließlich SMS-Connector v2 (allgemein verfügbar seit 8.9.1). [Weitere Informationen](../send/sms/sms.md) |
| Mobile-App-Kanal | Sendet personalisierte Benachrichtigungen über Apps an iOS- und Android-Geräte. [Weitere Informationen](../send/push.md) |
| Inhaltsverwaltung | Erstellt wiederkehrende Newsletter oder Websites und validiert und veröffentlicht Ihre Nachrichten. [Weitere Informationen](../../automation/workflow/content-management.md) |
| Online-Umfragen (Survey Manager) | Erstellt und verwaltet Online-Formulare zum Hinzufügen oder Ändern von Profilinformationen, zum Abonnieren, Abmelden oder Eintreten in einen Wettbewerb. [Weitere Informationen](../dev/surveys/about-surveys.md) |
| Marketing-Analyse | Analysiert und misst Daten, berechnet Statistiken und vereinfacht die Berichterstellung. [Weitere Informationen](../reporting/gs-reporting.md) |
| Reaktionsverwaltung | Misst den Erfolg und die Rentabilität von Marketing-Kampagnen oder -Angeboten über alle Kanäle hinweg. [Weitere Informationen](../../automation/response/about-response-manager.md) |
| Zugriff auf externe Daten (Federated Data Access) | Verarbeitet Informationen, die in externen Datenbanken gespeichert sind, ohne die Datenstruktur von Adobe Campaign zu ändern. [Weitere Informationen](../connect/fda.md) |
| Kampagnenoptimierung (Campaign Optimization) | Steuert, filtert und überwacht Sendungen, damit Nachrichten den Kundenanforderungen und den Kommunikationsrichtlinien des Unternehmens entsprechen. [Weitere Informationen](../../automation/campaign-opt/campaign-typologies.md) |
| Zustellbarkeits-Monitoring (Email Deliverability) | Ermittelt, ob Ihre Nachrichten den Posteingang erreichen, ohne dass sie zurückgeschickt werden oder als Spam gekennzeichnet werden. [Weitere Informationen](../send/monitoring-deliverability.md) |
| Couponverwaltung | Erstellt Couponsätze, die Marketing-Angeboten hinzugefügt werden [Weitere Informationen](../send/personalized-coupons.md) |
| Inbox-Rendering (IR) | Zeigt eine Vorschau der Nachrichten in den Kontexten an, in denen sie empfangen werden können, und überprüft die Kompatibilität mit den wichtigsten Desktop- und Web-E-Mail-Clients. [Weitere Informationen](../send/inbox-rendering.md) |
| Zentrales/lokales Marketing (verteiltes Marketing) | Implementiert Kooperationskampagnen zwischen zentralen Entitäten wie dem Hauptsitz und lokalen Entitäten wie Verkaufsstellen. [Weitere Informationen](../../automation/distributed-marketing/about-distributed-marketing.md) |
| CRM-Connectoren | Verknüpft Adobe Campaign mit CRM-Systemen von Drittanbietern. [Weitere Informationen](../connect/crm.md) |
| Web Analytics-Connectoren | Ermöglicht die Interaktion von Adobe Campaign und Adobe Analytics. [Weitere Informationen](../connect/ac-aa.md) |
| Integration mit AEM | Verwaltet den Inhalt von E-Mails und Formularen in Adobe Experience Manager. [Weitere Informationen](../connect/ac-aem.md) |
| Integration mit Adobe Experience Cloud Zielgruppen-Freigabe | Austauscht Audiences mit [!DNL Adobe CX Enterprise] (ehemals Adobe Experience Cloud)-Lösungen und -Programmen und gibt sie frei. [Weitere Informationen](../start/shared-audiences.md) |
| Integration mit Adobe Experience Cloud | Importiert und exportiert Zielgruppen aus [!DNL Adobe CX Enterprise]-Lösungen (ehemals Adobe Experience Cloud) in Adobe Campaign. [Weitere Informationen](../connect/integration.md) |
| Datenschutzbestimmung | Fügt Funktionen hinzu, um die Einhaltung von Datenschutzbestimmungen zu erleichtern. [Weitere Informationen](../start/privacy.md) |
| AMP-Unterstützung | Sendet dynamische E-Mails mit dem interaktiven AMP für das E-Mail-Format. [Weitere Informationen](../send/defining-interactive-content.md) |


>[!NOTE]
>
>Die Pakete Marketing-Ressourcen (MRM), Couponverwaltung und Online-Umfragen sind im Kontext einer Enterprise (FFDA)-Bereitstellung von Campaign nicht verfügbar. Weitere Informationen finden Sie unter [Funktionsverfügbarkeit](../architecture/enterprise-deployment.md#feature-availability).

## Verwandte Themen {#related-topics}

* [Arbeiten mit Datenpaketen](../dev/packages.md): Erstellen, exportieren und importieren Sie Ihre eigenen benutzerdefinierten Pakete.
* [Technische Workflows](../../automation/workflow/technical-workflows.md): Die integrierten technischen Workflows und das Paket, mit dem sie installiert werden.
* [Funktionsverfügbarkeit in FFDA-Bereitstellungen](enterprise-deployment.md#feature-availability): Die Funktionen, die in Enterprise (FFDA)-Bereitstellungen nicht verfügbar sind.
* [Nicht unterstützte Funktionen](../start/v7-to-v8.md#gs-removed): Die Funktionen von Campaign Classic v7, die in v8 nicht mehr unterstützt werden.
* [Globale Prinzipien](general-architecture.md): Was Sie in einer Managed Cloud Services-Umgebung ändern können und was nicht.
* [Erste Schritte mit Campaign v8](../start/get-started.md): Ein Überblick über die Kernfunktionen und Add-ons.

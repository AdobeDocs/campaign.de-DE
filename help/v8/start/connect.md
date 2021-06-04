---
product: Adobe Campaign
title: Erfahren Sie, wie Sie eine Verbindung mit Campaign v8 herstellen.
description: Verbindung mit Campaign v8 herstellen
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 03585f0c1514a80b0b0cba5a2d05fa3f44398405
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 77%

---

# Verbindung mit Adobe Campaign v8 herstellen{#gs-ac-connect}

Die Client-Konsole in Campaign ist ein Rich-Client, mit dem Sie eine Verbindung zu Ihren Campaign-Anwendungs-Servern herstellen können.

Bevor Sie beginnen, müssen Sie:

* Überprüfen Sie die Kompatibilität Ihrer Systeme und Tools mit Adobe Campaign in der [Kompatibilitätsmatrix](compatibility-matrix.md) .
* Campaign-Server-URL abrufen
* Benutzeranmeldeinformationen abrufen

## Client-Konsole herunterladen und installieren

Wenn Sie Campaign zum ersten Mal verwenden oder auf eine neuere Version aktualisieren möchten, müssen Sie die Client-Konsole herunterladen und installieren.

Dazu sind zwei Optionen verfügbar:

1. Stellen Sie als Campaign-Administrator eine Verbindung zur Adobe [Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) her und laden Sie das Installationsprogramm für die Client-Konsole herunter. Sie können die Konsole dann auf Ihrem lokalen Computer installieren.

1. Adobe kann die Konsole für Sie als Endanwender bereitstellen: Sobald die Konsole aktualisiert wird, werden Sie in einem Popup-Fenster aufgefordert, die neueste Version der Client-Konsole herunterzuladen.

>[!CAUTION]
>
>Adobe empfiehlt, die Option **[!UICONTROL Diese Frage nicht mehr stellen]** deaktiviert zu lassen, um sicherzustellen, dass alle Anwender benachrichtigt werden, wenn eine neue Version der Konsole verfügbar ist.  Wenn diese Option aktiviert ist, wird der Anwender nicht über neue verfügbare Versionen informiert.

## Verbindung erstellen

Nachdem die Client-Konsole neu installiert wurde, führen Sie die folgenden Schritte aus, um die Verbindung zum Anwendungs-Server herzustellen:

1. Starten Sie die Konsole über das Windows-**[!UICONTROL Start]**-Menü in der **Adobe Campaign**-Programmgruppe.

1. Klicken Sie in der oberen rechten Ecke der Felder mit den Anmeldedaten auf den Link, um das Fenster für die Verbindungskonfiguration aufzurufen.

1. Klicken Sie auf **[!UICONTROL Hinzufügen > Verbindung]** und geben Sie die Bezeichnung und URL des Adobe Campaign-Anwendungs-Servers ein.

1. Geben Sie per URL eine Verbindung zum Adobe Campaign-Anwendungs-Server an. Verwenden Sie entweder einen DNS oder einen Alias des Computers oder Ihre IP-Adresse.

   Sie können beispielsweise eine URL vom Typ [`https://<machine>.<domain>.com`](https://myserver.adobe.com) eingeben.

1. Wenn für Ihr Unternehmen Adobe Identity Management System (IMS) konfiguriert ist, aktivieren Sie die Option **[!UICONTROL Anmeldung mit einer Adobe ID]**.

1. Klicken Sie auf **[!UICONTROL OK]**, um Ihre Einstellungen zu speichern.

Sie können so viele Verbindungen wie erforderlich hinzufügen, um z. B. Verbindungen zu Ihren Test-, Staging- und Produktionsumgebungen herzustellen.

>[!NOTE]
>
>Die Schaltfläche **[!UICONTROL Hinzufügen]** erlaubt die Erstellung von **[!UICONTROL Ordnern]**, in die Sie Ihre verschiedenen Verbindungen per Drag-and-Drop verschieben können.

## Bei Adobe Campaign anmelden

Gehen Sie wie folgt vor, um sich bei einer vorhandenen Instanz anzumelden:

1. Starten Sie die Konsole über das Windows-**[!UICONTROL Start]**-Menü in der **Adobe Campaign**-Programmgruppe.

1. Klicken Sie in der oberen rechten Ecke der Felder mit den Anmeldedaten auf den Link, um das Fenster für die Verbindungskonfiguration aufzurufen.

1. Wählen Sie die Campaign-Instanz aus, bei der Sie sich anmelden möchten.

1. Bestätigen Sie die Aktion mit der Schaltfläche **[!UICONTROL OK]**.

1. Geben Sie Ihre Anwender-Anmeldedaten ein und klicken Sie auf **[!UICONTROL ANMELDEN]**.

   ![](assets/sign-in-v8.png)

Je nach Ihrer Konfiguration können Ihre Anmeldedaten wie folgt lauten:

* bereitgestellt von Ihrem Campaign-Administrator, der Ihnen Zugriff gewährt hat
* Ihre Adobe ID

## Benutzern Zugriff gewähren

Adobe Campaign ermöglicht es, die den unterschiedlichen Benutzern zugeteilten Rechte zu bestimmen und zu verwalten. Es handelt es sich um Berechtigungen und Beschränkungen folgender Aktivitäten:

* Zugriff auf bestimmte Funktionen (über spezifische Berechtigungen);
* Zugriff auf bestimmte Elemente;
* Erstellen, Ändern und/oder Löschen von Elementen (Versand, Kontakte, Kampagnen, Gruppen usw.).

Weitere Informationen zu Anwendern und zum Definieren ihrer Berechtigungen finden Sie in [diesem Abschnitt](permissions.md).

Als Campaign-Administrator sind Sie dafür verantwortlich, die Benutzer zu erstellen und Anmeldedaten der Anwender mit ihnen zu teilen.

## Verbindung mit Campaign über Ihre Adobe ID herstellen{#connect-ims}

Campaign-Anwender können über Adobe Identity Management System (IMS) mit ihrer Adobe ID eine Verbindung zur Adobe Campaign-Konsole herstellen. Diese Implementierung bietet folgende Vorteile:

* Verwendung ein und derselben ID für alle Adobe Experience Cloud-Lösungen;
* Speicherung der Verbindung bei der Verwendung von Adobe Campaign mit den verschiedenen Integrationen;
* Stärkere Sicherheitsrichtlinien für die Passwortverwaltung;
* Verwendung von Konten des Typs Federated ID (externer Identity Provider).

[!DNL :speech_balloon:] Als Benutzer von Managed Cloud Services  [kontaktieren Sie ](campaign-faq.md#support) Adobe, um Adobe IMS mit Campaign zu implementieren.

## Verbindung mit Campaign über Ihre LDAP-Anmeldung herstellen

Adobe Campaign kann so konfiguriert werden, dass der Anwender über seine LDAP-Authentifizierung auf die Plattform zugreift.

[!DNL :speech_balloon:] Als Benutzer von Managed Cloud Services  [kontaktieren Sie ](campaign-faq.md#support) Adobe, um die LDAP-Integration mit Campaign zu konfigurieren.


## Web-Zugriff{#web-access}

Bestimmte Teile der Anwendung können über einen einfachen Webbrowser über eine HTML-Benutzeroberfläche aufgerufen werden: Kampagnen-Dashboard, Cube-Reporting, Instanzüberwachung und mehr.

[!DNL :arrow_upper_right:] Weitere Informationen zum Webzugriff finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#console-and-web-access)

Der Webzugriff bietet eine Schnittstelle, die der Konsole ähnlich ist, jedoch eingeschränkte Funktionen aufweist.

Beispielsweise wird für einen bestimmten Benutzer eine Kampagne mit den folgenden Optionen in der Konsole angezeigt:

![](assets/campaign-from-console.png)

Beim Webzugriff ermöglichen die Optionen vor allem die Anzeige von:

![](assets/campaign-from-web.png)

Der Webzugriff wird auch für den Validierungsprozess verwendet: Benutzer können auf die E-Mail mit der Validierungsanfrage klicken und über ihren Webbrowser eine Verbindung zu Campaign herstellen, um Versandinhalte oder -budgets zu validieren oder abzulehnen.

[!DNL :arrow_upper_right:] Informationen zum Einrichten und Verwalten von Genehmigungen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=de#orchestrating-campaigns)

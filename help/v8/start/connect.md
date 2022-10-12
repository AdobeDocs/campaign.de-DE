---
title: Verbindung mit Campaign v8 herstellen
description: Erfahren Sie, wie Sie eine Verbindung mit Campaign v8 herstellen.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 100%

---

# Verbindung mit Adobe Campaign v8 herstellen{#gs-ac-connect}

Die Client-Konsole in Campaign ist ein Rich-Client, mit dem Sie eine Verbindung zu Ihren Campaign-Anwendungs-Servern herstellen können.

Bevor Sie beginnen, müssen Sie folgende Schritte ausführen:

* Überprüfen Sie die Kompatibilität Ihres Systems und Ihrer Tools mit Adobe Campaign in der [Kompatibilitätsmatrix](compatibility-matrix.md)
* Ermitteln Sie Ihre Campaign-Server-URL
* Erstellen Sie Ihre Adobe ID oder rufen Sie Ihre Benutzeranmeldeinformationen von Ihrem Unternehmen ab
* Installieren Sie die Microsoft Edge Webview2-Laufzeitumgebung auf Ihrem System (ab Campaign Classic 8.4). [Weitere Informationen](#webview)

## Installation der Microsoft Edge Webview2-Laufzeitumgebung {#webview}

Ab der Build-Version 8.4 von Campaign Classic ist die Installation der Microsoft Edge Webview 2-Laufzeitumgebung für jede Konsolen-Installation erforderlich.

WebView wird standardmäßig als Teil des Betriebssystems Windows 11 installiert. Wenn es nicht bereits auf Ihrem System vorhanden ist, werden Sie vom Installationsprogramm der Campaign-Konsole aufgefordert, es von der [Microsoft Developer Website](http://www.adobe.com/go/acc-ms-webview2-runtime-download_de) herunterzuladen. Beachten Sie, dass der Download-Link nicht mit Internet Explorer 11 funktioniert, da Microsoft die Unterstützung dieses Browsers eingestellt hat. Stellen Sie sicher, dass Sie einen anderen Browser verwenden, um auf den Link zuzugreifen.

## Client-Konsole herunterladen und installieren{#download-ac-console}

Wenn Sie Campaign zum ersten Mal verwenden oder auf eine neuere Version aktualisieren möchten, müssen Sie die Client-Konsole herunterladen und installieren.

Dazu sind zwei Optionen verfügbar:

1. Stellen Sie als Campaign-Administrator eine Verbindung zur Adobe [Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html) her und laden Sie das Installationsprogramm für die Client-Konsole herunter. Sie können die Konsole dann auf Ihrem lokalen Computer installieren.

1. Adobe kann die Konsole für Sie als Endanwender bereitstellen: Sobald die Konsole aktualisiert wird, werden Sie in einem Popup-Fenster aufgefordert, die neueste Version der Client-Konsole herunterzuladen.

>[!CAUTION]
>
>Adobe empfiehlt, die Option **[!UICONTROL Diese Frage nicht mehr stellen]** deaktiviert zu lassen, um sicherzustellen, dass alle Anwender benachrichtigt werden, wenn eine neue Version der Konsole verfügbar ist.  Wenn diese Option aktiviert ist, wird der Anwender nicht über neue verfügbare Versionen informiert.

## Verbindung erstellen{#create-your-connection}

Nachdem die Client-Konsole neu installiert wurde, führen Sie die folgenden Schritte aus, um die Verbindung zum Anwendungs-Server herzustellen:

1. Starten Sie die Konsole über das Windows-**[!UICONTROL Start]**-Menü in der **Adobe Campaign**-Programmgruppe.

1. Klicken Sie in der oberen rechten Ecke der Felder mit den Anmeldedaten auf den Link, um das Fenster für die Verbindungskonfiguration aufzurufen.

1. Klicken Sie auf **[!UICONTROL Hinzufügen > Verbindung]** und geben Sie die Bezeichnung und URL des Adobe Campaign-Anwendungs-Servers ein.

1. Geben Sie per URL eine Verbindung zum Adobe Campaign-Anwendungs-Server an. Verwenden Sie entweder einen DNS oder einen Alias des Computers oder Ihre IP-Adresse.

   Sie können beispielsweise eine URL vom Typ [`https://<machine>.<domain>.com`](https://myserver.adobe.com) eingeben.

1. Aktivieren Sie die Option **[!UICONTROL Anmeldung mit einer Adobe ID]**.

1. Klicken Sie auf **[!UICONTROL OK]**, um Ihre Einstellungen zu speichern.

Sie können so viele Verbindungen wie erforderlich hinzufügen, um z. B. Verbindungen zu Ihren Test-, Staging- und Produktionsumgebungen herzustellen.

>[!NOTE]
>
>Die Schaltfläche **[!UICONTROL Hinzufügen]** erlaubt die Erstellung von **[!UICONTROL Ordnern]**, in die Sie Ihre verschiedenen Verbindungen per Drag-and-Drop verschieben können.

## Bei Adobe Campaign anmelden {#logon-to-ac}

Gehen Sie wie folgt vor, um sich bei einer vorhandenen Instanz anzumelden:

1. Starten Sie die Konsole über das Windows-**[!UICONTROL Start]**-Menü in der **Adobe Campaign**-Programmgruppe.

1. Klicken Sie in der oberen rechten Ecke der Felder mit den Anmeldedaten auf den Link, um das Fenster für die Verbindungskonfiguration aufzurufen.

   ![](assets/connectToCampaign.png)

1. Wählen Sie die Campaign-Instanz aus, bei der Sie sich anmelden möchten.

1. Bestätigen Sie die Aktion mit der Schaltfläche **[!UICONTROL OK]**.

1. Sie können sich dann mit [Ihrer Adobe ID](#connect-ims) bei Campaign anmelden.

   ![](assets/adobeID.png)

>[!NOTE]
>
>Bei den Build-Versionen 8.4 von Campaign Classic kann es vorkommen, dass die Adobe Campaign-Client-Konsole während der Proxy-Authentifizierung zweimal nach den Proxy-Anmeldeinformationen fragt. Dies liegt daran, dass Microsoft Edge WebView2 im Gegensatz zum Internet Explorer keine Proxy-Anmeldeinformationen im Cache/Kennwortspeicher speichert.

## Benutzern Zugriff gewähren{#grant-access}

Adobe Campaign ermöglicht es, die den unterschiedlichen Benutzern zugeteilten Rechte zu bestimmen und zu verwalten. Es handelt es sich um Berechtigungen und Beschränkungen folgender Aktivitäten:

* Zugriff auf bestimmte Funktionen (über spezifische Berechtigungen);
* Zugriff auf bestimmte Elemente;
* Erstellen, Ändern und/oder Löschen von Elementen (Versand, Kontakte, Kampagnen, Gruppen usw.).

Weitere Informationen zu Anwendern und zum Definieren ihrer Berechtigungen finden Sie in [diesem Abschnitt](permissions.md).

Als Campaign-Administrator sind Sie dafür verantwortlich, die Benutzer zu erstellen und Anmeldedaten der Anwender mit ihnen zu teilen.

## Verbindung mit Campaign über Ihre Adobe ID herstellen{#connect-ims}

Campaign-Anwender stellen über das Adobe Identity Management System (IMS) mit ihrer Adobe ID eine Verbindung zur Adobe Campaign-Konsole her. Sie können für alle Adobe-Lösungen dieselbe ID verwenden. Die Verbindung wird bei Verwendung von Adobe Campaign mit anderen Lösungen gespeichert.

Weitere Informationen zu Adobe IMS finden Sie auf [dieser Seite](https://helpx.adobe.com/de/enterprise/using/identity.html).

## Web-Zugriff{#web-access}

Einige Bereiche des Programms können über einen Webbrowser mittels HTML-Benutzeroberfläche aufgerufen werden: darunter etwas das Reporting, die Versandvalidierung oder auch das Instanz-Monitoring.

Der Web-Zugriff bietet eine der Client-Konsole ähnliche Bedieneroberfläche mit eingeschränkten Funktionalitäten.

So wird z. B. für einen Benutzer eine Kampagne in der Client-Konsole mit folgenden Optionen angezeigt:

![](assets/campaign-from-console.png)

Beim Web-Zugriff ermöglichen die Optionen vor allem die Anzeige von:

![](assets/campaign-from-web.png)

Der Web-Zugriff wird auch für den Validierungsprozess verwendet: Benutzer können auf die E-Mail mit der Validierungsanfrage klicken und über ihren Webbrowser eine Verbindung zu Campaign herstellen, um Versandinhalte oder -budgets zu validieren oder abzulehnen.

Um über das Web auf Ihre Campaign-Instanz zuzugreifen, lautet die URL: `https://<your adobe campaign server>:<port number>/view/home`.

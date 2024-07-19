---
title: Herstellen einer Verbindung mit Campaign über die Client-Konsole
description: Erfahren Sie, wie Sie die Campaign-Client-Konsole auf Ihrem Computer installieren und eine Verbindung mit Adobe Campaign herstellen.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 10b1113a20c11e0b97804f597cb0a48568fcae3d
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 100%

---

# Herstellen einer Verbindung mit Campaign über die Client-Konsole{#gs-ac-connect}

Um Campaign mit der Client-Konsole zu verbinden, müssen Sie diese zunächst installieren und konfigurieren.

Bevor Sie beginnen, müssen Sie folgende Schritte ausführen:

* Überprüfen Sie die Kompatibilität Ihres Systems und Ihrer Tools mit Adobe Campaign in der [Kompatibilitätsmatrix](compatibility-matrix.md)
* Ermitteln Sie Ihre Campaign-Server-URL
* Erstellen Sie Ihre Adobe ID oder rufen Sie Ihre Benutzeranmeldedaten von Ihrem Unternehmen ab
* Installieren Sie die Microsoft Edge Webview2-Laufzeitumgebung auf Ihrem System. [Weitere Informationen](#webview)


>[!NOTE]
>
>Sie können die Verbindung zur Campaign Web-Benutzeroberfläche auch über einen Webbrowser herstellen.  Weitere Informationen über die neue Campaign Web-Benutzeroberfläche finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=de){target="_blank"}.


## Installieren der Client-Konsole{#download-ac-console}

### Microsoft Edge WebView2-Laufzeitumgebung {#webview}

Ab der Build-Version 8.4 von Campaign Classic ist die Installation der Microsoft Edge WebView2-Laufzeitumgebung für jede Installation der Client-Konsole erforderlich.

WebView wird standardmäßig als Teil des Betriebssystems Windows 11 installiert. Wenn sie nicht bereits auf Ihrem System vorhanden ist, fordert Sie das Installationsprogramm der Campaign-Client-Konsole auf, diese von der [Microsoft Developer Website](http://www.adobe.com/go/acc-ms-webview2-runtime-download_de){target="_blank"} herunterzuladen. Beachten Sie, dass der Download-Link nicht mit Internet Explorer 11 funktioniert, da Microsoft die Unterstützung dieses Browsers eingestellt hat. Stellen Sie sicher, dass Sie einen anderen Browser verwenden, um auf den Link zuzugreifen.

### Herunterladen der Konsole{#install-ac-console}

Bei der erstmaligen Verwendung von Campaign müssen Sie die Client-Konsole herunterladen und installieren.

Es gibt zwei Möglichkeiten, die Client-Konsole herunterzuladen:

1. Als Campaign-Admin verbinden Sie sich mit der [Adobe-Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html){target="_blank"}.

1. Für Endbenutzende stellen deren Campaign-Admins die Client-Konsole bereit und machen sie über eine spezielle URL verfügbar.

Sobald das Installationsprogramm für die Client-Konsole heruntergeladen wurde, installieren Sie es auf dem lokalen Rechner.

Beachten Sie, dass die Sprache der Client-Konsole nach der Installation nicht mehr geändert werden kann.

## Herstellen der Verbindung{#create-your-connection}

Sobald die Client-Konsole installiert ist, führen Sie die folgenden Schritte aus, um die Verbindung zum Anwendungs-Server herzustellen:

1. Starten Sie die Konsole und durchsuchen Sie den Link in der rechten Ecke, um den Bildschirm für die Verbindungskonfiguration aufzurufen.

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

Campaign-Anwender stellen über das Adobe Identity Management System (IMS) mit ihrer Adobe ID eine Verbindung zur Adobe Campaign-Konsole her. Sie können für alle Adobe-Lösungen dieselbe ID verwenden. Die Verbindung wird bei Verwendung von Adobe Campaign mit anderen Lösungen gespeichert. Weitere Informationen zu Adobe IMS finden Sie auf [dieser Seite](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"}.

Um sich bei einer Instanz anzumelden, gehen Sie wie folgt vor:

1. Starten Sie die Konsole und durchsuchen Sie den Link in der rechten Ecke, um den Bildschirm für die Verbindungskonfiguration aufzurufen.

   ![](assets/connectToCampaign.png)

1. Wählen Sie die Campaign-Instanz aus, bei der Sie sich anmelden möchten.

1. Bestätigen Sie die Aktion mit der Schaltfläche **[!UICONTROL OK]**.

Sie können sich dann mit Ihrer Adobe ID bei Campaign anmelden.

![](assets/adobeID.png)

>[!NOTE]
>
>Da Microsoft Edge WebView2 keine Proxy-Anmeldeinformationen speichert, kann die Konsole Sie bei Ihrer ersten Verbindung auffordern, sich zweimal zu authentifizieren.

## Aktualisieren Ihrer Client-Konsole{#upgrade-ac-console}

Wenn Ihr System auf eine neuere Version aktualisiert wird, müssen Sie Ihre Client-Konsole auf dieselbe Version aktualisieren. Dies ist eine Best Practice, und für einige Versionen ist dieses Upgrade obligatorisch. In diesem Fall wird dies in den [Versionshinweise](release-notes.md) angegeben.

Für Benutzerinnen und Benutzer von Managed Cloud Services stellt Adobe die Client-Konsole bereit. Wenn Sie eine Verbindung zu Ihrer aktualisierten Umgebung herstellen, werden Sie in einem Popup-Fenster aufgefordert, die neueste Version der Client-Konsole herunterzuladen. Sie müssen dieses Upgrade akzeptieren und die Client-Konsole wie gefordert aktualisieren.

>[!CAUTION]
>
>Adobe empfiehlt, die Option **[!UICONTROL Diese Frage nicht mehr stellen]** deaktiviert zu lassen, um sicherzustellen, dass Sie benachrichtigt werden, wenn eine neue Version der Konsole verfügbar ist. Wenn diese Option aktiviert ist, werden Benutzende nicht darüber informiert, dass ein Konsolen-Upgrade erforderlich ist.
>



## Gewähren von Zugriff für Benutzende{#grant-access}

Mit Adobe Campaign können Sie die den verschiedenen Benutzenden zugewiesenen Rechte definieren und verwalten.

Als Campaign-Administrator sind Sie dafür verantwortlich, die Benutzenden zu erstellen und ihre Anmeldedaten mit den Anwendern zu teilen.

Weitere Informationen zu Anwendern und zum Definieren ihrer Berechtigungen finden Sie in [diesem Abschnitt](gs-permissions.md).


## Zugreifen auf Campaign über einen Webbrowser {#connect-web-ac}

### Web-Benutzeroberfläche {#connect-web-ui}

Ab der Campaign-Version v8.6 haben Sie Zugriff auf die neue **Campaign Web-Benutzeroberfläche**, die über die zentrale Adobe Experience Cloud-Umgebung verfügbar ist. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen.

[Auf dieser Seite](campaign-ui.md#ac-web-ui) erfahren Sie, wie Sie eine Verbindung mit Adobe Experience Cloud herstellen und auf die Benutzeroberfläche von Adobe Campaign Web zugreifen.

Weitere Informationen finden Sie in der [Dokumentation zur Adobe Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

### Web-Zugriff {#web-access}

Einige Bereiche des Programms können über einen Webbrowser mittels HTML-Benutzeroberfläche aufgerufen werden: darunter etwas das Reporting, die Versandvalidierung oder auch das Instanz-Monitoring.

Der Web-Zugriff bietet eine der Client-Konsole ähnliche Bedieneroberfläche mit eingeschränkten Funktionalitäten.

So wird z. B. für einen Benutzer eine Kampagne in der Client-Konsole mit folgenden Optionen angezeigt:

![](assets/campaign-from-console.png)

Beim Web-Zugriff ermöglichen die Optionen vor allem die Anzeige von:

![](assets/campaign-from-web.png)

Der Web-Zugriff wird auch für den Validierungsprozess verwendet: Benutzer können auf die E-Mail mit der Validierungsanfrage klicken und über ihren Webbrowser eine Verbindung zu Campaign herstellen, um Versandinhalte oder -budgets zu validieren oder abzulehnen.

Um über das Web auf Ihre Campaign-Instanz zuzugreifen, lautet die URL: `https://<your adobe campaign server>:<port number>/view/home`.

---
title: Verbindung zu Campaign mit der Client-Konsole herstellen
description: Erfahren Sie, wie Sie die Campaign-Clientkonsole auf Ihrem Computer installieren und eine Verbindung mit Adobe Campaign herstellen
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 9df599ec0a898a1af16cb92d334d50375fde86ba
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 68%

---

# Verbindung zu Campaign mit der Client-Konsole herstellen{#gs-ac-connect}

Um eine Verbindung mit Campaign mit der Clientkonsole herzustellen, müssen Sie diese zunächst installieren und konfigurieren.

Bevor Sie beginnen, müssen Sie folgende Schritte ausführen:

* Überprüfen Sie die Kompatibilität Ihres Systems und Ihrer Tools mit Adobe Campaign in der [Kompatibilitätsmatrix](compatibility-matrix.md)
* Ermitteln Sie Ihre Campaign-Server-URL
* Erstellen Sie Ihre Adobe ID oder rufen Sie Ihre Benutzeranmeldeinformationen von Ihrem Unternehmen ab
* Installieren Sie die Microsoft Edge Webview2-Laufzeitumgebung auf Ihrem System. [Weitere Informationen](#webview)


>[!NOTE]
>
>Sie können auch über einen Webbrowser eine Verbindung zur Webbenutzeroberfläche von Campaign herstellen. Erfahren Sie mehr über die neue Campaign-Web-Benutzeroberfläche in [diese Dokumentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.


## Client-Konsole installieren{#download-ac-console}

### Microsoft Edge WebView2-Laufzeitumgebung {#webview}

Ab der Campaign Classic-Build-Version 8.4 ist die Installation der Microsoft Edge Webview 2-Laufzeit für jede Client-Konsoleninstallation erforderlich.

WebView wird standardmäßig als Teil des Betriebssystems Windows 11 installiert. Wenn es nicht bereits auf Ihrem System vorhanden ist, werden Sie vom Installationsprogramm der Campaign-Clientkonsole aufgefordert, es von herunterzuladen. [Microsoft Developer-Website](http://www.adobe.com/go/acc-ms-webview2-runtime-download_de){target="_blank"}. Beachten Sie, dass der Download-Link nicht mit Internet Explorer 11 funktioniert, da Microsoft die Unterstützung dieses Browsers eingestellt hat. Stellen Sie sicher, dass Sie einen anderen Browser verwenden, um auf den Link zuzugreifen.

### Herunterladen der Konsole{#install-ac-console}

Wenn Sie Campaign zum ersten Mal verwenden, müssen Sie die Clientkonsole herunterladen und installieren.

Es stehen zwei Optionen zum Herunterladen der Clientkonsole zur Verfügung:

1. Als Campaign-Administrierende verbinden Sie sich mit der Adobe [Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html){target="_blank"}.

1. Als Endbenutzer stellt Ihr Campaign-Administrator die Clientkonsole für Sie bereit und stellt sie über eine dedizierte URL zur Verfügung.

Nachdem das Installationsprogramm der Clientkonsole heruntergeladen wurde, installieren Sie es auf Ihrem lokalen Computer.

Beachten Sie, dass Sie die Sprache der Clientkonsole nach der Installation nicht mehr ändern können.

## Herstellen der Verbindung{#create-your-connection}

Nachdem die Client-Konsole installiert wurde, führen Sie die folgenden Schritte aus, um die Verbindung zum Anwendungsserver herzustellen:

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

## Clientkonsole aktualisieren{#upgrade-ac-console}

Wenn Ihr System auf eine neuere Version aktualisiert wird, müssen Sie Ihre Client-Konsole auf dieselbe Version aktualisieren. Dies ist eine Best Practice, und für einige Versionen ist dieses Upgrade obligatorisch. In diesem Fall wird dies in den [Versionshinweise](release-notes.md) angegeben.

Als Benutzer von Managed Cloud Service stellt Adobe die Clientkonsole für Sie bereit. Wenn Sie eine Verbindung zu Ihrer aktualisierten Umgebung herstellen, werden Sie aufgefordert, die neueste Version der Clientkonsole in einem Popup-Fenster herunterzuladen. Sie müssen dieses Upgrade akzeptieren und die Clientkonsole nach Bedarf aktualisieren.

>[!CAUTION]
>
>Adobe empfiehlt, die Option **[!UICONTROL Diese Frage nicht mehr stellen]** deaktiviert zu lassen, um sicherzustellen, dass Sie benachrichtigt werden, wenn eine neue Version der Konsole verfügbar ist. Wenn diese Option aktiviert ist, werden Benutzende nicht darüber informiert, dass ein Konsolen-Upgrade erforderlich ist.
>



## Gewähren von Zugriff für Benutzende{#grant-access}

Mit Adobe Campaign können Sie die den verschiedenen Benutzenden zugewiesenen Rechte definieren und verwalten.

Als Campaign-Administrator sind Sie dafür verantwortlich, die Benutzenden zu erstellen und ihre Anmeldedaten mit den Anwendern zu teilen.

Weitere Informationen zu Anwendern und zum Definieren ihrer Berechtigungen finden Sie in [diesem Abschnitt](gs-permissions.md).


## Web-Zugriff{#web-access}

Einige Bereiche des Programms können über einen Webbrowser mittels HTML-Benutzeroberfläche aufgerufen werden: darunter etwas das Reporting, die Versandvalidierung oder auch das Instanz-Monitoring.

Der Web-Zugriff bietet eine der Client-Konsole ähnliche Bedieneroberfläche mit eingeschränkten Funktionalitäten.

So wird z. B. für einen Benutzer eine Kampagne in der Client-Konsole mit folgenden Optionen angezeigt:

![](assets/campaign-from-console.png)

Beim Web-Zugriff ermöglichen die Optionen vor allem die Anzeige von:

![](assets/campaign-from-web.png)

Der Web-Zugriff wird auch für den Validierungsprozess verwendet: Benutzer können auf die E-Mail mit der Validierungsanfrage klicken und über ihren Webbrowser eine Verbindung zu Campaign herstellen, um Versandinhalte oder -budgets zu validieren oder abzulehnen.

Um über das Web auf Ihre Campaign-Instanz zuzugreifen, lautet die URL: `https://<your adobe campaign server>:<port number>/view/home`.

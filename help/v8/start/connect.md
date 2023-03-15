---
title: Herstellen einer Verbindung mit Campaign v8
description: Erfahren Sie, wie Sie eine Verbindung mit Adobe Campaign v8 herstellen und die Konsole auf Ihrem Computer installieren, um den Zugriff zu erleichtern.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 2ec240b139394ce8f54a5835a4fa7bd377d226eb
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 71%

---

# Verbindung mit Adobe Campaign v8 herstellen{#gs-ac-connect}

Sie müssen die Campaign Client Console installieren, um eine Verbindung zu Ihren Campaign-Anwendungsservern herzustellen.

Die Client Console ist eine native Anwendung, die über standardmäßige Internetprotokolle wie SOAP und HTTP mit dem Adobe Campaign-Anwendungsserver kommuniziert. In der Campaign Client-Konsole sind alle Funktionen und Einstellungen verfügbar. Sie erfordert minimale Bandbreite, da sie auf einem lokalen Cache beruht. Diese Konsole, die im Hinblick auf eine einfache Implementierung entwickelt wurde, kann über einen Internet-Browser implementiert werden, kann automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic erzeugt.

Bevor Sie beginnen, müssen Sie folgende Schritte ausführen:

* Überprüfen Sie die Kompatibilität Ihres Systems und Ihrer Tools mit Adobe Campaign in der [Kompatibilitätsmatrix](compatibility-matrix.md)
* Ermitteln Sie Ihre Campaign-Server-URL
* Erstellen Sie Ihre Adobe ID oder rufen Sie Ihre Benutzeranmeldeinformationen von Ihrem Unternehmen ab
* Installieren Sie die Microsoft Edge Webview2-Laufzeitumgebung auf Ihrem System. [Weitere Informationen](#webview)

## Installieren der Client-Konsole{#download-ac-console}

###  der Microsoft Edge Webview2-Laufzeitumgebung {#webview}

Ab der Build-Version von Campaign Classic 8.4 ist die Installation der Microsoft Edge Webview 2-Laufzeit für jede Client Console-Installation erforderlich.

WebView wird standardmäßig als Teil des Betriebssystems Windows 11 installiert. Wenn es nicht bereits auf Ihrem System vorhanden ist, werden Sie vom Installationsprogramm der Campaign Console aufgefordert, es von herunterzuladen. [Microsoft Developer-Website](http://www.adobe.com/go/acc-ms-webview2-runtime-download_de){target="_blank"}. Beachten Sie, dass der Download-Link nicht mit Internet Explorer 11 funktioniert, da Microsoft die Unterstützung dieses Browsers eingestellt hat. Stellen Sie sicher, dass Sie einen anderen Browser verwenden, um auf den Link zuzugreifen.

### Herunterladen der Konsole{#install-ac-console}

Wenn Sie Campaign zum ersten Mal verwenden, müssen Sie die Clientkonsole herunterladen und installieren.

Es stehen zwei Optionen zum Herunterladen der Client-Konsole zur Verfügung:

1. Campaign-Administratoren müssen eine Verbindung zu Adobe herstellen [Softwareverteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html){target="_blank"}.

1. Als Endbenutzer stellt Ihr Campaign-Administrator die Client Console für Sie bereit und stellt sie über eine dedizierte URL zur Verfügung.

Nachdem das Installationsprogramm von Client Console heruntergeladen wurde, installieren Sie es auf Ihrem lokalen Computer.

Beachten Sie, dass Sie die Sprache der Client Console nach der Installation nicht mehr ändern können.

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

Campaign-Anwender stellen über das Adobe Identity Management System (IMS) mit ihrer Adobe ID eine Verbindung zur Adobe Campaign-Konsole her. Sie können für alle Adobe-Lösungen dieselbe ID verwenden. Die Verbindung wird bei Verwendung von Adobe Campaign mit anderen Lösungen gespeichert. Weitere Informationen zu Adobe IMS finden Sie auf [dieser Seite](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"}.

Gehen Sie wie folgt vor, um sich bei einer Instanz anzumelden:

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

## Aktualisieren der Client-Konsole{#upgrade-ac-console}

Wenn Ihr System auf eine neuere Version aktualisiert wird, müssen Sie Ihre Client Console auf dieselbe Version aktualisieren. Dies ist eine Best Practice, und für einige Versionen ist dieses Upgrade obligatorisch. In diesem Fall wird dies im [Versionshinweise](release-notes.md).

Als Benutzer von Managed Cloud Services stellt Adobe die Client Console für Sie bereit. Wenn Sie eine Verbindung zu Ihrer aktualisierten Umgebung herstellen, werden Sie aufgefordert, die neueste Version der Client Console in einem Popup-Fenster herunterzuladen. Sie müssen dieses Upgrade akzeptieren und die Client Console nach Bedarf aktualisieren.

>[!CAUTION]
>
>Adobe empfiehlt, die Option **[!UICONTROL Diese Frage nicht mehr stellen]** deaktiviert zu lassen, um sicherzustellen, dass alle Anwender benachrichtigt werden, wenn eine neue Version der Konsole verfügbar ist. Wenn diese Option aktiviert ist, wird der Anwender nicht über neue verfügbare Versionen informiert.


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

---
title: Externe Konten in Campaign
description: Externe Konten in Campaign
feature: Application Settings
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 7b8a9a323afc3154e250b4c70c4339d6c6c265c0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Externe Konten konfigurieren

Adobe Campaign enthält eine Reihe vordefinierter externer Konten. Um Verbindungen zu externen Systemen einzurichten, können Sie neue externe Konten erstellen.

Externe Konten werden von technischen Prozessen, wie technischen Workflows oder Kampagnen-Workflows, verwendet. Beispiel: Bei der Einrichtung eines Dateitransfers in einem Workflow oder bei einem Datenaustausch mit einem anderen Programm (Adobe Target, Experience Manager usw.) müssen Sie ein externes Konto auswählen.

Sie können über Adobe Campaign **[!UICONTROL Explorer]** auf externe Konten zugreifen: Navigieren Sie zu **[!UICONTROL Administration]** `>` **[!UICONTROL Plattform]** `>` **[!UICONTROL Externe Konten]**.

![](assets/external-accounts.png)


>[!CAUTION]
>* Wenn Sie Managed Cloud Services-Benutzer sind, konfiguriert Adobe externe Konten für Ihre Instanz, die nicht geändert werden dürfen.

>
>* >Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) verwaltet ein spezielles externes **[!UICONTROL Full FDA]**-Konto (ffda) die Verbindung zwischen der lokalen Campaign-Datenbank und der Cloud-Datenbank ([!DNL Snowflake]).
>


## Campaign-spezifische externe Konten

Die folgenden technischen Konten werden von Adobe Campaign verwendet, um bestimmte Prozesse zu aktivieren und auszuführen.

### Bounce Messages {#bounce-mails-external-account}

>[!NOTE]
Die Microsoft Exchange Online OAuth 2.0-Authentifizierung für POP3-Funktionen ist ab Campaign v8.3 verfügbar. Informationen zu Ihrer Version finden Sie in [diesem Abschnitt](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)..

Das externe Konto **Bounce Messages** gibt das externe POP3-Konto an, das für die Verbindung mit dem E-Mail-Service verwendet werden soll. Alle Server, die für den POP3-Zugriff konfiguriert sind, können für den Empfang von Antwortsendungen verwendet werden.

Weitere Informationen über eingehende E-Mails finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html?lang=de)..

![](assets/bounce_external_1.png)

Um das externe Konto für **[!UICONTROL Bounce-Messages (defaultPopAccount)]** zu konfigurieren, benötigen Sie folgende Informationen:

* **[!UICONTROL Server]** - URL des POP3-Servers.

* **[!UICONTROL Port]** - POP3-Anschlussnummer. Der Standard-Port ist 110.

* **[!UICONTROL Konto]** - Name des Benutzers.

* **[!UICONTROL Passwort]** - Passwort des Benutzerkontos.

* **[!UICONTROL Verschlüsselung]** - Art der gewählten Verschlüsselung zwischen **[!UICONTROL Standardmäßig]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** oder **[!UICONTROL POP3S]**.

   Das externe Konto **Bounce Messages** gibt das externe POP3-Konto an, das für die Verbindung mit dem E-Mail-Service verwendet werden soll. Alle Server, die für den POP3-Zugriff konfiguriert sind, können für den Empfang von Antwortsendungen verwendet werden.

* **[!UICONTROL Funktion]** - E-Mail-Empfang oder SOAP-Router

![](assets/bounce_external_2.png)

>[!CAUTION]
Bevor Sie Ihr externes POP3-Konto mit Microsoft OAuth 2.0 konfigurieren, müssen Sie Ihre Anwendung zunächst im Azure-Portal registrieren. Weiterführende Informationen hierzu finden Sie auf [dieser Seite](https://docs.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

Um ein externes POP3-Programm mit Microsoft OAuth 2.0 zu konfigurieren, markieren Sie die Option **[!UICONTROL Microsoft OAuth 2.0]** und füllen Sie die folgenden Felder aus:

* **[!UICONTROL Azure-Mandant]** - Eine Azure ID (oder Verzeichnis-ID bzw. Mandanten-ID) finden Sie in der Dropdown-Liste **Grundlagen** der Anwendungsübersicht im Azure-Portal.

* **[!UICONTROL Azure Client ID]** - Die Client-ID (oder die Anwendungs- (Client-) ID) finden Sie im **Grundlagen** Dropdown-Liste der Anwendungsübersicht im Azure-Portal.

* **[!UICONTROL Azure Client-Geheimnis]** - Die Client-Geheimkennung finden Sie im **Kundengeheimnisse** aus der **Zertifikate &amp; Geheimnisse** Menü Ihrer Anwendung im Azure-Portal.

* **[!UICONTROL Azure-Umleitungs-URL]** - Die Umleitungs-URL finden Sie im **Authentifizierung** Menü Ihrer Anwendung im Azure-Portal. Sie sollte mit der folgenden Syntax enden: `nl/jsp/oauth.jsp`, z. B. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

   Nachdem Sie Ihre unterschiedlichen Anmeldedaten eingegeben haben, können Sie auf **[!UICONTROL Verbindung einrichten]** klicken, um die Konfiguration Ihres externen Kontos abzuschließen.

### Routing {#routing}

Mit dem externen **[!UICONTROL Routing]**-Konto können Sie jeden in Adobe Campaign verfügbaren Kanal abhängig von den installierten Packages konfigurieren.

>[!CAUTION]
Das externe Konto **[!UICONTROL Internes E-Mail-Routing]** (defaultEmailBulk) darf in Adobe Campaign v8 **nicht** aktiviert sein.

### Ausführungsinstanz {#execution-instance}

Im Kontext der Transaktionsnachrichten werden die Ausführungsinstanzen mit der Kontrollinstanz verknüpft und miteinander verbunden. Transaktionsnachrichten-Vorlagen werden in der Ausführungsinstanz bereitgestellt. Weitere Informationen zur Message Center-Architektur finden Sie auf [dieser Seite](../architecture/architecture.md#transac-msg-archi).

## Zugriff auf externe Systemkonten

* **Externe Datenbank (FDA)** - die **Externe Datenbank** Externes Konto vom Typ wird verwendet, um über Federated Data Access (FDA) eine Verbindung zu einer externen Datenbank herzustellen. Weitere Informationen zur Option Federated Data Access (FDA) finden Sie in [diesem Abschnitt](../connect/fda.md).

   Externe Datenbanken, die mit Adobe Campaign v8 kompatibel sind, sind in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) aufgeführt.

* **Twitter** - die **Twitter** Typ externes Konto wird verwendet, um Campaign mit Ihrem twitter-Konto zu verbinden und Nachrichten in Ihrem Namen zu posten. Weitere Informationen zur Twitter-Integration finden Sie in [diesem Abschnitt](../connect/ac-tw.md).

## Externe Konten zur Integration von Adobe-Lösungen

* **Adobe Experience Cloud** - Ein externes Konto vom Typ **[!UICONTROL Adobe Experience Cloud]** wird verwendet, um Adobe Identity Management Service (IMS) für die Verbindung mit Adobe Campaign zu implementieren. Weitere Informationen zu Adobe Identity Management Service (IMS) finden Sie in [diesem Abschnitt](../start/connect.md#connect-ims).

* **Web Analytics** - die **[!UICONTROL Web Analytics (Adobe Analytics)]** Das externe Konto wird verwendet, um die Datenübertragung von Adobe Analytics zu Adobe Campaign zu konfigurieren. Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aa.md).

* **Adobe Experience Manager** - die **[!UICONTROL AEM]** Mit dem externen Konto können Sie den Inhalt Ihrer E-Mail-Sendungen sowie Ihrer Formulare direkt in Adobe Experience Manager verwalten. Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aem.md).


## Externe CRM-Connector-Konten

* **Microsoft Dynamics CRM** - die **[!UICONTROL Microsoft Dynamics CRM]** Mit einem externen Konto können Sie Microsoft Dynamics-Daten in Adobe Campaign importieren und exportieren. Weitere Informationen zur Integration von Adobe Campaign mit Microsoft Dynamics CRM finden Sie auf [dieser Seite](../connect/ac-ms-dyn.md).

* **Salesforce.com** - die **[!UICONTROL Salesforce CRM]** Mit einem externen Konto können Sie Salesforce-Daten in Adobe Campaign importieren und exportieren. Weitere Informationen zur Integration von Adobe Campaign mit dem CRM Salesforce.com finden Sie auf [dieser Seite](../connect/ac-sfdc.md).

## Übertragen von Daten mit externen Konten

Diese externen Konten können mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden. Weitere Informationen **Dateiversand** in Workflows in [diese Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html?lang=de).

* **FTP und SFTP** - die **FTP** Mit dem externen Konto können Sie den Zugriff auf einen Server außerhalb von Adobe Campaign konfigurieren und testen. Sie können aber auch Ihre eigenen externen Konten erstellen, um eine Verbindung mit externen Systemen wie SFTP- oder FTP-Servern zum Zweck des Dateitransfers herzustellen.

   Geben Sie dazu in diesem externen Konto die Adresse und die Zugangsdaten für die Verbindungsherstellung zum SFTP- oder FTP-Server an.

* **Amazon Simple Storage Service (S3)** - die **AWS S3** Connector kann zum Importieren oder Exportieren von Daten in Adobe Campaign mithilfe eines **[!UICONTROL Dateiübertragung]** Workflow-Aktivität. Zum Einrichten dieses neuen externen Kontos benötigen Sie die folgenden Informationen:

   * **[!UICONTROL AWS-S3-Konto-Server]**: URL Ihres Servers, wie folgt ausgefüllt:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS-Zugriffsschlüssel-ID]**: Erfahren Sie, wie Sie Ihre AWS-Zugriffsschlüssel-ID in [Amazon-Dokumentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Geheimer Zugriffsschlüssel für AWS]**: Erfahren Sie, wie Sie Ihren geheimen Zugriffsschlüssel für AWS in finden [Amazon-Dokumentation](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS-Region]**: Weitere Informationen zu AWS-Regionen finden Sie in der [Amazon-Dokumentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * Die Checkbox **[!UICONTROL Server-seitige Verschlüsselung verwenden]** ermöglicht es Ihnen, Ihre Datei in S3 im verschlüsselten Modus zu speichern. Erfahren Sie, wie Sie die Zugriffsschlüssel-ID und den geheimen Zugriffsschlüssel in [Amazon-Dokumentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Azure Blob Storage** - die **Azure** kann zum Importieren oder Exportieren von Daten in Adobe Campaign mithilfe eines **[!UICONTROL Dateiübertragung]** Workflow-Aktivität. Um das externe **Azure**-Konto für die gemeinsame Verwendung mit Adobe Campaign zu konfigurieren, müssen Sie die folgenden Informationen eingeben:

   * **[!UICONTROL Server]**: URL Ihres Azure Blob Storage-Servers

   * **[!UICONTROL Verschlüsselung]**: Art der Verschlüsselung, **[!UICONTROL Keine]** oder **[!UICONTROL SSL]**.

   * **[!UICONTROL Zugriffsschlüssel]**: Erfahren Sie, wie Sie Ihre **[!UICONTROL Zugriffsschlüssel]** in [Microsoft-Dokumentation](https://docs.microsoft.com/de-de/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.

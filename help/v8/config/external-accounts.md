---
title: Externe Konten in Campaign
description: Konfigurieren Sie externe Konten, um Campaign mit externen Systemen wie POP3-, FDA-, CRM-, Speicher- und Adobe-Lösungen zu verbinden.
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 776a0e5eead9161b7e2c9d7746c72cba42ea42cb
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 67%

---


# Externe Konten konfigurieren {#config-external-accounts}

Adobe Campaign enthält eine Reihe vordefinierter externer Konten. Um Verbindungen zu externen Systemen einzurichten, können Sie neue externe Konten erstellen.

Externe Konten werden von technischen Prozessen, wie technischen Workflows oder Kampagnen-Workflows, verwendet. Beispiel: Bei der Einrichtung eines Dateitransfers in einem Workflow oder bei einem Datenaustausch mit einem anderen Programm (Adobe Target, Experience Manager usw.) müssen Sie ein externes Konto auswählen.

Sie können über Adobe Campaign **[!UICONTROL Explorer]** auf externe Konten zugreifen: Navigieren Sie zu **[!UICONTROL Administration]** `>` **[!UICONTROL Plattform]** `>` **[!UICONTROL Externe Konten]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Wenn Sie Managed Cloud Services-Benutzer oder -Benutzerin sind, konfiguriert Adobe externe Konten für Ihre Instanz, die nicht geändert werden dürfen.
>
>* Im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) verwaltet ein spezielles externes **[!UICONTROL Full FDA]**-Konto (ffda) die Verbindung zwischen der lokalen Campaign-Datenbank und der Cloud-Datenbank ([!DNL Snowflake]).
>

## Campaign-spezifische externe Konten {#ac-external-accounts}

Die folgenden technischen Konten werden von Adobe Campaign verwendet, um bestimmte Prozesse zu aktivieren und auszuführen.

### Bounce-E-Mails {#bounce-mails-external-account}

>[!NOTE]
>
>Die Microsoft Exchange Online OAuth 2.0-Authentifizierung für POP3-Funktionen ist ab Campaign v8.3 verfügbar. Informationen zu Ihrer Version finden Sie in [diesem Abschnitt](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

Das externe Konto **Bounce Messages** gibt das externe POP3-Konto an, das für die Verbindung mit dem E-Mail-Service verwendet werden soll. Alle Server, die für den POP3-Zugriff konfiguriert sind, können für den Empfang von Antwortsendungen verwendet werden.

Weitere Informationen über eingehende E-Mails finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html?lang=de){target="_blank"}.

![](assets/bounce_external_1.png)

Um das externe Konto für **[!UICONTROL Bounce-Messages (defaultPopAccount)]** zu konfigurieren, benötigen Sie folgende Informationen:

* **[!UICONTROL Server]** – URL des POP3-Servers.

* **[!UICONTROL Port]** – Port-Nummer der POP3-Verbindung. Der Standard-Port ist 110.

* **[!UICONTROL Konto]** – Name der Benutzerin bzw. des Benutzers.

* **[!UICONTROL Passwort]** – Passwort des Benutzerkontos.

* **[!UICONTROL Verschlüsselung]** – Typ der gewählten Verschlüsselung mit den Optionen **[!UICONTROL Standardmäßig]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** oder **[!UICONTROL POP3S]**.

* **[!UICONTROL Funktion]** - Eingehende E-Mail- oder SOAP-Router.

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Bevor Sie Ihr externes POP3-Konto mit Microsoft OAuth 2.0 konfigurieren, müssen Sie die Anwendung zunächst im Azure-Portal registrieren. Weiterführende Informationen hierzu finden Sie auf dieser [Seite](https://docs.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Um ein externes POP3-Programm mit Microsoft OAuth 2.0 zu konfigurieren, markieren Sie die Option **[!UICONTROL Microsoft OAuth 2.0]** und füllen Sie die folgenden Felder aus:

* **[!UICONTROL Azure-Mandant]** – Eine Azure-ID (oder Verzeichnis-ID bzw. Mandanten-ID) finden Sie in der Dropdown-Liste **Grundlagen** der Anwendungsübersicht im Azure-Portal.

* **[!UICONTROL Azure Client ID]** – Client-ID (oder Anwendungs- (Client) ID) finden Sie in der Dropdown-Liste **Grundlagen** der Anwendungsübersicht im Azure-Portal.

* **[!UICONTROL Azure-Client-Geheimnis]** – Die Client-Geheimnis-ID finden Sie in der Spalte **Client-Geheimnisse** im Menü **Zertifikate und Geheimnisse** Ihrer Anwendung im Azure-Portal.

* **[!UICONTROL Azure-Umleitungs-URL]** – Die Umleitungs-URL finden Sie im Menü **Authentifizierung** Ihrer Anwendung im Azure-Portal. Sie sollte mit der folgenden Syntax enden: `nl/jsp/oauth.jsp`, z. B. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Nachdem Sie Ihre Anmeldedaten eingegeben haben, klicken Sie auf **[!UICONTROL Verbindung einrichten]**, um die Konfiguration Ihres externen Kontos abzuschließen.

### Routing {#routing}

Mit dem externen **[!UICONTROL Routing]**-Konto können Sie jeden in Adobe Campaign verfügbaren Kanal abhängig von den installierten Packages konfigurieren.

Weitere Informationen zur Verwaltung externer Konten und zur Versandausführung finden Sie in [diesem Abschnitt](../architecture/architecture.md#split).

### Ausführungsinstanz {#execution-instance}

Im Zusammenhang mit dem Transaktionsnachrichtenversand ist die Ausführungsinstanz mit der Kontrollinstanz verknüpft und verbindet sie. Transaktionsnachrichten-Vorlagen werden in der Ausführungsinstanz bereitgestellt. Weitere Informationen zur Message Center-Architektur finden Sie auf [dieser Seite](../architecture/architecture.md#transac-msg-archi).

## Zugriff auf externe Systemkonten {#external-syst-external-accounts}

### Federated Data Access (FDA) {#fda-external-accounts}

Ein **externes Konto** Externe Datenbank) wird verwendet, um über Federated Data Access (FDA) eine Verbindung mit einer externen Datenbank herzustellen. Weitere Informationen zur Option „Federated Data Access“ (FDA) finden Sie in [diesem Abschnitt](../connect/fda.md).

>[!NOTE]
>
>Externe Datenbanken, die mit Adobe Campaign v8 kompatibel sind, sind in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) aufgeführt. FDA-Verbindungen verwenden ODBC-Treiber. Bei Adobe Campaign Managed Cloud Services werden der ODBC-Treiber und die Konfiguration externer Konten von Adobe eingerichtet.

Die Konfigurationseinstellungen für externe Konten hängen von der Datenbank-Engine ab. Bei Adobe Campaign Managed Cloud Services wird die Konfiguration externer Konten durch Adobe durchgeführt. Weitere Informationen zu dieser Konfiguration finden Sie in der Dokumentation zu [Adobe Campaign Classic v7](https://experienceleague.adobe.com/de/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts){target="_blank"}.

#### Externes DataBricks-Konto {#databricks-external-accounts}

Die Databricks FDA-Verbindung verwendet den Databricks ODBC-Treiber. Ab Campaign v8.9.1 unterstützen externe Databricks-Konten die OAuth2-Authentifizierung über den Service-Prinzipal (nicht interaktiver Fluss der Client-Anmeldeinformationen), was eine sichere Authentifizierung für den Federated Data Access bietet.

Weitere Informationen zu Service-Prinzipalen finden Sie in der Dokumentation zu [Microsoft](https://learn.microsoft.com/en-us/azure/databricks/admin/users-groups/service-principals){target="_blank"}.

So konfigurieren Sie die OAuth2-Authentifizierung über einen Service-Prinzipal in Campaign:

1. Der DataBricks Workspace-Administrator aktiviert Service-Prinzipale für den DataBricks Workspace und generiert Anmeldeinformationen. Um den Zugriff auf Ihre Azure-Datenblöcke-Ressourcen mit OAuth zu autorisieren, erstellen Sie ein OAuth-Geheimnis (das zum Generieren von OAuth-Zugriffstoken für die Authentifizierung verwendet wird).
2. Erstellen oder bearbeiten Sie in Adobe Campaign ein externes Databricks-Konto und öffnen Sie die Registerkarte **OAuth**.
3. Fügen Sie die Anmeldeinformationen in die Felder der Registerkarte OAuth des externen Datenbricks-Kontos ein.
4. Verwenden **[!UICONTROL Verbindung testen]** um die Konfiguration zu überprüfen.

### X (früher bekannt als Twitter) {#twitter-external-account}

Ein externes **Twitter**-Konto wird verwendet, um Campaign mit Ihrem X-Konto zu verbinden und Nachrichten in Ihrem Namen zu posten. Weitere Informationen zur X-Integration finden Sie in [diesem Abschnitt](../connect/ac-tw.md).

## Externe Konten zur Integration von Adobe-Lösungen {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - Das externe **[!UICONTROL Adobe Experience Cloud]**-Konto wird verwendet, um Adobe Identity Management Service (IMS) für die Verbindung mit Adobe Campaign zu implementieren. Weitere Informationen zu Adobe Identity Management Service (IMS) finden Sie in [diesem Abschnitt](../start/connect.md#logon-to-ac).

* **Web-Analyse** – Das externe **[!UICONTROL Web-Analyse (Adobe Analytics)]**-Konto wird verwendet, um die Datenübertragung von Adobe Analytics an Adobe Campaign zu konfigurieren. Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aa.md).

* **Adobe Experience Manager** – Mit dem externen **[!UICONTROL AEM]**-Konto können Sie den Inhalt Ihrer E-Mail-Sendungen und Ihrer Formulare direkt in Adobe Experience Manager verwalten. Weitere Informationen zur Integration von Adobe Campaign mit Adobe Experience Manager finden [&#x200B; auf dieser Seite &#x200B;](../connect/ac-aem.md).


## Externe CRM-Connector-Konten {#crm-external-accounts}

* **Microsoft Dynamics CRM** – Das externe **[!UICONTROL Microsoft Dynamics CRM]**-Konto ermöglicht den Import und Export von Microsoft Dynamics-Daten in Adobe Campaign. Weitere Informationen zur Integration von Adobe Campaign mit Microsoft Dynamics CRM finden Sie auf [dieser Seite](../connect/ac-ms-dyn.md).

* **Salesforce.com** – Das externe **[!UICONTROL Salesforce CRM]**-Konto ermöglicht den Import und Export von Salesforce-Daten in Adobe Campaign. Weitere Informationen zur Integration von Adobe Campaign mit dem CRM Salesforce.com finden Sie auf [dieser Seite](../connect/ac-sfdc.md).

## Übertragen von Daten mit externen Konten {#transfer-data-external-accounts}

Diese externen Konten können mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden. Weitere Informationen zur **Dateiübertragung** in Workflows finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html?lang=de){target="_blank"}.

* **FTP und SFTP** – Mit dem externen **FTP**-Konto können Sie den Zugriff auf einen Server außerhalb von Adobe Campaign konfigurieren und testen. Um Verbindungen mit externen Systemen wie SFTP- oder FTP-Servern für die Dateiübertragung einzurichten, können Sie Ihre eigenen externen Konten erstellen.

  Geben Sie dazu in diesem externen Konto die Adresse und die Anmeldedaten für die Verbindungsherstellung zum SFTP- oder FTP-Server an.

  >[!NOTE]
  >
  >Ab Version 8.5 können Sie sich jetzt bei der Konfiguration Ihres externen SFTP-Kontos sicher mit einem privaten Schlüssel authentifizieren. [Erfahren Sie mehr über die Schlüsselverwaltung](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=de){target="_blank"}.

* **Amazon Simple Storage Service (S3)** – Die **AWS S3**-Verbindung kann zum Importieren oder Exportieren von Daten in Adobe Campaign über die Workflow-Aktivität **[!UICONTROL Datei übertragen]** verwendet werden. Zum Einrichten dieses neuen externen Kontos benötigen Sie die folgenden Informationen:

   * **[!UICONTROL AWS S3-]**: URL Ihres Servers in der `<S3bucket name>.s3.amazonaws.com/<s3object path>`.

   * **[!UICONTROL Kennung des AWS-Zugriffsschlüssels]**: In der [Amazon-Dokumentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"} erfahren Sie, wie Sie die Kennung Ihres AWS-Zugangsschlüssels finden.

   * **[!UICONTROL Geheimer AWS-Zugriffsschlüssel]**: Erfahren Sie in der [Amazon-Dokumentation](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}, wie Sie Ihren geheimen Zugriffsschlüssel für AWS finden.

   * **[!UICONTROL AWS-Region]**: Weitere Informationen zu AWS-Regionen finden Sie in der [Amazon-Dokumentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * Die Checkbox **[!UICONTROL Server-seitige Verschlüsselung verwenden]** ermöglicht es Ihnen, Ihre Datei in S3 im verschlüsselten Modus zu speichern. Erfahren Sie in der [Amazon-Dokumentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}, wie Sie die Kennung des Zugriffsschlüssels und den geheimen Zugriffsschlüssel finden.

* **Azure Blob Storage** – Das externe **Azure**-Konto kann mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden. Um das externe **Azure**-Konto für die gemeinsame Verwendung mit Adobe Campaign zu konfigurieren, müssen Sie die folgenden Informationen eingeben:

   * **[!UICONTROL Server]**: URL Ihres Azure Blob Storage-Servers

   * **[!UICONTROL Encryption]**: Verschlüsselungstyp: **[!UICONTROL None]** oder **[!UICONTROL SSL]**.

   * **[!UICONTROL Zugriffsschlüssel]**: Erfahren Sie in der [Microsoft-Dokumentation](https://docs.microsoft.com/de-de/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}, wie Sie Ihren **[!UICONTROL Zugriffsschlüssel]** finden.

* **Microsoft Fabric** - Das externe **Microsoft Fabric**-Konto ermöglicht den Import und Export von Daten zwischen Microsoft Fabric und Adobe Campaign mithilfe der Workflow-Aktivität **[!UICONTROL Dateiübertragung]**. Um diese Integration zu konfigurieren, geben Sie die folgenden Details an:

   * **[!UICONTROL Server]**: URL Ihres Microsoft Fabric-Speicher-Servers.

   * **[!UICONTROL Anwendungs-ID]**: Die eindeutige Kennung der Anwendung, die zum Authentifizieren und Zugreifen auf Microsoft Fabric-Ressourcen verwendet wird.

   * **[!UICONTROL Client-Geheimnis]**: Der mit der Anwendung verknüpfte Authentifizierungsschlüssel oder das Passwort, der bzw. das für die sichere Verbindung mit Microsoft Fabric erforderlich ist.

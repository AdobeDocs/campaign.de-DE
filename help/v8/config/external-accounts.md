---
title: Externe Konten in Campaign
description: Externe Konten in Campaign
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: ht
source-wordcount: '1176'
ht-degree: 100%

---

# Externe Konten konfigurieren

Adobe Campaign enthält eine Reihe vordefinierter externer Konten. Um Verbindungen zu externen Systemen einzurichten, können Sie neue externe Konten erstellen.

Externe Konten werden von technischen Prozessen, wie technischen Workflows oder Kampagnen-Workflows, verwendet. Beispiel: Bei der Einrichtung eines Dateitransfers in einem Workflow oder bei einem Datenaustausch mit einem anderen Programm (Adobe Target, Experience Manager usw.) müssen Sie ein externes Konto auswählen.

Sie können über Adobe Campaign **[!UICONTROL Explorer]** auf externe Konten zugreifen: Navigieren Sie zu **[!UICONTROL Administration]** `>` **[!UICONTROL Plattform]** `>` **[!UICONTROL Externe Konten]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Im Kontext einer [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) verwaltet ein spezielles externes **[!UICONTROL Full FDA]**-Konto (ffda) die Verbindung zwischen der lokalen Campaign-Datenbank und der Cloud-Datenbank ([!DNL Snowflake]).
></br>Als Anwender von Managed Cloud Services wird dieses externe Konto für Ihre Instanz durch Adobe konfiguriert. Es darf nicht geändert werden.

## Campaign-spezifische externe Konten

Die folgenden technischen Konten werden von Adobe Campaign verwendet, um bestimmte Prozesse zu aktivieren und auszuführen.

![](../assets/do-not-localize/speech.png)  Adobe konfiguriert für Sie als Benutzer von Managed Cloud Services alle Campaign-spezifischen externen Konten.

### Bounce Messages {#bounce-mails-external-account}

>[!NOTE]
>
>Die Microsoft Exchange Online OAuth 2.0-Authentifizierung für POP3-Funktionen ist ab Campaign v8.3 verfügbar. Informationen zu Ihrer Version finden Sie in [diesem Abschnitt](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

Das externe Konto **Bounce Messages** gibt das externe POP3-Konto an, das für die Verbindung mit dem E-Mail-Service verwendet werden soll. Alle Server, die für den POP3-Zugriff konfiguriert sind, können für den Empfang von Antwortsendungen verwendet werden.

![](../assets/do-not-localize/book.png) Weitere Informationen zu eingehenden E-Mails finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html?lang=de){target=&quot;_blank&quot;}

![](assets/bounce_external_1.png)

Um das externe Konto für **[!UICONTROL Bounce-Messages (defaultPopAccount)]** zu konfigurieren, benötigen Sie folgende Informationen:

* **[!UICONTROL Server]**

   URL des POP3-Servers

* **[!UICONTROL Port]**

   Nummer des POP3-Verbindungsports. Standardmäßig ist dies der Port 110.

* **[!UICONTROL Konto]**

   Name des Benutzers.

* **[!UICONTROL Passwort]**

   Passwort des Benutzerkontos.

* **[!UICONTROL Verschlüsselung]**

   Typ der gewählten Verschlüsselung: **[!UICONTROL Standardmäßig]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** oder **[!UICONTROL POP3S]**.
Das externe Konto **Bounce Messages** gibt das externe POP3-Konto an, das für die Verbindung mit dem E-Mail-Service verwendet werden soll. Alle Server, die für den POP3-Zugriff konfiguriert sind, können für den Empfang von Antwortsendungen verwendet werden.

* **[!UICONTROL Funktion]**

   Eingehende E-Mail- oder SOAP-Router

![](assets/bounce_external_2.png)

>[!IMPORTANT]
>
>Bevor Sie Ihr externes POP3-Konto mit Microsoft OAuth 2.0 konfigurieren, müssen Sie Ihre Anwendung zunächst im Azure-Portal registrieren. Weiterführende Informationen hierzu finden Sie auf [dieser Seite](https://docs.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app).

Um ein externes POP3-Programm mit Microsoft OAuth 2.0 zu konfigurieren, markieren Sie die Option **[!UICONTROL Microsoft OAuth 2.0]** und füllen Sie die folgenden Felder aus:

* **[!UICONTROL Azure-Mandant]**

   Eine Azure ID (oder Verzeichnis-ID bzw. Mandanten-ID) finden Sie in der Dropdown-Liste **Grundlagen** der Anwendungsübersicht im Azure-Portal.

* **[!UICONTROL Azure-Client-ID]**

   Client-ID (oder Anwendungs (Client)-ID) finden Sie in der Dropdown-Liste **Grundlagen** der Anwendungsübersicht im Azure-Portal.

* **[!UICONTROL Azure-Client-Geheimnis]**:

   Die Client-Geheimnis-ID finden Sie in der Spalte **Client-Geheimnisse** im Menü **Zertifikate und Geheimnisse** Ihrer Anwendung im Azure-Portal.

* **[!UICONTROL Azure-Umleitungs-URL]**:

   Die Umleitungs-URL finden Sie im Menü **Authentifizierung** Ihrer Anwendung im Azure-Portal. Sie sollte mit der folgenden Syntax enden: `nl/jsp/oauth.jsp`, z. B. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Nachdem Sie Ihre unterschiedlichen Anmeldedaten eingegeben haben, können Sie auf **[!UICONTROL Verbindung einrichten]** klicken, um die Konfiguration Ihres externen Kontos abzuschließen.

### Routing {#routing}

Mit dem externen **[!UICONTROL Routing]**-Konto können Sie jeden in Adobe Campaign verfügbaren Kanal abhängig von den installierten Packages konfigurieren.

>[!CAUTION]
>
>Das externe Konto **[!UICONTROL Internes E-Mail-Routing]** (defaultEmailBulk) darf in Adobe Campaign v8 **nicht** aktiviert sein.

### Ausführungsinstanz {#execution-instance}

Im Kontext der Transaktionsnachrichten werden die Ausführungsinstanzen mit der Kontrollinstanz verknüpft und miteinander verbunden. Transaktionsnachrichten-Vorlagen werden in der Ausführungsinstanz bereitgestellt.

![](../assets/do-not-localize/glass.png) Weitere Informationen zur Message Center-Architektur finden Sie auf [dieser Seite](../architecture/architecture.md#transac-msg-archi).

## Zugriff auf externe Systemkonten

* **Externe Datenbank (FDA)**

   Verwenden Sie das externe Konto vom Typ **Externe Datenbank**, um über FDA eine Verbindung zu einer externen Datenbank herzustellen.

   Externe Datenbanken, die mit Adobe Campaign v8 kompatibel sind, sind in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) aufgeführt.

   ![](../assets/do-not-localize/glass.png) Weitere Informationen zur Option Federated Data Access (FDA) finden Sie in [diesem Abschnitt](../connect/fda.md).

## Externe Konten zur Integration von Adobe-Lösungen

* **Adobe Experience Cloud**

   Das externe **[!UICONTROL Adobe Experience Cloud]**-Konto wird verwendet, um Adobe IMS zu implementieren und mithilfe einer Adobe ID eine Verbindung zur Adobe Campaign-Konsole herzustellen.

   ![](../assets/do-not-localize/glass.png) Weitere Informationen zu Adobe Identity Management Service (IMS) finden Sie in [diesem Abschnitt](../start/connect.md#connect-ims).

* **Web Analytics**

   Verwenden Sie das externe Konto **[!UICONTROL Web Analytics (Adobe Analytics)]**, um die Datenübertragung von Adobe Analytics zu Adobe Campaign zu konfigurieren.

   ![](../assets/do-not-localize/glass.png) Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  Als Benutzer von Managed Cloud Services [kontaktieren Sie Adobe](../start/campaign-faq.md#support), um Adobe Analytics mit Campaign zu integrieren.

   * **Adobe Experience Manager**
   Mit dem externen Konto **[!UICONTROL AEM]** können Sie den Inhalt Ihrer E-Mail-Sendungen und Ihrer Formulare direkt in Adobe Experience Manager verwalten.

   ![](../assets/do-not-localize/glass.png) Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  Als Benutzer von Managed Cloud Services [kontaktieren Sie Adobe](../start/campaign-faq.md#support), um Adobe Experience Manager mit Adobe Campaign zu integrieren.


## Externe CRM-Connector-Konten

* **Microsoft Dynamics CRM**

   Das externe **[!UICONTROL Microsoft Dynamics CRM]**-Konto ermöglicht den Import und Export von Microsoft Dynamics-Daten in Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Weitere Informationen zur Integration von Adobe Campaign mit Microsoft Dynamics CRM finden Sie auf [dieser Seite](../connect/ac-ms-dyn.md).

* **Salesforce.com**

   Das externe **[!UICONTROL Salesforce CRM]**-Konto ermöglicht den Import und Export von Salesforce-Daten in Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Weitere Informationen zur Integration von Adobe Campaign mit dem CRM Salesforce.com finden Sie auf [dieser Seite](../connect/ac-sfdc.md).

## Übertragen von Daten mit externen Konten

Diese externen Konten können mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden.

![](../assets/do-not-localize/book.png) Weitere Informationen zur Dateiübertragung in Workflows finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html?lang=de){target=&quot;_blank&quot;}

* **FTP und SFTP**

   Mit dem externen **FTP**-Konto können Sie den Zugriff auf einen Server außerhalb von Adobe Campaign konfigurieren und testen. Sie können aber auch Ihre eigenen externen Konten erstellen, um eine Verbindung mit externen Systemen wie SFTP- oder FTP-Servern zum Zweck des Dateitransfers herzustellen.
Geben Sie dazu in diesem externen Konto die Adresse und die Zugangsdaten für die Verbindungsherstellung zum SFTP- oder FTP-Server an.

* **Amazon Simple Storage Service (S3)**

   Der **AWS S3**-Connector kann mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden. Zum Einrichten dieses neuen externen Kontos benötigen Sie die folgenden Informationen:

   * **[!UICONTROL AWS-S3-Konto-Server]**: URL Ihres Servers, wie folgt ausgefüllt:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL Kennung des AWS-Zugriffsschlüssels]**: Erfahren Sie, wie Sie Ihre Kennung des AWS-Zugriffsschlüssels in der [Amazon-Dokumentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) finden.

   * **[!UICONTROL Geheimer AWS-Zugriffsschlüssel]**: Erfahren Sie in der [Amazon-Dokumentation](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/), wie Sie Ihren geheimen Zugriffsschlüssel für AWS finden.

   * **[!UICONTROL AWS-Region]**: Weitere Informationen zu AWS-Regionen finden Sie in der [Amazon-Dokumentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * Die Checkbox **[!UICONTROL Server-seitige Verschlüsselung verwenden]** ermöglicht es Ihnen, Ihre Datei in S3 im verschlüsselten Modus zu speichern. Erfahren Sie in der [Amazon-Dokumentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys), wie Sie die Kennung des Zugriffsschlüssels und den geheimen Zugriffsschlüssel finden.

* **Azur Blob-Speicherung**

   Das externe **Azure**-Konto kann mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden. Um das externe **Azure**-Konto für die gemeinsame Verwendung mit Adobe Campaign zu konfigurieren, müssen Sie die folgenden Informationen eingeben:

   * **[!UICONTROL Server]**: URL Ihres Azure Blob Storage-Servers

   * **[!UICONTROL Verschlüsselung]**: Art der Verschlüsselung, **[!UICONTROL Keine]** oder **[!UICONTROL SSL]**.

   * **[!UICONTROL Zugriffsschlüssel]**: Erfahren Sie in der [Microsoft-Dokumentation](https://docs.microsoft.com/de-de/azure/storage/common/storage-account-keys-manage?tabs=azure-portal), wie Sie Ihren **[!UICONTROL Zugriffsschlüssel]** finden.

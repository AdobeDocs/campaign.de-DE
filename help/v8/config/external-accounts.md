---
title: Externe Konten in Campaign
description: Externe Konten in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1115'
ht-degree: 100%

---

# Externe Konten konfigurieren

Adobe Campaign enthält eine Reihe vordefinierter externer Konten. Um Verbindungen zu externen Systemen einzurichten, können Sie neue externe Konten erstellen.

Externe Konten werden von technischen Prozessen, wie technischen Workflows oder Kampagnen-Workflows, verwendet. Beispiel: Bei der Einrichtung eines Dateitransfers in einem Workflow oder bei einem Datenaustausch mit einem anderen Programm (Adobe Target, Experience Manager usw.) müssen Sie ein externes Konto auswählen.

Sie können über Adobe Campaign **[!UICONTROL Explorer]** auf externe Konten zugreifen: Navigieren Sie zu **[!UICONTROL Administration]** `>` **[!UICONTROL Plattform]** `>` **[!UICONTROL Externe Konten]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Ein bestimmtes externes **[!UICONTROL FFDA]**-Konto verwaltet die Verbindung zwischen der lokalen Campaign-Datenbank und der Cloud-Datenbank ([!DNL Snowflake]).
>
>Als Anwender von Managed Cloud Services wird dieses externe Konto für Ihre Instanz durch Adobe konfiguriert. Es darf nicht geändert werden.


## Campaign-spezifische externe Konten

Die folgenden technischen Konten werden von Adobe Campaign verwendet, um bestimmte Prozesse zu aktivieren und auszuführen.

?? Für Sie als Anwender von Managed Cloud Services werden alle Campaign-spezifischen externen Konten durch Adobe konfiguriert.

* **Bounce Messages (POP3)**

   Das externe Konto **Bounce Messages** gibt das externe POP3-Konto an, das für die Verbindung mit dem E-Mail-Service verwendet werden soll. Alle Server, die für den POP3-Zugriff konfiguriert sind, können für den Empfang von Antwortsendungen verwendet werden.

   ↗️ Weitere Informationen zu eingehenden E-Mails finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html?lang=de){target=&quot;_blank&quot;}.

* **Routing**

   Mit dem externen **[!UICONTROL Routing]**-Konto können Sie jeden in Adobe Campaign verfügbaren Kanal abhängig von den installierten Packages konfigurieren.

   >[!CAUTION]
   >
   >Das externe Konto **[!UICONTROL Internes E-Mail-Routing]** (defaultEmailBulk) darf in Adobe Campaign v8 **nicht** aktiviert sein.

* **Ausführungsinstanz konfigurieren**

   Im Kontext der Transaktionsnachrichten werden die Ausführungsinstanzen mit der Kontrollinstanz verknüpft und miteinander verbunden. Transaktionsnachrichten-Vorlagen werden in der Ausführungsinstanz bereitgestellt.

   ?? Weitere Informationen zur Message Center-Architektur finden Sie auf [dieser Seite](../dev/architecture.md#transac-msg-archi).

## Zugriff auf externe Systemkonten

* **Externe Datenbank (FDA)**

   Verwenden Sie das externe Konto vom Typ **Externe Datenbank**, um über FDA eine Verbindung zu einer externen Datenbank herzustellen.

   Externe Datenbanken, die mit Adobe Campaign v8 kompatibel sind, sind in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) aufgeführt.

   ?? Weitere Informationen zur Option &quot;Federated Data Access (FDA)&quot; finden Sie in [diesem Abschnitt](../connect/fda.md).

## Externe Konten zur Integration von Adobe-Lösungen

* **Adobe Experience Cloud**

   Das externe **[!UICONTROL Adobe Experience Cloud]**-Konto wird verwendet, um Adobe IMS zu implementieren und mithilfe einer Adobe ID eine Verbindung zur Adobe Campaign-Konsole herzustellen.

   ?? Weitere Informationen zu Adobe Identity Management Service (IMS) finden Sie in [diesem Abschnitt](../start/connect.md#connect-ims).

* **Web Analytics**

   Verwenden Sie das externe Konto **[!UICONTROL Web Analytics (Adobe Analytics)]**, um die Datenübertragung von Adobe Analytics zu Adobe Campaign zu konfigurieren.

   ?? Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aa.md).

   ?? Als Managed Cloud Services-Anwender können Sie [Adobe kontaktieren](../start/campaign-faq.md#support), um Adobe Analytics mit Campaign zu integrieren.

   * **Adobe Experience Manager**
   Mit dem externen Konto **[!UICONTROL AEM]** können Sie den Inhalt Ihrer E-Mail-Sendungen und Ihrer Formulare direkt in Adobe Experience Manager verwalten.

   ?? Weitere Informationen zur Integration von Adobe Campaign mit Adobe Analytics finden Sie auf [dieser Seite](../connect/ac-aem.md).

   ?? Als Managed Cloud Services-Anwender können Sie [Adobe kontaktieren](../start/campaign-faq.md#support), um Adobe Experience Manager mit Adobe Campaign zu integrieren.


## Externe CRM-Connector-Konten

* **Microsoft Dynamics CRM**

   Das externe **[!UICONTROL Microsoft Dynamics CRM]**-Konto ermöglicht den Import und Export von Microsoft Dynamics-Daten in Adobe Campaign.

   ?? Weitere Informationen zur Integration von Adobe Campaign mit Microsoft Dynamics CRM finden Sie auf [dieser Seite](../connect/crm.md).

   Beim Bereitstellungstyp **[!UICONTROL Web-API]** und der Authentifizierung mit **[!UICONTROL Passwort]** müssen Sie die folgenden Details angeben:

   * **[!UICONTROL Konto]**: Konto, mit dem die Anmeldung bei Microsoft CRM erfolgt

   * **[!UICONTROL Server]**: URL Ihres Microsoft CRM-Servers

   * **[!UICONTROL Client-ID]**: Client-ID, die Sie über das Verwaltungsportal von Microsoft Azure in der Kategorie **[!UICONTROL Code aktualisieren]** im Feld **[!UICONTROL Client-ID]** finden.

   * **[!UICONTROL CRM-Version]**: CRM-Version – **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** oder **[!UICONTROL Dynamics CRM 2016]**
   Beim Bereitstellungstyp **[!UICONTROL Web-API]** und der Authentifizierung mit **[!UICONTROL Zertifikat]** müssen Sie die folgenden Details angeben:

   * **[!UICONTROL Server]**: URL Ihres Microsoft CRM-Servers

   * **[!UICONTROL Privater Schlüssel (Base64-kodiert)]**: Privater Schlüssel mit Base64-Kodierung

   * **[!UICONTROL Benutzerdefinierte Schlüsselkennung]**

   * **[!UICONTROL Schlüsselkennung]**

   * **[!UICONTROL Client-ID]**: Client-ID, die Sie über das Verwaltungsportal von Microsoft Azure in der Kategorie **[!UICONTROL Code aktualisieren]** im Feld **[!UICONTROL Client-ID]** finden.

   * **[!UICONTROL CRM-Version]**: CRM-Version – **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** oder **[!UICONTROL Dynamics CRM 2016]**


* **Salesforce.com**

   Das externe **[!UICONTROL Salesforce CRM]**-Konto ermöglicht den Import und Export von Salesforce-Daten in Adobe Campaign.

   Um dieses externe Konto für die gemeinsame Verwendung mit Adobe Campaign zu konfigurieren, müssen Sie die folgenden Informationen eingeben:

   * **[!UICONTROL Konto]**: Konto, mit dem die Anmeldung bei Salesforce CRM erfolgt

   * **[!UICONTROL Passwort]**: Passwort, mit dem die Anmeldung bei Salesforce CRM erfolgt.

   * **[!UICONTROL Client-Kennung]**: Erfahren Sie auf [dieser Seite](https://help.salesforce.com/articleView?id=000205876&amp;type=1), wie Sie Ihre Client-Kennung finden.

   * **[!UICONTROL Security-Token]**: Erfahren Sie auf [dieser Seite](https://help.salesforce.com/articleView?id=000205876&amp;type=1), wie Sie Ihr Security-Token finden.

   * **[!UICONTROL API-Version]**: Wählen Sie die Version der API aus. Für dieses externe Konto müssen Sie Salesforce CRM mit dem Konfigurationsassistenten konfigurieren.

## Übertragen von Daten mit externen Konten

Diese externen Konten können mithilfe einer Workflow-Aktivität vom Typ **[!UICONTROL Dateiübertragung]** zum Importieren oder Exportieren von Daten in Adobe Campaign verwendet werden.

↗️ Weitere Informationen zur Dateiübertragung in Workflows finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html?lang=de){target=&quot;_blank&quot;}.

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

---
title: Migration technischer Benutzer zu einem technischen Konto in der Entwicklerkonsole
description: Migration technischer Benutzer zu einem technischen Konto in der Entwicklerkonsole
hide: true
hidefromtoc: true
source-git-commit: 8842404511bd6166d920ebdeee942007b33a1bab
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# Migration der technischen Campaign-Benutzer zur Adobe Developer Console {#migrate-tech-users-to-ims}

Ab Campaign v8.5 wird der Authentifizierungsprozess für Campaign v8 verbessert. Technische Benutzer müssen [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} , um eine Verbindung mit Campaign herzustellen. Ein technischer Benutzer ist ein Campaign-Benutzerprofil, das explizit für die API-Integration erstellt wurde. In diesem Artikel werden die Schritte beschrieben, die zum Migrieren eines technischen Benutzers zu einem technischen Konto in der Adobe Developer-Konsole erforderlich sind.

## Was hat sich geändert?{#ims-changes}

Campaign-Normalbenutzer stellen über Adobe Identity Management System (IMS) bereits über ihre Adobe ID eine Verbindung zur Adobe Campaign-Konsole her. Im Rahmen der Bemühungen um die Verbesserung des Sicherheits- und Authentifizierungsprozesses ruft die Adobe Campaign Client-Anwendung jetzt Campaign-APIs direkt mithilfe des Tokens für das technische IMS-Konto auf.

Erfahren Sie mehr über den neuen Serverauthentifizierungsprozess. [in der Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Diese Änderung gilt ab Campaign v8.5 und wird **mandatory** Starten von Campaign v8.6.


## Sind Sie betroffen?{#ims-impacts}

Wenn Sie Campaign-APIs verwenden, müssen Sie Ihre technischen Benutzer wie unten beschrieben zur Adobe Developer Console migrieren.

## Wie migriert man?{#ims-migration-procedure}

### Voraussetzungen{#ims-migration-prerequisites}

Bevor Sie mit dem Migrationsprozess beginnen, müssen Sie sich an Ihren Adobe-Support-Mitarbeiter wenden, damit Adobe-Techniker Ihre bestehenden Benutzergruppen und spezifischen Berechtigungen in das Adobe Identity Management System (IMS) migrieren können.

### Schritt 1: Erstellen/Aktualisieren Ihres Campaign-Projekts in der Adobe Developer Console{#ims-migration-step-1}

Integrationen werden im Rahmen einer **Projekt** in der Adobe Developer-Konsole. Weitere Informationen zu Projekten in [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Als Campaign v8-Benutzer sollten Sie bereits über ein Projekt in der Adobe Developer-Konsole verfügen. Ist dies nicht der Fall, müssen Sie ein Projekt erstellen. Die Schritte zum Erstellen eines Projekts werden im Detail beschrieben. [in der Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Sobald Sie Zugriff auf Ihr Campaign-Projekt haben, können Sie Dienste hinzufügen, einschließlich APIs, Adobe Campaign und I/O-Management-APIs. Für diese Migration müssen Sie in Ihrem Projekt die folgenden APIs hinzufügen: **I/O-Management-API** und **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Server to Server-Authentifizierung{#ims-migration-step-2}

Nachdem Ihr Projekt in der Adobe Developer Console erstellt wurde, fügen Sie eine API hinzu, die die Server-zu-Server-Authentifizierung verwendet. Erfahren Sie, wie Sie die OAuth-Server-zu-Server-Anmeldedaten in [in der Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Wenn die API erfolgreich verbunden wurde, können Sie auf die neu generierten Anmeldeinformationen zugreifen, einschließlich Client-ID und Client-Geheimnis, und ein Zugriffstoken generieren.

### Schritt 3: Hinzufügen des Produktprofils zum Projekt{#ims-migration-step-3}

Sie können jetzt Ihr Campaign-Produktprofil zum Projekt hinzufügen, wie unten beschrieben:

1. Öffnen Sie die Adobe Campaign-API.
1. Klicken Sie auf **Bearbeiten von Produktprofilen** button

   ![](assets/do-not-localize/ims-edit-api.png)

1. Weisen Sie alle relevanten Produktprofile der API zu, z. B. &quot;messagecenter&quot;, und speichern Sie Ihre Änderungen.
1. Navigieren Sie zum **Details zu Berechtigungen** und kopieren Sie die **Email für technische Konten** -Wert.

### Schritt 4: Aktualisieren des technischen Benutzers in der Clientkonsole {#ims-migration-step-4}

Der letzte Schritt besteht darin, den technischen Operator in der Adobe Campaign Client Console zu aktualisieren.

>[!CAUTION]
>
>Nach der Aktualisierung des Authentifizierungstyps für den technischen Benutzer funktionieren alle API-Integrationen mit diesem technischen Benutzer nicht mehr. Sie müssen [API-Integrationen aktualisieren](#ims-migration-step-6).

Gehen Sie wie folgt vor, um den Authentifizierungsmodus des technischen Benutzers auf IMS zu aktualisieren:

1. Navigieren Sie im Campaign Client Console-Explorer zum **Administration > Zugriffe > Benutzer**.
1. Bearbeiten Sie den vorhandenen technischen Benutzer, der für die APIs verwendet wurde.
1. Ersetzen Sie die **Name (login)** des technischen Benutzers durch die E-Mail-Adresse des technischen Kontos, die zuvor abgerufen wurde.
1. Navigieren Sie zum **Bearbeiten** Schaltfläche oben links neben **Datei** und wählen Sie **XML-Quelle bearbeiten**.
1. Aktualisieren Sie den Authentifizierungsmodus auf `ims`, wie folgt:

   ```javascript
   <operator 
   ...
       <access authenticationType="ims" ...
       ...
       </access>
   ...
   </operator>
   ```

1. Speichern Sie Ihre Änderungen.

Sie können den technischen Operator auch programmgesteuert mithilfe von SQL-Scripts oder Campaign-APIs aktualisieren. Mithilfe dieser Modi können Sie die Schritte automatisieren, die den Namen des Benutzers mit der E-Mail-Adresse und/oder dem Authentifizierungstyp des technischen Kontos aktualisieren.

* Verwenden Sie Folgendes **SQL-Skript** , um den Namen des Benutzers durch die zugehörige E-Mail-Adresse zu ersetzen:

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* Verwenden Sie Folgendes `queryDef.ExecuteQuery` **Campaign-API** die Kennung eines Benutzers für einen bestimmten technischen Benutzer abzurufen:

   ```javascript
   <?xml version="1.0" encoding="utf-8"?>
   <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
       <soap:Body>
           <ExecuteQuery xmlns="urn:xtk:queryDef">
               <sessiontoken>{session_token}</sessiontoken>
               <entity>
                   <queryDef schema="xtk:operator" operation="select">
                       <select>
                           <node expr="@id"/>
                       </select>
                       <where>
                           <condition expr="@name='{name}'"/>
                           <condition expr="@type=0"/>
                       </where>
                   </queryDef>
               </entity>
           </ExecuteQuery>
       </soap:Body>
   </soap:Envelope>
   ```

* Verwenden Sie Folgendes `session.Write` **Campaign-API** , um den Namen mit der angegebenen E-Mail-Adresse des technischen Kontos zu aktualisieren:

   ```javascript
   <?xml version="1.0" encoding="utf-8"?>
   <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
       <soap:Body>
           <Write xmlns="urn:xtk:session">
               <sessiontoken>{session_token}</sessiontoken>
               <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                   <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                       <access authenticationType="ims" />
                   </operator>
               </domDoc>
           </Write>
       </soap:Body>
   </soap:Envelope>
   ```

### Schritt 5: Überprüfen der Konfiguration {#ims-migration-step-5}

Um die Verbindung auszuprobieren, führen Sie die Schritte aus, die im Abschnitt [Handbuch zu den Anmeldedaten für Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} zum Generieren eines Zugriffstokens und Kopieren Sie den Beispielbefehl cURL .


### Schritt 6: Aktualisierung der API-Integrationen von Drittanbietern {#ims-migration-step-6}

Sie müssen die API-Integrationen mit Ihren Drittanbietersystemen aktualisieren.

Weitere Informationen zu den Schritten der API-Integration, einschließlich eines Beispielcodes für eine reibungslose Integration, finden Sie unter [Dokumentation zur Authentifizierung der Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Beispiele für Soap-Aufrufe{#ims-migration-samples}

Sobald der Migrationsprozess erreicht und validiert wurde, werden die SOAP-Aufrufe wie folgt aktualisiert:

* Vor der Migration

   ```sql
   POST /nl/jsp/soaprouter.jsp HTTP/1.1
   Host: localhost:8080
   Content-Type: application/soap+xml;
   SOAPAction: "nms:rtEvent#PushEvent"
   charset=utf-8
   
   <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:PushEvent>
           <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
           <urn:domEvent>
               <!--You may enter ANY elements at this point-->
               <rtEvent type="type" email="name@domain.com"/>
           </urn:domEvent>
       </urn:PushEvent>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

* Nach der Migration

   ```sql
   POST /nl/jsp/soaprouter.jsp HTTP/1.1
   Host: localhost:8080
   Content-Type: application/soap+xml;
   SOAPAction: "nms:rtEvent#PushEvent"
   charset=utf-8
   Authorization: Bearer <IMS_Technical_Token_Token>
   
   <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:PushEvent>
           <urn:sessiontoken></urn:sessiontoken>
           <urn:domEvent>
               <!--You may enter ANY elements at this point-->
               <rtEvent type="type" email="name@domain.com"/>
           </urn:domEvent>
       </urn:PushEvent>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

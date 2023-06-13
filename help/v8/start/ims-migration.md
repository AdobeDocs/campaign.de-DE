---
title: Migration technischer Benutzerinnen bzw. Benutzer zu einem technischen Konto in der Developer Console
description: Migration technischer Benutzerinnen bzw. Benutzer zu einem technischen Konto in der Developer Console
hide: true
hidefromtoc: true
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: ht
source-wordcount: '807'
ht-degree: 100%

---

# Migration von technischen Campaign-Benutzerinnen bzw. -Benutzer zur Adobe Developer Console {#migrate-tech-users-to-ims}

Ab Campaign v8.5 wird der Authentifizierungsprozess für Campaign v8 verbessert. Technische Benutzerinnen bzw. Benutzer müssen [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} verwenden, um eine Verbindung mit Campaign herzustellen. Eine technische Benutzerin bzw. ein technischer Benutzer ist ein Campaign-Benutzerprofil, das explizit für die API-Integration erstellt wurde. In diesem Artikel werden die Schritte beschrieben, die zum Migrieren einer technischen Benutzerin bzw. eines technischen Benutzers zu einem technischen Konto in der Adobe Developer Console erforderlich sind.

## Was hat sich geändert?{#ims-changes}

Reguläre Campaign-Anwenderinnen und Anwender stellen über das Adobe Identity Management System (IMS) mit ihrer Adobe ID eine Verbindung zur Adobe Campaign-Konsole her. Im Rahmen der Anstrengungen um die Verbesserung des Sicherheits- und Authentifizierungsprozesses ruft die Adobe Campaign-Client-Anwendung jetzt Campaign-APIs direkt mithilfe des Tokens für das technische IMS-Konto auf.

Erfahren Sie mehr über den neuen Server-zu-Server-Authentifizierungsprozess in der [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Diese Änderung gilt ab Campaign v8.5 und wird ab Campaign v8.6 **obligatorisch**.


## Sind Sie betroffen?{#ims-impacts}

Wenn Sie Campaign-APIs verwenden, müssen Sie Ihre technischen Benutzerinnen und Benutzer wie unten beschrieben zur Adobe Developer Console migrieren.

## Wie wird die Migration durchgeführt?{#ims-migration-procedure}

### Voraussetzungen{#ims-migration-prerequisites}

Bevor Sie mit dem Migrationsprozess beginnen, müssen Sie sich an Ihren Adobe-Kontakt wenden, damit die technischen Teams von Adobe Ihre bestehenden Benutzergruppen und spezifischen Berechtigungen zum Adobe Identity Management System (IMS) migrieren können.

### Schritt 1: Erstellen/Aktualisieren Ihres Campaign-Projekts in der Adobe Developer Console{#ims-migration-step-1}

Integrationen werden im Rahmen eines **Projekts** in der Adobe Developer Console erstellt. Weitere Informationen zu Projekten sind in der [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"} zu finden.

Als Anwenderin bzw. Anwender von Campaign v8 sollten Sie bereits über ein Projekt in der Adobe Developer Console verfügen. Ist dies nicht der Fall, müssen Sie ein Projekt erstellen. Die Schritte zum Erstellen eines Projekts werden im Detail in der [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"} beschrieben.

Sobald Sie Zugriff auf Ihr Campaign-Projekt haben, können Sie Dienste hinzufügen, einschließlich APIs, Adobe Campaign und I/O-Management-API. Für diese Migration müssen Sie in Ihrem Projekt die folgenden APIs hinzufügen: **I/O-Management-API** und **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Server-zu-Server-Authentifizierung{#ims-migration-step-2}

Nachdem Ihr Projekt in der Adobe Developer Console erstellt wurde, fügen Sie eine API hinzu, die die Server-zu-Server-Authentifizierung verwendet. Erfahren Sie in der [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}, wie Sie die OAuth-Server-zu-Server-Anmeldedaten einrichten,

Wenn die API erfolgreich verbunden wurde, können Sie auf die neu generierten Anmeldeinformationen zugreifen, einschließlich Client-ID und Client-Geheimnis, und ein Zugriffs-Token generieren.

### Schritt 3: Hinzufügen des Produktprofils zum Projekt{#ims-migration-step-3}

Sie können jetzt Ihr Campaign-Produktprofil zum Projekt hinzufügen, wie im Folgenden beschrieben:

1. Öffnen Sie die Adobe Campaign-API.
1. Klicken Sie auf Sie Schaltfläche **Produktprofile bearbeiten**.

   ![](assets/do-not-localize/ims-edit-api.png)

1. Weisen Sie alle relevanten Produktprofile der API zu, z. B. „messagecenter“, und speichern Sie Ihre Änderungen.
1. Navigieren Sie zur Registerkarte **Zugriffsdatendetails** und kopieren Sie den Wert von **E-Mail des technischen Kontos**.

### Schritt 4: Aktualisieren des technischen Benutzers bzw. der technischen Benutzerin in der Client-Konsole {#ims-migration-step-4}

Der letzte Schritt besteht darin, die technische Benutzerin bzw. den technischen Benutzer in der Adobe Campaign-Client-Konsole zu aktualisieren.

>[!CAUTION]
>
>Nach der Aktualisierung des Authentifizierungstyps für die technische Benutzerin bzw. den technischen Benutzer funktionieren alle API-Integrationen mit dieser technischen Benutzerin bzw. diesem technischen Benutzer nicht mehr. Sie müssen [Ihre API-Integrationen aktualisieren](#ims-migration-step-6).

Gehen Sie wie folgt vor, um den Authentifizierungsmodus der technischen Benutzerin bzw. des technischen Benutzers auf IMS zu aktualisieren:

1. Navigieren Sie im Explorer der Campaign-Client-Konsole zu **Administration > Zugriffsverwaltung > Benutzer**.
1. Bearbeiten Sie die vorhandene technische Benutzerin bzw. den technischen Benutzer, die bzw. der für APIs verwendet wurde.
1. Ersetzen Sie **Name (Anmeldung)** der technischen Benutzerin bzw. des technischen Benutzers durch die E-Mail-Adresse des technischen Kontos, die zuvor abgerufen wurde.
1. Navigieren Sie zur Schaltfläche **Bearbeiten** oben links neben **Datei** und wählen Sie **XML-Quelle bearbeiten** aus.
1. Aktualisieren Sie wie folgt den Authentifizierungsmodus auf `ims`:

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

Sie können die technische Benutzerin bzw. den technischen Benutzer auch programmgesteuert mithilfe von SQL-Scripts oder Campaign-APIs aktualisieren. Mithilfe dieser Modi können Sie die Schritte automatisieren, die den Namen der Benutzerin bzw. des Benutzers mit der E-Mail-Adresse und/oder dem Authentifizierungstyp des technischen Kontos aktualisieren.

* Verwenden Sie das folgende **SQL-Script**, um den Namen der Benutzerin oder des Benutzers durch die zugehörige E-Mail zu ersetzen:

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* Verwenden Sie die folgende `queryDef.ExecuteQuery` **Campaign-API**, um die Kennung einer Benutzerin bzw. eines Benutzers für eine bestimmte technische Benutzerin bzw. einen technischen Benutzer abzurufen:

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

* Verwenden Sie die folgende `session.Write` **Campaign-API**, um den Namen mit der angegebenen E-Mail-Adresse des technischen Kontos zu aktualisieren:

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

### Schritt 5: Validieren der Konfiguration {#ims-migration-step-5}

Um die Verbindung auszuprobieren, führen Sie die Schritte aus, die im Abschnitt [Handbuch zu den Anmeldedaten für Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} zum Generieren eines Zugriffs-Tokens beschrieben sind, und kopieren Sie den Beispiel-cURL-Befehl.


### Schritt 6: Aktualisieren der API-Integrationen von Drittanbietern {#ims-migration-step-6}

Sie müssen die API-Integrationen mit Ihren Drittanbietersystemen aktualisieren.

Weitere Informationen zu den Schritten der API-Integration, einschließlich eines Beispielcodes für eine reibungslose Integration, finden Sie unter [Dokumentation zur Authentifizierung der Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Beispiele für SOAP-Aufrufe{#ims-migration-samples}

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

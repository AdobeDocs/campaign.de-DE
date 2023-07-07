---
title: Migration von technischen Benutzerinnen und Benutzern zur Adobe Developer Console
description: Erfahren Sie, wie Sie technische Campaign-Benutzerinnen bzw. -Benutzer zu einem technischen Konto in der Adobe Developer-Konsole migrieren.
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '779'
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


Dieser Schritt ist nur erforderlich, wenn für diesen Benutzer bzw. diese Benutzerin (nicht über die Benutzergruppe) spezifische Ordnerberechtigungen oder spezifische Berechtigungen definiert wurden.

Sie müssen jetzt den neu erstellten technischen Benutzer bzw. die Benutzerin in der Adobe Campaign-Client-Konsole aktualisieren. Sie müssen die bestehenden Berechtigungen für den Ordner des technischen Benutzers bzw. der Benutzerin auf die neue Person übertragen.
Gehen Sie wie folgt vor, um diesen Benutzer bzw. diese Benutzerin zu aktualisieren:

1. Navigieren Sie im Explorer der Campaign-Client-Konsole zu **Administration > Zugriffsverwaltung > Benutzer**.
1. Greifen Sie auf den bestehenden technischen Benutzer bzw. die technische Benutzerin zu, der bzw. die für APIs verwendet wird.
1. Navigieren Sie zu den Ordnerberechtigungen und überprüfen Sie die Berechtigungen.
1. Wenden Sie dieselben Berechtigungen auf den neu erstellten technischen Benutzer bzw. die neu erstellte technische Benutzerin an. Die E-Mail-Adresse dieser Benutzerin bzw. dieses Benutzers ist der Wert der **E-Mail für technische Konten**, der zuvor kopiert wurde.
1. Speichern Sie Ihre Änderungen.


>[!CAUTION]
>
>Der neue technische Benutzer bzw. die Benutzerin muss mindestens einen API-Aufruf durchgeführt haben, damit er der Campaign-Client-Konsole hinzugefügt werden kann.
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

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

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

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
-->

### Schritt 5: Validieren der Konfiguration {#ims-migration-step-5}

Um die Verbindung auszuprobieren, führen Sie die Schritte aus, die im Abschnitt [Handbuch zu den Anmeldedaten für Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} zum Generieren eines Zugriffs-Tokens beschrieben sind, und kopieren Sie den Beispiel-cURL-Befehl.


### Schritt 6: Aktualisieren der API-Integrationen von Drittanbietern {#ims-migration-step-6}

Sie müssen die API-Integrationen mit Ihren Drittanbietersystemen aktualisieren.

Weitere Informationen zu den Schritten der API-Integration, einschließlich eines Beispielcodes für eine reibungslose Integration, finden Sie unter [Dokumentation zur Authentifizierung der Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Schritt 7: Entfernen des alten technischen Benutzers bzw. der Benutzerin {#ims-migration-step-7}


Nach der Migration aller API/benutzerdefinierten Code-Integrationen mit dem Benutzer bzw. der Benutzerin des technischen Kontos. Sie können den alten technischen Benutzer bzw. die alte technische Benutzerin aus der Campaign-Client-Konsole löschen.

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

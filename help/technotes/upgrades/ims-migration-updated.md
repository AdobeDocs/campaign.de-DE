---
title: Migration von technischen Benutzerinnen und Benutzern zur Adobe Developer Console
description: Erfahren Sie, wie Sie technische Campaign-Benutzerinnen bzw. -Benutzer zu einem technischen Konto in der Adobe Developer-Konsole migrieren.
hide: true
hidefromtoc: true
source-git-commit: d52744e1d798447bb6b90909607e42082f7eeaf5
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 20%

---

# Migration von technischen Campaign-Benutzerinnen bzw. -Benutzer zur Adobe Developer Console {#migrate-tech-users-to-ims}

Im Rahmen der Bemühungen um die Verbesserung des Sicherheits- und Authentifizierungsprozesses wird ab Campaign v8.5 der Authentifizierungsprozess für Campaign v8 verbessert. Technische Benutzer können jetzt die [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} to connect to Campaign. Learn more about the new server to server authentication process in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Eine technische Benutzerin bzw. ein technischer Benutzer ist ein Campaign-Benutzerprofil, das explizit für die API-Integration erstellt wurde. In diesem Artikel werden die Schritte beschrieben, die für die Migration eines technischen Benutzers zu einem technischen Konto über die Adobe Developer-Konsole erforderlich sind.


## Sind Sie betroffen?{#ims-impacts}

Wenn Sie API-Aufrufe von einem Campaign-externen System in die Campaign-Marketing-Instanz oder die Echtzeit-Message-Center-Instanz durchführen, müssen Sie den/die technischen Benutzer über die Adobe Developer-Konsole zu technischen Konten migrieren, wie unten beschrieben.

Diese Änderung gilt ab Campaign v8.5.


## Migrationsprozess {#ims-migration-procedure}

Führen Sie die folgenden Schritte aus, um technische Konten in der Adobe Developer-Konsole zu erstellen und diese neu erstellten Konten zu verwenden, um die Authentifizierungsmethoden für alle externen Systeme zu ändern, die API-Aufrufe in Adobe Campaign tätigen.

Eine Übersicht über die Schritte finden Sie unter:

* Erstellen eines Projekts in der Adobe Developer-Konsole
* Zuweisen der entsprechenden APIs zum neu erstellten Projekt
* Zuweisen der erforderlichen Campaign-Produktprofile zum Projekt
* APIs für die Verwendung der neu erstellten technischen Kontoanmeldeinformationen aktualisieren
* Entfernen Sie die veralteten technischen Operatoren aus Ihrer Campaign-Instanz.

### Voraussetzungen für die Migration{#ims-migration-prerequisites}

Um die technischen Konten erstellen zu können, die die technischen Benutzer ersetzen, muss die Voraussetzung, dass die entsprechenden Campaign-Produktprofile in der Admin Console für alle Campaign-Instanzen vorhanden sind, validiert werden. Weitere Informationen zu Produktprofilen finden Sie in der Adobe-Konsole unter [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Für API-Aufrufe in die Message-Center-Instanz(en) sollte während der Aktualisierung auf Campaign v8.5 oder während der Bereitstellung der Instanz ein Produktprofil erstellt worden sein. Dieses Produktprofil hat den Namen:

`campaign - <your campaign instance> - messagecenter`

Wenn Sie bereits die IMS-basierte Authentifizierung für den Benutzerzugriff auf Campaign verwendet haben, sollten die für die API-Aufrufe erforderlichen Produktprofile bereits in der Admin Console vorhanden sein. Wenn Sie eine benutzerdefinierte Benutzergruppe in Campaign für die API-Aufrufe an die Marketing-Instanz verwenden, müssen Sie dieses Produktprofil in der Admin Console erstellen.

Für andere Fälle müssen Sie sich an Ihren Adobe Transition Manager wenden, damit Adobe-Techniker Ihre bestehenden Benutzergruppen und spezifischen Berechtigungen zu den Produktprofilen innerhalb der Admin Console migrieren können.


### Schritt 1: Erstellen Ihres Campaign-Projekts in der Adobe Developer-Konsole {#ims-migration-step-1}

Integrationen werden im Rahmen eines **Projekts** in der Adobe Developer Console erstellt. Weitere Informationen zu Projekten sind in der [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"} zu finden.

Sie können jedes zuvor von Ihnen erstellte Projekt verwenden oder ein neues Projekt erstellen. Die Schritte zum Erstellen eines Projekts werden im Detail in der [Dokumentation zur Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/getting-started/) beschrieben. {target="_blank"} Nachfolgend finden Sie die wichtigsten Schritte.

<!--
For this migration, you must add below APIs in your project: **I/O Management API** and **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)-->

Um ein neues Projekt zu erstellen, klicken Sie auf **Neues Projekt erstellen** über den Hauptbildschirm in der Adobe Developer Console aus.

![](assets/New-Project.png)

Sie können die **Projekt bearbeiten** -Schaltfläche, um dieses Projekt umzubenennen.


### Schritt 2: Hinzufügen von APIs zu Ihrem Projekt {#ims-migration-step-2}

Fügen Sie im neu erstellten Projektbildschirm die erforderlichen APIs hinzu, um dieses Projekt als Technisches Konto für Ihre API-Aufrufe an Adobe Campaign verwenden zu können.

Gehen Sie wie folgt vor, um Ihrem Projekt APIs hinzuzufügen:

1. Klicken Sie auf **API hinzufügen** , um die APIs auszuwählen, die zum Projekt hinzugefügt werden sollen.
   ![](assets/do-not-localize/ims-updates-01.png)
1. Wählen Sie die Adobe Campaign-API aus und fügen Sie sie zu Ihrem Projekt hinzu, indem Sie das Kontrollkästchen oben rechts auf der Adobe Campaign-Karte aktivieren, das angezeigt wird, wenn Sie den Mauszeiger über die Karte bewegen
   ![](assets/do-not-localize/ims-updates-02.png)
1. Klicks **Nächste** unten auf dem Bildschirm.

### Schritt 3: Authentifizierungstyp auswählen  {#ims-migration-step-3}

Im **API konfigurieren** wählen Sie den Authentifizierungstyp aus. **OAuth Server-zu-Server** Für dieses Projekt ist eine Authentifizierung erforderlich. Stellen Sie sicher, dass sie ausgewählt ist, und klicken Sie auf **Nächste** unten auf dem Bildschirm.

![](assets/do-not-localize/ims-updates-03.png)

<!--
Once your project is created in the Adobe Developer Console, add an API that uses Server-to-Server authentication. Learn how to set up the OAuth Server-to-Server credential in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

When the API has been successfully connected, you can access the newly generated credentials including Client ID and Client Secret, as well as generate an access token.-->

### 4. Schritt - Produktprofile auswählen {#ims-migration-step-4}

Wie im Abschnitt Voraussetzungen beschrieben, müssen Sie die entsprechenden Produktprofile zuweisen, die vom Projekt verwendet werden sollen. In diesem Schritt müssen Sie das Produktprofil bzw. die Profile auswählen, die vom zu erstellenden technischen Konto verwendet werden sollen.

Wenn dieses technische Konto verwendet wird, um API-Aufrufe an die Message-Center-Instanz durchzuführen, wählen Sie die Adobe zum Erstellen eines Produktprofils aus, das mit `messagecenter`.

Wählen Sie für API-Aufrufe an die Marketing-Instanz(en) das Produktprofil aus, das der Instanz und der Benutzergruppe entspricht.

Klicken Sie nach Auswahl der gewünschten Produktprofile auf **Konfigurierte API speichern** unten auf dem Bildschirm.

<!--
You can now add your Campaign product profile to the project, as detailed below:

1. Open the Adobe Campaign API.
1. Click the **Edit product profiles** button

    ![](assets/do-not-localize/ims-edit-api.png)

1. Assign all the relevant Product Profiles to the API, for example 'messagecenter', and save your changes.
1. Browse to the **Credential details** tab of your project, and copy the **Technical Account Email** value.-->

### Schritt 5: Hinzufügen der I/O-Management-API zu Ihrem Projekt {#ims-migration-step-5}


Klicken Sie im Projektbildschirm auf das **[!UICONTROL + Zum Projekt hinzufügen]** und wählen **[!UICONTROL API]** oben links im Bildschirm, um die I/O-Management-API zu diesem Projekt hinzufügen zu können.

![](assets/do-not-localize/ims-updates-04.png)

Im **API hinzufügen** scrollen Sie nach unten, um die **I/O-Management-API** Karte. Wählen Sie es aus, indem Sie auf das Kontrollkästchen klicken, das angezeigt wird, wenn Sie den Mauszeiger über die Karte bewegen. Klicken Sie anschließend auf **Nächste** unten auf dem Bildschirm.

![](assets/do-not-localize/ims-updates-05.png)


Im **API konfigurieren** angezeigt, ist die OAuth Server-zu-Server-Authentifizierung bereits vorhanden. Klicks **Konfigurierte API speichern** unten auf dem Bildschirm.


![](assets/do-not-localize/ims-updates-06.png)

Dadurch gelangen Sie zurück zum Bildschirm Projekt in der I/O-Management-API des neu erstellten Projekts. Klicken Sie oben im Bildschirm in den Breadcrumbs auf den Projektnamen, um zur Hauptseite mit den Projektdetails zurückzukehren.


### Schritt 6: Überprüfen der Projekteinrichtung {#ims-migration-step-6}

Überprüfen Sie Ihr Projekt, um sicherzustellen, dass es mit dem **I/O-Management-API** und **Adobe Campaign-API** im Abschnitt &quot;Produkte und Dienste&quot;angezeigt und **OAuth Server-zu-Server** im Abschnitt Anmeldedaten .

![](assets/do-not-localize/ims-updates-07.png)


### Schritt 7: Validieren der Konfiguration {#ims-migration-step-7}

Um die Verbindung auszuprobieren, führen Sie die im Abschnitt [Handbuch zu den Anmeldedaten für Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} zum Generieren eines Zugriffstokens und Kopieren Sie den Beispielbefehl cURL . Sie können mithilfe dieser Anmeldeinformationen einen Seifenaufruf erstellen, um zu testen, ob Sie sich authentifizieren und eine korrekte Verbindung zu den Adobe Campaign-Instanzen herstellen können. Es wird empfohlen, diese Validierung durchzuführen, bevor alle Änderungen an den API-Integrationen von Drittanbietern vorgenommen werden.

### Schritt 8: Aktualisierung der API-Integrationen von Drittanbietern {#ims-migration-step-8}

Sie müssen jetzt die API-Integrationen aktualisieren, die Aufrufe an Adobe Campaign tätigen, um das neu erstellte technische Konto zu verwenden.

Weitere Informationen zu den Schritten der API-Integration, einschließlich eines Beispielcodes für eine reibungslose Integration, finden Sie unter [Dokumentation zur Authentifizierung der Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Im Folgenden finden Sie Beispiele für SOAP-Aufrufe, die die Vor- und Nach-Migration-Aufrufe für die Drittanbietersysteme anzeigen.

Sobald der Migrationsprozess erreicht und validiert wurde, werden die SOAP-Aufrufe wie folgt aktualisiert:



* Vor der Migration: Zugriffstoken für technische Konten wurden nicht unterstützt.

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

* Nach der Migration: Zugriffstoken für technische Konten werden unterstützt. Es wird erwartet, dass das Zugriffstoken in der `Authorization` Kopfzeile als Bearer-Token angegeben wird. Die Verwendung eines Sitzungs-Tokens sollte hier ignoriert werden, wie im folgenden Beispiel für einen SOAP-Aufruf dargestellt.

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



### Schritt 9: (optional) Aktualisieren Sie den technischen Kundenbetreuer in der Campaign Client Console. {#ims-migration-step-9}

Dieser Schritt ist optional und nur innerhalb der Marketing-Instanz(en) verfügbar, nicht aber in einer Message Center-Instanz. Wenn spezifische Ordnerberechtigungen oder spezifische Berechtigungen für den technischen Operator definiert wurden, nicht über die zugewiesenen Benutzergruppen. Sie müssen jetzt den neu erstellten Benutzer des technischen Kontos in der Admin Console aktualisieren, um die erforderlichen Ordnerberechtigungen oder spezifischen Berechtigungen zu erteilen.

Beachten Sie, dass der Benutzer des technischen Kontos NICHT in Adobe Campaign vorhanden ist, bis mindestens ein API-Aufruf an die Campaign-Instanz erfolgt. Zu diesem Zeitpunkt erstellt IMS den Benutzer in Campaign. Wenn Sie die technischen Benutzer in Campaign nicht finden können, können Sie erfolgreich einen API-Aufruf senden, wie beschrieben [in Schritt 7](#ims-migration-step-7).

1. Um die für den neuen Benutzer des technischen Kontos erforderlichen Änderungen anzuwenden, suchen Sie diese in der Campaign Client Console nach E-Mail-Adresse. Diese E-Mail-Adresse wurde während der obigen Schritte zur Projekterstellung und -authentifizierung erstellt.

   Klicken Sie auf die Schaltfläche **OAuth Server-zu-Server** -Überschrift **Anmeldeinformationen** des Projekts.

   ![](assets/do-not-localize/ims-updates-07.png)

   Scrollen Sie im Bildschirm &quot;Anmeldedaten&quot;nach unten, um die E-Mail-Adresse des technischen Kontos zu suchen, und klicken Sie auf die Schaltfläche **Kopieren** Schaltfläche.

   ![](assets/do-not-localize/ims-updates-08.png)

1. Sie müssen jetzt den neu erstellten technischen Benutzer bzw. die Benutzerin in der Adobe Campaign-Client-Konsole aktualisieren. Sie müssen die bestehenden Berechtigungen für den Ordner des technischen Benutzers bzw. der Benutzerin auf die neue Person übertragen.

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

### Schritt 10: Entfernen des alten technischen Benutzers aus Adobe Campaign {#ims-migration-step-10}

Nachdem Sie alle Drittanbietersysteme migriert haben, um das neue technische Konto mit IMS-Authentifizierung zu verwenden, können Sie den alten technischen Benutzer aus der Campaign Client-Konsole löschen.

Melden Sie sich dazu bei der Campaign-Client-Konsole an und navigieren Sie zu **Administration > Zugriffe > Benutzer** und die alten technischen Benutzer finden und löschen.

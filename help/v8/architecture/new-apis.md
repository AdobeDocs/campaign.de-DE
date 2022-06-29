---
title: FFDA-Bereitstellungs-APIs
description: FFDA-spezifische APIs
feature: Overview
role: Data Engineer
level: Beginner
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 5c1ced7972295e79418ac7ff14a6f0888e5ed39a
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 91%

---

# Spezifische FFDA-Kampagnen-APIs{#gs-new-api}

Im Kontext eines [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md)enthält Campaign v8 zwei spezifische APIs zum Verwalten von Daten zwischen der lokalen Campaign-Datenbank und der Cloud-Datenbank. Voraussetzungen für ihre Verwendung ist die Aktivierung des Staging-Mechanismus im Schema. [Weitere Informationen](staging.md)

* Aufnahme-API: **xtk.session.ingest**

   Diese API ist nur für die Dateneinfügung geeignet. [Weitere Informationen](#data-insert-api)

* Datenaktualisierungs-/Löschungs-API: **xtk.session.ingestExt**

   Mit dieser API können Daten aktualisiert oder gelöscht werden. [Weitere Informationen](#data-update-api)

Ein dedizierter integrierter Workflow synchronisiert die Daten in der Cloud-Datenbank.

## Einfügen von Daten {#data-insert-api}

Die API **xtk.session.ingest** ist nur für die Dateneinfügung vorgesehen. Keine Aktualisierung/Löschung.

### Einfügen ohne Abstimmung{#insert-no-reconciliation}

**In einem Workflow**

Verwenden Sie den folgenden Code in einer **JavaScript-Code**-Aktivität, um Daten ohne Abstimmung in die Cloud-Datenbank einzufügen:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Nach Ausführung des Workflows wird die Staging-Tabelle erwartungsgemäß befüllt.

**Von einem SOAP-Aufruf**

1. Fordern Sie den Authentifizierungs-Token an.
1. Lösen Sie die API aus. Die Payload ist:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID wird an die SOAP-Antwort zurückgesendet:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Als Ergebnis wird die Staging-Tabelle erwartungsgemäß befüllt.

![](assets/no-reconciliation.png)

### Einfügen mit Abstimmung

**In einem Workflow**

Verwenden Sie den folgenden Code in einer **JavaScript-Code**-Aktivität, um Daten mit Abstimmung in die Cloud-Datenbank einzufügen:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Nach Ausführung des Workflows wird die Staging-Tabelle erwartungsgemäß befüllt.

![](assets/with-reconciliation.png)


**Von einem SOAP-Aufruf**

1. Fordern Sie den Authentifizierungs-Token an.
1. Lösen Sie die API aus. Die Payload ist:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. In diesem Fall wird die UUID nicht an die Antwort zurückgegeben, da sie in der Payload bereitgestellt wurde. Die Antwort lautet:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Als Ergebnis wird die Staging-Tabelle erwartungsgemäß befüllt.

## Aktualisieren oder Löschen von Daten {#data-update-api}

Die API **xtk.session.IngestExt** wurde für die Aktualisierung/Löschung von Daten optimiert. Zum Einfügen verwenden Sie **xtk.session.ingest**. Das Einfügen funktioniert auch dann, wenn der Datensatz-Schlüssel nicht in der Staging-Tabelle enthalten ist.

### Einfügen/Aktualisieren

**In einem Workflow**

Verwenden Sie den folgenden Code in einer **JavaScript-Code**-Aktivität, um Daten in der Cloud-Datenbank zu aktualisieren:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Nach Ausführung des Workflows wird die Staging-Tabelle erwartungsgemäß aktualisiert.

![](assets/updated-data.png)

**Von einem SOAP-Aufruf**

1. Fordern Sie den Authentifizierungs-Token an.
1. Lösen Sie die API aus. Die Payload ist:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. Die SOAP-Antwort lautet:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Als Ergebnis wird die Staging-Tabelle erwartungsgemäß aktualisiert.

## Abonnementverwaltung {#sub-apis}

Die Abonnementverwaltung in Campaign wird auf [dieser Seite](../start/subscriptions.md) beschrieben.

Die Eingabe von An- und Abmeldedaten beruht auf dem [Staging-Mechanismus](staging.md) in der lokalen Campaign-Datenbank. Abonnenteninformationen werden temporär in Staging-Tabellen in der lokalen Datenbank gespeichert. Der Synchronisations-Workflow sendet diese Daten aus der lokalen Datenbank an die Cloud-Datenbank. Aus diesem Grund sind die An- und Abmeldevorgänge **asynchron**. Opt-in- und Opt-out-Anfragen werden stündlich über einen bestimmten technischen Workflow verarbeitet. [Weitere Informationen](replication.md#tech-wf)


**Verwandte Themen**

* [Campaign Classic v7 JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=de){target=&quot;_blank&quot;}

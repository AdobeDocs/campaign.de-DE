---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 46%
---
# decryptPassword

> Warnung:
>
> Diese Dokumentation wurde aktualisiert. Weitere Informationen finden Sie auf dieser [Seite](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript).

Entschlüsselt ein in einem externen Konto gespeichertes Passwort.

```text
decryptPassword (str)
```

## Parameter

**str** Die verschlüsselte Zeichenfolge.

## Rückgabewert

Gibt das Kennwort im Nur-Text-Format zurück.

## Bemerkungen

Diese Funktion kann nicht in Workflows, Web-Anwendungen, Berichten oder Sendungen aufgerufen werden, aber in JSSP- oder SOAP-Aufrufimplementierungen. Beispiel:

```javascript
          function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
          var cnx = null, sessionService = null;
          try
              {
                  var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
                  sessionService = new SoapService(cnx, 'xtk:session');
                  sessionService.addMethod("Logon", "xtk:session#Logon",
                      ["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
                      ["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
                  return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
              }
          catch( e ) {
          logError(e);
          }
          finally {
          if( sessionService ) sessionService.dispose();
          if( cnx ) cnx.dispose();
          }
          })
      
```

## Funktionen

**Verfügbar in:**

* SOAP-Methoden

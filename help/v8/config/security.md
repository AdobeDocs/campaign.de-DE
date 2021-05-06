---
solution: Campaign Classic
product: campaign
title: Best Practices für die Sicherheit von Kampagnen
description: Erste Schritte mit Best Practices zur Kampagne
translation-type: tm+mt
source-git-commit: aad5f67453079211b14e371da09e9dfc757acba9
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 34%

---

# Best Practices für die Sicherheit von Kampagnen {#ac-security}

In der Adobe nehmen wir die Sicherheit Ihrer digitalen Erfahrung sehr ernst. Sicherheitspraktiken sind tief in unsere internen Softwareentwicklungs- und -betriebsprozesse und -werkzeuge eingebunden und werden von unseren funktionsübergreifenden Teams rigoros befolgt, um Zwischenfälle auf angemessene Weise zu verhindern, zu erkennen und zu reagieren.

Darüber hinaus hilft uns unsere Zusammenarbeit mit Partnern, führenden Forschern, Sicherheitsforschungsinstituten und anderen Branchenverbänden dabei, mit den neuesten Bedrohungen und Schwachstellen Schritt zu halten und regelmäßig fortschrittliche Sicherheitstechniken in unsere Angebote und Dienstleistungen zu integrieren.

## Datenschutz

Die Datenschutzkonfiguration und entsprechende Härtungsmaßnahmen sind zentrale Bestandteile der Optimierung der Sicherheit. Im Folgenden finden Sie einige Best Practices zum Schutz der Privatsphäre:

* Protect Sie Ihre persönlichen Daten (PI) mit HTTPS anstelle von HTTP
* Verwenden Sie [PI-Ansicht-Einschränkung](../dev/restrict-pi-view.md), um den Datenschutz zu schützen und zu verhindern, dass Daten missbräuchlich verwendet werden
* Stellen Sie sicher, dass der Zugriff auf verschlüsselte Passwörter beschränkt ist
* Schützen Sie Seiten, die möglicherweise personenbezogene Daten enthalten (z. B. Mirrorseiten, Webanwendungen usw.).

:language_ballon: Als Managed Cloud Services-Benutzer arbeitet Adobe mit Ihnen zusammen, um diese Konfigurationen auf Ihrer Umgebung zu implementieren.

## Personalisierung            

Wenn Sie personalisierte Links zu Ihrem Inhalt hinzufügen, achten Sie darauf, dass im Hostname-Teil der URL keine Personalisierung vorhanden ist. So lassen sich potenzielle Sicherheitslücken verhindern. Die folgenden Beispiele sollten niemals in allen URL-Attributen &lt;`a href="">` oder `<img src="">` verwendet werden:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Dateneinschränkung

Sie müssen sicherstellen, dass keine authentifizierten Benutzer mit unzureichender Berechtigung auf die verschlüsselten Passwörter zugreifen können. Dazu gibt es zwei Möglichkeiten: den Zugriff auf Kennwortfelder oder die gesamte Entität einschränken (Erstellen >= 8770 erforderlich).

Mit dieser Einschränkung können Sie Passwortfelder entfernen, das externe Konto jedoch für alle Benutzer über die Benutzeroberfläche zugänglich machen. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/restrict-pi-view.md).

1. Gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Konfigurieren]** > **[!UICONTROL Datenschemata]**.

1. Erstellen Sie eine neue **[!UICONTROL Schemaerweiterung]**.

1. Wählen Sie **[!UICONTROL Externes Konto]** aus (extAccount).

1. Im letzten Bildschirm können Sie Ihr neues srcSchema bearbeiten, um den Zugriff auf alle Kennwortfelder einzuschränken:

   Sie können das Hauptelement (`<element name="extAccount" ... >`) wie folgt ersetzen:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   So kann Ihr erweitertes srcSchema aussehen:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >Sie können `$(loginId) = 0 or $(login) = 'admin'` durch `hasNamedRight('admin')` ersetzen, damit alle Benutzer mit Admin-Recht diese Kennwörter sehen können.


## Zugriffsverwaltung

Zugriffsverwaltung ist ein wichtiger Teil der Sicherheitshärtung. Im Folgenden finden Sie einige der wichtigsten Best Practices:

* Erstellen Sie eine ausreichende Anzahl von Sicherheitsgruppen.
* Stellen Sie sicher, dass jeder Benutzer über geeignete Zugriffsberechtigungen verfügt.
* Vermeiden Sie möglichst die Vergabe der Administrator-Funktion, und achten Sie darauf, dass sich nicht zu viele Benutzer in der Administrator-Gruppe befinden.

:arrow_upper_right: Weitere Informationen finden Sie in der [Adobe Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)

## Leitlinien für die Kodierung

Beachten Sie bei der Entwicklung in Adobe Campaign (Workflows, Javascript, JSSP usw.) immer folgende Richtlinien:

* Skripterstellung: Vermeiden Sie SQL-Anweisungen, verwenden Sie parametrierte Funktionen anstelle von String-Konkatenation, und vermeiden Sie SQL-Injection, indem Sie die zu verwendenden SQL-Funktionen auf die Zulassungsliste setzen.

* Sichern Sie das Datenmodell: Verwenden Sie Spezifische Berechtigungen, um Operatoraktionen zu begrenzen, Systemkomponenten hinzuzufügen (sysFilter).

* hinzufügen captchas in Webanwendungen: fügen Sie captchas in Ihren öffentlichen Landingpages und Abonnement-Seiten hinzu.

:arrow_upper_right: Weitere Informationen finden Sie in der [Adobe Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)

---
solution: Campaign v8
product: Adobe Campaign
title: Best Practices für die Sicherheit von Campaign
description: Erste Schritte mit Best Practices für die Sicherheit von Campaign
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 31%

---

# Best Practices für die Sicherheit von Campaign {#ac-security}

Bei der Adobe nehmen wir die Sicherheit Ihres digitalen Erlebnisses sehr ernst. Sicherheitspraktiken sind tief in unsere internen Softwareentwicklungs- und Betriebsprozesse und -werkzeuge eingebunden und werden von unseren funktionsübergreifenden Teams streng befolgt, um Vorfälle auf angemessene Weise zu verhindern, zu erkennen und darauf zu reagieren.

Darüber hinaus hilft uns unsere Zusammenarbeit mit Partnern, führenden Forschern, Sicherheitsforschungsinstitutionen und anderen Branchenverbänden dabei, über die neuesten Bedrohungen und Schwachstellen auf dem Laufenden zu bleiben und regelmäßig erweiterte Sicherheitstechniken in unsere Produkte und Dienstleistungen zu integrieren.

## Datenschutz

Die Datenschutzkonfiguration und entsprechende Härtungsmaßnahmen sind zentrale Bestandteile der Optimierung der Sicherheit. Im Folgenden finden Sie einige Best Practices bezüglich des Datenschutzes:

* Protect Ihrer personenbezogenen Kundendaten (PIs) mithilfe von HTTPS anstelle von HTTP
* Verwenden Sie [PI-Anzeigebeschränkung](../dev/restrict-pi-view.md), um den Datenschutz zu schützen und zu verhindern, dass Daten missbraucht werden
* Stellen Sie sicher, dass der Zugriff auf verschlüsselte Passwörter beschränkt ist
* Schützen Sie Seiten, die möglicherweise personenbezogene Daten enthalten (z. B. Mirrorseiten, Webanwendungen usw.).

:Sprache_Ballon: Als Benutzer von Managed Cloud Services arbeitet Adobe mit Ihnen zusammen, um diese Konfigurationen in Ihre Umgebung zu implementieren.

## Personalisierung            

Wenn Sie personalisierte Links zu Ihrem Inhalt hinzufügen, achten Sie darauf, dass im Hostname-Teil der URL keine Personalisierung vorhanden ist. So lassen sich potenzielle Sicherheitslücken verhindern. Die folgenden Beispiele sollten niemals in allen URL-Attributen &lt;`a href="">` oder `<img src="">` verwendet werden:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Dateneinschränkung

Sie müssen sicherstellen, dass keine authentifizierten Benutzer mit unzureichender Berechtigung auf die verschlüsselten Passwörter zugreifen können. Dazu gibt es zwei Möglichkeiten: den Zugriff auf Kennwortfelder oder auf die gesamte Entität beschränken.

Mit dieser Einschränkung können Sie Passwortfelder entfernen, aber das externe Konto bleibt für alle Benutzer über die Benutzeroberfläche zugänglich. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/restrict-pi-view.md).

1. Gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Konfigurieren]** > **[!UICONTROL Datenschemata]**.

1. Erstellen Sie eine neue **[!UICONTROL Schemaerweiterung]**.

1. Wählen Sie **[!UICONTROL Externes Konto]** aus (extAccount).

1. Im letzten Bildschirm können Sie Ihr neues srcSchema bearbeiten, um den Zugriff auf alle Kennwortfelder zu beschränken:

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

   So kann Ihr erweitertes srcSchema wie folgt aussehen:

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
   >Sie können `$(loginId) = 0 or $(login) = 'admin'` durch `hasNamedRight('admin')` ersetzen, damit alle Benutzer mit Administratorrechten diese Kennwörter sehen können.


## Zugriffsverwaltung

Zugriffsverwaltung ist ein wichtiger Teil der Sicherheitshärtung. Im Folgenden finden Sie einige der wichtigsten Best Practices:

* Erstellen Sie eine ausreichende Anzahl von Sicherheitsgruppen.
* Stellen Sie sicher, dass jeder Benutzer über geeignete Zugriffsberechtigungen verfügt.
* Vermeiden Sie möglichst die Vergabe der Administrator-Funktion, und achten Sie darauf, dass sich nicht zu viele Benutzer in der Administrator-Gruppe befinden.

:[!DNL :arrow_upper_right:]: Weitere Informationen finden Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)

## Kodierungsrichtlinien

Beachten Sie bei der Entwicklung in Adobe Campaign (Workflows, JavaScript, JSSP usw.) immer die folgenden Richtlinien:

* **Skripterstellung**: Vermeiden Sie SQL-Anweisungen, verwenden Sie parametrierte Funktionen anstelle von String-Konkatenation, und vermeiden Sie SQL-Injection, indem Sie die zu verwendenden SQL-Funktionen auf die Zulassungsliste setzen.

* **Sichern Sie das Datenmodell**: Verwenden Sie spezifische Berechtigungen, um Benutzeraktionen zu begrenzen, und fügen Sie Systemfilter hinzu (sysFilter).

* **Hinzufügen von Captchas in Webanwendungen**: Fügen Sie Captchas auf Ihren öffentlichen Landingpages und Anmeldeseiten hinzu.

:[!DNL :arrow_upper_right:]: Weitere Informationen finden Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)

---
title: Versionshinweise zu Campaign v8 2021
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2021
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '1592'
ht-degree: 98%

---

# Versionshinweise für 2021{#2021-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen aufgelistet, die mit **Campaign v8-Versionen 2021**.

## Version 8.2.8 {#release-8-2-8}

_Donnerstag, 28. Oktober 2021_

<table>
<thead>
<tr>
<th><strong>Eingehende Interaktionen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die Interaktionsverwaltung in Echtzeit ist jetzt für eingehende Kanäle verfügbar. Verwenden Sie das Modul "Inbound Interaction" in Campaign, um Ihren Kunden das beste Angebot zu unterbreiten, wenn sie Ihre Website besuchen oder sich an Ihr Callcenter wenden. Diese Funktion ist im Lieferumfang von Campaign v8 enthalten und erfordert eine spezifische Konfiguration für Ihre Instanz. Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um Zugriff auf das Modul "Inbound Interaction" zu erhalten.</p>
<p>Weitere Informationen finden Sie in der <a href="../interaction/interaction-architecture.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Kampagnenoptimierung</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Das Modul "Kampagnenoptimierung" ist jetzt verfügbar. Mit diesem Modul können Sie den Versand von Nachrichten steuern, filtern und überwachen. Um Konflikte zwischen Kampagnen zu vermeiden, kann Adobe Campaign verschiedene Kombinationen durch Anwendung spezifischer Beschränkungsregeln testen. Auf diese Weise werden ein ideal auf Kundenbedürfnisse abgestimmter Nachrichtenversand sowie eine kohärente Unternehmenskommunikation sichergestellt.</p>
<p>Weitere Informationen finden Sie in der <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=de#campaign-optimization">entsprechenden Dokumentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service ist eine neue Komponente von Cloud Database Manager. Sie hilft Benutzern, die Integrität von Einschränkungen eindeutiger Schlüssel in Cloud-Datenbanktabellen zu wahren und zu überwachen. Dies hilft Ihnen zu verhindern, dass doppelte Schlüssel eingefügt werden.
<p>Da in der Cloud-Datenbank keine Einschränkungen hinsichtlich der Einheitlichkeit erzwungen werden, führt Unicity Service auf Anwendungsebene Folgendes ein: <b>eine Reihe neuer Limits</b>, um das Risiko von Duplikaten bei der Datenverwaltung mit Adobe Campaign zu verringern.</p> 
<p>Unicity Service startet einen neuen integrierten Workflow namens <b>ffdaUnicity</b>, durch den die Einheitlichkeitsbeschränkungen überwacht werden und ein Warnhinweis ausgegeben wird, wenn Duplikate erkannt werden.</p>
<p>Weitere Informationen finden Sie im <a href="../architecture/keys.md">entsprechenden Handbuch</a>.</p>
</td> </tr> 
</tbody> 
</table>


**Verbesserungen**

* Der Snowflake-Connector wurde hinsichtlich der Leistung verbessert.
* Zu Überwachungs- und Testzwecken enthalten die Prüfprotokolle des Workflows **[!UICONTROL Replizieren von Staging-Daten]** jetzt die Anzahl der Datensätze, die an die FFDA-Datenbank (Full Federated Data Access) gesendet wurden.
* Die SQL-Code-Aktivität ermöglicht jetzt die Auswahl der Datenbank, in der das SQL-Skript gespeichert wird: die Standarddatenquelle oder ein ausgewähltes aktives externes FDA-Konto.
* Eine Reihe vordefinierter Warehouses ist jetzt verfügbar und kann verwendet werden, um verschiedene Abfragen parallel auszuführen, wie Segmentierung, ETL oder Spitzen. [Weitere Informationen](../config/workflows.md)

**Sonstige Änderungen**

* Das Feld **[!UICONTROL Verschlüsselte Kennung]** wurde zum Besucherschema hinzugefügt (`nms:visitor`). Dieses Feld wird berechnet und ist für Web-Programme vorgesehen.
* Es wurde ein Problem behoben, das dazu führte, dass die Versandanalyse fehlschlug, wenn einige IP-Affinitäten in einigen Mid-Sourcing-Containern vorhanden waren, aber nicht in allen. Jetzt werden alle IP-Affinitäten in der Datenbank gespeichert, sodass jeder Container auf die Affinitäten zugreifen kann, die in allen anderen Containern vorhanden sind. (NEO-37564)
* Sie können jetzt ein Paket mit mehreren Schemata und Navigationsbaum-Knoten importieren.

**Patches**

* Nachdem ein Benutzer in einem Datenschema das `<autoStg>`-Attribut aus einem Tabellendefinitionselement entfernt hatte oder dessen Wert von `true` in `false` geändert wurde, wurde die zugehörige Staging-Tabelle nicht gelöscht. Dieses Problem wurde behoben.
* Es wurde ein Problem behoben, das bei der Erstellung von Datensätzen mit einem speziellen Formular aufgrund der ID-Verwaltung mit einer FFDA-Datenquelle einen Fehler verursachte.
* Es wurde ein Problem behoben, das das Einfügen von Angeboten in einen Versand verhindern konnte, wenn die Angebote durch eine Anreicherungsaktivität in einem Workflow verwaltet wurden.
* Es wurde ein Problem behoben, das den Import von Packages verlangsamen konnte.
* Es wurde ein Problem behoben, das verhindern konnte, dass E-Mail-Sendungen an Testadressen durchgeführt wurden.
* Es wurde ein Problem behoben, das verhindern konnte, dass Vorschläge in der Tabelle mit den Angebotsvorschlägen gespeichert wurden.
* Es wurde ein Fehler behoben, der dazu führte, dass Probleme mit Netzwerküberschreitungen fälschlicherweise als Skriptunterbrechungsprobleme anstatt als Netzwerkfehler protokolliert wurden. Dieses Problem trat bei HTTP-Anfragen auf, die in JavaScript-Aktivitäten enthalten waren.
* Es wurde ein Problem behoben, durch das Angebote nicht in die Live-Angebotsumgebung auf Snowflake repliziert werden konnten.
* Es wurde ein Problem behoben, durch das das Attribut &quot;autoStg&quot; für nicht erweiterte integrierte Schemata ignoriert wurde.
* Es wurde ein Problem behoben, das verhinderte, dass Benutzer bei der Vorschau eines Profils den Link **[!UICONTROL Land/Region]** auswählen konnten.
* Es wurde ein Fehler behoben, der dazu führte, dass die Datumsauswahl in benutzerdefinierten Berichten zu einem Skriptfehler führte. (NEO-36345)
* Es wurde ein Problem behoben, das zum Absturz des Systems führte, wenn die Konfiguration im Falle von fehlerhaften Konfigurationsdateien neu generiert wurde.
* Es wurde ein Problem behoben, das verhinderte, dass die Marketing- und Kontrollinstanzen erfolgreich aktualisiert werden konnten.
* Es wurde ein Problem behoben, das zum Absturz des Abrechnungs-Workflows bei Marketing-Instanzen führen konnte.
* Es wurde ein Problem behoben, das zu doppelten Schlüsseln in nativen FFDA-Snowflake-Tabellen führen konnte. (NEO-38583)
* Es wurde ein Problem behoben, das dazu führen konnte, dass temporäre Workflow-Schemata verloren gingen, wenn zwei Deduplizierungsaktivitäten nacheinander bearbeitet wurden. (NEO-34063)
* Es wurde ein Problem behoben, durch das beim Ausführen der HoursDiff- und MinutesDiff-Funktionen von Amazon Redshift beim Versuch, die Zeitkomponente zu extrahieren, falsche Ergebnisse ausgegeben wurden.(NEO-31673)
* Es wurde ein Problem behoben, das dazu führen konnte, dass sich Benutzer aufgrund eines Proxy-Konfigurationsproblems nicht an der Konsole anmelden konnten. (NEO-38388)
* Es wurde ein Regressionsproblem behoben, das dazu führte, dass die Funktion **Ordner bereinigen** nicht ordnungsgemäß funktionierte. (NEO-37459)
* Es wurde ein Problem behoben, das dazu führen konnte, dass die Vorschau von Mobile-Sendungen, die mit einem Workflow verbunden waren, nicht angezeigt wurde.
* Es wurde ein Problem behoben, das dazu führen konnte, dass die Workflow-Aktivität **Liste lesen** nicht funktionierte, wenn die Liste in der Datenbank mit einer negativen ID identifiziert wurde. (NEO-39607)

## Version 8.1.20 {#release-8-1-20}

_Dienstag, 7. September 2021_

**Verbesserungen bei der Sicherheit**

* Es wurde ein Sicherheitsproblem behoben, um den Schutz vor Directory Traversal-Angriffen zu verbessern. (NEO-28547)

**Verbesserungen**

* Nach seinem End-of-Life wurde Flash aus allen damit verbundenen Campaign-Funktionen und -Komponenten entfernt und durch HTML5 ersetzt. Der Diagrammtyp **Tacho** wurde entfernt. (NEO-30330) [Mehr dazu](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=de)
* Bei der Installation der Client-Konsole unter Windows überprüft das Installationsprogramm jetzt, ob ein übergeordneter Registrierungsknoten vorhanden ist, und erstellt einen, wenn er fehlt. Dadurch werden potenzielle Probleme beim Starten der Konsole verhindert. (NEO-34854)
* Die Tracking-Signatur-Funktion wurde verbessert, um Fehler zu verhindern, die in Zusammenhang mit der Art und Weise stehen, in der Drittanbieter-Tools (E-Mail-Clients, Internet-Browser usw.) Sonderzeichen verarbeiten. URL-Parameter sind jetzt codiert.

**Sonstige Änderungen**

* Veraltete Microsoft CRM-Connectoren (Office 365- und On-Premise-Implementierungen) wurden aus der Benutzeroberfläche entfernt. [Mehr dazu](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=de#configure-acc-for-microsoft)
* Nach der Migration zu Tomcat 8 wurde das IIS-Setup-Skript aktualisiert, um Probleme mit der IIS-Integration zu beheben. (NEO-31019)
* Es wurde ein Schutzmechanismus hinzugefügt, mit dem nur der [technische Workflow &quot;Abrechnung&quot;](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=de#billing-report) auf der Marketing-Instanz ausgeführt werden kann.
* In den Daten- und Schema-Tabs des Fensters **Population ansehen** der Workflow-Transitionen wurde die Identifizierung der Datenquelle verbessert.
* Fehlende Datenbankindizes wurden den folgenden Schemata hinzugefügt, um Probleme bei der Datenbankaktualisierung zu vermeiden: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Korrekturen**

* Fehlerkorrektur – Der Bericht **Klickposition** funktioniert jetzt, wenn Angebote mit dem Versand verknüpft sind. (NEO-26295)
* Fehlerkorrektur – Die Aktivität **Unter-Workflow** erzeugt bei ihrer Ausführung jetzt zuverlässig eine Ausgabetabelle. (NEO-36242)
* Das Exportieren des Berichts **Deskriptive Analyse** in PDF funktioniert jetzt problemlos. (NEO-25847)
* Fehlerkorrektur – Sendungen können jetzt problemlos über einen externen E-Mail-Versand durchgeführt werden. (NEO-37435)
* Fehlerkorrektur – Die Verbindung mit Microsoft CRM über die Web-API funktioniert jetzt fehlerfrei. Die Fehlermeldung wurde entfernt, da keine Funktionen betroffen waren.
* Fehlerkorrektur – Wenn der Mid-Server als Relais zwischen Tracking- und Marketing-Servern festgelegt wird, funktioniert die Trackinglog-Deduplizierung jetzt problemlos. (NEO-36285)
* Fehlerkorrektur – Bei einer Regression kann Vault als spezifischer Code-Store verwendet werden.
* Fehlerkorrektur – In der Workflow-Aktivität **Anreicherung** können jetzt Variablen verwendet werden, wenn die eingehende Transition aus einer FDA-Datenquelle stammt.
* Fehlerkorrektur – Die ordnungsgemäße Replikation von Benutzergruppen und Berechtigungen wird nicht mehr durch ein Problem mit FFDA verhindert.
* Fehlerkorrektur – Jetzt wird kein falscher Abmelde-Link mehr über den Versand gesendet.
* Fehlerkorrektur – Die Replikationsverwaltung wirkt sich jetzt nicht mehr auf die Dauer des Postupgrades aus.
* Fehlerkorrektur – Die **Klickposition** wird jetzt angezeigt.
* Fehlerkorrektur – URLs in E-Mail-Nachrichten werden jetzt fehlerfrei angezeigt.

## Version 8.1.14 {#release-8-1-14}

_Freitag, 23. Juli 2021_

**Neue Funktionen**

<table>
<thead>
<tr>
<th><strong>Neue Workflow-Aktivität: Datenquelle ändern</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit der neuen Workflow-Aktivität <b>Datenquelle ändern</b> können Sie die Datenquelle der Arbeitstabelle eines Workflows ändern. Dies bietet eine höhere Flexibilität bei der Verwaltung von Daten in verschiedenen Datenquellen (FDA, FFDA und lokale Datenbanken).</p>
<p>In Adobe Campaign-Workflows werden Daten mithilfe von Arbeits- (oder temporären) Tabellen verwaltet. Während der Workflow-Ausführung geben Arbeitstabellen Daten für Workflow-Aktivitäten frei. Standardmäßig werden die Arbeitstabellen auf derselben Datenbank erstellt wie die Quelle der Daten, die abgefragt werden.</p>
<p>In Campaign v8 wird die wichtigste Profiltabelle direkt in der Cloud-Datenbank gespeichert. Wenn Sie also die Profiltabelle abfragen, wird auch eine Arbeitstabelle in der Cloud-Datenbank erstellt. In bestimmten Fällen kann es sinnvoll sein, die Arbeitstabelle in eine andere Datenquelle zu verschieben, um bestimmte Vorgänge auszuführen.</p>
<p>Weitere Informationen finden Sie im <a href="../config/workflows.md#change-data-source-activity">entsprechenden Handbuch</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Verfügbarkeit des LINE-Kanals</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Der <a href="../send/line.md">LINE-Kanal</a> ist jetzt in Campaign v8 verfügbar, einschließlich der folgenden Verbesserungen in Kombination mit dem Modul <a href="../send/transactional.md">Transaktionsnachrichten</a>:
<ul> 
<li><p>Fehlerkorrektur – Jetzt können Besucher in einem LINE-Versand als Ziel ausgewählt werden. 
</p></li>
<li><p>Fehlerkorrektur – Beim Abrufen von Besuchern aus der Ausführungsinstanz und deren Übertragung in die Marketing-Instanz treten jetzt keine Fehler mehr auf.
</p></li>
<li><p>Fehlerkorrektur – Echtzeit-Ereignisse werden jetzt korrekt verarbeitet.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**Sonstige Verbesserungen**

* Fehlerkorrektur – Der **Klicks**-Bericht wird jetzt für alle Sendungen zuverlässig angezeigt.
* Fehlerkorrektur – Bei der Workflow-Aktivität **Deduplizierung** tritt jetzt kein Fehler mehr auf, der zu ungenauer Duplikatzählung führt.
* Fehlerkorrektur – Bei der Verwendung einer Workflow-Abfrage mit dem Filter &quot;ID ist nicht leer&quot; wird in der Population einer Transition kein leeres Element mehr angezeigt.
* Fehlerkorrektur – In einem neuen Zielgruppen-Mapping können jetzt zusätzliche Felder erstellt werden.

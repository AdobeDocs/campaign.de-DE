---
product: Adobe Campaign
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5b81c8e9e391ea1a9ad1825e5102b66c7926c204
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 43%

---

# Aktuelle Version{#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **aktuellen Campaign v8-Version** aufgelistet.

## Version 8.1.20 {#release-8-1-20}

_7. September 2021_

**Verbesserungen bei der Sicherheit**

* Fehlerkorrektur - Es wurde ein Sicherheitsproblem behoben, um den Schutz vor Directory Traversal-Angriffen zu verbessern. (NEO-28547)

**Verbesserungen**

* Nach seinem Ende wurde Flash aus allen damit verbundenen Campaign-Funktionen und -Komponenten entfernt und durch HTML5 ersetzt. Der Diagrammtyp **Grafik** wurde entfernt. (NEO-30330) [mehr dazu](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* Bei der Installation der Clientkonsole unter Windows überprüft das Installationsprogramm jetzt, ob ein übergeordneter Registrierungsknoten vorhanden ist, und erstellt einen, wenn er fehlt. Dadurch werden potenzielle Probleme beim Starten der Konsole verhindert. (NEO-34854)
* Die Tracking-Signaturfunktion wurde verbessert, um Fehler zu verhindern, die in Zusammenhang mit der Art und Weise stehen, in der Drittanbieter-Tools (E-Mail-Clients, Internet-Browser usw.) Sonderzeichen verarbeiten. URL-Parameter sind jetzt kodiert.

**Sonstige Änderungen**

* Zuvor veraltete Microsoft CRM-Connectoren (Office 365- und On-Premise-Bereitstellungen) wurden aus der Benutzeroberfläche entfernt. [Mehr dazu](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* Nach der Migration zu Tomcat 8 wurde das IIS-Setup-Skript aktualisiert, um Probleme mit der IIS-Integration zu beheben. (NEO-31019)
* Es wurde ein Schutzmechanismus hinzugefügt, mit dem nur der technische Workflow [Rechnungsstellung](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report) auf der Marketing-Instanz ausgeführt werden kann -
* Die Identifizierung der Datenquelle wurde in den Daten- und Schema-Tabs des Fensters **Population anzeigen** der Workflow-Transitionen verbessert.
* Fehlende Datenbankindizes wurden den folgenden Schemas hinzugefügt, um Probleme bei der Datenbankaktualisierung zu vermeiden: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Korrekturen**

* Fehlerkorrektur - Der Bericht **Klicks** funktioniert jetzt, wenn Angebote mit dem Versand verknüpft sind. (NEO-26295)
* Fehlerkorrektur - Bei der Aktivität **Unter-Workflow** tritt jetzt kein Fehler mehr auf, wenn bei ihrer Ausführung keine Ausgabetabelle generiert wurde. (NEO-36242)
* Verschiedene Probleme beim Exportieren des Berichts **Deskriptive Analyse** in PDF wurden behoben. (NEO-25847)
* Fehlerkorrektur - Sendungen können jetzt problemlos durchgeführt werden, wenn ein externer E-Mail-Versand verwendet wird. (NEO-37435)
* Fehlerkorrektur - bei der Verbindung mit Microsoft CRM über die Web-API tritt kein Fehler mehr auf. Die Fehlermeldung wurde entfernt, da die Funktionen nicht betroffen waren.
* Fehlerkorrektur - Es wurde ein Problem mit der Trackinglog-Deduplizierung behoben, das auftrat, wenn der Mid-Server als Relais zwischen Tracking- und Marketing-Servern festgelegt wurde. (NEO-36285)
* Korrektur einer Regression, die dazu führte, dass Vault nicht als spezifischer Code-Store verwendet werden konnte.
* Fehlerkorrektur - Variablen können jetzt in einer Workflow-Aktivität vom Typ **Anreicherung** verwendet werden, wenn die eingehende Transition aus einer FDA-Datenquelle stammt.
* Es wurde ein Problem mit FFDA behoben, das die ordnungsgemäße Replikation von Benutzergruppen und Rechten verhinderte.
* Fehlerkorrektur - jetzt wird kein falscher Abmelde-Link mehr über den Versand gesendet.
* Fehlerkorrektur - Die Replikationsverwaltung wirkt sich jetzt nicht mehr auf die Dauer des Postupgrades aus.
* Fehlerkorrektur - **Klickposition** wird jetzt angezeigt.
* Fehlerkorrektur - URLs in E-Mail-Nachrichten werden jetzt nicht mehr beschädigt.

## Version 8.1.14 {#release-8-1-14}

_23. Juli 2021_

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

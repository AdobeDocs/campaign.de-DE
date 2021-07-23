---
product: Adobe Campaign
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Übersicht
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5d266b22661be2817e06ea71c1b0bec7f44a152d
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%

---

# Aktuelle Version{#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen aufgelistet, die mit der **aktuellen Campaign v8-Version** bereitgestellt werden.

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
<p>Mit der neuen Workflow-Aktivität <b>Datenquelle ändern</b> können Sie die Datenquelle der Arbeitstabelle eines Workflows ändern. Dies bietet eine höhere Flexibilität bei der Verwaltung von Daten über verschiedene Datenquellen (FDA, FFDA und lokale Datenbank) hinweg.</p>
<p>In Adobe Campaign-Workflows werden Daten mithilfe von funktionierenden (oder temporären) Tabellen verwaltet. Während der Workflow-Ausführung teilen Arbeitstabellen Daten über Workflow-Aktivitäten hinweg. Standardmäßig werden Arbeitstabellen in derselben Datenbank erstellt, in der auch die Quelle der Daten enthalten ist, die wir abfragen.</p>
<p>Mit Campaign v8 wird die Tabelle der Hauptprofile direkt in der Cloud-Datenbank gespeichert. Wenn Sie also die Tabelle Profile abfragen, wird auch eine Arbeitstabelle für die Cloud-Datenbank erstellt. In bestimmten Fällen kann es sinnvoll sein, die Arbeitstabelle in eine andere Datenquelle zu verschieben, um bestimmte Vorgänge auszuführen.</p>
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
<td> <p>Der LINE-Kanal ist jetzt in Campaign v8 verfügbar. Bei der Verwendung von LINE mit Message Center wurden folgende Verbesserungen vorgenommen:
</p>
<ul> 
<li><p>Fehlerkorrektur - Besucher können jetzt in einem LINE-Versand als Ziel ausgewählt werden. 
</p></li>
<li><p>Fehlerkorrektur - Beim Abrufen von Besuchern aus der Ausführungsinstanz zur Marketing-Instanz treten jetzt keine Fehler mehr auf.
</p></li>
<li><p>Fehlerkorrektur - Es wurden Probleme bei der Verarbeitung von Echtzeit-Ereignissen im Kontext von LINE-Sendungen mit Message Center behoben.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Sonstige Verbesserungen**

* Fehlerkorrektur - Der Bericht **Klicks** wird jetzt für bestimmte Sendungen angezeigt.
* Fehlerkorrektur - Bei der Workflow-Aktivität **Deduplizierung** tritt jetzt kein Fehler mehr auf, der zu ungenauer Duplikatzählung führen konnte.
* Fehlerkorrektur - Bei der Verwendung einer Workflow-Abfrage mit dem Filter &quot;ID ist nicht leer&quot; wird in der Transitionspopulation kein leeres Element mehr angezeigt.
* Fehlerkorrektur - in einem neuen Zielgruppen-Mapping können jetzt zusätzliche Felder erstellt werden.

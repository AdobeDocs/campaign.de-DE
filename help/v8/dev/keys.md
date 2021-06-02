---
product: Adobe Campaign
title: 'Schlüsselverwaltung in Campaign '
description: Erste Schritte mit der Schlüsselverwaltung
source-git-commit: 08c1f2fbe79845fe54670e25ac4a63ab65517513
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Schlüsselverwaltung und Einheitlichkeit {#key-management}

In Campaign v8 ist der Primärschlüssel eine Universally Unique IDentifier (UUID), eine Zeichenfolge für Zeichen. Um diese UUID zu erstellen, muss das Hauptelement des Schemas die Attribute **autouid** und **autopk** enthalten, die auf **true** gesetzt sind.

Adobe campaign v8 wird mit Snowflake als Hauptdatenbank geliefert. Die verteilte Architektur der Snowflake-Datenbank bietet keine Mechanismen zur Verwaltung der Einheitlichkeit eines Schlüssels in einer Tabelle: Endbenutzer sind dafür verantwortlich, die Konsistenz der Schlüssel in der Adobe Campaign-Datenbank sicherzustellen.

Die Vermeidung von Duplikaten bei Schlüsseln, insbesondere bei Primärschlüsseln, ist zur Wahrung der relationalen Datenbankkonsistenz erforderlich. Duplikate bei Primärschlüsseln führen zu Problemen mit Workflow-Aktivitäten für die Datenverwaltung wie **Abfrage**, **Abstimmung**, **Daten-Update** und mehr.

Adobe Campaign bietet leistungsstarke Tools zur Datenverwaltung, mit denen die Daten abgestimmt werden können. Stellen Sie sicher, dass Sie Daten je nach ihrer Präsenz in der Datenbank einfügen oder aktualisieren (**Abstimmung**), und entfernen Sie Duplikate, bevor Sie Daten erfassen (**Deduplizierung**). Als Best Practice empfiehlt Adobe die Übernahme einer [Detect](#detect-duplicates)- und [Correct](#correct-duplicates)-Strategie im Rahmen Ihres gesamten Data-Management-Prozesses, falls duplizierte Schlüssel in die Datenbank geladen wurden.

## Duplikate erkennen{#detect-duplicates}

Campaign verfügt über eine neue Schutzfunktion, mit der während der Versandvorbereitung automatisch duplizierte UUIDs aus einer Audience entfernt werden. Dieser neue Mechanismus verhindert, dass bei der Versandvorbereitung Fehler auftreten.

Als Endbenutzer können Sie diese Informationen in den Versandlogs überprüfen: Manche Empfänger können wegen eines duplizierten Schlüssels aus der Hauptzielgruppe ausgeschlossen werden. In diesem Fall wird die folgende Warnung angezeigt: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

In diesem Fall können Sie einen Workflow erstellen, um die doppelten Schlüssel zu identifizieren. Sie können diese Schlüssel dann korrigieren. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie einen neuen Workflow.

   ![](assets/new-wf.png)

1. Fügen Sie die Aktivität **Abfrage** hinzu.
1. Wählen Sie die Tabelle **Empfänger** aus.

   ![](assets/add-query-on-rcp.png)

1. Fügen Sie die Aktivität **Deduplizierung** hinzu und deduplizieren Sie sie auf dem Primärschlüssel (UUID). Behalten Sie nur ein Duplikat bei und aktivieren Sie die Option **Komplement erzeugen** , um eine ausgehende Transition für die Duplikate zu erstellen.

   ![](assets/deduplicate.png)

1. Speichern Sie die Dubletten mithilfe der Aktivität Listen-Update in einer Liste.

   ![](assets/list-update.png)

Jetzt können Sie direkt aus der Liste auf die duplizierten Empfänger zugreifen. Selbst wenn die Transition nur eine der duplizierten Zeilen enthält, werden alle Duplikate in der Liste protokolliert.


## Richtige Duplikate{#correct-duplicates}

Zur Korrektur der Duplikate müssen die Kunden die Campaign-Daten aktualisieren. Die Art der Aktion ist eng an die Art der Duplikate und die Implementierung gebunden. Wir können uns mit mehreren Fällen auseinander setzen, die eine andere Schadensminderungsstrategie erfordern (Entfernen, Zusammenführen oder Aktualisieren).

>[!IMPORTANT]
>
>Duplizierte Primärschlüssel verhindern die Verwendung integrierter Workflow-Aktivitäten zur Auswahl oder Aktualisierung einer bestimmten Zeile. Aufgrund der duplizierten UUID schlägt die Deduplizierung der Daten fehl und kann sich auf Ihre Datenbankintegrität auswirken. Daher wird dringend empfohlen, Duplikate zu korrigieren.

Beispiel:

* **Fall 1**  - Duplizierte Empfänger mit derselben UUID und denselben Profilinformationen (E-Mail, Vorname usw.) : Die Empfänger sehen wie &quot;echte&quot; Duplikate aus, und die Abschwächung könnte darin bestehen, nur eines der Duplikate zu entfernen.
Ein anderer Ansatz könnte darin bestehen, Informationen eines Empfängers mit dem anderen zusammenzuführen.

* **Fall 2**  - Duplizierte Empfänger mit derselben UUID, aber unterschiedlichen Profilinformationen (unterschiedliche E-Mail-Adresse, Vorname usw.):
Diesmal scheint es verschiedene Profile zu geben, und Sie können beide in der Campaign-Datenbank beibehalten. Dies bedeutet, dass wir es vorziehen könnten, nur eines der Duplikate zu aktualisieren, das eine neue UUID generiert. [Weitere Informationen finden Sie in diesem Beispiel](#deduplicate-sample).

Je nach Schadensbegrenzungsstrategie können Sie die Liste jederzeit aus einem anderen Workflow abfragen und dann die Aktualisierung entsprechend Ihren Anforderungen durchführen. Weitere Anleitungen erhalten Sie bei der Adobe.

### Beispiel für die Deduplizierung{#deduplicate-sample}

Bei duplizierten Empfängern können Sie beide Datensätze in der Campaign-Datenbank beibehalten. In diesem Fall müssen Sie eine davon mit einer neuen UUID aktualisieren.

Um eine SQL-Update-Abfrage in der Cloud-Datenbank auszuführen, können Sie die Workflow-Aktivität **SQL Data Management** verwenden und die folgende SQL-Aktualisierung ausführen:

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Sobald die ausgewählte Zeile mit einer neuen UUID aktualisiert wurde, können Sie die aktualisierte Zeile in der Benutzeroberfläche überprüfen und feststellen, dass die UUID erwartungsgemäß aktualisiert wurde. Sie können Duplikate auch in der Datenbank erkennen, indem Sie den Workflow **Duplikate erkennen** [ausführen, wie hier](#detect-duplicates) beschrieben.

---
title: SMPP-Connector in Versandeigenschaften
description: Über die Einstellungen des SMPP-Connectors in Sendungen
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 6%

---


# Beschreibung des SMPP-Connectors {#smpp-connector-desc}

>[!IMPORTANT]
>
>Dies gilt für Adobe Campaign v8.7.2 und höher.
>
>Ältere Versionen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"} .

## Datenfluss des SMS-Connectors {#sms-data-flow}

In diesem Abschnitt wird beschrieben, wie der SMS-Prozess mit Daten umgeht.

Im Folgenden finden Sie ein allgemeines Blockdiagramm, in dem zusammengefasst wird, wie der SMS-Prozess mit seiner Umgebung interagiert.

![](assets/smsv2_highlevel.png){zoomable="yes"}

Der SMS-Prozess umfasst zwei wichtige Komponenten: den SMPP-Connector selbst, der die Kommunikation mit dem SMPP-Provider verarbeitet, und eine Hintergrundaufgabe für die SR-Abstimmung.

### Datenfluss für SMPP-Konten {#sms-data-flow-smpp-accounts}

Der SMS-Prozess fragt nms:extAccount ab und erzeugt neue Verbindungen in seinem SMPP-Connector, wobei die Einstellungen jedes Kontos weitergegeben werden. Die Abrufhäufigkeit kann in serverConf in der Einstellung *configRefreshMillis* angepasst werden.

Für jedes aktive SMPP-Konto versucht der SMPP-Connector, Verbindungen immer aktiv zu halten. Wenn die Verbindung verloren geht, wird eine erneute Verbindung hergestellt.

### Datenfluss beim Nachrichtenversand {#sms-data-flow-sending-msg}

* Der SMS-Prozess wählt aktive Sendungen durch Scannen von nms:delivery aus. Ein Versand ist aktiv, wenn:
   * Sein Status bedeutet, dass Nachrichten gesendet werden können
   * Der Gültigkeitszeitraum ist nicht abgelaufen
   * Es handelt sich um einen Versand (z. B. handelt es sich nicht um eine Vorlage, sondern um keinen Löschvorgang)
   * Der SMPP-Connector könnte mindestens eine Verbindung für das externe Konto öffnen, das mit dem Versand verknüpft ist.
* Für jeden Versand lädt der SMS-Prozess Versandteile. Wenn der Teil des Versands teilweise gesendet wurde, prüft der SMS-Prozess, welche Nachrichten bereits gesendet wurden, indem er das Broadlog überprüft.
* Der SMS-Prozess erweitert die Vorlage mit Personalisierungsdaten aus der Versandkomponente.
* Der SMPP-Connector generiert eine MT (SUBMIT_SM PDU), die dem Inhalt und anderen Einstellungen entspricht.
* Der SMPP-Connector sendet den MT über eine Transmitter- (oder Transceiver-) Verbindung.
* Der Provider gibt eine ID für diesen MT zurück. Sie wird in nms:providerMsgId eingefügt.
* Der SMS-Prozess aktualisiert das Broadlog auf den Versandstatus.
* Im Fall eines endgültigen Fehlers aktualisiert der SMS-Prozess das Broadlog entsprechend und kann eine neue Fehlerart in nms:broadLogMsg erstellen.

### Datenfluss beim Empfangen von SR {#sms-data-flow-sr}

* Der SMPP-Connector empfängt und dekodiert den SR (DELIVER_SM PDU). Es verwendet im externen Konto definierte Regexes, um die Nachrichten-ID und den Status zu erhalten.
* Nachrichten-ID und Status werden in nms:providerMsgStatus eingefügt
* Nach dem Einfügen antwortet der SMPP-Connector mit einer DELIVER_SM_RESP-PDU.
* Wenn während des Prozesses etwas schiefgelaufen ist, sendet der SMPP-Connector eine negative DELIVER_SM_RESP-PDU und protokolliert eine Nachricht.

### Datenfluss beim Erhalt eines MO {#sms-data-flow-mo}

* Der SMPP-Connector empfängt und dekodiert die MO (DELIVER_SM PDU).
* Der Suchbegriff wird aus der Nachricht extrahiert. Wenn es mit einem deklarierten Keyword übereinstimmt, werden die entsprechenden Aktionen ausgeführt. Es kann in nms:address geschrieben werden, um die Quarantäne zu aktualisieren.
* Wenn benutzerdefinierte TLV deklariert werden, werden sie entsprechend ihren jeweiligen Einstellungen dekodiert.
* Der vollständig dekodierte und verarbeitete MO wird in die Tabelle nms:inSms eingefügt.
* Der SMPP-Connector antwortet mit einer DELIVER_SM_RESP-PDU. Wenn ein Fehler erkannt wurde, wird ein Fehlercode an den Provider zurückgegeben.

### Datenfluss bei Abstimmung von MT und SR {#sms-reconciling-mt-sr}

* Die SR-Abstimmungskomponente liest regelmäßig nms:providerMsgId und nms:providerMsgStatus. Daten aus beiden Tabellen werden verbunden.
* Für alle Nachrichten, die in beiden Tabellen einen Eintrag enthalten, wird der entsprechende Eintrag nms:broadLog aktualisiert.
* Die nms:broadLogMsg -Tabelle kann im Prozess aktualisiert werden, wenn eine neue Fehlerart erkannt wird, oder um Zähler für Fehler zu aktualisieren, die nicht manuell qualifiziert wurden.

## Abgleichen von MT-, SR- und broadLog-Einträgen {#sms-matching-entries}

Im Folgenden finden Sie ein Diagramm, das den gesamten Prozess beschreibt:

![](assets/message_processing.png){zoomable="yes"}

**Phase 1**

* Die Nachricht wird gescannt, formatiert und dann an den SMPP-Connector übertragen.
* Der SMPP-Connector formatiert ihn als SUBMIT_SM MT PDU.
* Der MT wird an den SMPP-Provider gesendet.
* Der Provider antwortet mit SUBMIT_SM_RESP. SUBMIT_SM und SUBMIT_SM_RESP werden durch ihre Sequenznummer abgeglichen.
* SUBMIT_SM_RESP stellt eine ID bereit, die vom Provider stammt. Diese ID wird zusammen mit der breiten Protokollkennung in die Tabelle nms:providerMsgId eingefügt.

**Phase 2**

* Der Provider sendet eine DELIVER_SM SR PDU.
* Der SR wird analysiert, um Anbieter-ID, Status und Fehler-Code zu extrahieren. In diesem Schritt werden Extraktionsregexes verwendet.
* Die Anbieter-ID und der entsprechende Status werden in nms:providerMsgStatus eingefügt.
* Wenn alle Daten sicher in die Datenbank eingefügt werden, antwortet der SMPP-Connector mit DELIVER_SM_RESP. DELIVER_SM und DELIVER_SM_RESP werden durch ihre Sequenznummer abgeglichen.

**Phase 3**

* Die SR-Abstimmungskomponente des SMS-Prozesses scannt die Tabellen nms:providerMsgId und nms:providerMsgStatus regelmäßig.
* Wenn eine Zeile in beiden Tabellen über übereinstimmende Anbieter-IDs verfügt, werden die beiden Einträge zusammengefügt. Dadurch kann die Broadlog-ID (gespeichert in providerMsgId) mit dem Status (gespeichert in providerMsgStatus) abgeglichen werden.
* Das Broadlog wird mit dem entsprechenden Status aktualisiert.

## Affinitäten und der dedizierte Prozess-Connector {#sms-affinities}

Affinitäten werden vom dedizierten Prozess-Connector ignoriert, er wird nur innerhalb des SMS-Prozesses ausgeführt.

## serverConf-Optionen {#sms-serverconf-options}

Einige Einstellungen können in serverConf.xml angepasst werden. Wie alle anderen Einstellungen in dieser Datei sollte sie in der Datei config-instance.xml angegeben werden. Alle Einstellungen befinden sich im Element &lt; mta2 > .

Diese Tabelle fasst alle Einstellungen zusammen. Min./Max. sinnvolle Werte geben eine grobe Vorstellung von dem Bereich, den Sie in den meisten Fällen berücksichtigen sollten. Der Debugging-Wert ist der Wert, den Sie wählen müssen, wenn Sie versuchen, Probleme zu finden, die nicht mit der Leistung in Zusammenhang stehen.

| Einstellung | Beschreibung | Standard | Mindest-vernünftiger Wert | Maximaler sinnlicher Wert | Debugging-Wert |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | Größe der aktualisierten Mikrostapel | 5000 | 100: Sehr niedrige Latenz | maxWaitingMessages/updateThreads: Wenn Sie diesen Wert überschreiten, ist dies nicht nützlich, da maxWaitingMessages die Pufferung ohnehin beschränkt | 1: Deaktivieren Sie die Mikrobatching-Funktion, aktualisieren Sie die Nachrichten einzeln. |
| configRefreshMillis | Zeitraum für das Neuladen der Konfiguration in Millisekunden | 10000 | pollPeriodMillis: Geringe Latenz | 600000: Nicht zu schnell neu laden, um Ressourcen zu sparen | 500: Geringe Latenz ermöglicht schnelleres Ausprobieren neuer Einstellungen |
| deliveryPartRetryCount | Maximale Häufigkeit, mit der ein deliveryPart wiederholt oder verschoben wird. Vorsicht: Ein Neustart des Versandvorgangs zählt als Neuversuch, Abstürze können auch als Neuversuch gezählt werden. | 20 | 1: Weitere Zustellversuche deaktivieren | 50: Sorgen Sie dafür, dass Nachrichten persistenter sind, um instabile Provider zu umgehen. | 1: Deaktiviert Neuversuche. 1000: Vermeiden Sie das Flushing von fehlgeschlagenen Nachrichten. |
| deliveryPartRetryDelaySeconds | Mindestverzögerung, bevor ein Versandkontingent erneut versucht wird. Dies ist Prozess- und Container-übergreifend. Die Verzögerung wird in Sekunden angegeben. | 60 | 0: Sofortige erneute Versuche | 3600: Sehr langsame Wiederholungen (1 Stunde zwischen jedem erneuten Versuch) | 1: Erleichtert die Durchführung weiterer Versuche in den ausgelasteten Logs. |
| logOutput | Senden Sie Monitoring- und Profildaten in der Hauptprotokollausgabe. | true | false: Kann den Durchsatz etwas erhöhen. Entmutigt. | true: Aktivieren Sie die Protokollierung. | true |
| maxWaitingMessages | Maximale Anzahl an zu jedem Zeitpunkt verarbeiteten Nachrichten | 50000 | 256: Ausreichend für einen einzelnen VersandTeil | 200000: Begrenzt auf SQL-Abfragelänge (64 k) | 1: Nachrichten einzeln verarbeiten |
| pollPeriodMillis | Abrufhäufigkeit der Datenbank (in Millisekunden) für die Überprüfung auf neue Nachrichten | 2000 | 500: Sehr niedrige Latenz | 10000: Größere Batches | 500: Geringe Latenz erleichtert das Debuggen. |
| prepareThreads | Anzahl der Threads für die Nachrichtenvorbereitung | 3 | 1: Einprozessoren | Anzahl der CPUs. Seien Sie vorsichtig mit der RAM-Nutzung. Für eine Erhöhung von über 6 ist möglicherweise eine Erhöhung von maxSMSMemoryMb, maxProcessMemoryAlertMb und maxProcessMemoryWarningMb erforderlich. | 1: Ein einzelnes Thread generiert sauberere Protokolle. |
| profDeliveryStat | Verschiedene aggregierte Statistiken über interne SMS-Prozesse protokollieren | true | false: Kann den Durchsatz etwas erhöhen. Entmutigt. | true: Low verbosity log | true |
| profLogPerMessage | jeden Verarbeitungsschritt für jede Nachricht protokollieren | false | false: Reduzieren Sie die Protokollausführlichkeit. | true: Sehr hohes Ausführlichkeits-Protokoll. **Nur verwenden, wenn unbedingt erforderlich**. Große Leistungseinbußen. **Deaktivieren Sie diese Einstellung, sobald genügend Daten gesammelt wurden**. | true |
| providerIdScanPeriod | Zeitraum in Sekunden zwischen Prüfungen auf neue Anbieter-IDs zur Abstimmung | 10 | 1: Geringe Latenz | 60: Größere Batches für mehr Durchsatz | 1: Geringe Latenz hilft beim Debugging der Nachrichtenverarbeitung. |
| providerIdThreads | Anzahl der Threads für den Abgleich der Anbieter-ID. 1 Thread pro Instanz ist ausreichend. Den Wert auf 0 festlegen, um ihn in diesem Container zu deaktivieren. | 1 | 0: In diesem Container deaktivieren | 1 | 1 |
| sendingThreads | Anzahl an Versand-Threads | 1 | 1: Einprozessoren | Anzahl der CPUs. Zu viele Threads beeinträchtigen normalerweise die Leistung. | 1: Ein einzelnes Thread generiert sauberere Protokolle. |
| updateThreads | Anzahl der Threads für die Datenbankaktualisierung | 1 | 1: Einprozessoren | Anzahl der CPUs. Jeder Thread erstellt eine eigene DB-Verbindung. | 1: Ein einzelnes Thread generiert sauberere Protokolle. |
| verifyMode | Nachrichten simulieren. Nachrichten werden nicht gesendet. Nützlich für das Debugging | false | false | true | false: Führen Sie das System normal aus. true: Nur DB-Zugriff und Nachrichtenvorbereitung testen. |

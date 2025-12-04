---
title: Wechsel zum neuen SMS-Connector v2
description: Erfahren Sie, wie Sie zum neuen SMS-Connector v2 wechseln.
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: ed9e784c1610a6f042b99223ac0d4cc0cf312b09
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Wechsel zum neuen SMS-Connector v2

In diesem Dokument werden das Verfahren und die wichtigsten Aspekte bei der Migration vom MTA-basierten SMS-Connector zum neuen **dedizierten SMS-Prozess-Connector** in Adobe Campaign v8 beschrieben.

## Warum zum V2-Connector wechseln?

Der dedizierte SMS-Prozess führt die Unterstützung für den SMPP-Transceiver-Modus ein, reduziert die Verbindungsanzahl und verbessert die Ressourceneffizienz, unterstützt jedoch bei Bedarf weiterhin Sender-/Empfängereinstellungen. Sie bietet deutlich mehr Stabilität, schnellere Wiederherstellung nach Fehlern, persistenten Verbindungen und keine Abhängigkeit von lokalen Dateien oder prozessübergreifender Kommunikation. Die Leistung wird ebenfalls verbessert, mit geringerer Latenz, höherem Durchsatz und intelligentem Microbatching, um Geschwindigkeit und Zuverlässigkeit auszugleichen. Darüber hinaus vereinfacht die Isolierung des SMS-Prozesses die Fehlerbehebung und minimiert Cross-Channel-Auswirkungen. Diese Verbesserungen machen den dedizierten Connector zu einer robusteren und skalierbareren Lösung für den SMS-Versand.

## Differences v1- und v2-Connectoren

Der dedizierte SMS-Connector in Adobe Campaign v8 führt mehrere Änderungen an der Architektur im Vergleich zum MTA-basierten Connector ein. Ein wichtiger Unterschied ist die standardmäßige Verwendung des SMPP-Transceiver-Modus, der die Anzahl der Verbindungen durch die Kombination von Sende- und Empfangsfunktionen reduziert. Wenn der Anbieter diesen Modus nicht unterstützt, können dennoch separate Sender- und Empfängerverbindungen verwendet werden. Im Gegensatz zum MTA-Connector hat die Aktivierung automatischer Antworten keine Auswirkungen auf die Anzahl der Verbindungen, und alle Empfängerverbindungen können jede Art eingehender Nachrichten verarbeiten.

Die Anzahl der Verbindungen wird jetzt mithilfe einer anderen Formel berechnet:

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

Der Parameter sendThreads , der in der serverConf definiert ist, ist standardmäßig 1 und sollte im Allgemeinen unverändert bleiben, es sei denn, er wird speziell für hohe Leistung optimiert. Da der gesamte SMS-Traffic über einen einzigen Prozess abgewickelt wird, ist die Verwaltung der Parallelität mithilfe dieser Parameter für die Steuerung der Systemlast und des Systemverhaltens von entscheidender Bedeutung.

Das Übertragungsfenster verhält sich ähnlich wie der MTA-Connector, hat aber im dedizierten Modus noch größere Auswirkungen auf die Leistung. Größere Übertragungsfenster reduzieren Datenbank-IOPS und verbessern den Durchsatz. Campaign kann Fenster mit mehr als 1.000 Nachrichten effizient verarbeiten, vorausgesetzt, der Anbieter unterstützt dies und der Anwendungsfall ermöglicht einen kleinen Spielraum für Nachrichtenverluste oder Duplizierungen im Falle von Verbindungsproblemen. Auf Anbieterseite kann durch die Konfiguration eines größeren SR-Versandfensters auch der Durchsatz von Versandberichten erheblich verbessert werden.

Schließlich wurde der zugrunde liegende Code aktualisiert, während die Handhabung von MO-Nachrichten (Mobile Originated Message Handling) funktionell unverändert bleibt. Der Durchsatz pro Verbindung ist weiterhin auf die gleiche Weise begrenzt, aber der dedizierte Connector ermöglicht einen viel schnelleren Burst-Versand. Ohne Durchsatzbeschränkungen kann das Senden mit hoher Geschwindigkeit jedoch die Provider- oder Systemressourcen überfordern, sodass es ratsam ist, explizite MT-Durchsatzbegrenzungen in der Konfiguration des externen Kontos festzulegen.

## Schaltverfahren

Um einen reibungslosen Wechsel zum dedizierten SMS-Prozess sicherzustellen, ist es am besten, den Vorgang bei geringem oder keinem SMS-Traffic durchzuführen. Einige gepufferte Nachrichten können verloren gehen oder einen ungültigen Status erhalten, wenn die MTA-Puffer nicht vollständig geleert werden. Es ist auch normal, einige SRs bis zu eine Woche nach dem Wechsel zu verpassen, aufgrund eines unvorhersehbaren SR-Timings. Wenn Sie diese Sicherheitsvorkehrungen nicht befolgen, kann dies trotz integrierter Sicherheitsvorkehrungen zu Nachrichtenverlusten oder Duplizierungen führen.

Beide SMS-Connectoren verwenden verschiedene Formate für die SR-Verarbeitung (Statusbericht). Obwohl beide auf die `NmsProviderMsgId`-Tabelle angewiesen sind, interagieren sie unterschiedlich mit ihr. Daher müssen beim Wechsel von Connectoren die gesamte Tabelle gelöscht werden, um Konflikte oder verwaiste Daten zu vermeiden. Es gibt mehrere Möglichkeiten, diese Bereinigung durchzuführen. Im Folgenden finden Sie die SQL-Abfragen, die Sie verwenden können:

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Schritte

1. Überprüfen Sie `serverConf` Einstellungen (`sms > mta2`).
1. Anhalten des Workflows zur Nachrichtenvorbereitung in Echtzeit (falls zutreffend).
1. Alle SMS-Sendungen anhalten.
1. Deaktivieren Sie das externe SMS-Konto.
1. Beenden und starten Sie die MTA- und SMS-Prozesse neu.
1. Stellen Sie sicher, dass keine SMPP-Verbindungen aktiv sind. Stellen Sie sicher, dass alle Sendungen angehalten wurden, falls vorhanden.
1. Löscht den Inhalt der `NmsProviderMsgId`- und `NmsProviderMsgStatus` in der Datenbank.
1. Im externen Konto:
   * Aktivieren Sie das Kontrollkästchen „Dedizierter Prozess“
   * Andere Einstellungen anpassen: untergeordnete MTA-Verbindungen, MT-Durchsatz, Übertragungsfenster
1. Aktivieren Sie das externe Konto erneut und speichern Sie es.
1. SMS-Sendungen fortsetzen.
1. Überprüfen Sie, ob die SMS-Services normal funktionieren.

>[!NOTE]
>
>Überwachen Sie die untergeordneten Protokolle von SMS, MTA und MTA auf Fehler oder Probleme.
>
>Speichern Sie frühere Einstellungen für externe Konten zu Rollback-Zwecken.

### Rollback

Ein Rollback zum MTA-Connector ist möglich, indem Sie die gleichen Schritte ausführen, die während des ersten Switches in der gleichen Reihenfolge verwendet wurden. Dazu gehört das Anhalten oder Anhalten aller SMS-Sendungen und die Wiederherstellung der ursprünglichen Konfiguration des externen Kontos.

1. Wenn die Instanz Echtzeit-Sendungen verwendet, pausieren Sie den technischen Workflow, der für die Vorbereitung dieser Nachrichten zuständig ist.
1. Alle SMS-Sendungen anhalten.
1. Deaktivieren Sie das externe SMS-Konto.
1. Beenden und starten Sie sowohl den MTA- als auch den SMS-Prozess neu.
1. Stellen Sie sicher, dass keine SMPP-Verbindungen aktiv bleiben. Überprüfen Sie in diesem Fall, ob alle Sendungen ordnungsgemäß angehalten wurden.
1. Löschen Sie die `NmsProviderMsgId`- und `NmsProviderMsgStatus` in der Datenbank.
1. Im externen Konto:
   * Deaktivieren Sie die Option „Dedizierter Prozess“ im externen Konto.
   * Alle vorherigen externen Kontoeinstellungen wiederherstellen: untergeordnete MTA-Verbindungen, MT-Durchsatz, Übertragungsfenster
1. Aktivieren und speichern Sie das externe Konto erneut.
1. Alle SMS-Sendungen fortsetzen.
1. Bestätigen Sie abschließend, dass die SMS-Dienste normal funktionieren.

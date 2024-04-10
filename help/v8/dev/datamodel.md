---
title: Erste Schritte mit dem Campaign-Datenmodell
description: Beginnen Sie mit dem Campaign-Datenmodell und nutzen Sie Daten aus Ihren Quellen, um Ihre Kommunikations- und Marketing-Ergebnisse zu nutzen.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 93%

---

# Erste Schritte mit dem Campaign-Datenmodell {#gs-ac-datamodel}

Adobe Campaign enthält ein vordefiniertes Datenmodell. Dieser Abschnitt enthält einige Details zu den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Interaktion. Adobe Campaign stützt sich auf eine Cloud-Datenbank mit Tabellen, die miteinander verknüpft sind.

Die Grundstruktur des Adobe Campaign-Datenmodells lässt sich wie folgt beschreiben:

* **Empfängertabelle**: Das Datenmodell basiert auf einer Haupttabelle, die standardmäßig die Empfängertabelle (**nmsRecipient**) ist. In dieser Tabelle werden alle Marketing-Profile gespeichert. Weitere Informationen zur Empfängertabelle finden Sie in [diesem Abschnitt](#ootb-profiles).

* **Versandtabelle**: Diese Tabelle speichert einen Eintrag pro Versandaktion. Normalerweise handelt es sich dabei um die Versandtabelle (**NmsDelivery**). in dieser Tabelle stellt eine Versandaktion oder Versandvorlage dar. Es enthält alle zum Ausführen von Sendungen erforderlichen Parameter wie Zielgruppe, Inhalt usw. Jeder Eintrag wird wiederholt aktualisiert, um den Versandfortschritt widerzuspiegeln

* **Protokolltabelle**: In diesen Tabellen werden alle Protokolle gespeichert, die mit der Ausführung der Kampagnen verbunden sind.

   * Versand-Logs sind sämtliche Nachrichten, die über alle Kanäle hinweg an Empfänger oder Geräte gesendet werden. Die Haupttabelle der Versandlogs (**NmsBroadLogRcp**) enthält die Versandlogs für alle Empfängerinnen und Empfänger.
   * Die Tabelle **nmsBroadlog** ist die größte Tabelle im System. Pro gesendeter Nachricht wird ein Eintrag gespeichert. Diese Einträge werden eingefügt, aktualisiert, um den Versandstatus zu verfolgen, und gelöscht, wenn der Verlauf gelöscht wird.
   * Die Haupttabelle der Trackinglogs (**NmsTrackingLogRcp**) speichert die Trackinglogs für alle Empfängerinnen und Empfänger. Die Trackinglogs beziehen sich auf Reaktionen von Empfängerinnen und Empfängern wie E-Mail-Öffnungen und Klicks. Jede Reaktion entspricht einem Trackinglog.

  Versand-Logs und Trackinglogs werden nach einem bestimmten Zeitraum gelöscht, der in Adobe Campaign angegeben und änderbar ist. Daher wird dringend empfohlen, die Logs regelmäßig zu exportieren.

* **Technische Tabellen**: Diese Tabellen sammeln technische Daten, die für den jeweiligen Prozess verwendet werden, einschließlich Benutzende und Benutzerberechtigungen (**xtkGroup**), Benutzersitzungen (**xtkSessionInfo**), Ordner in der Explorer-Struktur (**XtkFolder**), Workflows (**xtkWorkflow**) und mehr.

>[!NOTE]
>
>Um Beschreibungen der einzelnen Tabellen aufzurufen, navigieren Sie zu **Administration > Konfiguration > Datenschemata**, wählen Sie eine Ressource aus der Liste aus und klicken Sie auf die Registerkarte **Dokumentation**.

Wenn Sie mit Adobe Campaign beginnen, müssen Sie das Standarddatenmodell evaluieren, um zu prüfen, welche Tabelle am besten zur Speicherung Ihrer Marketing-Daten geeignet ist.

Sie können die standardmäßige Empfängertabelle mit den vordefinierten Feldern verwenden, wie in [diesem Abschnitt](#ootb-profiles) beschrieben. Bei Bedarf können Sie sie mit zwei Verfahren erweitern:

* [Erweitern einer vorhandenen Tabelle](extend-schema.md) mit neuen Feldern. Sie können der Empfängertabelle beispielsweise ein neues Feld „Treue“ hinzufügen.
* [Erstellen Sie eine neue Tabelle](create-schema.md), z. B. eine Tabelle „Einkauf“, in der alle von den einzelnen Profilen der Datenbank getätigten Käufe aufgelistet sind, und verknüpfen Sie sie mit der Empfängertabelle.

Best Practices für die Arbeit mit dem Campaign-Datenmodell in [Dieser Abschnitt](datamodel-best-practices.md).

## Native Profiltabelle {#ootb-profiles}

Die integrierte Empfängertabelle (nmsrecipient) in Adobe Campaign bietet einen guten Ausgangspunkt zum Erstellen Ihres Datenmodells. Sie verfügt über eine Reihe vordefinierter Felder und Tabellenverknüpfungen, die leicht erweitert werden können. Dies ist besonders dann nützlich, wenn Sie vor allem auf Empfänger abzielen, da sie für ein einfaches Empfänger-orientiertes Datenmodell geeignet ist.

Die Verwendung der standardmäßigen Empfängertabelle bietet folgende Vorteile:

* Sofortiges Arbeiten mit Schlüsselfunktionen wie Anmeldungen, Seed-Listen und mehr
* Bereitstellen einer Marketing-Datenbank mit einem Empfänger-orientierten Datenmodell
* Schnellere Implementierung
* Einfache Wartung durch Support und Partner

Es ist möglich, die Empfängertabelle zu erweitern. Die Anzahl der Empfänger oder Relationen in der Tabelle lässt sich aber nicht verringern.

Näheres dazu, wie Sie ein vorhandenes Schema erweitern, finden Sie in [diesem Abschnitt](extend-schema.md).

Beispiele für integrierte Empfängertabellen-Erweiterungen in [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#extending-a-table){target="_blank"}

Sie können auch eine andere Empfängertabelle nutzen, die besser auf Ihre geschäftlichen oder funktionalen Anforderungen zugeschnitten ist. Diese Methode weist Einschränkungen auf und wird in [diesem Abschnitt](custom-recipient.md) beschrieben.

## Campaign-Tabellen und Cloud-Datenbank

Zum besseren Verständnis der Tabellenverwaltung in Campaign v8 ist zu beachten, dass im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) die Tabellen zwischen Campaign und der Snowflake Cloud-Datenbank repliziert werden.

Erfahren Sie mehr über Replikationsstrategien und -verfahren in [Dieser Abschnitt](../architecture/replication.md).

**Verwandte Themen** 

Erfahren Sie, wie Sie Profile in importieren. [Dieser Abschnitt](../start/import.md)
Weitere Informationen zu Campaign-Audiences finden Sie in [Dieser Abschnitt](../start/audiences.md)

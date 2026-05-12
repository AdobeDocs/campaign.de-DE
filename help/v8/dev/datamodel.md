---
title: Erste Schritte mit dem Campaign-Datenmodell
description: Beginnen Sie mit dem Campaign-Datenmodell und nutzen Sie Daten aus Ihren Quellen, um Ihre Kommunikations- und Marketing-Ergebnisse zu nutzen.
feature: Data Model
role: Developer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
TQID: https://experienceleague.adobe.com/pUzg-KbbYOXppAjG0nQe9T16Co61ipNXywTjNaV76bU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: b5852c32-876b-41ae-92a7-9f588865ae52
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 737
ht-degree: 92%

---

# Erste Schritte mit dem Campaign-Datenmodell {#gs-ac-datamodel}

Adobe Campaign enthält ein vordefiniertes Datenmodell. Dieser Abschnitt enthält einige Details zu den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Interaktion. Adobe Campaign stützt sich auf eine Cloud-Datenbank mit Tabellen, die miteinander verknüpft sind.

Die Grundstruktur des Adobe Campaign-Datenmodells lässt sich wie folgt beschreiben:

* **Empfängertabelle**: Das Datenmodell basiert auf einer Haupttabelle, die standardmäßig die Empfängertabelle (**nmsRecipient**) ist. In dieser Tabelle werden alle Marketing-Profile gespeichert. Weitere Informationen zur Empfängertabelle finden Sie in [diesem Abschnitt](#ootb-profiles).

* **Versandtabelle**: Diese Tabelle speichert einen Eintrag pro Versandaktion. Normalerweise handelt es sich dabei um die Versandtabelle (**NmsDelivery**). in dieser Tabelle stellt eine Versandaktion oder Versandvorlage dar. Es enthält alle erforderlichen Parameter für die Durchführung von Sendungen wie Zielgruppe, Inhalt usw. Jeder Datensatz wird mehrmals aktualisiert, um den Versandfortschritt widerzuspiegeln

* **Protokolltabelle**: In diesen Tabellen werden alle Protokolle gespeichert, die mit der Ausführung der Kampagnen verbunden sind.

   * Versand-Logs sind sämtliche Nachrichten, die über alle Kanäle hinweg an Empfänger oder Geräte gesendet werden. Die Haupttabelle der Versandlogs (**NmsBroadLogRcp**) enthält die Versandlogs für alle Empfängerinnen und Empfänger.
   * Die Tabelle **nmsBroadlog** ist die größte Tabelle im System. Pro gesendeter Nachricht wird ein Eintrag gespeichert. Diese Einträge werden eingefügt, aktualisiert, um den Versandstatus zu verfolgen, und gelöscht, wenn der Verlauf gelöscht wird.
   * Die Haupttabelle der Trackinglogs (**NmsTrackingLogRcp**) speichert die Trackinglogs für alle Empfängerinnen und Empfänger. Die Trackinglogs beziehen sich auf Reaktionen von Empfängern wie E-Mail-Öffnungen und Klicks. Jede Reaktion entspricht einem Trackinglog.

  Versand-Logs und Trackinglogs werden nach einem bestimmten Zeitraum gelöscht, der in Adobe Campaign angegeben und änderbar ist. Daher wird dringend empfohlen, die Logs regelmäßig zu exportieren.

* **Technische Tabellen**: Diese Tabellen sammeln technische Daten, die für den jeweiligen Prozess verwendet werden, einschließlich Benutzende und Benutzerberechtigungen (**xtkGroup**), Benutzersitzungen (**xtkSessionInfo**), Ordner in der Explorer-Struktur (**XtkFolder**), Workflows (**xtkWorkflow**) und mehr.

>[!NOTE]
>
>Um Beschreibungen der einzelnen Tabellen aufzurufen, navigieren Sie zu **Administration > Konfiguration > Datenschemata**, wählen Sie eine Ressource aus der Liste aus und klicken Sie auf die Registerkarte **Dokumentation**.

Wenn Sie mit Adobe Campaign beginnen, müssen Sie das Standarddatenmodell evaluieren, um zu prüfen, welche Tabelle am besten zur Speicherung Ihrer Marketing-Daten geeignet ist.

Sie können die standardmäßige Empfängertabelle mit den vordefinierten Feldern verwenden, wie in [diesem Abschnitt](#ootb-profiles) beschrieben. Bei Bedarf können Sie sie mit zwei Verfahren erweitern:

* [Erweitern einer vorhandenen Tabelle](extend-schema.md) mit neuen Feldern. Sie können der Empfängertabelle beispielsweise ein neues Feld „Treue“ hinzufügen.
* [Erstellen Sie eine neue Tabelle](create-schema.md), z. B. eine Tabelle „Einkauf“, in der alle von den einzelnen Profilen der Datenbank getätigten Käufe aufgelistet sind, und verknüpfen Sie sie mit der Empfängertabelle.

Best Practices zum Arbeiten mit dem Campaign-Datenmodell finden Sie in [diesem Abschnitt](datamodel-best-practices.md).

## Native Profiltabelle {#ootb-profiles}

Die integrierte Empfängertabelle (nmsrecipient) in Adobe Campaign bietet einen guten Ausgangspunkt zum Erstellen Ihres Datenmodells. Sie verfügt über eine Reihe vordefinierter Felder und Tabellenverknüpfungen, die leicht erweitert werden können. Dies ist besonders dann nützlich, wenn Sie vor allem auf Empfänger abzielen, da sie für ein einfaches Empfänger-orientiertes Datenmodell geeignet ist.

Die Verwendung der standardmäßigen Empfängertabelle bietet folgende Vorteile:

* Sofortiges Arbeiten mit Schlüsselfunktionen wie Anmeldungen, Seed-Listen und mehr
* Bereitstellen einer Marketing-Datenbank mit einem Empfänger-orientierten Datenmodell
* Schnellere Implementierung
* Einfache Wartung durch Support und Partner

Es ist möglich, die Empfängertabelle zu erweitern. Die Anzahl der Empfänger oder Relationen in der Tabelle lässt sich aber nicht verringern.

Näheres dazu, wie Sie ein vorhandenes Schema erweitern, finden Sie in [diesem Abschnitt](extend-schema.md).

Beispiele für integrierte Empfängertabellen-Erweiterungen finden Sie in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#extending-a-table){target="_blank"}

Sie können auch eine andere Empfängertabelle nutzen, die besser auf Ihre geschäftlichen oder funktionalen Anforderungen zugeschnitten ist. Diese Methode weist Einschränkungen auf und wird in [diesem Abschnitt](custom-recipient.md) beschrieben.

## Campaign-Tabellen und Cloud-Datenbank

Zum besseren Verständnis der Tabellenverwaltung in Campaign v8 ist zu beachten, dass im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) die Tabellen zwischen Campaign und der Snowflake Cloud-Datenbank repliziert werden.

Weitere Informationen zu Replikationsstrategien und -verfahren finden Sie in [diesem Abschnitt](../architecture/replication.md).

**Verwandte Themen**

Erfahren Sie in [&#x200B; Abschnitt , wie Sie Profile importieren.](../start/import.md)
Weitere Informationen zu Campaign-Audiences finden [&#x200B; in diesem Abschnitt](../start/audiences.md)

---
title: Erste Schritte mit dem Campaign-Datenmodell
description: Beginnen Sie mit dem Campaign-Datenmodell und nutzen Sie Daten aus Ihren Quellen, um Ihre Kommunikations- und Marketing-Ergebnisse zu nutzen.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 74%

---

# Erste Schritte mit dem Campaign-Datenmodell{#gs-ac-datamodel}

Adobe Campaign enthält ein vordefiniertes Datenmodell. Dieser Abschnitt enthält einige Details zu den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Interaktion. Adobe Campaign stützt sich auf eine Cloud-Datenbank mit Tabellen, die miteinander verknüpft sind.

Die Grundstruktur des Adobe Campaign-Datenmodells lässt sich wie folgt beschreiben:

* **Empfängertabelle**: Das Datenmodell beruht auf einer Haupt-Tabelle, die standardmäßig die Empfängertabelle (**nmsRecipient**). In dieser Tabelle werden alle Marketing-Profile gespeichert. Weitere Informationen zur Empfängertabelle finden Sie unter [diesem Abschnitt](#ootb-profiles).

* **Versandtabelle**: Diese Tabelle speichert einen Datensatz pro Versandaktion. Normalerweise handelt es sich um die Versandtabelle (**NmsDelivery**). in dieser Tabelle eine Versandaktion oder eine Versandvorlage. Er enthält alle erforderlichen Parameter zum Ausführen von Sendungen wie Zielgruppe, Inhalt usw. Jeder Datensatz wird wiederholt aktualisiert, um den Versandfortschritt widerzuspiegeln

* **Protokolltabelle**: In diesen Tabellen werden alle Protokolle gespeichert, die mit der Ausführung der Kampagnen verbunden sind.

   * Versand-Logs sind sämtliche Nachrichten, die über alle Kanäle hinweg an Empfänger oder Geräte gesendet werden. Die wichtigste Tabelle der Versandlogs (**NmsBroadLogRcp**) enthält die Versandlogs für alle Empfänger.
   * Die **nmsBroadlog** -Tabelle ist die größte Tabelle im System. Pro gesendeter Nachricht wird ein Datensatz gespeichert. Diese Datensätze werden eingefügt, aktualisiert, um den Versandstatus zu verfolgen, und beim Löschen des Verlaufs gelöscht.
   * Die wichtigste Tabelle der Trackinglogs (**NmsTrackingLogRcp**) speichert die Trackinglogs für alle Empfänger. Die Trackinglogs beziehen sich auf Reaktionen von Empfängern wie E-Mail-Öffnungen und Klicks. Jede Reaktion entspricht einem Trackinglog.

  Versand-Logs und Trackinglogs werden nach einem bestimmten Zeitraum gelöscht, der in Adobe Campaign angegeben und änderbar ist. Daher wird dringend empfohlen, die Logs regelmäßig zu exportieren.

* **Technische Tabellen**: Sammlung technischer Daten, die für den jeweiligen Prozess verwendet werden, einschließlich Benutzer- und Benutzerberechtigungen (**xtkGroup**), Benutzersitzungen (**xtkSessionInfo**), Ordner in der Explorer-Struktur (**XtkFolder**), Workflows (**xtkWorkflow**) und mehr.

>[!NOTE]
>
>Um auf die Beschreibung der einzelnen Tabellen zuzugreifen, navigieren Sie zu **Administration > Konfiguration > Datenschemata**, wählen Sie eine Ressource aus der Liste aus und klicken Sie auf die **Dokumentation** Registerkarte.

Wenn Sie mit Adobe Campaign beginnen, müssen Sie das Standarddatenmodell evaluieren, um zu prüfen, welche Tabelle am besten zur Speicherung Ihrer Marketing-Daten geeignet ist.

Sie können die standardmäßige Empfängertabelle mit den vordefinierten Feldern verwenden, wie in [diesem Abschnitt](#ootb-profiles) beschrieben. Bei Bedarf können Sie sie mit zwei Verfahren erweitern:

* [Erweitern einer vorhandenen Tabelle](extend-schema.md) mit neuen Feldern. Sie können der Empfängertabelle beispielsweise ein neues Feld „Treue“ hinzufügen.
* [Erstellen Sie eine neue Tabelle](create-schema.md), z. B. eine Tabelle „Einkauf“, in der alle von den einzelnen Profilen der Datenbank getätigten Käufe aufgelistet sind, und verknüpfen Sie sie mit der Empfängertabelle.

![](../assets/do-not-localize/glass.png) Lernen Sie in [diesem Abschnitt](datamodel-best-practices.md) Best Practices zum Arbeiten mit dem Campaign-Datenmodell kennen.

## Native Profiltabelle {#ootb-profiles}

Die integrierte Empfängertabelle (nmsrecipient) in Adobe Campaign bietet einen guten Ausgangspunkt zum Erstellen Ihres Datenmodells. Sie verfügt über eine Reihe vordefinierter Felder und Tabellenverknüpfungen, die leicht erweitert werden können. Dies ist besonders dann nützlich, wenn Sie vor allem auf Empfänger abzielen, da sie für ein einfaches Empfänger-orientiertes Datenmodell geeignet ist.

Die Verwendung der standardmäßigen Empfängertabelle bietet folgende Vorteile:

* Sofortiges Arbeiten mit Schlüsselfunktionen wie Anmeldungen, Seed-Listen und mehr
* Bereitstellen einer Marketing-Datenbank mit einem Empfänger-orientierten Datenmodell
* Schnellere Implementierung
* Einfache Wartung durch Support und Partner

Es ist möglich, die Empfängertabelle zu erweitern. Die Anzahl der Empfänger oder Relationen in der Tabelle lässt sich aber nicht verringern.

![](../assets/do-not-localize/glass.png) Näheres dazu, wie Sie ein vorhandenes Schema erweitern, finden Sie in [diesem Abschnitt](extend-schema.md).

![](../assets/do-not-localize/book.png) Beispiele für integrierte Empfängertabellen-Erweiterungen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#extending-a-table).{target="_blank"}

Sie können auch eine andere Empfängertabelle nutzen, die besser auf Ihre geschäftlichen oder funktionalen Anforderungen zugeschnitten ist. Diese Methode weist Einschränkungen auf und wird in [diesem Abschnitt](custom-recipient.md) beschrieben.

## Campaign-Tabellen und Cloud-Datenbank

Zum besseren Verständnis der Tabellenverwaltung in Campaign v8 ist zu beachten, dass im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) die Tabellen zwischen Campaign und der Snowflake Cloud-Datenbank repliziert werden.

![](../assets/do-not-localize/glass.png) Weitere Informationen zu Replikationsstrategien und -verfahren finden Sie in [diesem Abschnitt](../architecture/replication.md).

**Verwandte Themen**

![](../assets/do-not-localize/glass.png): Erfahren Sie in [diesem Abschnitt](../start/import.md), wie Sie Profile importieren.
![](../assets/do-not-localize/glass.png)Weitere Informationen zu Campaign-Audiences finden Sie in [diesem Abschnitt](../start/audiences.md).

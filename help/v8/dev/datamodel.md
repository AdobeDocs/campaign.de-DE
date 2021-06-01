---
product: Adobe Campaign
title: Erste Schritte mit dem Campaign-Datenmodell
description: Erste Schritte mit dem Campaign-Datenmodell
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 88%

---

# Erste Schritte mit dem Campaign-Datenmodell{#gs-ac-datamodel}

Adobe Campaign enthält ein vordefiniertes Datenmodell. Dieser Abschnitt enthält einige Details zu den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Interaktion. Adobe Campaign stützt sich auf eine Cloud-Datenbank mit Tabellen, die miteinander verknüpft sind.

Die Grundstruktur des Adobe Campaign-Datenmodells lässt sich wie folgt beschreiben:

* **Empfängertabelle**: Das Datenmodell basiert auf einer Haupttabelle, die standardmäßig die Empfängertabelle (nmsRecipient) ist. Diese Tabelle ermöglicht eine Speicherung aller Marketing-Profile.

   [!DNL :bulb:] Weitere Informationen zur Empfängertabelle finden Sie in [diesem Abschnitt](#ootb-profiles).

* **Versandtabelle**: Das Datenmodell enthält auch einen Teil, der dem Speichern aller Marketing-Aktivitäten dient. Normalerweise handelt es sich dabei um die Versandtabelle (NmsDelivery). Jeder Datensatz in dieser Tabelle stellt eine Versandaktion oder Versandvorlage dar. Er enthält alle erforderlichen Parameter zum Ausführen von Sendungen wie Zielgruppe, Inhalt usw.

* **Protokolltabelle**: In diesen Tabellen werden alle Protokolle gespeichert, die mit der Ausführung der Kampagnen verbunden sind.

   Versand-Logs sind sämtliche Nachrichten, die über alle Kanäle hinweg an Empfänger oder Geräte gesendet werden. Die Haupttabelle Versandlogs (NmsBroadLogRcp) enthält die Versandlogs aller Empfänger.
Die Haupttabelle Trackinglogs (NmsTrackingLogRcp) speichert die Trackinglogs für alle Empfänger. Die Trackinglogs beziehen sich auf Reaktionen von Empfängern wie E-Mail-Öffnungen und Klicks. Jede Reaktion entspricht einem Trackinglog.
Versand-Logs und Trackinglogs werden nach einem bestimmten Zeitraum gelöscht, der in Adobe Campaign angegeben und änderbar ist. Daher wird dringend empfohlen, die Logs regelmäßig zu exportieren.

* **Technische Tabellen**: Erfassen Sie technische Daten, die für den Anwendungsprozess verwendet werden, einschließlich Operatoren und Benutzerrechte (xtkGroup), Ordner (XtkFolder).

>[!NOTE]
>
>Um Beschreibungen der einzelnen Tabellen aufzurufen, navigieren Sie zu &quot;Admin&quot; > &quot;Konfiguration&quot; > &quot;Datenschemata&quot;, wählen Sie eine Ressource aus der Liste und klicken Sie auf die Registerkarte **Dokumentation**.

Wenn Sie mit Adobe Campaign beginnen, müssen Sie das Standarddatenmodell evaluieren, um zu prüfen, welche Tabelle am besten zur Speicherung Ihrer Marketing-Daten geeignet ist.

Sie können die standardmäßige Empfängertabelle mit den vordefinierten Feldern verwenden, wie in [diesem Abschnitt](#ootb-profiles) beschrieben. Bei Bedarf können Sie sie mit zwei Verfahren erweitern:

* [Erweitern einer vorhandenen Tabelle](extend-schema.md) mit neuen Feldern. Sie können der Empfängertabelle beispielsweise ein neues Feld &quot;Treue&quot; hinzufügen.
* [Erstellen einer neuen Tabelle](create-schema.md), z. B. einer Tabelle &quot;Einkauf&quot;, in der alle von den einzelnen Profilen der Datenbank getätigten Käufe aufgelistet sind, und Verknüpfen mit der Empfängertabelle.

[!DNL :bulb:] Lernen Sie in [diesem Abschnitt](datamodel-best-practices.md) Best Practices zum Arbeiten mit dem Campaign-Datenmodell kennen.

## Integrierte Profiltabelle {#ootb-profiles}

Die integrierte Empfängertabelle (nmsrecipient) in Adobe Campaign bietet einen guten Ausgangspunkt zum Erstellen Ihres Datenmodells. Sie verfügt über eine Reihe vordefinierter Felder und Tabellenrelationen, die leicht erweitert werden können. Dies ist besonders dann nützlich, wenn Sie vor allem auf Empfänger abzielen, da sie für ein einfaches Empfänger-orientiertes Datenmodell geeignet ist.

Die Verwendung der standardmäßigen Empfängertabelle bietet folgende Vorteile:

* Sofortiges Arbeiten mit Schlüsselfunktionen wie Anmeldungen, Seed-Listen und mehr
* Bereitstellen einer Marketing-Datenbank mit einem Empfänger-orientierten Datenmodell
* Schnellere Implementierung
* Einfache Wartung durch Support und Partner

Es ist möglich, die Empfängertabelle zu erweitern. Die Anzahl der Empfänger oder Relationen in der Tabelle lässt sich aber nicht verringern.

[!DNL :bulb:] Näheres dazu, wie Sie ein vorhandenes Schema erweitern, finden Sie in [diesem Abschnitt](extend-schema.md).

[!DNL :arrow_upper_right:] Beispiele für integrierte Erweiterungen von Empfängertabellen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=de#extending-a-table)

Sie können auch eine andere Empfängertabelle nutzen, die besser auf Ihre geschäftlichen oder funktionalen Anforderungen zugeschnitten ist. Diese Methode weist Einschränkungen auf und wird in [diesem Abschnitt](custom-recipient.md) beschrieben.

## Campaign-Tabellen und Cloud-Datenbank

Beachten Sie für ein genaueres Verständnis der Tabellenverwaltung in Campaign v8, dass Tabellen zwischen Campaign und der zugehörigen Snowflake-Cloud-Datenbank repliziert werden.

[!DNL :bulb:] Weitere Informationen zu Replikationsstrategien und -verfahren finden Sie in [diesem Abschnitt](../config/replication.md).

**Verwandte Themen**

[!DNL :bulb:] Informationen zum Importieren von Profilen finden Sie in  [diesem ](../start/import.md)
[!DNL :bulb:] AbschnittWeitere Informationen zu Campaign-Zielgruppen finden Sie in  [diesem Abschnitt](../start/audiences.md)

---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit dem Campaign-Datenmodell
description: Erste Schritte mit dem Campaign-Datenmodell
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---

# Erste Schritte mit dem Campaign-Datenmodell{#gs-ac-datamodel}

Adobe Campaign enthält ein vordefiniertes Datenmodell. In diesem Abschnitt finden Sie einige Details zu den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Interaktion. Adobe Campaign stützt sich auf eine Cloud-Datenbank mit Tabellen, die verknüpft sind.

Die grundlegende Struktur des Adobe Campaign-Datenmodells kann wie folgt beschrieben werden:

* **Empfängertabelle**: Das Datenmodell beruht auf einer Haupt-Tabelle, die standardmäßig die Empfängertabelle (nmsRecipient) ist. Diese Tabelle ermöglicht die Speicherung aller Marketing-Profile.

   :bulb: Weiterführende Informationen zur Empfängertabelle finden Sie in [diesem Abschnitt](#ootb-profiles).

* **Versandtabelle**: Das Datenmodell enthält auch einen Teil, in dem alle Marketing-Aktivitäten gespeichert werden. Normalerweise handelt es sich um die Versandtabelle (NmsDelivery). Jeder Datensatz in dieser Tabelle stellt eine Versandaktion oder eine Versandvorlage dar. Sie enthält alle für die Durchführung von Sendungen erforderlichen Parameter wie Zielgruppe, Inhalt usw.

* **Protokolltabellen**: In diesen Tabellen werden alle Logs gespeichert, die mit der Ausführung der Kampagnen verknüpft sind.

   Versandlogs sind alle Nachrichten, die über alle Kanäle an Empfänger oder Geräte gesendet werden. Die Haupttabelle Versandlogs (NmsBroadLogRcp) enthält die Versandlogs aller Empfänger.
Die Haupttabelle Trackinglogs (NmsTrackingLogRcp) speichert die Trackinglogs für alle Empfänger. Die Trackinglogs beziehen sich auf Reaktionen von Empfängern wie E-Mail-Öffnungen und Klicks. Jede Reaktion entspricht einem Trackinglog.
Versandlogs und Trackinglogs werden nach einem bestimmten Zeitraum, der in Adobe Campaign angegeben ist, gelöscht und können geändert werden. Es wird daher dringend empfohlen, die Protokolle regelmäßig zu exportieren.

* **Technische Tabellen**: Erfassen Sie technische Daten, die für den Anwendungsprozess verwendet werden, einschließlich Operatoren und Benutzerrechte (xtkGroup), Ordner (XtkFolder).

>[!NOTE]
>
>Um auf die Beschreibung der einzelnen Tabellen zuzugreifen, gehen Sie zu Admin > Konfiguration > Datenschemata, wählen Sie eine Ressource aus der Liste aus und klicken Sie auf den Tab **Dokumentation** .

Beim Einstieg in Adobe Campaign müssen Sie das Standarddatenmodell bewerten, um zu überprüfen, welche Tabelle für die Speicherung Ihrer Marketing-Daten am besten geeignet ist.

Sie können die standardmäßige Empfängertabelle mit den nativen Feldern verwenden, wie in [diesem Abschnitt](#ootb-profiles) beschrieben. Bei Bedarf können Sie ihn um zwei Mechanismen erweitern:

* [Erweitern einer vorhandenen ](extend-schema.md) Tabelle um neue Felder. Beispielsweise können Sie der Empfängertabelle ein neues Feld &quot;Treueprogramm&quot;hinzufügen.
* [Erstellen Sie eine neue Tabelle](create-schema.md), z. B. eine &quot;Kauf&quot;-Tabelle, in der alle von jedem Profil der Datenbank getätigten Käufe aufgelistet werden, und verknüpfen Sie sie mit der Empfängertabelle.

:bulb: Entdecken Sie Best Practices beim Arbeiten mit dem Campaign-Datenmodell in [diesem Abschnitt](datamodel-best-practices.md).

## Integrierte Profiltabelle {#ootb-profiles}

Die integrierte Empfängertabelle (nmsrecipient) in Adobe Campaign bietet einen guten Ausgangspunkt für die Erstellung Ihres Datenmodells. Es verfügt über eine Reihe vordefinierter Felder und Tabellenlinks, die einfach erweitert werden können. Dies ist besonders nützlich, wenn Sie hauptsächlich Empfänger ansprechen, da es sich um ein einfaches, Empfängerzentriertes Datenmodell handelt.

Die Verwendung der standardmäßigen Empfängertabelle bietet folgende Vorteile:

* Vordefinierte Verwendung von wichtigen Funktionen wie Abonnements, Seed-Listen und mehr
* Bereitstellung einer Marketing-Datenbank mit einem empfängerorientierten Datenmodell
* Schnellere Implementierung
* Einfache Wartung durch Support und Partner

Es ist möglich, die Empfängertabelle zu erweitern, aber nicht die Anzahl der Felder oder Links in der Tabelle zu reduzieren.

:bulb: Erfahren Sie, wie Sie ein vorhandenes Schema in [diesem Abschnitt](extend-schema.md) erweitern.

:arrow_upper_right: Beispiele für integrierte Erweiterungen von Empfängertabellen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

Sie können auch eine andere Empfängertabelle verwenden, um Ihre geschäftlichen oder funktionellen Anforderungen besser zu erfüllen. Diese Methode weist Einschränkungen auf und wird in [diesem Abschnitt](custom-recipient.md) beschrieben.

## Kampagnentabellen und Cloud-Datenbank

Für ein besseres Verständnis der Tabellenverwaltung in Campaign v8 ist zu beachten, dass Tabellen zwischen Campaign und der zugehörigen Snowflake Cloud-Datenbank repliziert werden.

:bulb: Weitere Informationen zu Replikationsstrategie und -mechanismen finden Sie in [diesem Abschnitt](../config/replication.md).

**Verwandte Themen**

:bulb: Informationen zum Importieren von Profilen finden Sie in [diesem Abschnitt](../start/import.md)
:bulb: Weitere Informationen zu Campaign-Zielgruppen finden Sie in [diesem Abschnitt](../start/audiences.md) .

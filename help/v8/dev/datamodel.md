---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit dem Kampagne-Datenmodell
description: Erste Schritte mit dem Kampagne-Datenmodell
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 1%

---

# Erste Schritte mit dem Kampagne-Datenmodell{#gs-ac-datamodel}

Adobe Campaign enthält ein vordefiniertes Datenmodell. Dieser Abschnitt enthält einige Details zu den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Interaktion. Adobe Campaign stützt sich auf eine Cloud-Datenbank mit Tabellen, die miteinander verknüpft sind.

Die Grundstruktur des Adobe Campaign-Datenmodells lässt sich wie folgt beschreiben:

* **Empfänger-Tabelle**: Das Datenmodell basiert auf einer Haupt-Tabelle, die standardmäßig die Empfänger-Tabelle (nmsRecipient) ist. Diese Tabelle ermöglicht die Speicherung aller Marketing-Profil.

   :bulb: Weitere Informationen zur Tabelle &quot;Empfänger&quot;finden Sie unter [dieser Abschnitt](#ootb-profiles).

* **Versand-Tabelle**: Das Datenmodell enthält auch einen Teil, der alle Marketing-Aktivitäten speichert. Normalerweise ist es der Versand-Tisch (NmsDelivery). Jeder Datensatz in dieser Tabelle stellt eine Versand- oder Versandvorlage dar. Es enthält alle erforderlichen Parameter zum Ausführen von Versänden wie Zielgruppe, Inhalt usw.

* **Protokolle**: Diese Tabellen speichern alle Protokolle, die mit der Ausführung der Kampagnen verbunden sind.

   Versandlogs sind Nachrichten, die über alle Kanal an Empfänger oder Geräte gesendet werden. Die Haupt-Tabelle mit Versandlogs (NmsBroadLog) enthält die Versandlogs für alle Empfänger.
Die Haupt-Tabelle &quot;Trackinglogs&quot;(NmsTrackingLog) speichert die Trackinglogs für alle Empfänger. Die Trackinglogs beziehen sich auf Reaktionen von Empfängern wie E-Mail-Öffnungen und Klicks. Jede Reaktion entspricht einem Verfolgungsprotokoll.
Versandlogs und Trackinglogs werden nach einem bestimmten Zeitraum gelöscht, der im Adobe Campaign angegeben ist und geändert werden kann. Daher wird dringend empfohlen, die Stämme regelmäßig zu exportieren.

* **Technische Tabellen**: Erfassen Sie technische Daten, die für den jeweiligen Prozess verwendet werden, einschließlich Operatoren und Benutzerrechte (NmsGroup), Ordner (XtkFolder).

>[!NOTE]
>
>Um die Tabellenbeschreibung aufzurufen, gehen Sie zu Admin > Konfiguration > Data Schemas, wählen Sie eine Ressource aus der Liste und klicken Sie auf die Registerkarte **Dokumentation**.

Wenn Sie mit Adobe Campaign beginnen, müssen Sie das Standarddatenmodell bewerten, um zu prüfen, welche Tabelle am besten zur Speicherung Ihrer Marketingdaten geeignet ist.

Sie können die Standardtabelle für Empfänger mit den vordefinierten Feldern verwenden, wie in [diesem Abschnitt](#ootb-profiles) beschrieben. Bei Bedarf können Sie ihn um zwei Mechanismen erweitern:

* [Erweitern einer vorhandenen ](extend-schema.md) Tabelle mit neuen Feldern Sie können der Tabelle &quot;Empfänger&quot;beispielsweise ein neues Feld &quot;Kundentreue&quot;hinzufügen.
* [Erstellen Sie eine neue Tabelle](create-schema.md), z. B. eine &quot;Einkaufstabelle&quot;, in der alle von den einzelnen Profilen der Datenbank getätigten Käufe aufgelistet sind, und verknüpfen Sie diese mit der Tabelle &quot;Empfänger&quot;.

:bulb: Entdecken Sie Best Practices beim Arbeiten mit Kampagne-Datamodel in [diesem Abschnitt](datamodel-best-practices.md).

## Integrierte Profil-Tabelle {#ootb-profiles}

Die integrierte Empfänger-Tabelle (nmsempfänger) in Adobe Campaign bietet einen guten Ausgangspunkt zum Erstellen Ihres Datenmodells. Es verfügt über eine Reihe vordefinierter Felder und Tabellenlinks, die leicht erweitert werden können. Dies ist besonders dann nützlich, wenn Sie hauptsächlich auf Empfänger abzielen, da es zu einem einfachen Empfänger-orientierten Datenmodell passt.

Die Verwendung der Standardtabelle für Empfänger bietet folgende Vorteile:

* Standardmäßige Arbeit mit Schlüsselfunktionen wie Abonnements, Seed-Listen und mehr
* Bereitstellung einer Marketingdatenbank mit einem Empfänger-orientierten Datenmodell
* Schnellere Implementierung
* Einfache Wartung durch Support und Partner

Es ist möglich, die Tabelle zu erweitern, aber nicht die Anzahl der Empfänger oder Links in der Tabelle zu verringern.

:bulb: Erfahren Sie, wie Sie ein vorhandenes Schema in [diesem Abschnitt](extend-schema.md) erweitern.

:arrow_upper_right: Beispiele für integrierte Empfänger-Tabellenerweiterungen in [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

Sie können auch eine andere Tabelle verwenden, um besser auf Ihre geschäftlichen oder funktionalen Anforderungen zugeschnitten zu sein. Diese Methode hat Einschränkungen und wird in [diesem Abschnitt](custom-recipient.md) beschrieben.

## Kampagne und Cloud-Datenbank

Für ein besseres Verständnis der Tabellenverwaltung in Kampagne v8 beachten Sie, dass Tabellen zwischen der Kampagne und der zugehörigen Snowflake Cloud-Datenbank repliziert werden.

:bulb: Weitere Informationen zu Replikationsstrategien und -mechanismen finden Sie in [diesem Abschnitt](../config/replication.md).

**Verwandte Themen**

:bulb: Entdecken Sie, wie Sie Profil in [diesem Abschnitt](../start/import.md) importieren.
:bulb: Weitere Informationen zu Audiencen der Kampagne finden Sie in [diesem Abschnitt](../start/audiences.md)

---
solution: Campaign v8
product: Adobe Campaign
title: Standardmäßige Empfängertabelle ändern
description: Erfahren Sie, wie Sie mit einer benutzerdefinierten Empfängertabelle arbeiten.
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 93%

---

# Benutzerdefinierte Empfängertabelle verwenden{#gs-ac-custom-recipient}

Adobe Campaign umfasst eine integrierte Profitabelle: **nmsRecipient**. Diese Tabelle beinhaltet eine Reihe vordefinierter Felder und Tabellen, die sich auf unkomplizierte Weise erweitern lassen. Weitere Informationen zu dieser Tabelle finden Sie auf [dieser Seite](datamodel.md#ootb-profiles).

Die integrierte Tabellenerweiterung bietet Flexibilität, lässt jedoch nicht zu, dass einige nicht verwendete Felder oder Links entfernt werden. Wenn Ihr Datenmodell deutlich von Struktur der in Campaign integrierten Empfängertabellen abweicht oder Sie über eine große Zahl von Profilen verfügen, kann daher die Verwendung einer benutzerdefinierten Empfängertabelle sinnvoll sein.  Bei ihrer Implementierung ist allerdings gewisse Vorsicht geboten.

Diese Funktion ermöglicht es Adobe Campaign, Daten aus einer externen Datenbank zu verarbeiten. Diese Daten werden als ein Satz von Profilen für den Versand verwendet. Die Implementierung dieses Prozesses ist mit bestimmten Einschränkungen verbunden, darunter:

* Kein Update-Stream zur und von der Campaign Cloud-Datenbank: Daten aus dieser Tabelle können direkt über die Datenbank-Engine aktualisiert werden, die sie hostet.
* Prozesse, die in der vorhandenen Datenbank ausgeführt werden, müssen stabil sein.
* Bei Verwendung einer Profildatenbank ohne Standardstruktur: Es besteht die Möglichkeit, dass der Versand an in verschiedenen Tabellen mit unterschiedlichen Strukturen gespeicherte Profile erfolgt, wobei eine einzelne Instanz verwendet wird.

In diesem Abschnitt werden die wichtigen Aspekte rund um die Zuordnung vorhandener Tabellen in Adobe Campaign sowie die Konfigurationseinstellungen erläutert, anhand derer Sendungen über jede beliebige Tabelle ausgeführt werden können. Ebenfalls erläutert wird die Erstellung von Abfrageschnittstellen.

>[!CAUTION]
>
>Eine Anpassung von Adobe Campaign sollte nur von erfahrenen Benutzer vorgenommen werden. Voraussetzung hierfür sind Kenntnisse rund um die Erstellung von Eingabeformularen und Schemata.


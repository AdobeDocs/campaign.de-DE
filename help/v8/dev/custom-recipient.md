---
solution: Campaign v8
product: Adobe Campaign
title: Standard-Empfängertabelle ändern
description: Erfahren Sie, wie Sie eine benutzerdefinierte Empfängertabelle verwenden
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 2%

---

# Verwenden einer benutzerdefinierten Empfängertabelle{#gs-ac-custom-recipient}

Adobe Campaign verfügt über eine integrierte Profiltabelle: **nmsRecipient**. Diese Tabelle enthält eine Reihe vordefinierter Felder und Tabellen, die einfach erweitert werden können. Weitere Informationen zu dieser Tabelle finden Sie auf [dieser Seite](datamodel.md#ootb-profiles).

Die integrierte Tabellenerweiterung bietet Flexibilität, lässt jedoch nicht zu, dass einige nicht verwendete Felder oder Links entfernt werden. Daher kann die Verwendung einer benutzerdefinierten Empfängertabelle eine gute Option sein, wenn Ihr Datenmodell sich stark von der integrierten Empfängertabellenstruktur in Campaign unterscheidet oder wenn Sie über eine große Anzahl von Profilen verfügen.  Diese Methode erfordert jedoch bei ihrer Umsetzung bestimmte Vorsichtsmaßnahmen.

Mit dieser Funktion kann Adobe Campaign Daten aus einer externen Datenbank verarbeiten: Diese Daten werden als Profilgruppe für Sendungen verwendet. Die Implementierung dieses Prozesses beinhaltet Einschränkungen wie:

* Kein Update-Stream zur und von der Campaign Cloud-Datenbank: Daten aus dieser Tabelle können direkt über die Datenbank-Engine aktualisiert werden, die sie hostet.
* Prozesse, die auf der vorhandenen Datenbank ausgeführt werden, müssen stabil sein.
* Verwenden einer Profildatenbank mit einer nicht standardmäßigen Struktur: Möglichkeit des Versands an Profilen, die in verschiedenen Tabellen mit unterschiedlichen Strukturen gespeichert sind, mithilfe einer einzigen Instanz.

In diesem Abschnitt werden die Schlüsselpunkte für die Zuordnung vorhandener Tabellen in Adobe Campaign und die Konfigurationseinstellungen beschrieben, die für die Ausführung von Sendungen auf der Basis einer beliebigen Tabelle gelten. Außerdem wird beschrieben, wie Abfragen von Schnittstellen für Endbenutzer erstellt werden.

>[!CAUTION]
>
>Die Anpassung von Adobe Campaign ist erfahrenen Benutzern vorbehalten. Sie erfordert Fachwissen in der Formular- und Schemagestaltung.


---
solution: Campaign Classic
product: campaign
title: Standardtabelle des Empfängers ändern
description: Erfahren Sie, wie Sie eine Tabelle mit benutzerdefiniertem Empfänger verwenden
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
translation-type: tm+mt
source-git-commit: 5b9e381c154420c57a66e5b41b25bd4754036c60
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Verwenden einer benutzerdefinierten Empfängertabelle{#gs-ac-custom-recipient}

Adobe Campaign verfügt über einen integrierten Profil-Tisch: **nmsRecipient**. Diese Tabelle enthält eine Reihe vordefinierter Felder und Tabellen, die leicht erweitert werden können. Weitere Informationen zu dieser Tabelle finden Sie auf [dieser Seite](datamodel.md#ootb-profiles).

Integrierte Tabellenerweiterungen bieten eine gute Flexibilität, aber es ist nicht möglich, nicht verwendete Angebote oder Links zu entfernen. Daher kann die Verwendung einer benutzerdefinierten Empfänger-Tabelle sinnvoll sein, wenn sich Ihr Datenmodell deutlich von der in der Kampagne integrierten Empfänger-Tabellenstruktur unterscheidet oder wenn Sie eine große Anzahl von Profilen haben.  Diese Methode erfordert jedoch bei ihrer Implementierung bestimmte Vorsichtsmaßnahmen.

Mit dieser Funktion kann Adobe Campaign Daten aus einer externen Datenbank verarbeiten: Diese Daten werden als eine Reihe von Profilen für Versand verwendet. Die Implementierung dieses Prozesses beinhaltet Einschränkungen wie:

* Kein Updatestream zur und von der Kampagne Cloud-Datenbank: Daten aus dieser Tabelle können direkt über die Datenbank-Engine aktualisiert werden, die sie hostet.
* Prozesse, die auf der vorhandenen Datenbank ausgeführt werden, müssen stabil sein.
* Verwenden einer Profil-Datenbank mit einer nicht standardmäßigen Struktur: Möglichkeit, Profil, die in verschiedenen Tabellen mit verschiedenen Strukturen gespeichert sind, mit einer einzigen Instanz zu liefern.

In diesem Abschnitt werden die Schlüsselpunkte für die Zuordnung vorhandener Tabellen in Adobe Campaign und die Konfigurationseinstellungen beschrieben, die zum Ausführen von Versänden je nach Tabelle gelten. Außerdem wird beschrieben, wie Sie Abfrageschnittstellen für Endbenutzer entwerfen.


>[!CAUTION]
>
>Die Anpassung des Adobe Campaigns ist nur für erfahrene Benutzer vorgesehen. Es erfordert Expertise im Input Form und Schema Design.


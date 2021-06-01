---
product: Adobe Campaign
title: Datenbankstruktur aktualisieren
description: Datenbankstruktur aktualisieren
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 100%

---

# Datenbankstruktur aktualisieren{#updating-the-database-structure}

Um die an den Schemata vorgenommenen Änderungen anzuwenden, starten Sie den Datenbankaktualisierungs-Assistenten. Auf diesen Assistenten kann über **[!UICONTROL Tools > Erweitert > Datenbank aktualisieren]** zugegriffen werden. Er prüft, ob die physische Struktur der Datenbank mit ihrer logischen Beschreibung übereinstimmt, und führt die SQL-Aktualisierungs-Scripts aus.

![](assets/schema_update.png)

Die Module in der Datenbank werden automatisch ausgefüllt und aktiviert.

![](assets/schema_update_select2.png)

Führen Sie die Schritte aus und sehen Sie sich das SQL-Script für Datenbank-Update an:

![](assets/schema_update2.png)

>[!NOTE]
>
>Es befindet sich in einem Bearbeitungsfeld und kann geändert werden, indem SQL-Code gelöscht oder hinzugefügt wird.

Starten Sie anschließend das Datenbank-Update:

![](assets/schema_update3.png)

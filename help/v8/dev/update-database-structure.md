---
title: Datenbankstruktur aktualisieren
description: Datenbankstruktur aktualisieren
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: ht
source-wordcount: '97'
ht-degree: 100%

---

# Datenbankstruktur aktualisieren{#updating-the-database-structure}

Um die an den Schemata vorgenommenen Änderungen anzuwenden, starten Sie den Datenbankaktualisierungs-Assistenten. Auf diesen Assistenten kann über **[!UICONTROL Tools > Erweitert > Datenbankstruktur aktualisieren]** zugegriffen werden. Er prüft, ob die physische Struktur der Datenbank mit ihrer logischen Beschreibung übereinstimmt, und führt die SQL-Aktualisierungs-Scripts aus.

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

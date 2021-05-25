---
solution: Campaign v8
product: Adobe Campaign
title: Datenbankstruktur aktualisieren
description: Datenbankstruktur aktualisieren
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# Datenbankstruktur{#updating-the-database-structure} aktualisieren

Um die Änderungen an den Schemas anzuwenden, starten Sie den Datenbankaktualisierungs-Assistenten. Auf diesen Assistenten können Sie über **[!UICONTROL Tools > Erweitert > Datenbankstruktur aktualisieren]** zugreifen. Er prüft, ob die physische Struktur der Datenbank mit der logischen Beschreibung übereinstimmt, und führt die SQL-Update-Skripte aus.

![](assets/schema_update.png)

Die Module in der Datenbank werden automatisch ausgefüllt und aktiviert.

![](assets/schema_update_select2.png)

Führen Sie die Schritte aus und zeigen Sie das SQL-Skript zur Datenbankaktualisierung an:

![](assets/schema_update2.png)

>[!NOTE]
>
>Dies befindet sich in einem Bearbeitungsfeld und kann geändert werden, um SQL-Code zu löschen oder hinzuzufügen.

Starten Sie anschließend die Datenbankaktualisierung:

![](assets/schema_update3.png)

---
title: Datenbankstruktur aktualisieren
description: Datenbankstruktur aktualisieren
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: 'https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 61%
---
# Datenbankstruktur aktualisieren {#updating-the-database-structure}

Um die an den Schemata vorgenommenen Änderungen anzuwenden, starten Sie den Datenbankaktualisierungs-Assistenten. Auf diesen Assistenten kann über **[!UICONTROL Tools > Erweitert > Datenbankstruktur aktualisieren]** zugegriffen werden. Er prüft, ob die physische Struktur der Datenbank mit ihrer logischen Beschreibung übereinstimmt, und führt die SQL-Aktualisierungs-Scripts aus.

![Der Assistent zum Aktualisieren von Datenbanken aktualisiert die Seite Parameter mit der Schaltfläche Weiter , um den automatischen Erkennungsprozess zu starten](assets/schema_update.png)

Die Module in der Datenbank werden automatisch ausgefüllt und aktiviert.

![Datenbankaktualisierungs-Assistent Tabellen bearbeiten Seitenlistentabellen bearbeiten, wobei die CusContracts-Tabelle auf „Synchronisieren“ gesetzt ist](assets/schema_update_select2.png)

Führen Sie die Schritte aus und sehen Sie sich das SQL-Script für Datenbank-Update an:

![Aktualisierungsassistent für Datenbankaktualisierungen Seite mit dem SQL CREATE TABLE-Skript für CusContracts](assets/schema_update2.png)

>[!NOTE]
>
>Es befindet sich in einem Bearbeitungsfeld und kann geändert werden, indem SQL-Code gelöscht oder hinzugefügt wird.

Starten Sie anschließend das Datenbank-Update:

![Datenbankaktualisierungs-Assistent : Starten Sie die Seite für die Datenbankaktualisierung, wobei das Protokoll den Abschluss der Aktualisierung bei 100 % anzeigt](assets/schema_update3.png)

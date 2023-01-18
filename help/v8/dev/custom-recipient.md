---
title: Ändern der standardmäßigen Empfängertabelle
description: Erfahren Sie, wie Sie mit einer benutzerdefinierten Empfängertabelle arbeiten.
feature: Custom Resources, Profiles
role: User, Developer
level: Beginner, Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 87%

---

# Verwenden einer benutzerdefinierten Empfängertabelle{#gs-ac-custom-recipient}

Adobe Campaign umfasst eine integrierte Profitabelle: **nmsRecipient**. Diese Tabelle beinhaltet eine Reihe vordefinierter Felder und Tabellen, die sich leicht erweitern lassen. Weitere Informationen zu dieser Tabelle finden Sie auf [dieser Seite](datamodel.md#ootb-profiles).

Die integrierte Erweiterung für Tabellen ist zwar sehr flexibel, bietet aber keine Möglichkeit, nicht verwendete Angebote oder Links zu entfernen. Wenn Ihr Datenmodell deutlich von Struktur der in Campaign integrierten Empfängertabellen abweicht oder Sie über eine große Zahl von Profilen verfügen, kann daher die Verwendung einer benutzerdefinierten Empfängertabelle sinnvoll sein.  Bei ihrer Implementierung ist allerdings gewisse Vorsicht geboten.

![](../assets/do-not-localize/book.png) Erfahren Sie, wie Sie Ihre Instanz so konfigurieren, dass eine benutzerdefinierte Empfängertabelle verwendet wird in [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html?lang=de){target="_blank"}.
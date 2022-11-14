---
title: Audiences für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Audiences für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# Audiences für Adobe Experience Cloud-Lösungen freigeben{#shared-audiences}

Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Import von Audiences/Segmenten aus den verschiedenen Lösungen der Adobe Experience Cloud in Adobe Campaign. Der Import von Audiences erfolgt in Adobe Campaign in Listen.

* Export von Listen in Form von Adobe Experience Cloud-Audiences. Diese Audiences können dann in den anderen von Ihnen verwendeten Lösungen der Adobe Experience Cloud genutzt werden. Der Export von Audiences erfolgt innerhalb eines Workflows im Anschluss an eine Audience-Bestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppe]**.

Diese Integration unterstützt zwei Arten von Adobe Experience Cloud-Kennungen:

* **Besucher-ID**: Diese Kennung ermöglicht die Abstimmung der Adobe Experience Cloud-Besuchenden mit den Adobe Campaign-Empfangenden.
* **Declared ID**: Diese Kennung gleicht alle Arten von Daten mit Elementen aus der Adobe Campaign-Datenbank ab. Es handelt sich um den vordefinierten Abstimmschlüssel in Adobe Campaign.

   >[!NOTE]
   >
   > Eine Declared ID-Datenquelle kann auch mit der People Core Service-Integration verwendet werden.
   >
   >Wenn Sie die People Core Service-Integration verwenden und die Audience Manager-Integration hinzufügen möchten, benötigen Sie die Hilfe eines Beraters für Adobe Audience Manager, um zu vermeiden, dass alle ID-Synchronisationen verloren gehen, die beim Wechsel zu dieser Declared ID-Datenquelle in einem Adobe Audience Manager-Kontext erfasst wurden.

Siehe:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de)

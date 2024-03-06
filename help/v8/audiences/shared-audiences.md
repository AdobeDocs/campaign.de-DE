---
title: Zielgruppen für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Zielgruppen für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 88%

---

# Zielgruppen für Adobe Experience Cloud-Lösungen freigeben{#shared-audiences}

Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Import von Audiences/Segmenten aus den verschiedenen Lösungen der Adobe Experience Cloud in Adobe Campaign. Der Import von Audiences erfolgt in Adobe Campaign in Listen.

* Export von Listen in Form von freigegebenen Adobe Experience Cloud-Zielgruppen. Diese Zielgruppen können in den verschiedenen von Ihnen verwendeten Adobe Experience Cloud-Lösungen verwendet werden. Der Export von Zielgruppen erfolgt innerhalb eines Workflows im Anschluss an eine Zielgruppenbestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppen]**.

Diese Integration unterstützt zwei Arten von Adobe Experience Cloud-Kennungen:

* **Besucher-ID**: Diese Kennung ermöglicht die Abstimmung der Adobe Experience Cloud-Besuchenden mit den Adobe Campaign-Empfangenden.
* **Declared ID**: Diese Kennung stimmt alle Arten von Daten mit Elementen aus der Adobe Campaign-Datenbank ab. Es handelt sich um den vordefinierten Abstimmschlüssel in Adobe Campaign.

  >[!NOTE]
  >
  > Eine Declared ID-Datenquelle kann auch mit der People Core Service-Integration verwendet werden.
  >
  >Wenn Sie die People Core Service-Integration verwenden und die Audience Manager-Integration hinzufügen möchten, benötigen Sie die Hilfe eines Beraters für Adobe Audience Manager, um zu vermeiden, dass alle ID-Synchronisationen verloren gehen, die beim Wechsel zu dieser Declared ID-Datenquelle in einem Adobe Audience Manager-Kontext erfasst wurden.

Siehe:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de)

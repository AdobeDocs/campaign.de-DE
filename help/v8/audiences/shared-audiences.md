---
title: Zielgruppen für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Zielgruppen für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 84%

---

# Zielgruppen für Adobe Experience Cloud-Lösungen freigeben{#shared-audiences}

Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Import von Audiences/Segmenten aus den verschiedenen Lösungen der Adobe Experience Cloud in Adobe Campaign. Der Import von Audiences erfolgt in Adobe Campaign in Listen.

* Exportieren Sie Listen in Form von freigegebenen Adobe Experience Cloud-Zielgruppen. Diese Zielgruppen können in den verschiedenen Adobe Experience Cloud-Lösungen verwendet werden, die Sie verwenden. Der Export von Zielgruppen erfolgt innerhalb eines Workflows im Anschluss an eine Zielgruppenbestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppen]**.

Diese Integration unterstützt zwei Arten von Adobe Experience Cloud-Kennungen:

* **Besucher-ID**: Diese Kennung ermöglicht die Abstimmung der Adobe Experience Cloud-Besuchenden mit den Adobe Campaign-Empfangenden.
* **Declared ID**: Diese Kennung stimmt alle Arten von Daten mit Elementen aus der Adobe Campaign-Datenbank ab. Es handelt sich um den vordefinierten Abstimmschlüssel in Adobe Campaign.

  >[!NOTE]
  >
  > Eine Declared ID-Datenquelle kann auch mit der People Core Service-Integration verwendet werden.
  >
  >Wenn Sie die People Core Service-Integration verwenden und die Audience Manager-Integration hinzufügen möchten, benötigen Sie die Hilfe einer Beraterin bzw. eines Beraters für Adobe Audience Manager, um zu vermeiden, dass alle ID-Synchronisationen verloren gehen, die beim Wechsel zu dieser Declared ID-Datenquelle in einem Adobe Audience Manager-Kontext erfasst wurden.

Siehe:

[Adobe Audience Manager-Wissensdatenbank](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de){target="_blank"}.

[Komponentenhandbuch für die zentrale Adobe Experience Cloud-Benutzeroberfläche](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de){target="_blank"}.

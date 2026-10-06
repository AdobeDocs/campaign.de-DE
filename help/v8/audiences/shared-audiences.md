---
title: Zielgruppen für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Zielgruppen für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 95%
---
# Zielgruppen für Adobe Experience Cloud-Lösungen freigeben{#shared-audiences}

Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Importen Sie Zielgruppen/Segmente aus den verschiedenen Adobe Experience Cloud-Lösungen in Adobe Campaign. Zielgruppen können über Listen in Adobe Campaign importiert werden.

* Exportieren Sie Listen in Form von freigegebenen Adobe Experience Cloud-Zielgruppen. Diese Zielgruppen können dann in den anderen von Ihnen verwendeten Adobe Experience Cloud-Lösungen genutzt werden. Der Export von Zielgruppen erfolgt innerhalb eines Workflows im Anschluss an eine Zielgruppenbestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppen]**.

Diese Integration unterstützt zwei Arten von Adobe Experience Cloud-IDs:

* **Besucher-ID**: Diese Kennung ermöglicht die Abstimmung der Adobe Experience Cloud-Besuchenden mit den Adobe Campaign-Empfangenden.
* **Declared ID**: Diese Kennung stimmt alle Arten von Daten mit Elementen aus der Adobe Campaign-Datenbank ab. Es handelt sich um den vordefinierten Abstimmschlüssel in Adobe Campaign.

  >[!NOTE]
  >
  > Eine Declared ID-Datenquelle kann auch mit der People Core Service-Integration verwendet werden.
  >
  >Wenn Sie die People Core Service-Integration verwenden und die Audience Manager-Integration hinzufügen möchten, benötigen Sie die Hilfe einer Beraterin bzw. eines Beraters für Adobe Audience Manager, um zu vermeiden, dass alle ID-Synchronisationen verloren gehen, die beim Wechsel zu dieser Declared ID-Datenquelle in einem Adobe Audience Manager-Kontext erfasst wurden.

Siehe:

[Adobe Audience Manager-Wissensdatenbank](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de){target="_blank"}.

[Handbuch zu Komponenten der zentralen Benutzeroberfläche von Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de){target="_blank"}.

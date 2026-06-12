---
title: Zielgruppen für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Zielgruppen für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences
role: User
level: Beginner
hide: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
TQID: https://experienceleague.adobe.com/Q7eY7lPXlHWEcaj-Hx4Bbqj-hwzMvrlxGGYeN5AxzRE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: b285c321f3b905150b31621941ea99608d627739
workflow-type: tm+mt
source-wordcount: 270
ht-degree: 83%

---

# Zielgruppen für Adobe Experience Cloud-Lösungen freigeben{#shared-audiences}


Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Importieren Sie freigegebene Audiences/Segmente aus verschiedenen Adobe Experience Cloud-Lösungen in Adobe Campaign. Zielgruppen können über Listen in Adobe Campaign importiert werden.

* Exportieren Sie Listen in Form von Adobe Experience Cloud-Audiences. Diese Zielgruppen können dann in den anderen von Ihnen verwendeten Adobe Experience Cloud-Lösungen genutzt werden. Der Export von Zielgruppen erfolgt innerhalb eines Workflows im Anschluss an eine Zielgruppenbestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppen]**.

Diese Integration unterstützt zwei Arten von Adobe Experience Cloud-IDs:

* **Besucher-ID**: Dieser Kennungstyp ermöglicht die Abstimmung der Adobe Experience Cloud-Besucher mit den Adobe Campaign-Empfängern.
* **Declared ID**: Dieser Kennungstyp ermöglicht die Abstimmung aller Datentypen mit Elementen aus der Adobe Campaign-Datenbank. Er wird in Adobe Campaign als vordefinierter Abstimmschlüssel dargestellt.

  >[!NOTE]
  >
  > Eine Declared ID-Datenquelle kann jetzt auch mit der Integration des People Core Service verwendet werden.
  >
  >Wenn Sie die People Core Service-Integration verwenden und die Audience Manager-Integration hinzufügen möchten, benötigen Sie die Hilfe einer Beraterin bzw. eines Beraters für Adobe Audience Manager, um zu vermeiden, dass alle ID-Synchronisationen verloren gehen, die beim Wechsel zu dieser Declared ID-Datenquelle in einem Adobe Audience Manager-Kontext erfasst wurden.

Siehe:

[Dokumentation zu Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de){target="_blank"}

[Handbuch der Komponenten der zentralen Benutzeroberfläche von Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de){target="_blank"}


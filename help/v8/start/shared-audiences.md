---
title: Zielgruppen für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Zielgruppen für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 85%

---

# Zielgruppen für Adobe Experience Cloud-Lösungen freigeben{#shared-audiences}


Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Import von Audiences/Segmenten aus den verschiedenen Lösungen der Adobe Experience Cloud in Adobe Campaign. Der Import von Audiences erfolgt in Adobe Campaign in Listen.

* Export von Listen in Form von freigegebenen Adobe Experience Cloud-Zielgruppen. Diese Zielgruppen können in den verschiedenen von Ihnen verwendeten Adobe Experience Cloud-Lösungen verwendet werden. Der Export von Zielgruppen erfolgt innerhalb eines Workflows im Anschluss an eine Zielgruppenbestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppen]**.

Diese Integration unterstützt zwei Arten von Adobe Experience Cloud-Kennungen:

* **Besucher-ID**: Dieser Kennungstyp ermöglicht die Abstimmung der Adobe Experience Cloud-Besucher mit den Adobe Campaign-Empfängern.
* **Declared ID**: Dieser Kennungstyp ermöglicht die Abstimmung aller Datentypen mit Elementen aus der Adobe Campaign-Datenbank. Er wird in Adobe Campaign als vordefinierter Abstimmschlüssel dargestellt.

  >[!NOTE]
  >
  > Eine Declared ID-Datenquelle kann jetzt auch mit der Integration des People Core Service verwendet werden.
  >
  >Wenn Sie die People Core Service-Integration verwenden und die Audience Manager-Integration hinzufügen möchten, benötigen Sie die Hilfe einer Beraterin bzw. eines Beraters für Adobe Audience Manager, um zu vermeiden, dass alle ID-Synchronisationen verloren gehen, die beim Wechsel zu dieser Declared ID-Datenquelle in einem Adobe Audience Manager-Kontext erfasst wurden.

Siehe:

[Adobe Audience Manager-Dokumentation](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=de){target="_blank"}

[Komponentenleitfaden für die zentrale Adobe Experience Cloud-Benutzeroberfläche](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=de){target="_blank"}

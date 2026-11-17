---
title: Zielgruppen für Adobe Experience Cloud-Lösungen freigeben
description: Erfahren Sie, wie Sie Zielgruppen für Adobe Experience Cloud-Lösungen freigeben können
feature: Audiences
role: User
level: Beginner
hide: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
TQID: 'https://experienceleague.adobe.com/Q7eY7lPXlHWEcaj-Hx4Bbqj-hwzMvrlxGGYeN5AxzRE'
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: edaf625cfe93558dcbfa8570646633ab1bbf3adc
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 82%
---
# Audiences für [!DNL Adobe CX Enterprise] Lösungen freigeben{#shared-audiences}


Option 1: AEP-Quellen und -Ziele

Option 2: Adobe Personen/AAM

Sie können **Adobe Campaign** mit **People Core Service** oder Adobe Audience Manager integrieren. Anschließend können Sie:

* Importieren Sie freigegebene Audiences/Segmente aus verschiedenen [!DNL CX Enterprise]-Lösungen in Adobe Campaign. Zielgruppen können über Listen in Adobe Campaign importiert werden.

* Exportieren Sie Listen in Form [!DNL CX Enterprise] freigegebenen Audiences. Diese Zielgruppen können in den verschiedenen [!DNL CX Enterprise]-Lösungen verwendet werden, die Sie verwenden. Der Export von Zielgruppen erfolgt innerhalb eines Workflows im Anschluss an eine Zielgruppenbestimmung mithilfe der dedizierten Aktivität **[!UICONTROL Aktualisierung freigegebener Zielgruppen]**.

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


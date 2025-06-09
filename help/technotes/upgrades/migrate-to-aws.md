---
title: Migrieren der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS)
description: Migrieren der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 98%

---

# Migration der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Was hat sich geändert?{#aws-changes}

Im Rahmen unserer kontinuierlichen Bemühungen, einen qualitativ hochwertigen E-Mail-Versand bereitzustellen, wird die Campaign-E-Mail-Versandinfrastruktur von Adobe-gehosteten Rechenzentren zu Amazon Web Services (AWS) verschoben.

Dieser Schritt gewährleistet hohe Verfügbarkeit, optimalen Durchsatz und die Möglichkeit, die Skalierung an die Bedürfnisse unserer Kundinnen und Kunden anzupassen.

## Sind Sie betroffen?{#aws-impact}

Diese Änderung betrifft:

* gehostete und hybride Kundinnen und Kunden von Campaign Classic v7
* Kundinnen und Kunden von Campaign Managed Services
* alle Kundinnen und Kunden von Campaign-v8
* Kundinnen und Kunden von Campaign Standard

## Wann wird diese Migration stattfinden?{#aws-timeline}

Die Migration der Entwicklungs- und Staging-Umgebungen erfolgt im **Oktober 2023**.

Die Migration der Produktionsumgebungen beginnt im **Januar 2024**. Weitere Einzelheiten werden zu gegebener Zeit bekannt gegeben.

Als Campaign-Kundin oder -Kunde erhalten Sie bei der Planung der Migrationswellen zusätzliche Benachrichtigungen. Benachrichtigungen werden mindestens 7 Tage vor der Migration der Staging-Umgebungen und mindestens 30 Tage vor der Migration der Produktionsumgebungen gesendet.

## Wie wirkt sich das aus?{#impact}

Dieser Schritt wird für die Kundinnen und Kunden transparent sein:

* Die Länge der einzelnen Migrationswellen variiert je nach der Anzahl der betroffenen Campaign-Instanzen. Wenn eine Migrationswelle geplant ist, enthält die Benachrichtigung die erwartete Dauer.

* Campaign-Instanzen können während des Migrationsfensters keine E-Mails senden. Andere Campaign-Funktionen sind nicht betroffen.


## Häufig gestellte Fragen {#aws-faq}

* **Warum ist dieses Upgrade obligatorisch?**

  Adobe plant die Stilllegung des alten Rechenzentrums. Die dort ausgeführten Adobe Campaign-Instanzen müssen in das neue Referenz-Rechenzentrum, Amazon Web Services (AWS) übertragen werden.

  Die Adobe Managed Services-Cloud wird auf Amazon Web Services (AWS) gehostet, einer modernen, sicheren und optimierten Umgebung. [Weitere Informationen zu Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Für welche Kundinnen und Kunden gilt diese Migration?**

  Bei allen Kundinnen und Kunden von Campaign v8, hybridem und gehostetem Campaign Classic v7 sowie Campaign Managed Services wird die Migration der Umgebungen durchgeführt. Auch Kundinnen und Kunden von Campaign Standard sind betroffen.

* **Mit welcher Ausfallzeit ist zu rechnen?**

  Die Migration dauert vermutlich zwischen 30 Minuten und 60 Minuten. Die Länge jedes Migrationsschritts variiert jedoch je nach Anzahl der betroffenen Campaign-Instanzen. Wenn eine Migrationswelle geplant ist, enthält die Benachrichtigung die erwartete Dauer.

* **Gibt es Maßnahmen, die auf Kundenseite für diese Migration getroffen werden müssen?**

  Es sind keine Aktionen erforderlich, da die Migration automatisch von Adobe ausgeführt wird.

* **Welche Validierungen müssen auf Kundenseite ausgeführt werden?**

  Für diese Migration sind keine spezifischen Tests erforderlich. Falls ein Problem festgestellt wird, wenden Sie sich bitte an die [Adobe-Kundenunterstützung](https://experienceleague.adobe.com/?support-solution=Campaign&amp;lang=de#support){target="_blank"}.


* **Kann ich eine Änderung des geplanten Zeitfensters für das Sicherheits-Update anfordern?**

  Da es sich um eine obligatorische Migration handelt, können wir keine Änderungen am bestehenden Zeitplan vornehmen.

Für alle anderen Fragen wenden Sie sich bitte an die [Adobe-Kundenunterstützung](https://experienceleague.adobe.com/?support-solution=Campaign&amp;lang=de#support){target="_blank"}.

---
title: Migrieren der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS)
description: Migrieren der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: 3a8fd0a0c721d03f1818dce45b58a841284bbb00
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 20%

---


# Campaign - Versand der Infrastrukturmigration nach Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Was hat sich geändert?{#aws-changes}

Im Rahmen unserer kontinuierlichen Bemühungen, einen qualitativ hochwertigen E-Mail-Versand bereitzustellen, wird die Campaign-E-Mail-Versand-Infrastruktur von Adobe-gehosteten Rechenzentren nach Amazon Web Services (AWS) verschoben.

Dieser Schritt gewährleistet hohe Verfügbarkeit, optimalen Durchsatz und die Möglichkeit, die Skalierung an die Bedürfnisse unserer Kunden anzupassen.

## Sind Sie betroffen?{#aws-impact}

Diese Änderung betrifft:

* Campaign Classic v7 gehostete und hybride Kunden
* Campaign Managed Services-Kunden
* Alle Campaign v8-Kunden

## Wann wird diese Migration stattfinden?{#aws-timeline}

Die Migration der Entwicklungs- und Staging-Umgebungen erfolgt in **Oktober 2023**.

Die Migration der Produktionsumgebungen ist für den Beginn in **Januar 2024**. Weitere Informationen werden im nächsten Schritt des Datums bereitgestellt.

Als Campaign-Kunde erhalten Sie bei der Planung der Migrationswellen eine zusätzliche Benachrichtigung. Benachrichtigungen werden mindestens 7 Tage vor der Migration für Staging-Umgebungen und mindestens 30 Tage vor der Migration für Produktionsumgebungen gesendet.

## Wie wirkt sich das aus?{#impact}

Dieser Schritt wird für die Kunden transparent sein:

* Die Migration wird voraussichtlich zwischen 30 Minuten und 60 Minuten dauern

* Campaign-Instanzen können während des Migrationsfensters keine E-Mails senden. Andere Campaign-Funktionen sind nicht betroffen.


## Häufig gestellte Fragen {#aws-faq}

* **Warum ist dieses Upgrade obligatorisch?**

  Die neue Campaign-Versandinfrastruktur, die von Adobe Web Services (AWS) gehostet wird, verbessert die Qualität und Zuverlässigkeit für unsere Kunden. Es bietet außerdem eine starke und moderne Infrastruktur, um eine bessere Verfügbarkeit und optimalen Durchsatz zu gewährleisten.

* **Welche Kunden sind für diese Migration vorgesehen?**

  Bei allen Campaign v8-Kunden und Campaign Classic v7-Hybrid-, gehosteten und Campaign Managed Services-Kunden wird die Migration ihrer Umgebungen durchgeführt.

* **Mit welcher Ausfallzeit ist zu rechnen?**

  Die erwartete Ausfallzeit liegt zwischen 30 und 60 Minuten.

* **Gibt es vom Kunden für die Migration erforderliche Aktionen?**

  Es sind keine Aktionen erforderlich, da die Migration automatisch durch Adobe ausgeführt wird.

* **Welche Validierungen müssen von den Kunden ausgeführt werden?**

  Für diese Migration sind keine spezifischen Tests erforderlich. Falls ein Problem festgestellt wird, wenden Sie sich bitte an die [Adobe-Kundenunterstützung](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **Kann ich eine Änderung des geplanten Zeitfensters für das Sicherheits-Update anfordern?**

  Da es sich um eine obligatorische Migration handelt, empfehlen wir dringend, sich an den vorhandenen Zeitplan anzupassen.


Für alle anderen Fragen wenden Sie sich bitte an die [Adobe-Kundenunterstützung](https://experienceleague.adobe.com/?support-solution=Campaign#support).

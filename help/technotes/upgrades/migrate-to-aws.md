---
title: Migrieren der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS)
description: Migrieren der Campaign-Versandinfrastruktur zu Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: 53080e3641e0070b0b6e47d1ec8b55b4c7aa2b1a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Campaign - Versand der Infrastrukturmigration nach Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Was hat sich geändert?{#aws-changes}

Im Rahmen unserer kontinuierlichen Bemühungen, einen qualitativ hochwertigen E-Mail-Versand bereitzustellen, wird die Campaign-E-Mail-Versand-Infrastruktur von Adobe-gehosteten Rechenzentren nach Amazon Web Services (AWS) verschoben.

Dieser Schritt gewährleistet hohe Verfügbarkeit, optimalen Durchsatz und die Möglichkeit, die Skalierung an die Bedürfnisse unserer Kunden anzupassen.

## Sind Sie betroffen?{#aws-impact}

Als v8-Kunde oder als gehosteter, hybrider oder Managed Services Campaign-Kunde von v7 sind Sie betroffen.

## Wann wird diese Migration stattfinden?{#aws-timeline}

Die Migration der Entwicklungs- und Staging-Umgebungen erfolgt in **Oktober 2023**.

Die Migration der Produktionsumgebungen ist für den Beginn in **Januar 2024**. Weitere Informationen werden im nächsten Schritt des Datums bereitgestellt.

Als Campaign-Kunde erhalten Sie bei der Planung der Migrationswellen eine zusätzliche Benachrichtigung. Die Benachrichtigungen werden mindestens sieben Tage vor der Migration gesendet.

## Wie wirkt sich das aus?{#impact}

Dieser Schritt wird für die Kunden transparent sein:

* Das Senden von IPs und der Campaign-Build-Version bleibt unverändert wie vor dem Umstieg.

* Während des Migrationsfensters können Campaign-Instanzen keine E-Mails senden. Andere Campaign-Funktionen sind nicht betroffen.

* Alle E-Mails, die vor dem Wartungsfenster in die Warteschlange gestellt werden, müssen erneut gesendet werden.

>[!NOTE]
>
>Wenden Sie sich bei Fragen zu dieser Migration an Ihren Adobe-Support-Mitarbeiter oder wenden Sie sich an [Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>



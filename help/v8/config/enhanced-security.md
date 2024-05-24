---
title: Campaign-Add-on für verbesserte Sicherheit
description: Erste Schritte mit dem Campaign-Add-on für verbesserte Sicherheit
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 55c16fe19125ea54035a8f97928484c7baea161b
workflow-type: ht
source-wordcount: '753'
ht-degree: 100%

---


# Campaign-Add-on für verbesserte Sicherheit {#enhanced-security}

Um die Netzwerkverbindung sicherer zu machen und die Sicherheit Ihrer Ressourcen zu verbessern, bietet [!DNL Adobe Campaign] ein neues Add-on für **verbesserte Sicherheit**.

Dieses Add-on umfasst zwei Ökosystemfunktionen:

* [Sichere CMK-Integration (Customer Managed Key)](#secure-cmk-integration)

* [Sicheres VPN-Tunneling (Virtual Private Network)](#secure-vpn-tunneling)

Diese Funktionen werden nachfolgend beschrieben.

Auf dieser Seite finden Sie einige Schutzmechanismen und Einschränkungen in Bezug auf die erweiterten Sicherheitsfunktionen. Außerdem sollten Sie sicherstellen, dass alle Anwendungsfälle für die sichere CMK-Integration bzw. das sichere VPN-Tunneling funktionieren.

Nach der Implementierung dieser Funktionen überwacht Adobe Folgendes:

* die Verfügbarkeit Ihrer Instanz und sendet eine Warnmeldung, wenn der Schlüssel nicht verfügbar ist.

* die VPN-Tunnel und sendet eine Warnmeldung, falls ein Problem auftritt.

## Sichere CMK-Integration (Customer Managed Key) {#secure-cmk-integration}

Die **sichere CMK-Integration (Customer Managed Key)** ermöglicht es Ihnen, ruhende Daten mithilfe Ihres eigenen Schlüssels über Ihr Amazon Web Services(AWS)-Konto zu verschlüsseln.

Kundenverwaltete Schlüssel sind KMS-Schlüssel (Key Management Service) in Ihrem AWS-Konto, die Sie erstellen, besitzen und verwalten. Sie haben die volle Kontrolle über diese KMS-Schlüssel und verwenden sie zum Verschlüsseln und Entschlüsseln von Daten. Indem Sie die Verantwortung für die Generierung und Verwaltung von Verschlüsselungsschlüsseln übernehmen, erhalten Sie dank dieser Kapazität mehr Kontrolle über diese Schlüssel, einschließlich des Widerrufs eines Schlüssels.

>[!CAUTION]
>
>Wenn Sie einen Schlüssel widerrufen, müssen Sie sich der Auswirkungen bewusst sein. [Weitere Informationen](#cmk-callouts)

Um die CMK-Integration in Campaign zu aktivieren, führen Sie die folgenden Schritte aus:

1. Verbinden Sie sich mit Ihrem [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}-Konto.

1. Generieren Sie mithilfe des AWS Key Management Service (KMS) einen Schlüssel mit automatischer Rotation. [Weitere Informationen dazu](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Wenden Sie die von Adobe bereitgestellte Regel auf Ihr AWS-Konto an, um Zugriff auf Ihre Ressourcen zu gewähren. [Weitere Informationen dazu](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Teilen Sie Ihren [Amazon-Ressourcennamen (Schlüssel-ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} mit [!DNL Adobe Campaign]. Wenden Sie sich dazu an den Adobe-Support. <!--or Adobe transition manager?-->

1. Erstellen und testen Sie die Amazon EventBridge-Regeln, um die Überwachung Ihrer Schlüssel durch Adobe zu aktivieren. [Weitere Informationen](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### Schutzmechanismen und Einschränkungen {#cmk-callouts}

Die folgenden Schutzmechanismen und Einschränkungen gelten für die CMK-Integration mit Adobe Campaign v8:

* Adobe stellt kein [Amazon Web Services (AWS)-Konto](https://aws.amazon.com/){target="_blank"} bereit. Sie müssen über ein eigenes AWS-Konto verfügen und dieses so einrichten, dass es Ihren Schlüssel generiert und für Adobe freigibt.

* Nur [AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS)-Schlüssel werden unterstützt. Es können keine Schlüssel verwendet werden, die von Kundinnen und Kunden außerhalb von KMS erzeugt wurden.&#x200B;

* Bei der Ersteinrichtung ist mit Ausfallzeiten zu rechnen.Die Dauer der Ausfallzeit hängt von der Größe Ihrer Datenbank ab.

* Als Kundin bzw. Kunde besitzen und verwalten Sie den Schlüssel. Bei jeder Änderung Ihres Schlüssels müssen Sie sich an Adobe wenden.

* Sie können Ihren Schlüssel mit [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} überprüfen und ihn bei Bedarf widerrufen.&#x200B;

* Wenn Sie den Schlüssel widerrufen, deaktivieren oder löschen, wird der Zugriff auf Ihre verschlüsselten Ressourcen und Ihre Instanz gesperrt, bis Sie die entsprechende Aktion rückgängig machen.

  >[!CAUTION]
  >
  >Wenn Sie den Schlüssel deaktivieren und diese Aktion nicht innerhalb von 7 Tagen rückgängig machen, kann Ihre Datenbank nur aus einem Backup wiederhergestellt werden.
  >
  >Wenn Sie den Schlüssel löschen und diese Aktion nicht innerhalb von 30 Tagen rückgängig machen, werden alle Ihre Daten dauerhaft gelöscht und gehen verloren.&#x200B;

## Sicheres Virtual-Private-Network-Tunneling {#secure-vpn-tunneling}

Das **sichere Virtual Private Network(VPN)-Tunneling** ist ein VPN von einer Site zur anderen, das einen sicheren Zugang für Ihre sich im Transit befindlichen Daten über ein privates Netzwerk von Ihrem Standort zur [!DNL Adobe Campaign]-Instanz bietet.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Um eine hohe Verfügbarkeit (HA, High Availability), zu gewährleisten, verwendet es zwei Tunnel, um im Falle eines Problems in einem Tunnel einen Ausfall zu vermeiden.

Die folgenden drei Anwendungsfälle werden unterstützt:

* Federated Data Access (FDA) über VPN, um von der Campaign-Instanz über VPN auf Ihre On-Premise-Datenbank zuzugreifen

* Instanz-Login über ein VPN von einem Thick Client

* Instanz-SFTP-Zugriff über ein VPN

>[!CAUTION]
>
>Nur On-Premise-Datenbanken und AWS-konforme VPN-Geräte werden unterstützt. [Weitere Informationen](#vpn-callouts)

Um die ordnungsgemäße Verwendung dieser Funktion sicherzustellen, befolgen Sie die folgenden Richtlinien:

* Richten Sie auf Ihrer Seite das VPN auf der Grundlage der VPN-Konfiguration auf der Adobe-Seite ein.

* Lassen Sie beide Tunnel für hohe Verfügbarkeit aktiv.

* Überwachen Sie den Tunnel auf Ihrer Seite.

* Sie müssen Initiator des Tunnels sein und in der Lage sein, die Verbindung neu zu initiieren, wenn der Tunnel unterbrochen wird.

* Richten Sie auf Ihrer Seite einen Mechanismus zum erneuten Aufbau der Verbindung ein, falls diese ausfällt.


### Schutzmechanismen und Einschränkungen {#vpn-callouts}

Die folgenden Schutzmechanismen und Einschränkungen gelten für die VPN-Tunnelintegration mit Adobe Campaign v8:

* Es werden nur On-Premise-Datenbanken unterstützt, wie <!--Richa to check the list with PM-->:

   * MySQL
   * Netezza
   * Oracle
   * SAP HANA
   * SQL Server
   * Sybase
   * Teradata
   * Hadoop über HiveSQL

* Es werden nur AWS-konforme VPN-Geräte unterstützt. Eine Liste kompatibler Geräte finden Sie auf [dieser Seite](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* VPN-Verbindungen zu Drittanbietern oder externen Anbietern werden nicht unterstützt.

* Von Adobe verwaltete zusätzliche VPNs für private Cloud-Datenbanken sind nicht enthalten.

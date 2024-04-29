---
title: Verbessertes Sicherheits-Add-on
description: Erste Schritte mit dem Campaign Enhanced Security-Add-on
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: cec935c2c73e3df4d2e03d54305004df9bd2655e
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---


# Verbessertes Sicherheits-Add-on {#enhanced-security}

Um die Netzwerkverbindung sicherer zu machen und die Sicherheit Ihrer Ressourcen zu verbessern, [!DNL Adobe Campaign] bietet eine neue **Verbesserte Sicherheit** -Add-on.

Dieses Add-on umfasst derzeit zwei Ökosystemfunktionen:

* [Sichere CMK-Integration](#secure-cmk-integration)

* [Sicheres VPN-Tunneln](#secure-vpn-tunneling)

## Sichere CMK-Integration {#secure-cmk-integration}

**Sichere Integration von kundenverwaltetem Schlüssel (CMK)** ermöglicht Ihnen, Ihre Instanz und Ihre Daten mithilfe Ihres eigenen Schlüssels über Ihr AWS-Konto zu verschlüsseln<!--instead of Adobe-owned keys-->. Indem Sie die Verantwortung für die Generierung und Verwaltung von Verschlüsselungsschlüsseln übernehmen, können Sie mit dieser Kapazität mehr Kontrolle über diese Schlüssel haben, einschließlich der Sperrung eines Schlüssels.

>[!CAUTION]
>
>Wenn Sie einen Schlüssel widerrufen, müssen Sie sich der Auswirkungen bewusst sein. [Weitere Informationen](#cmk-callouts)

Gehen Sie wie folgt vor, um diese Funktion zu aktivieren:

1. Vergewissern Sie sich, dass Sie [AWS](https://aws.amazon.com/){target="_blank"} -Konto.

1. Generieren Sie mithilfe des AWS Key Management Service (KMS) einen Schlüssel mit automatischer Rotation. [Erfahren Sie mehr](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}

1. Wenden Sie die von Adobe bereitgestellte Richtlinie auf Ihr AWS-Konto an, um Zugriff auf Ihre Ressourcen zu gewähren. [Weitere Infos](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"} <!--link TBC-->

1. Geben Sie Ihren Amazon-Ressourcennamen (key ARN) für [!DNL Adobe Campaign]. Wenden Sie sich dazu an Ihren Adobe-Support-Mitarbeiter. <!--or Adobe transition manager?-->

1. Erstellen und testen Sie die Amazon EventBridge-Regeln, um die Überwachung Ihrer Schlüssel durch Adobe zu ermöglichen. &#x200B; [Weitere Informationen](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}

## Sicheres VPN-Tunneln {#secure-vpn-tunneling}

**Sicheres VPN-Tuning (Virtual Private Network)** ist ein standortübergreifendes VPN, das einen sicheren Zugriff für Ihre Daten ermöglicht, die über ein privates Netzwerk von Ihrem Standort zum [!DNL Adobe Campaign] -Instanz.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Um eine hohe Verfügbarkeit (HA) zu gewährleisten, verwendet es zwei Tunnels, um im Falle eines Problems in einem Tunnel einen Ausfall zu vermeiden

Es werden drei Anwendungsfälle unterstützt:

* FDA über VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Anmeldung einer Instanz über VPN von einem dicken Client

* Instanz-SFTP-Zugriff über VPN

>[!CAUTION]
>
>Nur On-Premise-Datenbanken und AWS-konforme VPN-Geräte werden unterstützt. [Weitere Informationen](#vpn-callouts)

Um die ordnungsgemäße Verwendung dieser Funktion sicherzustellen, befolgen Sie die folgenden Richtlinien:

* Richten Sie Ihr seitiges VPN basierend auf der Adobe-seitigen VPN-Konfiguration ein.

* Halten Sie beide Tunnel für HA bereit.

* Überwachen Sie Ihren Seitentunnel.

* Sie müssen der Initiator des Tunnels sein und so ausgerichtet sein, dass Sie die Verbindung neu starten, wenn der Tunnel ausfällt.

* Richten Sie einen Wiederholungsmechanismus an Ihrem Ende ein, falls ein Verbindungsfehler auftritt.

## Schutzmechanismen {#callouts}

Im Folgenden finden Sie einige Limits und Einschränkungen in Bezug auf die erweiterten Sicherheitsfunktionen.

* Stellen Sie sicher, dass alle Anwendungsfälle für die sichere CMK-Integration/Secure VPN-Tunnelverarbeitung funktionieren.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* Adobe überwacht:

   * Ihre Instanzverfügbarkeit und fahren Sie mit der Warnung fort, wenn der Schlüssel nicht verfügbar ist.

   * Die VPN-Tunnel und fahren mit der Warnung fort, falls Probleme auftreten.

### Limits bei der sicheren CMK-Integration {#cmk-callouts}

* Adobe stellt kein AWS-Konto bereit. Sie müssen über ein eigenes AWS-Konto verfügen und dieses so einrichten, dass Sie Ihren Schlüssel generieren und für Adobe freigeben.

* Nur [AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS)-Schlüssel werden unterstützt. Es können keine kundengenerierten Schlüssel außerhalb von KMS verwendet werden. &#x200B;

* Für die Ersteinrichtung sind einige Ausfallzeiten erforderlich. &#x200B;Die Ausfallzeitdauer hängt von der Größe Ihrer Datenbank ab.

* Da Sie den Schlüssel besitzen und pflegen, müssen Sie sich bei jeder Änderung Ihres Schlüssels an die Adobe wenden. &#x200B;

* Sie können Ihren Schlüssel mit [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} und sperren Sie sie bei Bedarf. &#x200B;

* Wenn Sie den Schlüssel sperren, deaktivieren oder löschen, wird der Zugriff auf Ihre verschlüsselten Ressourcen und Instanzen erst wieder aufgehoben, wenn Sie die entsprechende Aktion zurücksetzen.

  >[!CAUTION]
  >
  >Wenn Sie den Schlüssel deaktivieren und diese Aktion nicht innerhalb von 7 Tagen zurücksetzen, kann Ihre Datenbank nur aus der Sicherung abgerufen werden.
  >
  >Wenn Sie den Schlüssel löschen und diese Aktion nicht innerhalb von 30 Tagen wiederherstellen, werden alle Ihre Daten dauerhaft gelöscht und gehen verloren. &#x200B;

### Sichere VPN-Tunnelwächter {#vpn-callouts}

* Derzeit werden nur On-Premise-Datenbanken unterstützt, wie z. B.<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * Teradata 
   * Hadoop über HiveSQL

* Es werden nur AWS-konforme VPN-Geräte unterstützt. Eine Liste kompatibler Geräte finden Sie unter [diese Seite](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* VPN-Verbindungen zu Drittanbietern oder externen Anbietern werden nicht unterstützt.

* Adobe-verwaltete zusätzliche VPNs für private Cloud-Datenbanken sind nicht enthalten.

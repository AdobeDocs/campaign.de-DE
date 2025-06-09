---
product: campaign
title: Technote – Handbuch zur Rotation von Anmeldedaten
description: Technote zu Adobe Campaign – Handbuch zur Rotation von Anmeldedaten
hide: true
hidefromtoc: true
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
source-git-commit: 14e49a0b4de1b82239113bd670213449f464c27f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 93%

---

# Technote: Handbuch zur Rotation von Anmeldedaten {#ac-customer-credentials}

Als Kundin bzw. Kunde sind Sie dafür verantwortlich, Ihre Anmeldedaten regelmäßig durch einen neuen Satz zu ersetzen, um das Risiko einer Kompromittierung zu verringern.

## Anmeldedaten für Adobe Campaign-Optionen {#ac-options-credentials}

Über den Knoten **Administration > Plattform > Optionen** in Adobe Campaign Explorer können Sie Änderungen an den Adobe Campaign-Optionen vornehmen. Wenn Sie hier Zugangsdaten gespeichert haben, stellen Sie sicher, dass diese rotiert werden.

![](assets/technote-2.png)

## Anmeldedaten für externe Konten {#ac-accounts-credentials}

Über den Knoten **Administration > Plattform > Externe Konten** können Sie Änderungen an den externen Konten von Adobe Campaign vornehmen.

Bitte rotieren Sie alle in den externen Konten gespeicherten Anmeldedaten.

>[!CAUTION]
>
>Ändern Sie **nicht** die von Adobe verwalteten Anmeldedaten. Externe Konten mit `adobe`-bezogenen Servern sollten nicht geändert werden.

![](assets/technote-1.png)

Für die spezifischen technischen Operatoren `mc*` (z. B.: mc1, mc2, etc) und `Interaction*` (z. B.: interaction1, interaction2, etc.) kann einer der beiden folgenden Ansätze verfolgt werden:

1. Adobe kann die Anmeldedaten für solche Operatoren ändern und sie mit Ihnen teilen. Beachten Sie, dass alle Integrationen, die diese Operatoren verwenden, nicht mehr funktionieren, bis die Anmeldedaten für diese Operatoren auf Ihrer Seite aktualisiert werden.

1. Adobe kann **neue** Operatoren erstellen, die jedem bestehenden Operator entsprechen, und diese mit Ihnen teilen. Nach Ihrer Umstellung auf die neuen Operatoren löscht Adobe alle Vorkommen der alten Operatoren.


## Mobile Services – Private Schlüssel/Zertifikate  {#ac-key-credentials}

Informationen zur Rotation der auf Mobile Services bezogenen privaten Schlüssel und Zertifikate finden Sie unter den nachfolgenden Links.

* Informationen zu Android finden Sie [dieser Dokumentation](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}.
Navigieren Sie zum Abschnitt **Erstellen einer Mobile App für Android > Konfigurieren der API-Version**.

* Informationen zu iOS finden Sie [dieser Dokumentation](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}.
Navigieren Sie zum Abschnitt **Erstellen einer Mobile App für iOS > Authentifizierungsmodus**.

## GPG-Schlüssel {#ac-gpg-credentials}

Für die Rotation von GPG-Schlüsseln müssen die folgenden Schritte ausgeführt werden:

1. Entschlüsseln Sie die vorhandenen Daten mit dem vorhandenen Schlüssel. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Erstellen Sie ein neues GPG-Schlüsselpaar. Weitere Informationen zur Verwaltung von GPG-Schlüsseln finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/de/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Ersetzen Sie die Verwendung vorhandener GPG-Schlüssel in allen Workflows durch den neu erstellten Schlüssel.

1. Löschen Sie den vorhandenen GPG-Schlüssel.

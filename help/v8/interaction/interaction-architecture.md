---
title: Verstehen der Architektur von Campaign Interaction
description: Grundlegendes zur Architektur von Campaign Interaction
feature: Interaction, Offers
role: Developer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 52%

---

# Umgebungen und Architektur von Campaign Interaction

## Umgebungen {#environments}

Für jede im Zusammenhang mit der Angebotsverwaltung verwendete Zielgruppendimension existiert ein Umgebungspaar:

* Eine **Design**-Umgebung, in der der Angebotsverantwortliche sich darum kümmert, Angebote zu erstellen und zu kategorisieren, zu bearbeiten und den Validierungsprozess zu starten, damit sie verwendet werden können. Die Regeln für jede Kategorie, die Platzierungen, in denen Angebote unterbreitet werden können, und die vordefinierten Filter, die zum Definieren der Eignung eines Angebots verwendet werden, werden ebenfalls in dieser Umgebung definiert.

  Kategorien können automatisch durch die Validierung oder manuell in der Live-Umgebung veröffentlicht werden.

  Der Prozess zur Genehmigung von Angeboten wird [in diesem Abschnitt](interaction-offer.md#approve-offers) beschrieben.

* Eine **Live**-Umgebung, in der die in der Design-Umgebung genehmigten Angebote sowie die verschiedenen Platzierungen, Filter, Kategorien und Regeln zu finden sind. Bei einer Abfrage des Angebotsmoduls verwendet das Modul immer Angebote aus der Live-Umgebung.

Ein Angebot wird nur für die Platzierungen bereitgestellt, die während des Genehmigungsprozesses ausgewählt wurden. Daher kann ein Angebot live sein, aber auf einer Platzierung, die ebenfalls live ist, nicht verwendet werden können.

## Eingehende und ausgehende Interaktionen {#interaction-types}

Das Adobe Campaign Interaction-Modul bietet zwei Arten von Interaktionen:

* **eingehende** Interaktionen, initiiert durch einen Kontakt. [Weitere Informationen](interaction-present-offers.md)
* **ausgehende** Interaktionen, die von einem versandverantwortlichen Benutzer für die Kampagne initiiert werden. [Weitere Informationen](interaction-send-offers.md)

Diese beiden Interaktionstypen können entweder im **Einzelmodus** (das Angebot wird für einen einzelnen Kontakt berechnet) oder im **Batch-Modus** (das Angebot wird für eine Gruppe von Kontakten berechnet) ausgeführt werden. Im Allgemeinen werden eingehende Interaktionen im Einzelmodus und ausgehende Interaktionen im Batch-Modus ausgeführt. Es kann jedoch bestimmte Ausnahmen geben, beispielsweise bei [Transaktionsnachrichten](../send/transactional.md), bei denen die ausgehende Interaktion im Einzelmodus erfolgt.

Wenn ein Angebot unterbreitet werden kann oder soll (je nach Konfiguration), spielt das Angebotsmodul eine zentrale Rolle: Es ermittelt automatisch aus einer Reihe von möglichen Angeboten das für den Kontakt am besten geeignete Angebot, indem es die für ihn vorliegenden Daten und die in der Anwendung definierten Regeln kombiniert und abgleicht.

![](assets/architecture_interaction2.png)

## Verteilte Architektur

Um die Skalierbarkeit zu unterstützen und rund um die Uhr Service für den eingehenden Kanal zu bieten, wird das **Interaction**-Modul in einer verteilten Architektur implementiert. Diese Art von Architektur wird bereits mit [Message Center](../architecture/architecture.md#transac-msg-archi) verwendet und besteht aus mehreren Instanzen:

* einer oder mehrerer Kontrollinstanzen für den ausgehenden Kanal, welche die Marketing-Datenbank und die Design-Umgebung beherbergen;
* einer oder mehrerer Ausführungsinstanzen für den eingehenden Kanal.

![](assets/interaction_powerbooster_schema.png)

Kontrollinstanzen sind dem eingehenden Kanal vorbehalten und enthalten die Online-Version des Katalogs. Jede Ausführungsinstanz ist unabhängig und einem Kontaktsegment gewidmet (z. B. einer Ausführungsinstanz pro Land). Aufrufe des Angebotsmoduls müssen direkt an der Ausführung erfolgen (eine spezifische URL pro Ausführungsinstanz). Da die Synchronisation zwischen Instanzen nicht automatisch erfolgt, müssen Interaktionen desselben Kontakts über dieselbe Instanz gesendet werden.

### Synchronisation {#synchronization}

Die Angebotssynchronisierung erfolgt über Pakete. In Ausführungsinstanzen wird allen Katalogobjekten der externe Kontoname vorangestellt. Dies bedeutet, dass mehrere Kontrollinstanzen (z. B. Entwicklungs- und Produktionsinstanzen) auf derselben Ausführungsinstanz unterstützt werden können.

>[!CAUTION]
>
>Verwenden Sie kurze und explizite interne Namen.

Die Bereitstellung und Veröffentlichung der Angebote in den Ausführungs- und Kontrollinstanzen erfolgt automatisch.

In der Design-Umgebung gelöschte Angebote werden in allen Live-Instanzen deaktiviert. Veraltete Vorschläge und Angebote werden nach der Bereinigungsperiode (angegeben im Bereitstellungsassistenten jeder Instanz) und der Gleitperiode (angegeben in den Typologieregeln der eingehenden Vorschläge) automatisch in allen Instanzen gelöscht.

![](assets/interaction_powerbooster_schema2.png)

Für jede Umgebung und jedes externe Konto wird ein Workflow für die Vorschlagssynchronisierung erstellt. Die Synchronisierungsfrequenz kann für jede Umgebung und jedes externe Konto angepasst werden.

Beachten Sie die folgenden Synchronisierungsmechanismen:

* Wenn Sie die Funktion zum Wechsel von einer anonymen in eine identifizierte Umgebung (fall back) nutzen möchten, müssen sich die beiden betroffenen Umgebungen in derselben Ausführungsinstanz befinden.
* Die Synchronisierung zwischen mehreren Ausführungsinstanzen wird nicht in Echtzeit durchgeführt. Interaktionen desselben Kontakts müssen an dieselbe Instanz gesendet werden. Die Kontrollinstanz muss dem ausgehenden Kanal zugeordnet sein (keine Echtzeit).
* Die Marketing-Datenbank wird nicht automatisch synchronisiert. Die in den Gewichtungs- und Eignungsregeln verwendeten Marketing-Daten müssen in Ausführungsinstanzen dupliziert werden. Dieser Prozess ist nicht standardmäßig, Sie müssen ihn während der Integrationsphase entwickeln.
* Die Synchronisation von Vorschlägen erfolgt ausschließlich über FDA-Verbindung.
* Falls Sie Interaction und Message Center auf derselben Instanz verwenden, erfolgt die Synchronisation in beiden Fällen über das FDA-Protokoll.

### Package-Konfiguration {#packages-configuration}

Eventuelle Schemaerweiterungen in direktem Zusammenhang mit **Interaktion** (Angebote, Vorschläge, Empfänger usw.) Muss auf den Ausführungsinstanzen bereitgestellt werden.

Das Package **Interaktion** wird auf allen Instanzen installiert (Kontrolle und Ausführung). Zwei weitere Packages sind verfügbar: ein Package für die Kontrollinstanzen und das andere für jede Ausführungsinstanz.

>[!NOTE]
>
>Wenn Sie das Paket installieren **werden die Felder vom** long **der Tabelle nms:proposition**, z. B. die Vorschlagskennung, zu Feldern vom Typ **int64**. Dieser Datentyp wird in der Dokumentation zu [Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=de#mapping-the-types-of-adobe-campaign-dbms-data){target="_blank"}.

Die Aufbewahrungsdauer der Daten wird für jede Instanz konfiguriert (über die Variable **[!UICONTROL Datenbereinigung]** im Bereitstellungsassistenten). Bei Ausführungsinstanzen muss dieser Zeitraum der historischen Tiefe entsprechen, die für die Berechnung von Typologieregeln (beweglicher Zeitraum) und Eignungsregeln erforderlich ist.

Bei den Kontrollinstanzen müssen Sie darüber hinaus:

1. Erstellen Sie pro Ausführungsinstanz ein externes Konto:

   ![](assets/interaction_powerbooster1.png)

   * Geben Sie einen Titel sowie einen kurzen und expliziten internen Namen an.
   * Wählen Sie den Typ **[!UICONTROL Ausführungsinstanz]** aus.
   * Kreuzen Sie die Option **[!UICONTROL Aktiviert]** an.
   * Geben Sie die Verbindungsparameter zur Ausführungsinstanz an.
   * Jeder Ausführungsinstanz muss eine Kennung zugeordnet werden. Dies geschieht durch Klick auf die Schaltfläche **[!UICONTROL Verbindung initialisieren]**.
   * Kreuzen Sie die verwendete Anwendung an: **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]** oder beide.
   * Geben Sie das verwendete FDA-Konto ein. Auf den Ausführungsinstanzen muss ein Benutzer erstellt werden, der über die folgenden Lese- und Schreibrechte für die Datenbank der betreffenden Instanz verfügt:

     ```
     grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
     grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
     ```

   >[!NOTE]
   >
   >Die IP-Adresse der Kontrollinstanz muss in den Ausführungsinstanzen zugelassen sein.

1. Die Umgebung konfigurieren:

   ![](assets/interaction_powerbooster2.png)

   * Geben Sie alle Ausführungsinstanzen an.
   * Definieren Sie für jede Instanz den Aktualisierungsrhythmus und die Vorschlagsfilter (z. B. nach Land).

     >[!NOTE]
     >
     >Wenn ein Fehler auftritt, können Sie die Synchronisierungs-Workflows und Angebotsbenachrichtigungen einsehen. Diese sind in den technischen Workflows der Anwendung zu finden.

Wenn aus Optimierungsgründen nur ein Teil der Marketing-Datenbank in den Ausführungsinstanzen dupliziert wird, können Sie ein eingeschränktes, mit der Umgebung verknüpftes Schema angeben, damit die Benutzer nur Daten verwenden können, die in den Ausführungsinstanzen verfügbar sind. Sie können ein Angebot mit Daten erstellen, die in Ausführungsinstanzen nicht verfügbar sind. Dazu müssen Sie die Regel für die anderen Kanäle deaktivieren, indem Sie diese Regel auf den ausgehenden Kanal (**[!UICONTROL Wird berücksichtigt, wenn]** -Feld).

![](assets/ita_filtering.png)

### Wartungsoptionen {#maintenance-options}

Folgende Wartungsoptionen stehen für die Kontrollinstanz zur Verfügung:

>[!CAUTION]
>
>Diese Optionen sind nur bei klar definierten Wartungsbedarfen zu nutzen.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: Datum der letzten Synchronisation einer Umgebung in einer bestimmten Instanz.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: Datum der letzten Synchronisation der Vorschläge eines bestimmten Schemas zwischen zwei Instanzen.
* **`NmsInteraction_MapWorkflowId`**: Option, die die Liste aller erzeugten Synchronisations-Workflows enthält.

Die folgende Option steht für Ausführungsinstanzen zur Verfügung:

**NmsExecutionInstanceId**: Option, die die Instanzkennung enthält.

### Package-Installation {#packages-installation}

Wenn Ihre Instanz zuvor nicht über das Package **Interaction** verfügte, ist keine Migration erforderlich. Standardmäßig liegt die Vorschlagstabelle nach der Installation der Pakete in 64 Bit vor.

>[!CAUTION]
>
>Je nach Anzahl an existierenden Vorschlägen in Ihrer Instanz kann dieser Vorgang sehr zeitintensiv sein.

* Wenn Ihre Instanz nur über wenige oder gar keine Vorschläge verfügt, ist keine manuelle Änderung der Vorschlagstabelle erforderlich. Die Änderung wird vorgenommen, wenn Pakete installiert werden.
* Wenn Ihre Instanz viele Vorschläge hat, ist es besser, die Struktur der Vorschlagstabelle zu ändern, bevor Sie die Steuerungspakete installieren und ausführen. Es wird empfohlen, die Abfragen während eines Zeitraums mit geringer Aktivität auszuführen.

>[!NOTE]
>
>Falls Sie spezifische Konfigurationen in Ihrer Vorschlagstabelle vorgenommen haben, müssen die Abfragen entsprechend angepasst werden.


Es gibt zwei Methoden:

**Arbeitstabelle** (empfohlen)

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**Alter Table**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```

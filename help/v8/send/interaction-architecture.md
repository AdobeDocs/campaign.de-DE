---
title: Architektur von Campaign Interaction
description: Architektur der Campaign-Interaktion
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: tm+mt
source-wordcount: '1328'
ht-degree: 57%

---

# Campaign-Interaktionsumgebungen und -architektur

## Umgebungen {#environments}

Für jede im Zusammenhang mit der Angebotsverwaltung verwendete Zieldimension existiert ein Umgebungspaar:

* A **Design** Umgebung, in der der Angebotsverantwortliche Angebote erstellt und kategorisiert, sie bearbeitet und den Validierungsprozess startet, damit sie verwendet werden können. Die Regeln für jede Kategorie, die Platzierungen, in denen Angebote unterbreitet werden können, und die vordefinierten Filter, mit denen die Eignung eines Angebots bestimmt wird, werden ebenfalls in dieser Umgebung definiert.

   Kategorien können automatisch durch die Validierung oder manuell in der Live-Umgebung veröffentlicht werden.

   Die Vorgehensweise zur Angebotsvalidierung wird im Detail beschrieben. [in diesem Abschnitt](interaction-offer.md#approve-offers).

* A **live** Umgebung, in der die genehmigten Angebote aus der Design-Umgebung sowie die verschiedenen in der Design-Umgebung konfigurierten Platzierungen, Filter, Kategorien und Regeln zu finden sind. Bei einem Aufruf des Angebotsmoduls verwendet das Angebotsmodul stets Angebote aus der Live-Umgebung.

Ein Angebot wird nur für die bei der Validierung ausgewählten Platzierungen freigegeben. Dies bedeutet, dass ein Angebot u. U. live sein, aber trotzdem nicht in einer Platzierung verwendet werden kann, selbst wenn diese ebenfalls live ist.

## Eingehende und ausgehende Interaktionen {#interaction-types}

Das Adobe Campaign Interaction-Modul bietet zwei Arten von Interaktionen:

* **Inbound** Interaktionen, initiiert durch einen Kontakt. [Weitere Informationen](interaction-present-offers.md)
* **ausgehende** Interaktionen, die von einem Campaign Delivery Manager initiiert werden. [Weitere Informationen](interaction-send-offers.md)

Diese beiden Arten von Interaktionen können entweder in **Einzelmodus** (Angebot wird für einen einzelnen Kontakt berechnet) oder in **Batch-Modus** (Angebot wird für eine Gruppe von Kontakten berechnet). Im Allgemeinen werden eingehende Interaktionen im Einzelmodus durchgeführt und ausgehende Interaktionen im Batch-Modus. Es kann jedoch bestimmte Ausnahmen geben für [Transaktionsnachrichten](transactional.md) , wobei die ausgehende Interaktion beispielsweise im Einzelmodus erfolgt.

Sobald ein Angebot unterbreitet werden kann oder muss (je nach Konfiguration), spielt das Angebotsmodul die Vermittlerrolle: berechnet automatisch das bestmögliche Angebot für einen Kontakt aus den verfügbaren Angeboten, indem die über den Kontakt empfangenen Daten und die verschiedenen Regeln kombiniert werden, die wie in der Anwendung angegeben angewendet werden können.

![](assets/architecture_interaction2.png)

## Verteilte Architektur

Um die Skalierbarkeit zu unterstützen und rund um die Uhr Service für den eingehenden Kanal zu bieten, muss die **Interaction** -Modul wird in einer verteilten Architektur implementiert. Diese Art von Architektur wird bereits mit [Message Center](../dev/architecture.md#transac-msg-archi) und besteht aus mehreren Instanzen:

* einer oder mehrerer Kontrollinstanzen für den ausgehenden Kanal, welche die Marketing-Datenbank und die Design-Umgebung beherbergen;
* einer oder mehrerer Ausführungsinstanzen für den eingehenden Kanal.

![](assets/interaction_powerbooster_schema.png)

Kontrollinstanzen sind dem eingehenden Kanal vorbehalten und enthalten die Online-Version des Katalogs. Jede Ausführungsinstanz ist unabhängig und einem Kontaktsegment gewidmet (z. B. eine Ausführungsinstanz pro Land). Aufrufe des Angebotsmoduls müssen direkt an der Ausführung erfolgen (eine spezifische URL pro Ausführungsinstanz). Da die Synchronisation zwischen Instanzen nicht automatisch erfolgt, müssen Interaktionen desselben Kontakts über dieselbe Instanz gesendet werden.

### Synchronisation {#synchronization}

Die Synchronisation von Vorschlägen erfolgt in Packages. In den Ausführungsinstanzen werden alle Katalogobjekte durch Voranstellung des Namens des externen Kontos gekennzeichnet. Dies ermöglicht die Unterstützung mehrerer Kontrollinstanzen (z. B. Design- und Live-Instanzen) auf derselben Ausführungsinstanz.

>[!CAUTION]
>
>Verwenden Sie kurze und explizite interne Namen.

Die Freigabe und Veröffentlichung der Angebote in den Ausführungs- und Kontrollinstanzen erfolgt automatisch.

In der Design-Umgebung gelöschte Angebote werden in allen Live-Instanzen deaktiviert. Obsolete Vorschläge und Angebote werden nach Ablauf der durch die Bereinigungsparameter im Softwareverteilungs-Assistenten aller Instanzen definierten Frist und des in den Typologieregeln definierten beweglichen Zeitraums automatisch gelöscht.

![](assets/interaction_powerbooster_schema2.png)

Für jedes externe Konto und jede Umgebung wird ein Synchronisations-Workflow erstellt. Die Synchronisationshäufigkeit kann individuell angepasst werden.

Beachten Sie die folgenden Synchronisierungsmechanismen:

* Wenn Sie die Funktion zum Wechsel von einer anonymen in eine identifizierte Umgebung (fall back) nutzen möchten, müssen sich die beiden betroffenen Umgebungen in derselben Ausführungsinstanz befinden.
* Die Synchronisation von verschiedenen Ausführungsinstanzen erfolgt nicht in Echtzeit. Alle Interaktionen eines spezifischen Kontakts müssen immer an dieselbe Instanz gesendet werden. Die Kontrollinstanz ist dem ausgehenden Kanal vorbehalten (keine Echtzeit-Verarbeitung).
* Die Marketing-Datenbank wird nicht automatisch synchronisiert. Aus diesem Grund müssen die im Zusammenhang mit den Eignungsregeln und Gewichtungen verwendeten Marketingdaten in die Ausführungsinstanzen dupliziert werden. Dieser Prozess ist im Verlauf der Integrationsphase zu entwickeln.
* Die Synchronisation von Vorschlägen erfolgt ausschließlich über FDA-Verbindung.
* Falls Sie Interaction und Message Center auf derselben Instanz verwenden, erfolgt die Synchronisation in beiden Fällen über das FDA-Protokoll.

### Package-Konfiguration {#packages-configuration}

Eventuelle Schemaerweiterungen in direktem Zusammenhang mit **Interaction** (beispielsweise Angebots-, Vorschlags- oder Empfängerschema) sind auf die Ausführungsinstanzen freizugeben.

Die **Interaction** installiert wird auf allen Instanzen (Kontrolle und Ausführung). Zwei weitere Packages sind verfügbar: ein Paket für die Kontrollinstanzen und das andere für jede Ausführungsinstanz.

>[!NOTE]
>
>Wenn Sie das Paket installieren, wird die **long** Typfelder der **nms:proposition** -Tabelle, z. B. die Vorschlagskennung, werden **int64** Typfelder. Dieser Datentyp wird im Abschnitt [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=en#mapping-the-types-of-adobe-campaign-dbms-data){target=&quot;_blank&quot;}.

Die Aufbewahrungsdauer der Daten wird für jede Instanz konfiguriert (über die Variable **[!UICONTROL Datenbereinigung]** im Softwareverteilungs-Assistenten). Bei Ausführungsinstanzen muss dieser Zeitraum der historischen Tiefe entsprechen, die für die Berechnung von Typologieregeln (beweglicher Zeitraum) und Eignungsregeln erforderlich ist.

Bei den Kontrollinstanzen müssen Sie darüber hinaus:

1. Pro Ausführungsinstanz ein externes Konto erstellen:

   ![](assets/interaction_powerbooster1.png)

   * Geben Sie einen Titel sowie einen kurzen und expliziten internen Namen an.
   * Wählen Sie den Typ **[!UICONTROL Ausführungsinstanz]** aus.
   * Kreuzen Sie die Option **[!UICONTROL Aktiviert]** an.
   * Geben Sie die Verbindungsparameter zur Ausführungsinstanz an.
   * Jeder Ausführungsinstanz muss eine Kennung zugeordnet werden. Dies geschieht durch Klick auf die Schaltfläche **[!UICONTROL Verbindung initialisieren]**.
   * Kreuzen Sie die verwendete Anwendung an: **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]** oder beide.
   * Geben Sie das genutzte FDA-Konto an. Benutzer müssen in den Ausführungsinstanzen erstellt werden und über die folgenden Lese- und Schreibberechtigungen in den entsprechenden Instanzen verfügen:

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
      >Sollten Fehler auftreten, sind die technischen Workflows zur Vorschlagssynchronisation und Angebotsbenachrichtigung zu prüfen.

Falls aus Optimierungsgründen nur ein Teil der Marketing-Datenbank in die Ausführungsinstanzen dupliziert wird, haben Sie die Möglichkeit, ein der Umgebung zugeordnetes eingeschränktes Schema zu definieren. Auf diese Weise können die Benutzer nur die Daten verwenden, die tatsächlich in den Ausführungsinstanzen zur Verfügung stehen. Es ist trotzdem möglich, ein Angebot zu erstellen, das Daten verwendet, die nicht in der Ausführungsinstanz verfügbar sind. Begrenzen Sie hierfür mithilfe des Felds **[!UICONTROL Berücksichtigt wenn]** die Regel auf den gewünschten ausgehenden Kanal.

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

Wenn Ihre Instanz zuvor nicht über die **Interaction** -Paket enthalten, ist keine Migration erforderlich. Standardmäßig beträgt die Vorschlagstabelle 64 Bit, nachdem die Pakete installiert wurden.

>[!CAUTION]
>
>Je nach Anzahl an existierenden Vorschlägen in Ihrer Instanz kann dieser Vorgang sehr zeitintensiv sein.

* Wenn Ihre Instanz keine oder nur wenige Vorschläge enthält, ist kein manueller Eingriff in Bezug auf die Vorschlagstabelle erforderlich. Die Änderung erfolgt zum Zeitpunkt der Package-Installation.
* Wenn Ihre Instanz eine große Anzahl an Vorschlägen enthält, wird empfohlen, die Struktur der Vorschlagstabelle vor Installation der Ausführungs- und Kontroll-Packages anzupassen. Die diesbezüglichen Abfragen sind vorzugsweise zu einem Zeitpunkt mit geringer Auslastung auszuführen.

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

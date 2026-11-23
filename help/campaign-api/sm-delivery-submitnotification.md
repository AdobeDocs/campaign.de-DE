---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# Submit Notification

Erstellung und Unterbreitung einer Benachrichtigung von einer Versandvorlage ausgehend

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## Parameter

**scenarioName** Interner Name der Vorlage

**target** Zielgruppe des Versands, die die Zielgruppe im Szenario ersetzt

## Rückgabewert(e)

**notificationId** Benachrichtigungskennung

## Bemerkungen

Warnung: Diese API ist nicht für die Verwaltung großer Datenmengen oder für die Arbeit in Echtzeit konzipiert. Es wurde entwickelt, um maximal mehrere Aufrufe pro Minute zu verarbeiten. SubmitNotification blockiert den Thread während der Versandanalyse. Dies kann einige Sekunden dauern. Der Parameter „target“ gibt die Versandzielgruppe an. Es überschreibt ein in der Vorlage angegebenes Ziel. Für den Versand an eine Zielgruppe in der Datenbank verwendet das Zielelement die folgende Syntax:

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

Versand an eine Zielgruppe in einer Datei:

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

Es ist möglich, die Zielgruppe explizit zu definieren (in Wirklichkeit ist der Inhalt der als Zielgruppe verwendeten Datei):

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

Es ist auch möglich, das in der Vorlage definierte Ziel mit dem Attribut &quot;\_keepTemplateTarget“ beizubehalten

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja

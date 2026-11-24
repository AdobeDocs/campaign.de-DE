---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 4%
---
# Laich

Erstellt eine auf einer Vorlage basierende Workflow-Instanz, führt einen Patch durch und startet den Workflow.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## Parameter

**workflowId** Kennung oder interner Name der Workflow-Vorlage.

**patch** Das XML-Element, das mit dem Modell zusammengeführt werden muss, um die Instanz vor der Ausführung zu erhalten. Beispiel:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

Dieses Beispiel ersetzt die Argumente der Aktivität „notepad“. Wenn Sie diesen Patch nicht anwenden möchten, verwenden Sie ein leeres &lt;workflow/>-Element oder eine leere Zeichenfolge.

## Rückgabewert(e)

**instanceId** Kennung der aus der Vorlage erstellten Instanz.

## Bemerkungen

Der Befehl wird asynchron ausgeführt und hat keine sofortige Auswirkung nach der Rückgabe der Methode. Der Workflow wird mit dem Konto des aufrufenden Benutzers gestartet.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja

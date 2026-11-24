---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# Gruppe registrieren

Fügt die ausgewählten Empfänger zu einer Liste hinzu

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## Parameter

**groupList** Listen

**recipientList** Empfängerliste

**registrieren** Empfänger an-/abmelden

## Rückgabewert(e)

Keine.

## Beispiel

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## Funktionen

**Schema:** [nms:recipient](s-nms-recipient.md)

**static:**

Ja

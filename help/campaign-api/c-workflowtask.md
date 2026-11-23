---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask (Klasse)

Status einer Workflow-Aufgabe.

Ein ⌐`WorkflowTask` ist eine Klasse, die nicht instanziiert werden kann und für die in den Workflow-Aktivitäten namens `task` nur eine Instanz zugänglich ist.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | Kennzeichnet die Aufgabe als abgeschlossen. |
| [postEvent](m-workflowtask-postevent.md) | Aktiviert eine Transition. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | Zieht das nächste Verarbeitungsdatum durch die Aufgabe vor. |
| [doneTransition](m-workflowtask-donetransition.md) | Gibt die Transition „Fertig“ der Aktivität zurück. |
| [errorTransition](m-workflowtask-errortransition.md) | Gibt die Fehlertransition der Aktivität aus. |
| [transitionByType](m-workflowtask-transitionbytype.md) | Gibt die dem angegebenen Typ entsprechende Transition zurück. |
| [transitionByName](m-workflowtask-transitionbyname.md) | Gibt die dem angegebenen Namen entsprechenden Transitionen aus. |
| [Übergänge](m-workflowtask-transitions.md) | Gibt die Liste der Transitionen der Aktivität aus |
| [Warten](m-workflowtask-wait.md) | Wartet auf ein Signal. |

## Funktionen

**Verfügbar in:**

* Workflow

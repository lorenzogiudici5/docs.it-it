---
title: Operatori condizionali Null (Riferimenti per C#)
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 823b9dc886bf2448ca9da4ac640bfe56f90d3ff3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194852"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. e ?[] - Operatori condizionali Null (C# e Visual Basic)
Testa il valore dell'operando sul lato sinistro per i valori Null prima di eseguire un accesso ai membri (`?.`) o un'operazione (`?[]`) di indicizzazione; restituisce `null` se l'operando sul lato sinistro restituisce `null`. 

Questi operatori consentono di scrivere meno codice per gestire i controlli null, soprattutto per l'ordinamento decrescente delle strutture di dati.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 Gli operatori condizionali Null causano corto circuiti.  Se un'operazione in una catena di operazioni condizionali di indice e accesso ai membri restituisce Null, l'esecuzione delle altre operazioni della catena viene interrotta.  Nell'esempio seguente, `E` non viene eseguito se `A`, `B` o `C` restituisce Null.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 L'accesso ai membri con condizione Null viene usato anche per chiamare delegati in modo thread-safe scrivendo molto meno codice.  In passato era necessario codice simile al seguente:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 Ora tutto è molto più semplice:  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `PropertyChanged` una sola volta, mantenendo il risultato in una variabile temporanea. È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `PropertyChanged?(e)`.  
  
## <a name="language-specifications"></a>Specifiche del linguaggio  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [ ?? (operatore null-coalescing)](null-coalescing-operator.md)  
- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  

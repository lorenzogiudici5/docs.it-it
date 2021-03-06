---
title: Operatore %= (Riferimenti per C#)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: ab3a6a8d5cbfeb4d527ca1f9c233ddfaba3d35ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188716"
---
# <a name="-operator-c-reference"></a>Operatore %= (Riferimenti per C#)

Operatore di assegnazione di resto.

Un'espressione che usa l'operatore `%=`, ad esempio  

```csharp
x %= y
```  

equivale a  

```csharp
x = x % y
```  

con la differenza che `x` viene valutato una sola volta.
  
L'[operatore di resto](remainder-operator.md) `%` calcola il resto dopo la divisione dei due operandi. È supportato da tutti i tipi numerici.

Se un tipo definito dall'utente [esegue l'overload](../keywords/operator.md) dell'[operatore di resto](remainder-operator.md) `%`, l'operatore di assegnazione di resto `%=` viene sottoposto a overload in modo implicito.
  
Nell'esempio seguente viene illustrato l'uso dell'operatore `%=`:

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)

---
title: "Procedura: implementare conversioni tra struct definite dall'utente (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: cff85d60c1b59f4d1ca028f8fc02fee5728fa3d6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696652"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Procedura: implementare conversioni tra struct definite dall'utente (Guida per programmatori C#)
Questo esempio definisce due struct, `RomanNumeral` e `BinaryNumeral`, e illustra le conversioni tra di loro.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
-   Nell'esempio precedente l'istruzione:  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     esegue una conversione da `RomanNumeral` a `BinaryNumeral`. Poiché non c'è una conversione diretta da `RomanNumeral` a `BinaryNumeral`, vengono usati un cast per la conversione da `RomanNumeral` a `int` e un altro cast per la conversione da `int` a `BinaryNumeral`.  
  
-   Anche l'istruzione  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     esegue una conversione da `BinaryNumeral` a `RomanNumeral`. Poiché `RomanNumeral` definisce una conversione implicita da `BinaryNumeral`, non è necessario il cast.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

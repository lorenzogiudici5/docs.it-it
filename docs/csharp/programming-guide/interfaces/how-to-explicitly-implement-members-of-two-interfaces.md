---
title: 'Procedura: implementare in modo esplicito i membri di due interfacce (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 6c02585b57acef654c6613bef1a276a433763af6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514673"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a>Procedura: implementare in modo esplicito i membri di due interfacce (Guida per programmatori C#)
L'implementazione di [interfaccia](../../../csharp/language-reference/keywords/interface.md) esplicita consente inoltre al programmatore di implementare due interfacce con gli stessi nomi di membro e assegnare a ogni membro dell'interfaccia un'implementazione separata. Questo esempio mostra le dimensioni di una casella sia in unità metriche che anglosassoni. La [classe](../../../csharp/language-reference/keywords/class.md) Box implementa due interfacce, IEnglishDimensions e IMetricDimensions, che rappresentano i diversi sistemi di misura. Entrambe le interfacce hanno nomi di membri identici, Length e Width.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se si vogliono impostare come predefinite le misure in unità anglosassoni, implementare i metodi Length e Width normalmente e implementare in modo esplicito i metodi Length e Width dall'interfaccia IMetricDimensions:  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 In questo caso, è possibile accedere alle unità anglosassoni dall'istanza della classe e alle unità metriche dall'istanza dell'interfaccia:  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Interfacce](../../../csharp/programming-guide/interfaces/index.md)  
- [Procedura: Implementare in modo esplicito i membri di interfaccia](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)

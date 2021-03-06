---
title: "Procedura: definire l'uguaglianza di valori per un tipo (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- overriding Equals method [C#]
- object equivalence [C#]
- Equals method [C#], overriding
- value equality [C#]
- equivalence [C#]
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
ms.openlocfilehash: 8abcace9c648ba2132d2b6849ae1c9d347d6fd29
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126783"
---
# <a name="how-to-define-value-equality-for-a-type-c-programming-guide"></a>Procedura: definire l'uguaglianza di valori per un tipo (Guida per programmatori C#)
Quando si definisce una classe o uno struct, si decide se è opportuno creare una definizione personalizzata di uguaglianza di valore, o equivalenza, per il tipo. In genere, l'uguaglianza di valori viene implementata quando si prevede che oggetti del tipo vengano aggiunti a una raccolta, o quando lo scopo principale di tali oggetti consiste nell'archiviare un set di campi o di proprietà. È possibile basare la definizione di uguaglianza di valori su un confronto di tutti i campi e di tutte le proprietà nel tipo, oppure su un sottoinsieme. Ma in entrambi i casi e in entrambe le classi e gli struct, l'implementazione deve seguire le cinque garanzie di equivalenza:  
  
1.  `x.Equals(x)` restituisce `true`. Questa viene denominata proprietà riflessiva.  
  
2.  `y.Equals(x)` restituisce lo stesso valore di `x.Equals(y)`. Questa viene denominata proprietà simmetrica.  
  
3.  Se `(x.Equals(y) && y.Equals(z))` restituisce `true`, `x.Equals(z)` restituirà `true`. Questa viene denominata proprietà transitiva.  
  
4.  Le successive chiamate di `x.Equals(y)` restituiscono lo stesso valore purché gli oggetti a cui x e y fanno riferimento non vengano modificati.  
  
5.  `x.Equals(null)` restituisce `false`. `null.Equals(null)` genera tuttavia un'eccezione in quanto non rispetta la regola numero 2 precedente.  
  
 Gli struct definiti hanno già un'implementazione predefinita di uguaglianza di valore che eredita dall'override <xref:System.ValueType?displayProperty=nameWithType> del metodo <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>. Questa implementazione usa il processo di reflection per esaminare tutti i campi e tutte le proprietà nel tipo. Sebbene questa implementazione produca risultati corretti, è relativamente lenta rispetto a un'implementazione personalizzata che viene scritta specificamente per il tipo.  
  
 I dettagli di implementazione per l'uguaglianza di valori sono diversi per le classi e gli struct. Tuttavia, sia le classi che gli struct richiedono gli stessi passaggi di base per l'implementazione dell'uguaglianza:  
  
1.  Eseguire l'override del metodo di tipo [virtual](../../../csharp/language-reference/keywords/virtual.md) <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>. Nella maggior parte dei casi l'implementazione di `bool Equals( object obj )` deve solo chiamare il metodo `Equals` specifico per il tipo, che è l'implementazione dell'interfaccia <xref:System.IEquatable%601?displayProperty=nameWithType>. (Vedere il passaggio 2.)  
  
2.  Implementare l'interfaccia <xref:System.IEquatable%601?displayProperty=nameWithType> definendo un metodo `Equals` specifico per il tipo. È in questo passaggio che viene eseguito il confronto di equivalenza effettivo. Ad esempio, è possibile definire l'uguaglianza confrontando solo uno o due campi nel tipo. Non generare eccezioni da `Equals`. Solo per le classi: questo metodo deve esaminare solo i campi che vengono dichiarati nella classe. Deve chiamare `base.Equals` per esaminare i campi presenti nella classe di base. Non eseguire questa operazione se il tipo eredita direttamente da <xref:System.Object>, perché l'implementazione <xref:System.Object> di <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> esegue un controllo di uguaglianza dei riferimenti.  
  
3.  Facoltativo ma consigliato: eseguire l'overload degli operatori [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) e [!=](../../../csharp/language-reference/operators/not-equal-operator.md).  
  
4.  Eseguire l'override di <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType> in modo che due oggetti con uguaglianza di valori producano lo stesso codice hash.  
  
5.  Facoltativo: per supportare le definizioni di "maggiore di" o "minore di", implementare l'interfaccia <xref:System.IComparable%601> per il tipo e sottoporre anche a overload gli operatori [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) e [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).  
  
 Nel primo esempio che segue viene illustrata l'implementazione di una classe. Nel secondo esempio viene illustrata l'implementazione di uno struct.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come implementare l'uguaglianza di valori in una classe (tipo riferimento).  
  
 [!code-csharp[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_1.cs)]  
  
 Nelle classi (tipi riferimento) l'implementazione predefinita di entrambi i metodi <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> esegue un confronto di uguaglianza dei riferimenti, non un controllo di uguaglianza dei valori. Quando un responsabile dell'implementazione esegue l'override del metodo virtuale, lo scopo è assegnare a tale metodo una semantica di uguaglianza di valore.  
  
 Gli operatori `==` e `!=` possono essere usati con le classi anche se la classe non ne esegue l'overload. Tuttavia, il comportamento predefinito è eseguire una verifica dell'uguaglianza dei riferimenti. Se in una classe si esegue l'overload del metodo `Equals`, è consigliabile eseguire l'overload degli operatori `==` e `!=`, ma non è obbligatorio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come implementare l'uguaglianza di valori in uno struct (tipo valore):  
  
 [!code-csharp[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_2.cs)]  
  
 Per gli struct, l'implementazione predefinita di <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>, che è la versione sottoposta a override in <xref:System.ValueType?displayProperty=nameWithType>, esegue un controllo di uguaglianza dei valori usando il processo di reflection per confrontare i valori di ogni campo nel tipo. Quando un responsabile dell'implementazione esegue l'override del metodo virtuale `Equals` in uno struct, lo scopo è specificare un mezzo più efficiente per la verifica dell'uguaglianza di valori e facoltativamente basare il confronto su alcuni subset del campo o delle proprietà dello struct.  
  
 Gli operatori [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) e [!=](../../../csharp/language-reference/operators/not-equal-operator.md) non possono funzionare con uno struct a meno che lo struct non ne esegua esplicitamente l'overload.  
  
## <a name="see-also"></a>Vedere anche

- [Confronti di uguaglianza](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)

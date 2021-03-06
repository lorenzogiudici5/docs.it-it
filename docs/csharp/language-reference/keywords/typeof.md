---
title: typeof (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 039294d17d25d1d8775e7f92f46f5f57f2ac3212
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146680"
---
# <a name="typeof-c-reference"></a>typeof (Riferimenti per C#)

Viene usato per ottenere l'oggetto `System.Type` per un tipo. L'espressione `typeof` assume il formato seguente:

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a>Note

Per ottenere il tipo di runtime di un'espressione, è possibile usare il metodo di .NET Framework <xref:System.Object.GetType%2A>, come nell'esempio seguente:

```csharp
int i = 0;
System.Type type = i.GetType();
```

Non è possibile sottoporre l'operatore `typeof` a overload.

L'operatore `typeof` può essere usato anche su tipi generici aperti. I tipi con più di un parametro di tipo devono avere il numero appropriato di virgole nella specifica. Nell'esempio seguente viene illustrato come determinare se il tipo restituito di un metodo è un elemento <xref:System.Collections.Generic.IEnumerable%601> generico. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> restituirà `null` se il tipo restituito non è un tipo generico <xref:System.Collections.Generic.IEnumerable%601>.

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a>Esempio

Questo esempio usa il metodo <xref:System.Object.GetType%2A> per determinare il tipo usato per contenere il risultato di un calcolo numerico. Ciò dipende dai requisiti di archiviazione del numero risultante.

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Operatore typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.Type?displayProperty=nameWithType>
- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
- [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)
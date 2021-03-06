---
title: Spazi dei nomi - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 4abdf8a0008ce50a89eb5f3ad3512a9579dc832a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236752"
---
# <a name="namespaces-c-programming-guide"></a>Spazi dei nomi (Guida per programmatori C#)

Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi. Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
`System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi. Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
Per altre informazioni, vedere la [direttiva using](../../language-reference/keywords/using-directive.md).  
  
Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi. Usare la parola chiave [namespace](../../language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

Il nome dello spazio dei nomi deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.

## <a name="namespaces-overview"></a>Panoramica degli spazi dei nomi  

Gli spazi dei nomi hanno le proprietà riportate di seguito:  
  
- Consentono di organizzare progetti di codice di grandi dimensioni.  
- Vengono delimitati usando l'operatore `.`.  
- La direttiva `using` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.  
- Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi <xref:System> di .NET.  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Uso degli spazi dei nomi](using-namespaces.md)
- [Procedura: Usare l'alias dello spazio dei nomi globale](how-to-use-the-global-namespace-alias.md)
- [Procedura: Usare lo spazio dei nomi My](how-to-use-the-my-namespace.md)
- [Guida per programmatori C#](../index.md)  
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
- [Parole chiave per gli spazi dei nomi](../../language-reference/keywords/namespace-keywords.md)  
- [Direttiva using](../../language-reference/keywords/using-directive.md)  
- [:: (operatore)](../../language-reference/operators/namespace-alias-qualifer.md)  
- [. (operatore)](../../language-reference/operators/member-access-operator.md)

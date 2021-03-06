---
title: Eseguire left outer join (LINQ in C#)
description: Informazioni su come eseguire left outer join usando LINQ in C#.
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 329fe9e17640931c5eb39b33b791a7a77a6f7b89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506596"
---
# <a name="perform-left-outer-joins"></a>Eseguire left outer join

Un left outer join è un join in cui viene restituito ogni elemento della prima raccolta, anche se non ha elementi correlati nella seconda raccolta. È possibile usare LINQ per eseguire un left outer join chiamando il metodo <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nei risultati di un join di gruppo.

## <a name="example"></a>Esempio

L'esempio seguente illustra come usare il metodo <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nei risultati di un join di gruppo per eseguire un left outer join.

Il primo passaggio nella produzione di un left outer join di due raccolte consiste nell'esecuzione di un inner join usando un join di gruppo. Per una descrizione di questo processo, vedere [Eseguire inner join](perform-inner-joins.md). In questo esempio l'elenco di oggetti `Person` è unito tramite inner join all'elenco di oggetti `Pet` basati su un oggetto `Person` che corrisponde a `Pet.Owner`.

Il secondo passaggio consiste nell'includere ogni elemento della prima raccolta di sinistra nel set di risultati anche se l'elemento non ha corrispondenze nella raccolta di destra. Questa operazione viene eseguita chiamando <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> in ogni sequenza di elementi corrispondenti dal join di gruppo. In questo esempio <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> viene chiamato in ogni sequenza di oggetti `Pet` corrispondenti. Il metodo restituisce una raccolta che contiene un solo valore predefinito se la sequenza di oggetti `Pet` corrispondenti è vuota per qualsiasi oggetto `Person`, assicurando in questo modo che ogni oggetto `Person` sia rappresentato nella raccolta di risultati.

> [!NOTE]
> Il valore predefinito per un tipo di riferimento è `null`. Di conseguenza, l'esempio cerca un riferimento Null prima di accedere a ogni elemento di ogni raccolta `Pet`.

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable.Join%2A>  
- <xref:System.Linq.Enumerable.GroupJoin%2A>  
- [Eseguire inner join](perform-inner-joins.md)  
- [Eseguire join raggruppati](perform-grouped-joins.md)  
- [Tipi anonimi](../programming-guide/classes-and-structs/anonymous-types.md)  
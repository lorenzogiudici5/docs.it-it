---
title: Eseguire un join usando una chiave composta (LINQ in C#)
description: Informazioni su come eseguire un join usando una chiave composta in LINQ.
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: ae37d03f996f0b0cc184a86663f16d62e6c29c69
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080104"
---
# <a name="join-by-using-composite-keys"></a>Eseguire un join usando chiavi composte

In questo esempio viene illustrato come eseguire operazioni di join in cui si vuole usare più di una chiave per definire una corrispondenza. Ciò è possibile usando una chiave composta, che viene creata come tipo anonimo o tipo denominato con i valori che si vogliono confrontare. Se la variabile di query viene passata attraverso i limiti del metodo, usare un tipo denominato che esegue l'override di <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> per la chiave. I nomi delle proprietà e l'ordine in cui si verificano devono essere identici in ogni chiave.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come usare una chiave composta per eseguire un join dei dati da tre tabelle:

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

L'inferenza del tipo nelle chiavi composte dipende dai nomi delle proprietà nelle chiavi e dall'ordine in cui si verificano. Se le proprietà nelle sequenze di origine non contengono gli stessi nomi, è necessario assegnare nuovi nomi nelle chiavi. Ad esempio, se nella tabella `Orders` e nella tabella `OrderDetails` vengono usati nomi diversi per le colonne, è possibile creare chiavi composte assegnando nomi identici nei tipi anonimi:

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

Le chiavi composte possono essere usate anche nella clausola `group`.

## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query)](index.md)  
- [Clausola join](../language-reference/keywords/join-clause.md)  
- [Clausola group](../language-reference/keywords/group-clause.md)  
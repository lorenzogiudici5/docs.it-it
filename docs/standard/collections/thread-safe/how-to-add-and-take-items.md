---
title: 'Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74518f6f56f65668d4c7f073a79c9e7de27d7978
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45645762"
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection
Questo esempio mostra come aggiungere e rimuovere elementi in un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> in modo bloccante e non bloccante. Per altre informazioni su <xref:System.Collections.Concurrent.BlockingCollection%601>, vedere [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
 Per un esempio su come enumerare un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> finché non sarà vuoto e non verranno aggiunti altri elementi, vedere [Procedura: Usare ForEach per rimuovere elementi in un oggetto BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).
  
## <a name="example"></a>Esempio  
 Il primo esempio mostra come aggiungere e rimuovere elementi in modo da bloccare le operazioni se la raccolta è temporaneamente vuota (durante la rimozione) o ha raggiunto la capacità massima (durante l'aggiunta) oppure se è trascorso un periodo di timeout specificato. Si noti che il blocco relativo alla capacità massima è abilitato solo quando l'oggetto BlockingCollection è stato creato specificando una capacità massima nel costruttore.  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a>Esempio  
 Questo secondo esempio mostra come aggiungere e rimuovere elementi in modo da non bloccare le operazioni. Se non è presente alcun elemento, se è stata raggiunta la capacità massima per una raccolta con vincoli oppure è trascorso il periodo di timeout, l'operazione <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> restituisce false. In questo modo, il thread può eseguire per un breve periodo altre operazioni utili e quindi riprovare a recuperare un nuovo elemento o ad aggiungere lo stesso elemento che non è stato possibile aggiungere in precedenza. Il programma illustra inoltre come implementare l'annullamento quando si accede a un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601>.  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
- [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)

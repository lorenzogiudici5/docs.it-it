---
title: 'Procedura: eseguire query asincrone sul servizio dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 4d8e8f15bbb1efeb0b26e452d1b2a51772be9ed7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358713"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Procedura: eseguire query asincrone sul servizio dati (WCF Data Services)
Tramite la libreria client di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile eseguire in modo asincrono operazioni client-server, ad esempio query e salvataggio di modifiche. Per ulteriori informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
>  In un'applicazione in cui il callback deve essere richiamato su un thread specifico, è necessario effettuare il marshalling in modo esplicito del metodo <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Per ulteriori informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come eseguire una query asincrona chiamando il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> per l'avvio della query. Il delegato inline chiama il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> per visualizzare i risultati della query.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

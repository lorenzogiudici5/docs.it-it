---
title: Contratti dati compatibili con versioni successive
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
ms.openlocfilehash: 95a72d5d09538bc6f663f2376c7f8f928909cd57
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492206"
---
# <a name="forward-compatible-data-contracts"></a>Contratti dati compatibili con versioni successive
Una funzionalità di Windows Communication Foundation (WCF) è di sistema di contratti dati che i contratti può evolversi nel tempo in modo da non causare interruzioni. Ovvero, un client con una versione precedente di un contratto dati può comunicare con un servizio dotato di una versione più recente dello stesso contratto dati, oppure un client con una versione più recente di un contratto dati può comunicare con un client dotato di una versione precedente dello stesso contratto dati. Per altre informazioni, vedere [procedure consigliate: controllo delle versioni del contratto dati](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).  
  
 È possibile applicare, in base alle esigenze, la maggior parte delle funzionalità di controllo delle versioni quando vengono create versioni nuove di un contratto dati esistente. Tuttavia, una funzionalità di controllo delle versioni, *andata e ritorno*, deve essere compilato nel tipo della prima versione per il corretto funzionamento.  
  
## <a name="round-tripping"></a>Sequenze di andata e ritorno  
 Le sequenze di andata e ritorno si verificano quando i dati passano da una versione nuova a una versione precedente e di nuovo alla versione nuova di un contratto dati. Le sequenze di andata e ritorno garantiscono che non vi sarà perdita di dati. L'attivazione delle sequenze di andata e ritorno rende il tipo compatibile con versioni successive con eventuali modifiche future supportate dal modello di controllo delle versioni del contratto dati.  
  
 Per consentire sequenze di andata e ritorno per un particolare tipo, quest'ultimo deve implementare l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject>. L'interfaccia contiene una proprietà, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>, che restituisce il tipo <xref:System.Runtime.Serialization.ExtensionDataObject>. La proprietà archivia qualsiasi dato da versioni future del contratto dati che è sconosciuto alla versione corrente.  
  
### <a name="example"></a>Esempio  
 Il contratto dati seguente non è compatibile con modifiche future.  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 Per rendere il tipo compatibile con le modifiche future, ad esempio l'aggiunta di un nuovo membro dati denominato "phoneNumber", implementare l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject>.  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 Quando l'infrastruttura WCF rileva dati che non fa parte del contratto dati originale, i dati vengono archiviati nella proprietà e conservati. Tali dati non vengono elaborati in nessun altro modo a parte l'archiviazione temporanea. Se l'oggetto viene restituito di nuovo all'origine, anche i dati originali (sconosciuti) vengono restituiti. I dati, pertanto, hanno eseguito sequenze di andata e ritorno dall'endpoint di origine senza perdite. Si noti che se l'endpoint di origine, tuttavia, ha richiesto l'elaborazione dei dati, questa aspettativa rimane insoddisfatta e l'endpoint deve in qualche modo rilevare e accogliere la modifica.  
  
 Il tipo <xref:System.Runtime.Serialization.ExtensionDataObject> non contiene metodi o proprietà pubblici. Di conseguenza, è impossibile ottenere accesso diretto ai dati archiviati all'interno della proprietà <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>.  
  
 La funzionalità delle sequenze di andata e ritorno può essere disattivata, impostando `ignoreExtensionDataObject` su `true` nel costruttore <xref:System.Runtime.Serialization.DataContractSerializer> o impostando la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> su `true` in <xref:System.ServiceModel.ServiceBehaviorAttribute>. Quando questa funzionalità è disattivata, il deserializzatore non popolerà la proprietà <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> e il serializzatore non creerà il contenuto della proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 [Controllo delle versioni dei contratti di dati](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [Procedure consigliate: Controllo delle versioni del contratto di dati](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)

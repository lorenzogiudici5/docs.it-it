---
title: '&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 8433ac8f698f3e5569802a8d76f7dedaf22f53c3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180377"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a>&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;
Specifica le impostazioni per un servizio di conversazione protetta.  
  
 \<system.ServiceModel>  
\<i comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<serviceCredentials>  
\<secureConversationAuthentication >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`securityStateEncoderType`|Stringa che specifica il tipo di <xref:System.ServiceModel.Security.SecurityStateEncoder> da usare.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
  
## <a name="remarks"></a>Note  
 Usare questo elemento di configurazione per specificare un elenco di tipi di attestazione noti per la serializzazione dei cookie del token del contesto di sicurezza (SCT, Security Context Token), oltre a un codificatore per la codifica e la sicurezza delle informazioni sui cookie. Per altre informazioni su SCT, vedere <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

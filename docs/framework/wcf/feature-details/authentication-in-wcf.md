---
title: Autenticazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 401bd8901f4d8b9292e83d3e54d0afce30c9584f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785830"
---
# <a name="authentication-in-wcf"></a>Autenticazione in WCF
Gli argomenti seguenti illustrano svariati meccanismi diversi in Windows Communication Foundation (WCF) che forniscono l'autenticazione, ad esempio, l'autenticazione di Windows, i certificati X.509 e nome utente e password.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Usare provider di appartenenza ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Le funzionalità ASP.NET comprendono un provider di appartenenze e ruoli, un database in cui archiviare coppie di nome utente e password per l'autenticazione e ruoli utente per l'autorizzazione. Questo argomento viene illustrato come servizi WCF possono utilizzare lo stesso database per autenticare e autorizzare gli utenti.  
  
 [Procedura: Usare un validator di nome utente e password personalizzato](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Viene dimostrato come integrare un validator di nome utente e password personalizzato  
  
 [Identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 Come ulteriore misura di sicurezza, un client può autenticare il servizio specificando quella prevista *identità* del servizio. Se l'identità prevista e l'identità restituita dal servizio non corrispondono, si verifica l'errore di autenticazione.  
  
 [Negoziazione di sicurezza e timeout](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Viene descritto l'utilizzo della proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> nella classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Debug degli errori di autenticazione di Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Vengono analizzati problemi comuni riscontrabili durante l'autenticazione di Windows.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Scenari di sicurezza comuni](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modello di sicurezza per Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)

---
title: WSDL e criteri
ms.date: 03/30/2017
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
ms.openlocfilehash: 330a48989e9d6ca3cee0d11bf4b3fce38a25fa3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501095"
---
# <a name="wsdl-and-policy"></a>WSDL e criteri
Questo argomento descrive Windows Communication Foundation (WCF) WSDL 1.1, WS-Policy e WS-PolicyAttachment dettagli di implementazione, nonché ulteriori asserzioni WS-Policy e le estensioni WSDL 1.1 introdotte da WCF.  
  
 WCF implementa le specifiche WS-Policy e WS-PolicyAttachment inviate a W3C con i vincoli e i chiarimenti descritti in questo documento.  
  
 In questo documento vengono usati i prefissi e gli spazi dei nomi riportati nella tabella seguente.  
  
|Prefisso|Spazio dei nomi|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|http://schemas.xmlsoap.org/ws/2004/09/policy|  
|wsp (WS-Policy 1.5)|http://www.w3.org/ns/ws-policy|  
|http|http://schemas.microsoft.com/ws/06/2004/policy/http|  
|msmq|http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq|  
|msf|http://schemas.microsoft.com/ws/2006/05/framing/policy|  
|mssp|http://schemas.microsoft.com/ws/2005/07/securitypolicy|  
|msc|http://schemas.microsoft.com/ws/2005/12/wsdl/contract|  
|cdp|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="wcf-wsdl11-extensions"></a>Estensioni WSDL1.1 di WCF  
 WCF Usa le estensioni WSDL1.1 seguenti per descrivere i requisiti delle sessioni di contratto.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 xs: Boolean, indica questa operazione avvia una sessione WCF. il valore predefinito è `false`.  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 xs: Boolean, indica l'operazione termina una sessione WCF. il valore predefinito è `false`.  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, indica che questo contratto richiede una sessione per essere stabilito.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>URI dei trasporti delle associazioni SOAP 1.x HTTP  
 WCF Usa gli URI seguenti per indicare i trasporti da usare per gli elementi di estensione associazioni WSDL 1.1, SOAP 1.1 e SOAP 1.2.  
  
|Trasporto|URI|  
|---------------|---------|  
|HTTP|http://schemas.xmlsoap.org/soap/http|  
|TCP|http://schemas.microsoft.com/soap/tcp|  
|MSMQ|http://schemas.microsoft.com/soap/msmq|  
|Named pipe|http://schemas.microsoft.com/soap/named-pipe|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Asserzioni di criteri implementate da WCF  
 Oltre alle asserzioni di criteri introdotte nelle specifiche dei servizi Web (WS-*) e indicate nelle altre sezioni di questo documento, WCF implementa le asserzioni di criteri seguenti.  
  
|Asserzione di criteri|Soggetto dei criteri|Descrizione|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Endpoint|L'endpoint usa l'autenticazione di base HTTP.|  
|http:HttpDigestAuthentication|Endpoint|L'endpoint usa l'autenticazione digest HTTP.|  
|http:HttpNegotiateAuthentication|Endpoint|L'endpoint usa l'autenticazione Negotiate HTTP.|  
|http:HttpNtlmAuthentication|Endpoint|L'endpoint usa l'autenticazione NTLM HTTP.|  
|msf:Streamed|Endpoint|L'endpoint usa il framing dei messaggi trasmessi. Questa asserzione viene usata con il protocollo di framing dei messaggi fornito per trasporti quali TCP e named pipe.|  
|msf:SslTransportSecurity|Endpoint|L'endpoint usa la protezione a livello di trasporto (TLS) con il framing dei messaggi.|  
|msf:WindowsTransportSecurity|Endpoint|L'endpoint usa Security Provider Negotiation (SPNEGO) con il framing dei messaggi.|  
|msmq:MsmqBestEffort|Endpoint|MSMQ con le migliori garanzie.|  
|msmq:MsmqSession|Endpoint|MSMQ con le garanzie di sessione.|  
|msmq:MsmqVolatile|Endpoint|MSMQ volatile.|  
|msmq:Authenticated|Endpoint|L'autenticazione viene usata con il trasporto MSMQ.|  
|msmq:WindowsDomain|Endpoint|MSMQ usa l'autenticazione dei domini di Windows.|  
|cdp:CompositeDuplex|Endpoint|L'endpoint usa due connessioni di trasporto contrarie separate per i messaggi in ingresso e in uscita.|  
|mssp:RsaToken|Annidata|Asserzione del token della chiave RSA. Questo requisito viene generalmente soddisfatto da una chiave RSA serializza direttamente come parte delle informazioni sulla chiave in una firma di verifica dell'autenticità.|  
|mssp:SslContextToken|Annidata|Richiede che venga usato un SecurityContextToken ottenuto mediante un handshake TLS binario che usa WS-Trust. Le asserzioni annidate includono: sp:RequireDerivedKeys, mssp:MustNotSendCancel, mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|Annidata|Specifica un requisito secondo cui all'autorità emittente di un determinato SecurityContextToken non devono essere inviati messaggi di richiesta di un token RST (Request Security Token) [WS-Trust] usando l'associazione Cancel [WS-Trust, WS-SC]. Se questa asserzione è presente, tali messaggi di richiesta non devono essere inviati all'autorità emittente. Se questa asserzione non è presente, tali messaggi di richiesta possono essere inviati all'autorità emittente.|  
|mssp:RequireClientCertificate|Annidata|Questo elemento facoltativo specifica un requisito secondo cui deve essere fornito un certificato client come parte del protocollo TLSNEGO. Se questa asserzione è presente, deve essere fornito un certificato client. Se questa asserzione non è presente, non deve essere fornito un certificato client. Questa asserzione non deve essere usata al di fuori di mssp:SslContextToken.|  
  
## <a name="see-also"></a>Vedere anche  
 [Pubblicazione WSDL personalizzata](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)  
 [Procedura: Esportare informazioni WSDL personalizzate](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)  
 [Procedura: Importare informazioni WSDL personalizzate](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)

---
title: Cert2spc.exe (strumento di test dei certificati del distributore di software)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75c782cbe7a45c05212c99448df6e8536a17f38d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50202735"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a>Cert2spc.exe (strumento di test dei certificati del distributore di software)
Lo strumento di verifica dei certificati dell'editore del software (Cert2spc.exe) crea un certificato SPC (Software Publisher's Certificate) da uno o più certificati X.509 ed è finalizzato unicamente ai test. È possibile ottenere un certificato SPC valido da un'autorità di certificazione quale VeriSign o Thawte. Per ulteriori informazioni sulla creazione di certificati X.509, vedere [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione dei comandi).  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7. Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|`certN.cer`|Il nome di un certificato X.509 da includere nel file SPC. È possibile specificare più nomi separati da spazi.|  
|`crlN.crl`|Il nome di un elenco di revoche di certificati da includere nel file SPC. È possibile specificare più nomi separati da spazi.|  
|`outputSPCfile.spc`|Il nome dell'oggetto PKCS #7 che conterrà i certificati X.509.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="examples"></a>Esempi  
 Il comando che segue crea un certificato SPC da `myCertificate.cer` e lo inserisce in `mySPCFile.spc`.  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 Il comando che segue crea un certificato SPC da `oneCertificate.cer` e `twoCertificate.cer` e lo inserisce in `mySPCFile.spc`.  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Strumenti](../../../docs/framework/tools/index.md)  
 [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione certificati)  
 [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

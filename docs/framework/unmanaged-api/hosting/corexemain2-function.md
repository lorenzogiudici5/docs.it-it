---
title: Funzione _CorExeMain2
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 573336b32040f44ff1b59fcbb75b59aa00976b5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430179"
---
# <a name="corexemain2-function"></a>Funzione _CorExeMain2
Esegue il punto di ingresso nel codice mappato alla memoria specificato. Questa funzione viene chiamata dal caricatore del sistema operativo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pUnmappedPE`  
 [in] Puntatore al codice mappato alla memoria.  
  
 `cUnmappedPE`  
 [in] Il numero di elementi `pUnmappedPE` può contenere.  
  
 `pImageNameIn`  
 [in] Un puntatore al nome dell'immagine eseguibile.  
  
 `pLoadersFileName`  
 [in] Il nome del file di caricatore.  
  
 `pCmdLine`  
 [in] Parametri della riga di comando, se presente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

---
title: Funzione _CorExeMain2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorExeMain2
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorExeMain2
helpviewer_keywords: _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c705627de8e8157212ae3e6a2ab4f2c12246653
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corexemain2-function"></a><span data-ttu-id="ce620-102">Funzione _CorExeMain2</span><span class="sxs-lookup"><span data-stu-id="ce620-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="ce620-103">Esegue il punto di ingresso nel codice mappato alla memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="ce620-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="ce620-104">Questa funzione viene chiamata dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ce620-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce620-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce620-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce620-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce620-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="ce620-107">[in] Puntatore al codice mappato alla memoria.</span><span class="sxs-lookup"><span data-stu-id="ce620-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="ce620-108">[in] Il numero di elementi `pUnmappedPE` può contenere.</span><span class="sxs-lookup"><span data-stu-id="ce620-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="ce620-109">[in] Un puntatore al nome dell'immagine eseguibile.</span><span class="sxs-lookup"><span data-stu-id="ce620-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="ce620-110">[in] Il nome del file di caricatore.</span><span class="sxs-lookup"><span data-stu-id="ce620-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="ce620-111">[in] Parametri della riga di comando, se presente.</span><span class="sxs-lookup"><span data-stu-id="ce620-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce620-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce620-112">Requirements</span></span>  
 <span data-ttu-id="ce620-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce620-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce620-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce620-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce620-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce620-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce620-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce620-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce620-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce620-117">See Also</span></span>  
 [<span data-ttu-id="ce620-118">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="ce620-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
---
title: Metodo ISymUnmanagedENCUpdate::UpdateMethodLines
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateMethodLines
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba3e4443ecccb0e49e3a4e5a12ae07fd8916ac21
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="6ec0f-102">Metodo ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="6ec0f-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="6ec0f-103">Consente l'aggiornamento delle informazioni di riga per un metodo che non è stato ricompilato, ma le cui righe sono stati spostati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="6ec0f-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="6ec0f-104">È consentito un delta per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="6ec0f-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec0f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ec0f-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ec0f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ec0f-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="6ec0f-107">[in] I metadati del token del metodo.</span><span class="sxs-lookup"><span data-stu-id="6ec0f-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="6ec0f-108">[in] Matrice di `INT32` valori che indica i delta per ogni punto di sequenza nel metodo.</span><span class="sxs-lookup"><span data-stu-id="6ec0f-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="6ec0f-109">[in] Oggetto `ULONG` contenente la dimensione del `pDeltas` parametro.</span><span class="sxs-lookup"><span data-stu-id="6ec0f-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ec0f-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6ec0f-110">Return Value</span></span>  
 <span data-ttu-id="6ec0f-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6ec0f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec0f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ec0f-112">Requirements</span></span>  
 <span data-ttu-id="6ec0f-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6ec0f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec0f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec0f-114">See Also</span></span>  
 [<span data-ttu-id="6ec0f-115">ISymUnmanagedENCUpdate (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6ec0f-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
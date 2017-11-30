---
title: Metodo ICLRProbingAssemblyEnum::Get
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cdd198f7a7a35fe4df371f3a53964b94459fd314
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="ac70f-102">Metodo ICLRProbingAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="ac70f-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="ac70f-103">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="ac70f-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac70f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac70f-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac70f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac70f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="ac70f-106">[in] Indice in base zero dell'identità dell'assembly da restituire.</span><span class="sxs-lookup"><span data-stu-id="ac70f-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="ac70f-107">[out] Un buffer contenente i dati di identità di assembly.</span><span class="sxs-lookup"><span data-stu-id="ac70f-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="ac70f-108">[in, out] Le dimensioni del `pwzBuffer` buffer.</span><span class="sxs-lookup"><span data-stu-id="ac70f-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac70f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac70f-109">Return Value</span></span>  
  
|<span data-ttu-id="ac70f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac70f-110">HRESULT</span></span>|<span data-ttu-id="ac70f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac70f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac70f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac70f-112">S_OK</span></span>|<span data-ttu-id="ac70f-113">`Get`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac70f-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="ac70f-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ac70f-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ac70f-115">`pwzBuffer`è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="ac70f-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="ac70f-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="ac70f-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="ac70f-117">L'enumerazione non contiene più elementi.</span><span class="sxs-lookup"><span data-stu-id="ac70f-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="ac70f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac70f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac70f-119">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac70f-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac70f-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac70f-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac70f-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac70f-121">The call timed out.</span></span>|  
|<span data-ttu-id="ac70f-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac70f-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac70f-123">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="ac70f-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac70f-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac70f-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac70f-125">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ac70f-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac70f-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac70f-126">E_FAIL</span></span>|<span data-ttu-id="ac70f-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ac70f-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac70f-128">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ac70f-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac70f-129">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac70f-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac70f-130">Note</span><span class="sxs-lookup"><span data-stu-id="ac70f-130">Remarks</span></span>  
 <span data-ttu-id="ac70f-131">L'identità in corrispondenza dell'indice 0 è l'identità specifica per l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="ac70f-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="ac70f-132">L'identità in corrispondenza dell'indice 1 è l'assembly di architettura neutra per Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="ac70f-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="ac70f-133">L'identità in corrispondenza dell'indice 2 non contiene alcuna informazione di architettura.</span><span class="sxs-lookup"><span data-stu-id="ac70f-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="ac70f-134">`Get`viene in genere chiamato due volte.</span><span class="sxs-lookup"><span data-stu-id="ac70f-134">`Get` is typically called twice.</span></span> <span data-ttu-id="ac70f-135">La prima chiamata fornisce un valore null per `pwzBuffer`e imposta `pcchBufferSize` per le dimensioni appropriate per `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ac70f-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="ac70f-136">La seconda chiamata viene fornito un dimensionati `pwzBuffer`e contiene i dati di identità assembly canonica dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="ac70f-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac70f-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac70f-137">Requirements</span></span>  
 <span data-ttu-id="ac70f-138">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac70f-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac70f-139">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ac70f-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac70f-140">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac70f-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac70f-141">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac70f-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac70f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac70f-142">See Also</span></span>  
 [<span data-ttu-id="ac70f-143">ICLRProbingAssemblyEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ac70f-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="ac70f-144">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ac70f-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
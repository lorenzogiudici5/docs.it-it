---
title: Metodo ICLRGCManager2::SetGCStartupLimitsEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73f5678008354b312964f0cb32d768d36a641fd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="49936-102">Metodo ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="49936-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="49936-103">Imposta le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="49936-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49936-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49936-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49936-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49936-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="49936-106">[in] La dimensione specificata per un segmento di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="49936-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="49936-107">La dimensione minima del segmento è 4 MB.</span><span class="sxs-lookup"><span data-stu-id="49936-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="49936-108">Segmenti possono essere aumentate in incrementi di 1 MB o maggiori.</span><span class="sxs-lookup"><span data-stu-id="49936-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="49936-109">[in] La dimensione massima specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="49936-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="49936-110">La dimensione minima per la generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="49936-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49936-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="49936-111">Return Value</span></span>  
  
|<span data-ttu-id="49936-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49936-112">HRESULT</span></span>|<span data-ttu-id="49936-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49936-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49936-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="49936-114">S_OK</span></span>|<span data-ttu-id="49936-115">`SetGCStartupLimitsEx`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="49936-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="49936-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49936-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49936-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="49936-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49936-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49936-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49936-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="49936-119">The call timed out.</span></span>|  
|<span data-ttu-id="49936-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49936-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49936-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="49936-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49936-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49936-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49936-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="49936-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49936-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49936-124">E_FAIL</span></span>|<span data-ttu-id="49936-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="49936-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49936-126">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="49936-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49936-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="49936-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49936-128">Note</span><span class="sxs-lookup"><span data-stu-id="49936-128">Remarks</span></span>  
 <span data-ttu-id="49936-129">I valori che `SetGCStartupLimitsEx` set possono essere specificati solo prima che l'host viene avviata.</span><span class="sxs-lookup"><span data-stu-id="49936-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="49936-130">Le chiamate successive a `SetGCStartupLimitsEx` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="49936-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="49936-131">Per impostare uno dei parametri senza influire su altro, specificare 0 (zero) per il parametro che non si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="49936-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49936-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49936-132">Requirements</span></span>  
 <span data-ttu-id="49936-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49936-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49936-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="49936-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49936-135">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49936-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49936-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49936-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49936-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49936-137">See Also</span></span>  
 [<span data-ttu-id="49936-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="49936-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="49936-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="49936-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="49936-140">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="49936-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="49936-141">ICLRGCManager2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="49936-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
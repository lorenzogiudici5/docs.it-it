---
title: Metodo IHostSemaphore::Wait
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d30a946cadc312e683d256ce6f08528cffa95481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="9dca6-102">Metodo IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="9dca6-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="9dca6-103">Fa sì che l'oggetto corrente [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) in attesa fino a quando non è di proprietà istanza o il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="9dca6-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dca6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dca6-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dca6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9dca6-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="9dca6-106">[in] Il numero di millisecondi di attesa prima della restituzione, se l'oggetto corrente `IHostSemaphore` istanza non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="9dca6-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="9dca6-107">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che specifica l'azione che operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="9dca6-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dca6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9dca6-108">Return Value</span></span>  
  
|<span data-ttu-id="9dca6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dca6-109">HRESULT</span></span>|<span data-ttu-id="9dca6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dca6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dca6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dca6-111">S_OK</span></span>|<span data-ttu-id="9dca6-112">`Wait`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9dca6-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="9dca6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dca6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dca6-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dca6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dca6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dca6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dca6-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dca6-116">The call timed out.</span></span>|  
|<span data-ttu-id="9dca6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dca6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dca6-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="9dca6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dca6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dca6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dca6-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9dca6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dca6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dca6-121">E_FAIL</span></span>|<span data-ttu-id="9dca6-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9dca6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dca6-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9dca6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dca6-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9dca6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9dca6-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="9dca6-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="9dca6-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e sceglie corrente `IHostSemaphore` istanza come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="9dca6-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9dca6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dca6-127">Requirements</span></span>  
 <span data-ttu-id="9dca6-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dca6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dca6-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9dca6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dca6-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dca6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dca6-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dca6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dca6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dca6-132">See Also</span></span>  
 [<span data-ttu-id="9dca6-133">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9dca6-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="9dca6-134">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9dca6-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="9dca6-135">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9dca6-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="9dca6-136">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9dca6-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="9dca6-137">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9dca6-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
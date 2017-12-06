---
title: Metodo IHostTaskManager::CreateTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CreateTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ba71fcd35b16654ab67db3f657f7821c23b702
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="69ed1-102">Metodo IHostTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="69ed1-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="69ed1-103">Richieste che l'host crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="69ed1-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69ed1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69ed1-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69ed1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69ed1-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="69ed1-106">[in] La dimensione richiesta, in byte, dello stack richiesto oppure 0 (zero) per la dimensione predefinita.</span><span class="sxs-lookup"><span data-stu-id="69ed1-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="69ed1-107">[in] Un puntatore alla funzione l'attività è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="69ed1-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="69ed1-108">[in] Un puntatore ai dati utente deve essere passato alla funzione, o null se la funzione non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="69ed1-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="69ed1-109">[out] Un puntatore all'indirizzo di un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza creata da host oppure null se non è possibile creare l'attività.</span><span class="sxs-lookup"><span data-stu-id="69ed1-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="69ed1-110">L'attività rimane in uno stato sospeso finché non viene avviata in modo esplicito da una chiamata a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="69ed1-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69ed1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="69ed1-111">Return Value</span></span>  
  
|<span data-ttu-id="69ed1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69ed1-112">HRESULT</span></span>|<span data-ttu-id="69ed1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69ed1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69ed1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="69ed1-114">S_OK</span></span>|<span data-ttu-id="69ed1-115">`CreateTask`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="69ed1-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="69ed1-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69ed1-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69ed1-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="69ed1-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="69ed1-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="69ed1-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="69ed1-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="69ed1-119">The call timed out.</span></span>|  
|<span data-ttu-id="69ed1-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="69ed1-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="69ed1-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="69ed1-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="69ed1-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="69ed1-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="69ed1-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="69ed1-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="69ed1-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69ed1-124">E_FAIL</span></span>|<span data-ttu-id="69ed1-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="69ed1-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="69ed1-126">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="69ed1-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="69ed1-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="69ed1-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="69ed1-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="69ed1-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="69ed1-129">Memoria insufficiente è disponibile per creare l'attività richiesta.</span><span class="sxs-lookup"><span data-stu-id="69ed1-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69ed1-130">Note</span><span class="sxs-lookup"><span data-stu-id="69ed1-130">Remarks</span></span>  
 <span data-ttu-id="69ed1-131">CLR chiama `CreateTask` per richiedere che l'host crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="69ed1-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="69ed1-132">L'host restituisce un puntatore a interfaccia a un `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="69ed1-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="69ed1-133">L'attività restituita deve rimanere sospesa fino a quando non viene avviata in modo esplicito da una chiamata a `IHostTask::Start`.</span><span class="sxs-lookup"><span data-stu-id="69ed1-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69ed1-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69ed1-134">Requirements</span></span>  
 <span data-ttu-id="69ed1-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69ed1-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69ed1-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="69ed1-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69ed1-137">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69ed1-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69ed1-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69ed1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ed1-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69ed1-139">See Also</span></span>  
 [<span data-ttu-id="69ed1-140">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="69ed1-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="69ed1-141">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="69ed1-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="69ed1-142">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="69ed1-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="69ed1-143">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="69ed1-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
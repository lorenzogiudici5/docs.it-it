---
title: Metodo IHostTaskManager::LeaveRuntime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.LeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 326fa3d495cafe187f06e1e6a804cbe90fb12efd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="e04fa-102">Metodo IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="e04fa-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="e04fa-103">Notifica all'host che l'attività attualmente in esecuzione sta per lasciare common language runtime (CLR) e immettere il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="e04fa-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e04fa-104">Una chiamata corrispondente al [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione sta rientrando nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e04fa-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04fa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e04fa-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e04fa-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e04fa-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="e04fa-107">[in] L'indirizzo all'interno del file eseguibile portabile con mapping di funzione non gestita da chiamare.</span><span class="sxs-lookup"><span data-stu-id="e04fa-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e04fa-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e04fa-108">Return Value</span></span>  
  
|<span data-ttu-id="e04fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e04fa-109">HRESULT</span></span>|<span data-ttu-id="e04fa-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e04fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e04fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e04fa-111">S_OK</span></span>|<span data-ttu-id="e04fa-112">`LeaveRuntime`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e04fa-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="e04fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e04fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e04fa-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e04fa-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e04fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e04fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e04fa-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e04fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="e04fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e04fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e04fa-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="e04fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e04fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e04fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e04fa-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e04fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e04fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e04fa-121">E_FAIL</span></span>|<span data-ttu-id="e04fa-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e04fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e04fa-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e04fa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e04fa-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e04fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e04fa-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e04fa-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e04fa-126">Memoria insufficiente è disponibile per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="e04fa-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e04fa-127">Note</span><span class="sxs-lookup"><span data-stu-id="e04fa-127">Remarks</span></span>  
 <span data-ttu-id="e04fa-128">Le sequenze di chiamate da e verso codice non gestito possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="e04fa-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="e04fa-129">Ad esempio, nell'elenco seguente descrive una situazione ipotetica in cui la sequenza di chiamate a `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.</span><span class="sxs-lookup"><span data-stu-id="e04fa-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="e04fa-130">Operazione</span><span class="sxs-lookup"><span data-stu-id="e04fa-130">Action</span></span>|<span data-ttu-id="e04fa-131">Chiamata al metodo corrispondente</span><span class="sxs-lookup"><span data-stu-id="e04fa-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="e04fa-132">Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C utilizzando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="e04fa-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="e04fa-133">La funzione C non gestita chiama un metodo in una DLL gestita scritta in c#.</span><span class="sxs-lookup"><span data-stu-id="e04fa-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="e04fa-134">La funzione c# gestita chiama un'altra funzione non gestita scritta in C, sempre tramite platform invoke.</span><span class="sxs-lookup"><span data-stu-id="e04fa-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="e04fa-135">La seconda funzione non gestita restituisce l'esecuzione della funzione di c#.</span><span class="sxs-lookup"><span data-stu-id="e04fa-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="e04fa-136">La funzione c# restituisce l'esecuzione per la prima funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e04fa-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="e04fa-137">La prima funzione non gestita restituisce l'esecuzione del programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e04fa-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="e04fa-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e04fa-138">Requirements</span></span>  
 <span data-ttu-id="e04fa-139">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e04fa-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e04fa-140">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e04fa-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e04fa-141">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e04fa-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e04fa-142">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e04fa-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04fa-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e04fa-143">See Also</span></span>  
 [<span data-ttu-id="e04fa-144">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e04fa-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e04fa-145">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e04fa-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e04fa-146">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e04fa-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e04fa-147">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e04fa-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
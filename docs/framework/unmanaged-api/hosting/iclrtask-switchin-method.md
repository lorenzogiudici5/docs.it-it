---
title: Metodo ICLRTask::SwitchIn
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchIn
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01e91c4febfebf8ec8ffd4c0ffbf8e33a4ff0edd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="2143a-102">Metodo ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="2143a-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="2143a-103">Notifica a common language runtime (CLR) che l'attività che corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza si trova ora in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="2143a-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2143a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2143a-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2143a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2143a-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="2143a-106">[in] Un handle per il thread fisico in cui l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2143a-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2143a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2143a-107">Return Value</span></span>  
  
|<span data-ttu-id="2143a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2143a-108">HRESULT</span></span>|<span data-ttu-id="2143a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2143a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2143a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2143a-110">S_OK</span></span>|<span data-ttu-id="2143a-111">`SwitchIn`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2143a-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="2143a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2143a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2143a-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2143a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2143a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2143a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2143a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2143a-115">The call timed out.</span></span>|  
|<span data-ttu-id="2143a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2143a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2143a-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="2143a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2143a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2143a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2143a-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2143a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2143a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2143a-120">E_FAIL</span></span>|<span data-ttu-id="2143a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2143a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2143a-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2143a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2143a-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2143a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2143a-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="2143a-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="2143a-125">`SwitchIn`è stato chiamato senza una chiamata precedente a [SwitchOut (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="2143a-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2143a-126">Note</span><span class="sxs-lookup"><span data-stu-id="2143a-126">Remarks</span></span>  
 <span data-ttu-id="2143a-127">Il `threadHandle` parametro rappresenta un handle per il thread del sistema operativo in cui l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza è stata pianificata.</span><span class="sxs-lookup"><span data-stu-id="2143a-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="2143a-128">Se la rappresentazione è stata eseguita sul thread, è necessario chiamare [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) prima di passare all'attività.</span><span class="sxs-lookup"><span data-stu-id="2143a-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2143a-129">Una chiamata a `SwitchIn` senza una chiamata precedente a `SwitchOut` ha esito negativo con un valore HRESULT HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="2143a-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2143a-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2143a-130">Requirements</span></span>  
 <span data-ttu-id="2143a-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2143a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2143a-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2143a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2143a-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2143a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2143a-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2143a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2143a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2143a-135">See Also</span></span>  
 [<span data-ttu-id="2143a-136">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2143a-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2143a-137">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2143a-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2143a-138">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2143a-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2143a-139">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2143a-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
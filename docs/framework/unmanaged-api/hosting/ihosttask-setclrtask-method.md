---
title: Metodo IHostTask::SetCLRTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.SetCLRTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54706b1c3a6ea1864137e2eca135fa6bd883b345
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="39349-102">Metodo IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="39349-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="39349-103">Associa un `ICLRTask` istanza con l'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="39349-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39349-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39349-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39349-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39349-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="39349-106">[in] Un puntatore a interfaccia per il `ICLRTask` istanza sia associato all'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="39349-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39349-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="39349-107">Return Value</span></span>  
  
|<span data-ttu-id="39349-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39349-108">HRESULT</span></span>|<span data-ttu-id="39349-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39349-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39349-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="39349-110">S_OK</span></span>|<span data-ttu-id="39349-111">`SetCLRTask`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="39349-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="39349-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39349-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39349-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="39349-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39349-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39349-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39349-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="39349-115">The call timed out.</span></span>|  
|<span data-ttu-id="39349-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39349-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39349-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="39349-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39349-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39349-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39349-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="39349-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39349-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39349-120">E_FAIL</span></span>|<span data-ttu-id="39349-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="39349-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39349-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="39349-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39349-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="39349-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39349-124">Note</span><span class="sxs-lookup"><span data-stu-id="39349-124">Remarks</span></span>  
 <span data-ttu-id="39349-125">CLR chiama `SetCLRTask` per associare un `ICLRTask` istanza con l'oggetto corrente `IHostTask` istanza, che è stato creato da una chiamata a [CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="39349-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39349-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39349-126">Requirements</span></span>  
 <span data-ttu-id="39349-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39349-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39349-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="39349-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39349-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39349-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39349-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39349-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39349-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39349-131">See Also</span></span>  
 [<span data-ttu-id="39349-132">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="39349-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="39349-133">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="39349-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="39349-134">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="39349-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="39349-135">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="39349-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
---
title: Metodo IActionOnCLREvent::OnEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IActionOnCLREvent.OnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b2f609969ccf67f07701d20578225f1618293968
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="17a79-102">Metodo IActionOnCLREvent::OnEvent</span><span class="sxs-lookup"><span data-stu-id="17a79-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="17a79-103">Esegue callback su eventi registrati tramite una chiamata al [ICLROnEventManager::](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="17a79-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17a79-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17a79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17a79-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="17a79-106">[in] Uno del [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valori, che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="17a79-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="17a79-107">[in] Un puntatore a un oggetto che contiene i dettagli sulle `event`.</span><span class="sxs-lookup"><span data-stu-id="17a79-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17a79-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17a79-108">Return Value</span></span>  
  
|<span data-ttu-id="17a79-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17a79-109">HRESULT</span></span>|<span data-ttu-id="17a79-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17a79-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17a79-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="17a79-111">S_OK</span></span>|<span data-ttu-id="17a79-112">`OnEvent`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="17a79-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="17a79-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17a79-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17a79-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="17a79-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17a79-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17a79-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17a79-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="17a79-116">The call timed out.</span></span>|  
|<span data-ttu-id="17a79-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17a79-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17a79-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="17a79-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17a79-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17a79-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17a79-120">Un evento è stato annullato durante un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="17a79-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17a79-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17a79-121">E_FAIL</span></span>|<span data-ttu-id="17a79-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="17a79-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17a79-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="17a79-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17a79-124">Le chiamate successive a un metodo di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17a79-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17a79-125">Note</span><span class="sxs-lookup"><span data-stu-id="17a79-125">Remarks</span></span>  
 <span data-ttu-id="17a79-126">Il `data` parametro è un puntatore a un oggetto di tipo non specificato.</span><span class="sxs-lookup"><span data-stu-id="17a79-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="17a79-127">Se il `event` parametro `Event_DomainUnload`, `data` è l'identificatore numerico per il <xref:System.AppDomain> che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="17a79-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="17a79-128">L'host può intraprendere l'azione appropriata utilizzando questo identificatore come chiave.</span><span class="sxs-lookup"><span data-stu-id="17a79-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="17a79-129">Se `event` è `Event_MDAFired`, `data` è un puntatore a un [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) istanza contenente l'output del messaggio da un gestiti (Assistente al debug).</span><span class="sxs-lookup"><span data-stu-id="17a79-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="17a79-130">Assistenti al debug gestito sono una funzionalità di Common Language Runtime che consentono agli sviluppatori eseguendo il debug, tramite la generazione di messaggi XML su eventi che altrimenti sarebbero difficili da rilevare.</span><span class="sxs-lookup"><span data-stu-id="17a79-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="17a79-131">Tali messaggi possono essere particolarmente utili in transizioni tra codice gestito e di debug.</span><span class="sxs-lookup"><span data-stu-id="17a79-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="17a79-132">Per ulteriori informazioni, vedere [la diagnosi di errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="17a79-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17a79-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17a79-133">Requirements</span></span>  
 <span data-ttu-id="17a79-134">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17a79-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17a79-135">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="17a79-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17a79-136">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17a79-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17a79-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17a79-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a79-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17a79-138">See Also</span></span>  
 [<span data-ttu-id="17a79-139">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="17a79-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="17a79-140">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="17a79-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="17a79-141">IActionOnCLREvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="17a79-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="17a79-142">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="17a79-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="17a79-143">ICLROnEventManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="17a79-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="17a79-144">MDAInfo (struttura)</span><span class="sxs-lookup"><span data-stu-id="17a79-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
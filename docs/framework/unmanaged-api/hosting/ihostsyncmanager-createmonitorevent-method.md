---
title: Metodo IHostSyncManager::CreateMonitorEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateMonitorEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c16c1376237916d09fb4156b023f4f1cc51a7d54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="10ad0-102">Metodo IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="10ad0-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="10ad0-103">Crea un oggetto evento di reimpostazione automatica monitorato.</span><span class="sxs-lookup"><span data-stu-id="10ad0-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ad0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10ad0-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10ad0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10ad0-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="10ad0-106">[in] Cookie da associare all'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="10ad0-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="10ad0-107">[out] Un puntatore all'indirizzo di un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="10ad0-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10ad0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="10ad0-108">Return Value</span></span>  
  
|<span data-ttu-id="10ad0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10ad0-109">HRESULT</span></span>|<span data-ttu-id="10ad0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10ad0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10ad0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="10ad0-111">S_OK</span></span>|<span data-ttu-id="10ad0-112">`CreateMonitorEvent`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="10ad0-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="10ad0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10ad0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10ad0-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="10ad0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10ad0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10ad0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10ad0-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="10ad0-116">The call timed out.</span></span>|  
|<span data-ttu-id="10ad0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10ad0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10ad0-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="10ad0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10ad0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10ad0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10ad0-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="10ad0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10ad0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10ad0-121">E_FAIL</span></span>|<span data-ttu-id="10ad0-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="10ad0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10ad0-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="10ad0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10ad0-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10ad0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="10ad0-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="10ad0-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="10ad0-126">È disponibile per creare l'oggetto evento richiesto non è sufficiente memoria.</span><span class="sxs-lookup"><span data-stu-id="10ad0-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10ad0-127">Note</span><span class="sxs-lookup"><span data-stu-id="10ad0-127">Remarks</span></span>  
 <span data-ttu-id="10ad0-128">`CreateMonitorEvent`Restituisce un `IHostAutoEvent` usati da CLR nella sua implementazione di gestito <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="10ad0-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="10ad0-129">Questo metodo riflette Win32 `CreateEvent` funzione, con un valore di `false` specificato per il `bManualReset` parametro.</span><span class="sxs-lookup"><span data-stu-id="10ad0-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="10ad0-130">L'host può utilizzare il cookie per determinare quale attività sono in attesa sul monitor chiamando il [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="10ad0-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ad0-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10ad0-131">Requirements</span></span>  
 <span data-ttu-id="10ad0-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ad0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ad0-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="10ad0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10ad0-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10ad0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10ad0-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ad0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ad0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ad0-136">See Also</span></span>  
 [<span data-ttu-id="10ad0-137">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="10ad0-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="10ad0-138">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="10ad0-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="10ad0-139">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="10ad0-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="10ad0-140">Monitoraggi</span><span class="sxs-lookup"><span data-stu-id="10ad0-140">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
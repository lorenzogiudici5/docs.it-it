---
title: Metodo IHostMemoryManager::VirtualProtect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualProtect
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f8d363054ab4728ae031ccea44eb8eb853354ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="026dc-102">Metodo IHostMemoryManager::VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="026dc-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="026dc-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="026dc-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="026dc-104">L'implementazione Win32 di `VirtualProtect` modifica la protezione in un'area di pagine salvate nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="026dc-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="026dc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="026dc-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="026dc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="026dc-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="026dc-107">[in] Un puntatore all'indirizzo di base per la memoria virtuale i cui attributi di protezione devono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="026dc-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="026dc-108">[in] Le dimensioni in byte, dell'area delle pagine di memoria da modificare.</span><span class="sxs-lookup"><span data-stu-id="026dc-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="026dc-109">[in] Il tipo di protezione della memoria da applicare.</span><span class="sxs-lookup"><span data-stu-id="026dc-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="026dc-110">[out] Puntatore al valore precedente della memoria protezione.</span><span class="sxs-lookup"><span data-stu-id="026dc-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="026dc-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="026dc-111">Return Value</span></span>  
  
|<span data-ttu-id="026dc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="026dc-112">HRESULT</span></span>|<span data-ttu-id="026dc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="026dc-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="026dc-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="026dc-114">S_OK</span></span>|<span data-ttu-id="026dc-115">`VirtualProtect`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="026dc-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="026dc-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="026dc-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="026dc-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="026dc-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="026dc-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="026dc-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="026dc-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="026dc-119">The call timed out.</span></span>|  
|<span data-ttu-id="026dc-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="026dc-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="026dc-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="026dc-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="026dc-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="026dc-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="026dc-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="026dc-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="026dc-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="026dc-124">E_FAIL</span></span>|<span data-ttu-id="026dc-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="026dc-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="026dc-126">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="026dc-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="026dc-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="026dc-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="026dc-128">Note</span><span class="sxs-lookup"><span data-stu-id="026dc-128">Remarks</span></span>  
 <span data-ttu-id="026dc-129">Questa implementazione di `VirtualProtect` restituisce un valore HRESULT, mentre l'implementazione Win32 restituisce un valore diverso da zero per indicare l'esito positivo e il valore zero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="026dc-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="026dc-130">Per ulteriori informazioni, vedere la documentazione di piattaforma di Windows.</span><span class="sxs-lookup"><span data-stu-id="026dc-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="026dc-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="026dc-131">Requirements</span></span>  
 <span data-ttu-id="026dc-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="026dc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="026dc-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="026dc-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="026dc-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="026dc-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="026dc-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="026dc-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="026dc-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="026dc-136">See Also</span></span>  
 [<span data-ttu-id="026dc-137">IHostMemoryManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="026dc-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
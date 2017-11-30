---
title: Interfaccia IHostCrst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="f2ca9-102">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="f2ca9-102">IHostCrst Interface</span></span>
<span data-ttu-id="f2ca9-103">Serve come rappresentazione dell'host di una sezione critica di threading.</span><span class="sxs-lookup"><span data-stu-id="f2ca9-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2ca9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f2ca9-104">Methods</span></span>  
  
|<span data-ttu-id="f2ca9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f2ca9-105">Method</span></span>|<span data-ttu-id="f2ca9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2ca9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2ca9-107">Enter (metodo)</span><span class="sxs-lookup"><span data-stu-id="f2ca9-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="f2ca9-108">Entra nella sezione critica.</span><span class="sxs-lookup"><span data-stu-id="f2ca9-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="f2ca9-109">Leave (metodo)</span><span class="sxs-lookup"><span data-stu-id="f2ca9-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="f2ca9-110">Esce dalla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="f2ca9-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="f2ca9-111">SetSpinCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="f2ca9-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="f2ca9-112">Imposta il conteggio di selezione per la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="f2ca9-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="f2ca9-113">TryEnter (metodo)</span><span class="sxs-lookup"><span data-stu-id="f2ca9-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="f2ca9-114">Tenta di accedere immediatamente sezione critica e i report l'esito.</span><span class="sxs-lookup"><span data-stu-id="f2ca9-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2ca9-115">Note</span><span class="sxs-lookup"><span data-stu-id="f2ca9-115">Remarks</span></span>  
 <span data-ttu-id="f2ca9-116">`IHostCrst`consente a common language runtime (CLR) per comunicare direttamente con la rappresentazione dell'host di una sezione critica, anziché utilizzare le funzioni Win32, ad esempio `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="f2ca9-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ca9-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2ca9-117">Requirements</span></span>  
 <span data-ttu-id="f2ca9-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ca9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ca9-119">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f2ca9-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2ca9-120">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2ca9-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2ca9-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ca9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ca9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2ca9-122">See Also</span></span>  
 [<span data-ttu-id="f2ca9-123">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f2ca9-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f2ca9-124">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f2ca9-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="f2ca9-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f2ca9-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
---
title: Interfaccia ICorDebugMutableDataTarget
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef1c0b7a56f6bd1f7e87650b72dfe8b1411ef7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="72ea8-102">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="72ea8-102">ICorDebugMutableDataTarget Interface</span></span>
<span data-ttu-id="72ea8-103">Estende il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="72ea8-103">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72ea8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="72ea8-104">Methods</span></span>  
  
|<span data-ttu-id="72ea8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="72ea8-105">Method</span></span>|<span data-ttu-id="72ea8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72ea8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72ea8-107">Metodo ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="72ea8-107">ContinueStatusChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="72ea8-108">Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="72ea8-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="72ea8-109">SetThreadContext (metodo)</span><span class="sxs-lookup"><span data-stu-id="72ea8-109">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="72ea8-110">Imposta il contesto (valori del registro) per un thread.</span><span class="sxs-lookup"><span data-stu-id="72ea8-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="72ea8-111">Metodo WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="72ea8-111">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="72ea8-112">Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ea8-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72ea8-113">Note</span><span class="sxs-lookup"><span data-stu-id="72ea8-113">Remarks</span></span>  
 <span data-ttu-id="72ea8-114">Questa estensione per il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia può essere implementata da strumenti di debug che vogliono modificare il processo di destinazione (ad esempio, per eseguire debug attivo invasivo).</span><span class="sxs-lookup"><span data-stu-id="72ea8-114">This extension to the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="72ea8-115">Tutti questi metodi sono facoltativi. Se infatti non si implementa questa interfaccia o si verifica un errore durante le chiamate a questi metodi, non si perde alcuna funzionalità principale di debug basata su ispezione.</span><span class="sxs-lookup"><span data-stu-id="72ea8-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="72ea8-116">Qualsiasi `HRESULT` di errore di questi metodi verrà propagato all'esterno come `HRESULT` della chiamata al metodo ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="72ea8-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="72ea8-117">Si noti che una sola chiamata al metodo ICorDebug può restituire più modifiche e non esistono meccanismi che assicurano che le modifiche correlate vengano applicate in modo transazionale (tutte o nessuna).</span><span class="sxs-lookup"><span data-stu-id="72ea8-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="72ea8-118">Se quindi una modifica non riesce dopo che altre (per la stessa chiamata a ICorDebug) hanno avuto esito positivo, il processo di destinazione potrà rimanere in uno stato incoerente e il debug potrà diventare inaffidabile.</span><span class="sxs-lookup"><span data-stu-id="72ea8-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ea8-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72ea8-119">Requirements</span></span>  
 <span data-ttu-id="72ea8-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72ea8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ea8-121">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="72ea8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72ea8-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72ea8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72ea8-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ea8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ea8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72ea8-124">See Also</span></span>  
 [<span data-ttu-id="72ea8-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="72ea8-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="72ea8-126">Debug</span><span class="sxs-lookup"><span data-stu-id="72ea8-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
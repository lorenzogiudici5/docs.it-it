---
title: Metodo ICorDebugVirtualUnwinder::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4dc0b8bf7915fe579c4764bc06c1f2534eeb759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="4d514-102">Metodo ICorDebugVirtualUnwinder::Next</span><span class="sxs-lookup"><span data-stu-id="4d514-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="4d514-103">Avanza fino al contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="4d514-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d514-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d514-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d514-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d514-105">Parameters</span></span>  
 <span data-ttu-id="4d514-106">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d514-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d514-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4d514-107">Return Value</span></span>  
 <span data-ttu-id="4d514-108">`S_OK` se la rimozione è stata eseguita correttamente o `CORDBG_S_AT_END_OF_STACK` se la rimozione non riesce perché non vi sono più frame.</span><span class="sxs-lookup"><span data-stu-id="4d514-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="4d514-109">Se viene restituito un HRESULT, le API ICorDebug restituiranno `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="4d514-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d514-110">Note</span><span class="sxs-lookup"><span data-stu-id="4d514-110">Remarks</span></span>  
 <span data-ttu-id="4d514-111">Il percorso di chiamate nello stack deve garantire un progresso in avanti, in modo che un'eventuale chiamata a `Next` restituisca un errore HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="4d514-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="4d514-112">Restituzione `S_OK` all'infinito potrebbe provocare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="4d514-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d514-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4d514-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d514-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d514-114">Requirements</span></span>  
 <span data-ttu-id="4d514-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d514-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d514-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4d514-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d514-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d514-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d514-118">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d514-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d514-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d514-119">See Also</span></span>  
 [<span data-ttu-id="4d514-120">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="4d514-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="4d514-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4d514-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
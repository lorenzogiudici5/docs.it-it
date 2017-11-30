---
title: Funzione FunctionTailcall2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall2
helpviewer_keywords: FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c1f9b0f6a83b774f6b308f7d4daa068eadebcce4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="b8aee-102">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="b8aee-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="b8aee-103">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b8aee-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8aee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8aee-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8aee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8aee-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="b8aee-106">[in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="b8aee-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="b8aee-107">[in] Identificatore della funzione modificato, quali il profiler specificato in precedenza tramite [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="b8aee-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="b8aee-108">[in] Oggetto `COR_PRF_FRAME_INFO` che punta alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b8aee-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="b8aee-109">Il profiler deve trattare come handle opaco che può essere passato al motore di esecuzione di [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="b8aee-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8aee-110">Note</span><span class="sxs-lookup"><span data-stu-id="b8aee-110">Remarks</span></span>  
 <span data-ttu-id="b8aee-111">La funzione di destinazione della chiamata tail utilizzerà lo stack frame corrente e verrà restituito direttamente al chiamante della funzione che ha effettuato la parte finale di chiamare.</span><span class="sxs-lookup"><span data-stu-id="b8aee-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="b8aee-112">Ciò significa che un [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback non verrà emesso per una funzione che rappresenta la destinazione di una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="b8aee-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="b8aee-113">Il valore di `func` parametro non è valido dopo il `FunctionTailcall2` funzione perché il valore potrebbe cambiare oppure essere distrutto.</span><span class="sxs-lookup"><span data-stu-id="b8aee-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="b8aee-114">Il `FunctionTailcall2` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="b8aee-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="b8aee-115">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b8aee-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="b8aee-116">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b8aee-116">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="b8aee-117">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="b8aee-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="b8aee-118">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b8aee-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b8aee-119">L'implementazione di `FunctionTailcall2` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b8aee-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="b8aee-120">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="b8aee-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b8aee-121">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionTailcall2` restituisce.</span><span class="sxs-lookup"><span data-stu-id="b8aee-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="b8aee-122">Inoltre, il `FunctionTailcall2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="b8aee-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8aee-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8aee-123">Requirements</span></span>  
 <span data-ttu-id="b8aee-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8aee-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8aee-125">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b8aee-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b8aee-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8aee-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8aee-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8aee-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8aee-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8aee-128">See Also</span></span>  
 [<span data-ttu-id="b8aee-129">FunctionEnter2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="b8aee-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="b8aee-130">FunctionLeave2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="b8aee-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="b8aee-131">SetEnterLeaveFunctionHooks2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="b8aee-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="b8aee-132">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="b8aee-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
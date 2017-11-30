---
title: Funzione FunctionEnter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter
helpviewer_keywords: FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd98e6db0f400d022fe0af4e96336616cbb7183
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter-function"></a><span data-ttu-id="46c03-102">Funzione FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="46c03-102">FunctionEnter Function</span></span>
<span data-ttu-id="46c03-103">Notifica al profiler di controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="46c03-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46c03-104">Il `FunctionEnter` funzione è obsoleta in .NET Framework versione 2.0, e il suo utilizzo comporta una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="46c03-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="46c03-105">Utilizzare il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) funzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="46c03-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46c03-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46c03-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46c03-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="46c03-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="46c03-108">[in] Identificatore della funzione a cui il controllo viene passato.</span><span class="sxs-lookup"><span data-stu-id="46c03-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46c03-109">Note</span><span class="sxs-lookup"><span data-stu-id="46c03-109">Remarks</span></span>  
 <span data-ttu-id="46c03-110">Il `FunctionEnter` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="46c03-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="46c03-111">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="46c03-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="46c03-112">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="46c03-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="46c03-113">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="46c03-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="46c03-114">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="46c03-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="46c03-115">L'implementazione di `FunctionEnter` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="46c03-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="46c03-116">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="46c03-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="46c03-117">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionEnter` restituisce.</span><span class="sxs-lookup"><span data-stu-id="46c03-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="46c03-118">Inoltre, il `FunctionEnter` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="46c03-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46c03-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46c03-119">Requirements</span></span>  
 <span data-ttu-id="46c03-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c03-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c03-121">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="46c03-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="46c03-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46c03-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46c03-123">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="46c03-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c03-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46c03-124">See Also</span></span>  
 [<span data-ttu-id="46c03-125">FunctionEnter2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="46c03-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="46c03-126">FunctionLeave2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="46c03-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="46c03-127">FunctionTailcall2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="46c03-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="46c03-128">SetEnterLeaveFunctionHooks2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="46c03-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="46c03-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="46c03-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
---
title: Metodo ICorProfilerCallback::ExceptionUnwindFinallyEnter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec1b05e67a10f5e7b22a950d1dec24528b5c4914
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="a7530-102">Metodo ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="a7530-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="a7530-103">Notifica al profiler che la fase di rimozione dell'eccezione gestione sta entrando in un `finally` clausola contenuta nella funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a7530-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7530-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7530-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7530-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7530-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a7530-106">[in] L'ID della funzione che contiene il `finally` clausola.</span><span class="sxs-lookup"><span data-stu-id="a7530-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7530-107">Note</span><span class="sxs-lookup"><span data-stu-id="a7530-107">Remarks</span></span>  
 <span data-ttu-id="a7530-108">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="a7530-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a7530-109">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="a7530-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a7530-110">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="a7530-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7530-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7530-111">Requirements</span></span>  
 <span data-ttu-id="a7530-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7530-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7530-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7530-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7530-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7530-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7530-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7530-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7530-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7530-116">See Also</span></span>  
 [<span data-ttu-id="a7530-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a7530-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a7530-118">Metodo GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="a7530-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)  
 [<span data-ttu-id="a7530-119">ExceptionUnwindFinallyLeave (metodo)</span><span class="sxs-lookup"><span data-stu-id="a7530-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
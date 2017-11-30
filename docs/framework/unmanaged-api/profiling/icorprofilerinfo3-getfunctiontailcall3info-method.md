---
title: Metodo ICorProfilerInfo3::GetFunctionTailcall3Info
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aae55a9e183c9e013603218ba217be79b2425e46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="8aa1d-102">Metodo ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="8aa1d-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="8aa1d-103">Fornisce lo stack frame della funzione da segnalare al profiler tramite la [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="8aa1d-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="8aa1d-104">Questo metodo può essere chiamato solo durante il callback `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="8aa1d-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa1d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8aa1d-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8aa1d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8aa1d-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8aa1d-107">[in] Il `FunctionID` della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="8aa1d-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="8aa1d-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="8aa1d-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="8aa1d-109">Il profiler deve fornire la stessa `eltInfo` fornito al profiler tramite la `FunctionTailcall3WithInfo` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8aa1d-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="8aa1d-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="8aa1d-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="8aa1d-111">Questo handle è valido solo durante il callback `FunctionTailcall3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="8aa1d-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8aa1d-112">Note</span><span class="sxs-lookup"><span data-stu-id="8aa1d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aa1d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8aa1d-113">Requirements</span></span>  
 <span data-ttu-id="8aa1d-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aa1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aa1d-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8aa1d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8aa1d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aa1d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aa1d-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aa1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa1d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aa1d-118">See Also</span></span>  
 [<span data-ttu-id="8aa1d-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8aa1d-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="8aa1d-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8aa1d-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="8aa1d-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8aa1d-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="8aa1d-122">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8aa1d-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="8aa1d-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8aa1d-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8aa1d-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="8aa1d-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
---
title: Metodo ICorDebugNativeFrame::SetIP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.SetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 563566a877d589ecd32575c095cdc812c28f6334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="fc265-102">Metodo ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="fc265-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="fc265-103">Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="fc265-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc265-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc265-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc265-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc265-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="fc265-106">[in] Posizione di offset nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="fc265-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc265-107">Note</span><span class="sxs-lookup"><span data-stu-id="fc265-107">Remarks</span></span>  
 <span data-ttu-id="fc265-108">Le chiamate a `SetIP` invalidano immediatamente tutti i frame e sulle sequenze per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="fc265-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="fc265-109">Se il debugger deve ottenere informazioni sui frame dopo una chiamata a `SetIP`, è necessario eseguire una nuova traccia dello stack.</span><span class="sxs-lookup"><span data-stu-id="fc265-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="fc265-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) tenterà di mantenere lo stack frame in uno stato valido.</span><span class="sxs-lookup"><span data-stu-id="fc265-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="fc265-111">Tuttavia, anche se il frame è in uno stato valido, per quanto riguarda il runtime, è comunque possibile problemi, ad esempio variabili locali non inizializzate e così via.</span><span class="sxs-lookup"><span data-stu-id="fc265-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="fc265-112">Il chiamante è responsabile per assicurare la coerenza del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fc265-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="fc265-113">Su piattaforme a 64 bit, il puntatore all'istruzione non può essere spostato fuori da un `catch` o `finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="fc265-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="fc265-114">Se `SetIP` viene chiamato per rendere un tale spostamento su una piattaforma a 64 bit, verrà restituito un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="fc265-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc265-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc265-115">Requirements</span></span>  
 <span data-ttu-id="fc265-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc265-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc265-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fc265-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc265-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc265-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc265-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc265-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc265-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc265-120">See Also</span></span>  
 
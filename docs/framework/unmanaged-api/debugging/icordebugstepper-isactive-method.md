---
title: Metodo ICorDebugStepper::IsActive
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25e4b59c59ee4340c14da22143f49c645e1dcc7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="38dfd-102">Metodo ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="38dfd-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="38dfd-103">Ottiene un valore che indica se ICorDebugStepper è attualmente in esecuzione un passaggio.</span><span class="sxs-lookup"><span data-stu-id="38dfd-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38dfd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38dfd-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38dfd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38dfd-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="38dfd-106">[out] Restituisce `true` se il gestore di istruzioni è attualmente in esecuzione un passaggio; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="38dfd-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38dfd-107">Note</span><span class="sxs-lookup"><span data-stu-id="38dfd-107">Remarks</span></span>  
 <span data-ttu-id="38dfd-108">Qualsiasi azione passaggio rimane attiva finché il debugger non riceve un [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) chiama, che disattiva automaticamente il gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="38dfd-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="38dfd-109">Un gestore di istruzioni può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) prima del callback condizione viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="38dfd-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38dfd-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38dfd-110">Requirements</span></span>  
 <span data-ttu-id="38dfd-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38dfd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38dfd-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="38dfd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38dfd-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38dfd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38dfd-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38dfd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
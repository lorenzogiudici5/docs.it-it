---
title: ICorDebugBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b78b61b99fb8f236e787f3acbf993d0a1c57e797
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="765e3-102">ICorDebugBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="765e3-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="765e3-103">Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="765e3-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="765e3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="765e3-104">Methods</span></span>  
  
|<span data-ttu-id="765e3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="765e3-105">Method</span></span>|<span data-ttu-id="765e3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="765e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="765e3-107">Activate (metodo)</span><span class="sxs-lookup"><span data-stu-id="765e3-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="765e3-108">Imposta lo stato attivo di questo `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="765e3-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="765e3-109">IsActive (metodo)</span><span class="sxs-lookup"><span data-stu-id="765e3-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="765e3-110">Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attiva.</span><span class="sxs-lookup"><span data-stu-id="765e3-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="765e3-111">Note</span><span class="sxs-lookup"><span data-stu-id="765e3-111">Remarks</span></span>  
 <span data-ttu-id="765e3-112">I punti di interruzione non supportano direttamente le espressioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="765e3-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="765e3-113">Se si desidera tale funzionalità, un debugger deve implementarla in cima `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="765e3-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="765e3-114">Estende l'interfaccia ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="765e3-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="765e3-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="765e3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="765e3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="765e3-116">Requirements</span></span>  
 <span data-ttu-id="765e3-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="765e3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="765e3-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="765e3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="765e3-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="765e3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="765e3-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="765e3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765e3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="765e3-121">See Also</span></span>  
 [<span data-ttu-id="765e3-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="765e3-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
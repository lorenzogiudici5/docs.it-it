---
title: Metodo ICorDebugAssembly3::GetContainerAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f9a32520c2a67c0bc51a3f88e9822db49e4a3974
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="3ff3e-102">Metodo ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="3ff3e-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="3ff3e-103">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="3ff3e-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff3e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ff3e-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ff3e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ff3e-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="3ff3e-106">Un puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly del contenitore o **null** se la chiamata al metodo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3ff3e-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ff3e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3ff3e-107">Return Value</span></span>  
 <span data-ttu-id="3ff3e-108">`S_OK`Se la chiamata al metodo ha esito positivo; in caso contrario, `S_FALSE`, e `ppAssembly` è **null**.</span><span class="sxs-lookup"><span data-stu-id="3ff3e-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ff3e-109">Note</span><span class="sxs-lookup"><span data-stu-id="3ff3e-109">Remarks</span></span>  
 <span data-ttu-id="3ff3e-110">Se l'assembly è stato unito ad altri assembly in un singolo assembly del contenitore, il metodo restituisce l'assembly del contenitore.</span><span class="sxs-lookup"><span data-stu-id="3ff3e-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="3ff3e-111">Per ulteriori informazioni e terminologia, vedere il [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="3ff3e-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ff3e-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3ff3e-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ff3e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ff3e-113">Requirements</span></span>  
 <span data-ttu-id="3ff3e-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ff3e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ff3e-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3ff3e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ff3e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ff3e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ff3e-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff3e-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff3e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ff3e-118">See Also</span></span>  
 [<span data-ttu-id="3ff3e-119">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="3ff3e-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="3ff3e-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3ff3e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
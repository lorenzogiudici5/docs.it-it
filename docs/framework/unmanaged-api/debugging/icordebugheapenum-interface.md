---
title: Interfaccia ICorDebugHeapEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapEnum
helpviewer_keywords: ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbc97aec2fc9758df17767188c6b4d044b5016fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="bf92a-102">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="bf92a-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="bf92a-103">Fornisce un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="bf92a-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="bf92a-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="bf92a-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf92a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bf92a-105">Methods</span></span>  
  
|<span data-ttu-id="bf92a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="bf92a-106">Method</span></span>|<span data-ttu-id="bf92a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf92a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf92a-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="bf92a-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="bf92a-109">Ottiene il numero specificato di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="bf92a-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf92a-110">Note</span><span class="sxs-lookup"><span data-stu-id="bf92a-110">Remarks</span></span>  
 <span data-ttu-id="bf92a-111">Il `ICorDebugHeapEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="bf92a-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="bf92a-112">Un `ICorDebugHeapEnum` istanza viene popolata con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze chiamando il [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bf92a-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="bf92a-113">Ogni [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanza nella raccolta rappresenta un oggetto nell'heap in tempo reale oppure un oggetto che non contiene una radice da qualsiasi oggetto, ma non ha ancora recuperato da garbage collector.</span><span class="sxs-lookup"><span data-stu-id="bf92a-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="bf92a-114">Il [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti nella raccolta possono essere enumerati chiamando il [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bf92a-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf92a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf92a-115">Requirements</span></span>  
 <span data-ttu-id="bf92a-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf92a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf92a-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bf92a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf92a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf92a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf92a-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf92a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf92a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf92a-120">See Also</span></span>  
 [<span data-ttu-id="bf92a-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bf92a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
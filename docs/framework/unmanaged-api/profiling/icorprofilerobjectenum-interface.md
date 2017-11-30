---
title: Interfaccia ICorProfilerObjectEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum
helpviewer_keywords: ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b46f33485a63404f11dc0606e420ec9c3c43f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerobjectenum-interface"></a><span data-ttu-id="406e7-102">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="406e7-102">ICorProfilerObjectEnum Interface</span></span>
<span data-ttu-id="406e7-103">Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati dal [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="406e7-103">Provides methods to sequentially iterate through a collection of frozen objects that are generated by the [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="406e7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="406e7-104">Methods</span></span>  
  
|<span data-ttu-id="406e7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="406e7-105">Method</span></span>|<span data-ttu-id="406e7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="406e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="406e7-107">Clone (metodo)</span><span class="sxs-lookup"><span data-stu-id="406e7-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|<span data-ttu-id="406e7-108">Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerObjectEnum`.</span><span class="sxs-lookup"><span data-stu-id="406e7-108">Gets an interface pointer to a copy of this `ICorProfilerObjectEnum` interface.</span></span>|  
|[<span data-ttu-id="406e7-109">GetCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="406e7-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|<span data-ttu-id="406e7-110">Ottiene il numero totale di oggetti bloccati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="406e7-110">Gets the total number of frozen objects in the collection.</span></span>|  
|[<span data-ttu-id="406e7-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="406e7-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|<span data-ttu-id="406e7-112">Ottiene il numero specificato di oggetti contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="406e7-112">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="406e7-113">Reset (metodo)</span><span class="sxs-lookup"><span data-stu-id="406e7-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|<span data-ttu-id="406e7-114">Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.</span><span class="sxs-lookup"><span data-stu-id="406e7-114">Moves this enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="406e7-115">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="406e7-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|<span data-ttu-id="406e7-116">Sposta il cursore dell'enumeratore dalla posizione corrente in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="406e7-116">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="406e7-117">Note</span><span class="sxs-lookup"><span data-stu-id="406e7-117">Remarks</span></span>  
 <span data-ttu-id="406e7-118">L'interfaccia `ICorProfilerObjectEnum` è un enumeratore.</span><span class="sxs-lookup"><span data-stu-id="406e7-118">The `ICorProfilerObjectEnum` interface is an enumerator.</span></span> <span data-ttu-id="406e7-119">Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore.</span><span class="sxs-lookup"><span data-stu-id="406e7-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="406e7-120">In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi di matrice, evitando così i problemi relativi al passaggio di matrici di grandi dimensioni come parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="406e7-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems related to passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="406e7-121">Utilizzare [ICorProfilerInfo2:: EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) per ottenere un puntatore per il `ICorProfilerObjectEnum` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="406e7-121">Use [ICorProfilerInfo2::EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) to obtain a pointer to the `ICorProfilerObjectEnum` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="406e7-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="406e7-122">Requirements</span></span>  
 <span data-ttu-id="406e7-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="406e7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="406e7-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="406e7-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="406e7-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="406e7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="406e7-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="406e7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406e7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="406e7-127">See Also</span></span>  
 [<span data-ttu-id="406e7-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="406e7-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="406e7-129">EnumModuleFrozenObjects (metodo)</span><span class="sxs-lookup"><span data-stu-id="406e7-129">EnumModuleFrozenObjects Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)
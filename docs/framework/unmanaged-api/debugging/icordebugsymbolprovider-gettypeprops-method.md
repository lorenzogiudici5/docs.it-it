---
title: Metodo ICorDebugSymbolProvider::GetTypeProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ba736caf8d8d823a4cb56c75aa2202ad616983fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="8f3cb-102">Metodo ICorDebugSymbolProvider::GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="8f3cb-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="8f3cb-103">Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f3cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f3cb-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f3cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f3cb-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="8f3cb-106">[in] Indirizzo RVA (Relative Virtual Address) in un oggetto vtable</span><span class="sxs-lookup"><span data-stu-id="8f3cb-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="8f3cb-107">[in] Dimensione della matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="8f3cb-108">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="8f3cb-109">[out] [out] Puntatore alla dimensione della matrice `signature` restituita.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="8f3cb-110">[out] Buffer contenente le firme typespec di tutti i parametri generici.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f3cb-111">Note</span><span class="sxs-lookup"><span data-stu-id="8f3cb-111">Remarks</span></span>  
 <span data-ttu-id="8f3cb-112">Per ottenere la dimensione del tipo richiesta `signature` matrice, impostare il `cbSignature` argomento su 0 e `signature` a **null**.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="8f3cb-113">Quando il metodo viene restituito, `pcbSignature` conterrà il numero di byte necessari per la matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f3cb-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8f3cb-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f3cb-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f3cb-115">Requirements</span></span>  
 <span data-ttu-id="8f3cb-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f3cb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f3cb-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8f3cb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f3cb-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f3cb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f3cb-119">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f3cb-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f3cb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f3cb-120">See Also</span></span>  
 [<span data-ttu-id="8f3cb-121">Metodo GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="8f3cb-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)  
 [<span data-ttu-id="8f3cb-122">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8f3cb-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="8f3cb-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8f3cb-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
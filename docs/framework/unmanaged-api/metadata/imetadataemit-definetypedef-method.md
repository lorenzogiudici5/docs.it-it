---
title: Metodo IMetaDataEmit::DefineTypeDef
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeDef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a344f592b47d452b4d016f08cefddda650128188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="5954d-102">Metodo IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="5954d-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="5954d-103">Crea una definizione di tipo per un tipo common language runtime e ottiene un token di metadati per la definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="5954d-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5954d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5954d-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5954d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5954d-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="5954d-106">[in] Il nome del tipo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="5954d-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="5954d-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="5954d-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="5954d-108">Si tratta di una maschera di bit di `CoreTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="5954d-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="5954d-109">[in] Il token della classe di base.</span><span class="sxs-lookup"><span data-stu-id="5954d-109">[in] The token of the base class.</span></span> <span data-ttu-id="5954d-110">Deve essere un `mdTypeDef` o `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="5954d-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="5954d-111">[in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5954d-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="5954d-112">[out] Il `mdTypeDef` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="5954d-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5954d-113">Note</span><span class="sxs-lookup"><span data-stu-id="5954d-113">Remarks</span></span>  
 <span data-ttu-id="5954d-114">Un flag nel `dwTypeDefFlags` specifica se il tipo creato è un tipo di sistema tipo comuni (classe o interfaccia) o un tipo di valore di sistema tipo comune.</span><span class="sxs-lookup"><span data-stu-id="5954d-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="5954d-115">A seconda dei parametri forniti, questo metodo, come effetto collaterale, potrebbe anche creare un `mdInterfaceImpl` record per ogni interfaccia implementata da questo tipo o ereditata.</span><span class="sxs-lookup"><span data-stu-id="5954d-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="5954d-116">Tuttavia, questo metodo non restituisce uno di questi `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="5954d-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="5954d-117">Se un client desidera aggiungere o modificare un secondo momento un `mdInterfaceImpl` token, è necessario utilizzare il `IMetaDataImport` interfaccia per enumerarli.</span><span class="sxs-lookup"><span data-stu-id="5954d-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="5954d-118">Se si desidera utilizzare la semantica di COM del `[default]` interfaccia, è necessario fornire l'interfaccia predefinita come primo elemento in `rtkImplements`; un attributo personalizzato impostato nella classe indicherà che la classe dispone di un'interfaccia predefinita (che viene sempre considerato il prima di tutto `mdInterfaceImpl` token dichiarato per la classe).</span><span class="sxs-lookup"><span data-stu-id="5954d-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="5954d-119">Ogni elemento del `rtkImplements` matrice contiene un `mdTypeDef` o `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="5954d-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="5954d-120">Deve essere l'ultimo elemento nella matrice `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="5954d-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5954d-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5954d-121">Requirements</span></span>  
 <span data-ttu-id="5954d-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5954d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5954d-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5954d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5954d-124">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5954d-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5954d-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5954d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5954d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5954d-126">See Also</span></span>  
 [<span data-ttu-id="5954d-127">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5954d-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5954d-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5954d-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
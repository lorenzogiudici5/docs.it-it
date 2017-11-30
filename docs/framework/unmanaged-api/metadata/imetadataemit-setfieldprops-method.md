---
title: Metodo IMetaDataEmit::SetFieldProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f031e79deab57184043eaa44d2d8a3d369187c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="c3253-102">Metodo IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="c3253-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="c3253-103">Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.</span><span class="sxs-lookup"><span data-stu-id="c3253-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3253-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3253-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3253-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3253-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="c3253-106">[in] Il token per il campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c3253-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="c3253-107">[in] Attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="c3253-107">[in] Field attributes.</span></span> <span data-ttu-id="c3253-108">Si tratta di una maschera di bit di `CorFieldAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="c3253-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="c3253-109">[in] Il `ELEMENT_TYPE_`  *\**  per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="c3253-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="c3253-110">Si tratta di un `CorElementType` valore.</span><span class="sxs-lookup"><span data-stu-id="c3253-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="c3253-111">Se non è definita una costante, impostare questo valore su `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="c3253-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c3253-112">[in] Il valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="c3253-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="c3253-113">[in] Le dimensioni, in caratteri Unicode, di `pValue`.</span><span class="sxs-lookup"><span data-stu-id="c3253-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3253-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3253-114">Requirements</span></span>  
 <span data-ttu-id="c3253-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3253-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3253-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c3253-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3253-117">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3253-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3253-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3253-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3253-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3253-119">See Also</span></span>  
 [<span data-ttu-id="c3253-120">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3253-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c3253-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c3253-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
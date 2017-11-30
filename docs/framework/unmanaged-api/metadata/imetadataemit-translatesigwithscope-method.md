---
title: Metodo IMetaDataEmit::TranslateSigWithScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.TranslateSigWithScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5127defc97423283b52b7b5bd8c6b7a31104fbc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="b8467-102">Metodo IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="b8467-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="b8467-103">Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito unito.</span><span class="sxs-lookup"><span data-stu-id="b8467-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8467-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8467-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8467-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8467-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="b8467-106">[in] L'interfaccia per importare l'assembly (in cui è definita la firma).</span><span class="sxs-lookup"><span data-stu-id="b8467-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="b8467-107">[in] Il blob hash per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b8467-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="b8467-108">[in] Il numero di byte in `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="b8467-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="b8467-109">[in] L'interfaccia per l'ambito di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="b8467-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="b8467-110">[in] Firma da importare.</span><span class="sxs-lookup"><span data-stu-id="b8467-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b8467-111">[in] Le dimensioni, in byte, di `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b8467-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="b8467-112">[in] L'interfaccia per esportare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b8467-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="b8467-113">[in] L'interfaccia per l'ambito dei metadati di esportazione.</span><span class="sxs-lookup"><span data-stu-id="b8467-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="b8467-114">[out] Il buffer contenente il BLOB della firma convertita.</span><span class="sxs-lookup"><span data-stu-id="b8467-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="b8467-115">[in] La capacità, in byte, di `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="b8467-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="b8467-116">[out] Il numero di byte effettivi nella firma convertita.</span><span class="sxs-lookup"><span data-stu-id="b8467-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8467-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8467-117">Requirements</span></span>  
 <span data-ttu-id="b8467-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8467-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8467-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b8467-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8467-120">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8467-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8467-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8467-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8467-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8467-122">See Also</span></span>  
 [<span data-ttu-id="b8467-123">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="b8467-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="b8467-124">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b8467-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="b8467-125">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b8467-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b8467-126">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b8467-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="b8467-127">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b8467-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
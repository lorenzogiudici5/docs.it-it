---
title: Metodo IMetaDataImport::EnumPermissionSets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 031e97ad1b8180a64bc789ae52e141932d600782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="3c7eb-102">Metodo IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="3c7eb-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="3c7eb-103">Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c7eb-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c7eb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c7eb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3c7eb-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3c7eb-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="3c7eb-108">[in] Token di metadati che limita l'ambito della ricerca, o NULL per la ricerca nell'ambito più ampio possibile.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="3c7eb-109">[in] Flag che rappresentano il <xref:System.Security.Permissions.SecurityAction> valori da includere in `rPermission`, oppure zero per restituire tutte le azioni.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="3c7eb-110">[out] Matrice utilizzata per archiviare i token di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c7eb-111">[in] Dimensione massima della matrice `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3c7eb-112">[out] Il numero di token di autorizzazione restituiti in `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c7eb-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c7eb-113">Return Value</span></span>  
  
|<span data-ttu-id="3c7eb-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c7eb-114">HRESULT</span></span>|<span data-ttu-id="3c7eb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c7eb-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c7eb-116">`EnumPermissionSets`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c7eb-117">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="3c7eb-118">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c7eb-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c7eb-119">Requirements</span></span>  
 <span data-ttu-id="3c7eb-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c7eb-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c7eb-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3c7eb-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c7eb-122">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c7eb-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c7eb-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c7eb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7eb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c7eb-124">See Also</span></span>  
 [<span data-ttu-id="3c7eb-125">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c7eb-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3c7eb-126">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c7eb-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
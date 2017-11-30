---
title: Enumerazione CorNativeLinkFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkFlags
helpviewer_keywords: CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09afda63959d974af71e0264ad116c20d3af1923
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="6ab5b-102">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="6ab5b-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="6ab5b-103">Fornisce valori di flag usati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6ab5b-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ab5b-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6ab5b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6ab5b-105">Members</span></span>  
  
|<span data-ttu-id="6ab5b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6ab5b-106">Member</span></span>|<span data-ttu-id="6ab5b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ab5b-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="6ab5b-108">Non indica nessun flag.</span><span class="sxs-lookup"><span data-stu-id="6ab5b-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="6ab5b-109">Indica un `setLastError` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="6ab5b-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="6ab5b-110">Indica un `nomangle` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="6ab5b-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="6ab5b-111">Non usato.</span><span class="sxs-lookup"><span data-stu-id="6ab5b-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ab5b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ab5b-112">Requirements</span></span>  
 <span data-ttu-id="6ab5b-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ab5b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ab5b-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6ab5b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ab5b-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ab5b-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ab5b-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ab5b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab5b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ab5b-117">See Also</span></span>  
 [<span data-ttu-id="6ab5b-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6ab5b-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
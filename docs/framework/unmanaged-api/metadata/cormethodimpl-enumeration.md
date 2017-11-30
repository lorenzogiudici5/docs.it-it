---
title: Enumerazione CorMethodImpl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodImpl
helpviewer_keywords: CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 85ee55c0d4ec0d3fb8c18dff570afefeb2eaf25e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="d39e6-102">Enumerazione CorMethodImpl</span><span class="sxs-lookup"><span data-stu-id="d39e6-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="d39e6-103">Contiene valori che descrivono funzionalità di implementazione dei metodi.</span><span class="sxs-lookup"><span data-stu-id="d39e6-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d39e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d39e6-104">Syntax</span></span>  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="d39e6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d39e6-105">Members</span></span>  
  
|<span data-ttu-id="d39e6-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d39e6-106">Member</span></span>|<span data-ttu-id="d39e6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d39e6-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="d39e6-108">Flag che descrivono il tipo di codice.</span><span class="sxs-lookup"><span data-stu-id="d39e6-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="d39e6-109">Specifica che l'implementazione del metodo è Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d39e6-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="d39e6-110">Specifica che l'implementazione del metodo è nativa.</span><span class="sxs-lookup"><span data-stu-id="d39e6-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="d39e6-111">Specifica che l'implementazione del metodo OPTIL.</span><span class="sxs-lookup"><span data-stu-id="d39e6-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="d39e6-112">Specifica che l'implementazione del metodo è fornito da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="d39e6-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="d39e6-113">Flag che indicano se il codice sia gestito o meno.</span><span class="sxs-lookup"><span data-stu-id="d39e6-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="d39e6-114">Specifica che l'implementazione del metodo non è gestito.</span><span class="sxs-lookup"><span data-stu-id="d39e6-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="d39e6-115">Specifica che l'implementazione del metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="d39e6-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="d39e6-116">Specifica che il metodo è definito.</span><span class="sxs-lookup"><span data-stu-id="d39e6-116">Specifies that the method is defined.</span></span> <span data-ttu-id="d39e6-117">Questo flag viene utilizzato principalmente in scenari di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="d39e6-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="d39e6-118">Specifica che la firma del metodo non può essere alterata per una conversione HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d39e6-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="d39e6-119">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="d39e6-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="d39e6-120">Specifica che il metodo è a thread singolo mediante il relativo corpo.</span><span class="sxs-lookup"><span data-stu-id="d39e6-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="d39e6-121">Specifica che il metodo non può essere impostato come inline.</span><span class="sxs-lookup"><span data-stu-id="d39e6-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="d39e6-122">Specifica che il metodo deve essere resa inline se possibile.</span><span class="sxs-lookup"><span data-stu-id="d39e6-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="d39e6-123">Specifica che il metodo non deve essere ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="d39e6-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="d39e6-124">Il valore massimo valido per un `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="d39e6-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d39e6-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d39e6-125">Requirements</span></span>  
 <span data-ttu-id="d39e6-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d39e6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d39e6-127">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="d39e6-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d39e6-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d39e6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39e6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d39e6-129">See Also</span></span>  
 [<span data-ttu-id="d39e6-130">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d39e6-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
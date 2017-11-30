---
title: Funzione ForwardTranslateAccelerator (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 663b28ed1a9430a6280ccd0ee9a44da2dea0c3cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f158b-102">Funzione ForwardTranslateAccelerator (riferimenti alle API non gestita di WPF)</span><span class="sxs-lookup"><span data-stu-id="f158b-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f158b-103">Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="f158b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f158b-104">Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="f158b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f158b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f158b-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f158b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f158b-106">Parameters</span></span>  
 <span data-ttu-id="f158b-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="f158b-107">pMsg</span></span>  
 <span data-ttu-id="f158b-108">Un puntatore a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f158b-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="f158b-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="f158b-109">appUnhandled</span></span>  
 <span data-ttu-id="f158b-110">`true`Quando l'app è già stato fornito l'opportunità di gestire il messaggio di input, ma non è gestito. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f158b-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f158b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f158b-111">Requirements</span></span>  
 <span data-ttu-id="f158b-112">**Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f158b-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f158b-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="f158b-113">**DLL:**</span></span>  
  
 <span data-ttu-id="f158b-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="f158b-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f158b-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="f158b-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f158b-116">**Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f158b-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f158b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f158b-117">See Also</span></span>  
 [<span data-ttu-id="f158b-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="f158b-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
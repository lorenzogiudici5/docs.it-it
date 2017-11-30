---
title: Metodo ICorDebugStringValue::GetLength
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c072e7420e400e6402c8697eefc62c658c590261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="ac37f-102">Metodo ICorDebugStringValue::GetLength</span><span class="sxs-lookup"><span data-stu-id="ac37f-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="ac37f-103">Ottiene il numero di caratteri nella stringa di cui fa riferimento ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="ac37f-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac37f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac37f-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac37f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac37f-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="ac37f-106">[out] Un puntatore a un valore che specifica la lunghezza della stringa di cui fa riferimento questo `ICorDebugStringValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="ac37f-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac37f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac37f-107">Requirements</span></span>  
 <span data-ttu-id="ac37f-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac37f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac37f-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ac37f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac37f-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac37f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac37f-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac37f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
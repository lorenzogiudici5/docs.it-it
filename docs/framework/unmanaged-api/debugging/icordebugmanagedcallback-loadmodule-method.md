---
title: Metodo ICorDebugManagedCallback::LoadModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d133bffdf98306c17bb223dc25e84d6bf9e2ce2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="2ac9a-102">Metodo ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="2ac9a-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="2ac9a-103">Notifica al debugger che un modulo di common language runtime (CLR) è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="2ac9a-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ac9a-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ac9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ac9a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2ac9a-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="2ac9a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="2ac9a-107">[in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="2ac9a-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ac9a-108">Note</span><span class="sxs-lookup"><span data-stu-id="2ac9a-108">Remarks</span></span>  
 <span data-ttu-id="2ac9a-109">Il `LoadModule` callback fornisce un momento appropriato per esaminare i metadati per il modulo, impostare i flag del compilatore just-in-time (JIT) o di abilitare o disabilitare i callback per il modulo di caricamento delle classi.</span><span class="sxs-lookup"><span data-stu-id="2ac9a-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac9a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ac9a-110">Requirements</span></span>  
 <span data-ttu-id="2ac9a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac9a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac9a-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2ac9a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ac9a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ac9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac9a-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac9a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ac9a-115">See Also</span></span>  
 [<span data-ttu-id="2ac9a-116">UnloadModule (metodo)</span><span class="sxs-lookup"><span data-stu-id="2ac9a-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="2ac9a-117">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2ac9a-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
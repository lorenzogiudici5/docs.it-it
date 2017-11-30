---
title: Metodo ICorDebugManagedCallback2::CreateConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.CreateConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 716321508c18a415dc8e5c1c3e7e350deaf00a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="ed8df-102">Metodo ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="ed8df-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="ed8df-103">Notifica al debugger che è stata creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="ed8df-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed8df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed8df-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed8df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed8df-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="ed8df-106">[in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui è stata creata la connessione</span><span class="sxs-lookup"><span data-stu-id="ed8df-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="ed8df-107">[in] L'ID della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="ed8df-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="ed8df-108">[in] Un puntatore al nome della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="ed8df-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed8df-109">Note</span><span class="sxs-lookup"><span data-stu-id="ed8df-109">Remarks</span></span>  
 <span data-ttu-id="ed8df-110">Oggetto `CreateConnection` callback verrà generato in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="ed8df-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="ed8df-111">Quando un debugger si connette a un processo che contiene le connessioni.</span><span class="sxs-lookup"><span data-stu-id="ed8df-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="ed8df-112">In questo caso, il runtime generare e inviare un `CreateConnection` evento e un [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) evento per ogni connessione del processo.</span><span class="sxs-lookup"><span data-stu-id="ed8df-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="ed8df-113">Quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nel [API di Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed8df-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed8df-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed8df-114">Requirements</span></span>  
 <span data-ttu-id="ed8df-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed8df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed8df-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ed8df-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed8df-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed8df-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed8df-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed8df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8df-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed8df-119">See Also</span></span>  
 [<span data-ttu-id="ed8df-120">ICorDebugManagedCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ed8df-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ed8df-121">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ed8df-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
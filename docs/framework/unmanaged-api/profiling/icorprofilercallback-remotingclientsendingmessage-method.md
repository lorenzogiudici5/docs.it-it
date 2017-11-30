---
title: Metodo ICorProfilerCallback::RemotingClientSendingMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientSendingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a77acb736cec02da6839335e981016469eeb42b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="980c1-102">Metodo ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="980c1-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="980c1-103">Notifica al profiler che il client invia una richiesta al server.</span><span class="sxs-lookup"><span data-stu-id="980c1-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="980c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="980c1-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="980c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="980c1-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="980c1-106">[in] Un valore che corrisponde al valore fornito [ICorProfilerCallback:: RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) in queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="980c1-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="980c1-107">I cookie dei GUID remoti sono attive.</span><span class="sxs-lookup"><span data-stu-id="980c1-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="980c1-108">Il canale riesce a trasmettere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="980c1-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="980c1-109">I cookie GUID sono attivi sul processo del lato server.</span><span class="sxs-lookup"><span data-stu-id="980c1-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="980c1-110">Ciò consente l'associazione semplice delle chiamate remote e la creazione di uno stack di chiamata logico.</span><span class="sxs-lookup"><span data-stu-id="980c1-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="980c1-111">[in] Un valore che è `true` se la chiamata è asincrona; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="980c1-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="980c1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="980c1-112">Requirements</span></span>  
 <span data-ttu-id="980c1-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="980c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="980c1-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="980c1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="980c1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="980c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="980c1-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="980c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="980c1-117">See Also</span></span>  
 [<span data-ttu-id="980c1-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="980c1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
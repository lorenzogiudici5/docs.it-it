---
title: Enumerazione CLR_DEBUGGING_PROCESS_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_PROCESS_FLAGS
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords: CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5040b1e1eb7ec4bd814329de156fcdfeb9c383c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="12d31-102">Enumerazione CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="12d31-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="12d31-103">Fornisce i valori utilizzati per il [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="12d31-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12d31-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="12d31-105">Membri</span><span class="sxs-lookup"><span data-stu-id="12d31-105">Members</span></span>  
  
|<span data-ttu-id="12d31-106">Membro</span><span class="sxs-lookup"><span data-stu-id="12d31-106">Member</span></span>|<span data-ttu-id="12d31-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12d31-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="12d31-108">Il runtime dispone di un evento del debugger gestito a non-catch-up per inviare.</span><span class="sxs-lookup"><span data-stu-id="12d31-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="12d31-109">Vedere la sezione Osservazioni per la distinzione tra gli eventi di aggiornamento e non-catch-up.</span><span class="sxs-lookup"><span data-stu-id="12d31-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="12d31-110">L'evento gestito che è in sospeso è un <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> richiesta.</span><span class="sxs-lookup"><span data-stu-id="12d31-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12d31-111">Note</span><span class="sxs-lookup"><span data-stu-id="12d31-111">Remarks</span></span>  
 <span data-ttu-id="12d31-112">Aggiornamento degli eventi includono processo, il dominio applicazione, assembly, modulo e le notifiche di creazione di thread che portano il debugger fino allo stato corrente dopo che è connesso a un processo.</span><span class="sxs-lookup"><span data-stu-id="12d31-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="12d31-113">Gli eventi non-catch-up, indicati dal `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, includere tutte le altri eventi del debugger, ad esempio le eccezioni e le notifiche di assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="12d31-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="12d31-114">Il `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag consente al runtime di distinguere tra un'eccezione di terminazione e una richiesta per allegare un debugger gestito che può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="12d31-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12d31-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12d31-115">Requirements</span></span>  
 <span data-ttu-id="12d31-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12d31-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12d31-117">**Intestazione:** Metahost. idl, Metahost. h</span><span class="sxs-lookup"><span data-stu-id="12d31-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="12d31-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12d31-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12d31-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12d31-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d31-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12d31-120">See Also</span></span>  
 [<span data-ttu-id="12d31-121">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="12d31-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="12d31-122">Debug</span><span class="sxs-lookup"><span data-stu-id="12d31-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
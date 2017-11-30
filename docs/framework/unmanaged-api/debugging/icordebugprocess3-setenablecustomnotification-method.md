---
title: Metodo ICorDebugProcess3::SetEnableCustomNotification
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3.SetEnableCustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d4c6604d57b28cca33007b9d72d4b4c06e6d062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="31f0a-102">Metodo ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="31f0a-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="31f0a-103">Attiva e disattiva le notifiche di debugger personalizzati del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="31f0a-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31f0a-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31f0a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31f0a-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="31f0a-106">[in] Tipo che specifica le notifiche di debugger personalizzate.</span><span class="sxs-lookup"><span data-stu-id="31f0a-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="31f0a-107">[in] `true` per abilitare le notifiche di debugger personalizzate; `false` per disabilitare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="31f0a-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="31f0a-108">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="31f0a-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31f0a-109">Note</span><span class="sxs-lookup"><span data-stu-id="31f0a-109">Remarks</span></span>  
 <span data-ttu-id="31f0a-110">Quando `fEnable` è impostato su `true`, le chiamate al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> trigger metodo un [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="31f0a-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="31f0a-111">Le notifiche sono disabilitate per impostazione predefinita. Pertanto, il debugger deve specificare qualsiasi tipo di notifica a conoscenza e si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="31f0a-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="31f0a-112">Poiché il [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) dell'ambito di classe dominio applicazione, il debugger deve chiamare `SetEnableCustomNotification` per ogni dominio dell'applicazione nel processo se vuole ricevere la notifica l'intero processo.</span><span class="sxs-lookup"><span data-stu-id="31f0a-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="31f0a-113">A partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], la sola notifica supportata è una dipendenza cross-thread di notifica.</span><span class="sxs-lookup"><span data-stu-id="31f0a-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f0a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31f0a-114">Requirements</span></span>  
 <span data-ttu-id="31f0a-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f0a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f0a-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="31f0a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31f0a-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31f0a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31f0a-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f0a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f0a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31f0a-119">See Also</span></span>  
 [<span data-ttu-id="31f0a-120">ICorDebugProcess3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="31f0a-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [<span data-ttu-id="31f0a-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="31f0a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="31f0a-122">Debug</span><span class="sxs-lookup"><span data-stu-id="31f0a-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
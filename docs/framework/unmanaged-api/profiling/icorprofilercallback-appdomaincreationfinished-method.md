---
title: Metodo ICorProfilerCallback::AppDomainCreationFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d21198253e10434b37261d34cf12ef60c26f7e71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="a01f1-102">Metodo ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="a01f1-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="a01f1-103">Notifica al profiler che è stato creato un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a01f1-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a01f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a01f1-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a01f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a01f1-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="a01f1-106">[in] Identifica il dominio di cui è stato creato.</span><span class="sxs-lookup"><span data-stu-id="a01f1-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a01f1-107">[in] Un valore HRESULT che indica se la creazione del dominio applicazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a01f1-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a01f1-108">Note</span><span class="sxs-lookup"><span data-stu-id="a01f1-108">Remarks</span></span>  
 <span data-ttu-id="a01f1-109">L'ID dell'applicazione non è valido per qualsiasi richiesta di informazioni fino a quando il `AppDomainCreationFinished` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="a01f1-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="a01f1-110">Alcune parti del caricamento del dominio applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="a01f1-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="a01f1-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="a01f1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a01f1-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte della creazione del dominio applicazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a01f1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a01f1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a01f1-113">Requirements</span></span>  
 <span data-ttu-id="a01f1-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a01f1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a01f1-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a01f1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a01f1-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a01f1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a01f1-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a01f1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01f1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a01f1-118">See Also</span></span>  
 [<span data-ttu-id="a01f1-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a01f1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
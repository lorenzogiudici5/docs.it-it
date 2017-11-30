---
title: Funzione di Silverlight CreateDebuggingInterfaceFromVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1c37609d6fe95e95b19e6ab86bbb9ce4e9e1b87a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="2ed3c-102">Funzione di Silverlight CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="2ed3c-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="2ed3c-103">Common language runtime (CLR) versione stringa restituito da accetta il [funzione CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)e restituisce un'interfaccia del debugger corrispondente (in genere, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="2ed3c-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed3c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ed3c-104">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ed3c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ed3c-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="2ed3c-106">[in] Stringa di versione di CLR nell'oggetto del debug di destinazione, che viene restituito dal [funzione CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="2ed3c-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="2ed3c-107">[out] Puntatore a un puntatore a un oggetto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="2ed3c-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="2ed3c-108">Sarà possibile eseguire il cast di questo oggetto per un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) dell'oggetto prima che venga restituito.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-108">This object will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ed3c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2ed3c-109">Return Value</span></span>  
 <span data-ttu-id="2ed3c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ed3c-110">S_OK</span></span>  
 <span data-ttu-id="2ed3c-111">`ppCordb`fa riferimento a un oggetto valido che implementa il [interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-111">`ppCordb` references a valid object that implements the [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="2ed3c-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2ed3c-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="2ed3c-113">`szDebuggeeVersion` o `ppCordb` è null.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="2ed3c-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="2ed3c-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="2ed3c-115">Impossibile trovare un componente necessario per il debug CLR.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="2ed3c-116">Ciò significa che non è stato possibile trovare mscordaccore.dll o mscordbi.dll nella stessa directory del file CoreCLR.dll di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="2ed3c-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="2ed3c-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="2ed3c-118">Significa che la versione di mscordaccore.dll o mscordbi.dll non corrisponde a quella del file CoreCLR.dll di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="2ed3c-119">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="2ed3c-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2ed3c-120">Impossibile restituire un [interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2ed3c-120">Unable to return an [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ed3c-121">Note</span><span class="sxs-lookup"><span data-stu-id="2ed3c-121">Remarks</span></span>  
 <span data-ttu-id="2ed3c-122">L'interfaccia restituita fornisce funzionalità per connettersi a un CLR nel processo di destinazione ed eseguire il debug del codice gestito eseguito da CLR.</span><span class="sxs-lookup"><span data-stu-id="2ed3c-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed3c-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ed3c-123">Requirements</span></span>  
 <span data-ttu-id="2ed3c-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ed3c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed3c-125">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="2ed3c-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="2ed3c-126">**Libreria:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="2ed3c-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="2ed3c-127">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2ed3c-127">**.NET Framework Versions:** 3.5 SP1</span></span>
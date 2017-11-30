---
title: Funzione QualifierSet_BeginEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_BeginEnumeration Reimposta l'enumeratore dei qualificatori di un oggetto.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_BeginEnumeration
helpviewer_keywords: QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f66df772032b8e96b4956f3ed9a5818e961bd919
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="f8028-103">QualifierSet_BeginEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="f8028-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="f8028-104">Reimposta l'enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f8028-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f8028-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8028-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="f8028-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8028-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="f8028-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="f8028-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="f8028-108">[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="f8028-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="f8028-109">[in] Combinazione bit per bit dei valori descritti in o flag di [osservazioni](#remarks) sezione che specifica i qualificatori da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f8028-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="f8028-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f8028-110">Return value</span></span>

<span data-ttu-id="f8028-111">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="f8028-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f8028-112">Costante</span><span class="sxs-lookup"><span data-stu-id="f8028-112">Constant</span></span>  |<span data-ttu-id="f8028-113">Valore</span><span class="sxs-lookup"><span data-stu-id="f8028-113">Value</span></span>  |<span data-ttu-id="f8028-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8028-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f8028-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f8028-115">0x80041008</span></span> | <span data-ttu-id="f8028-116">Il `lFlags` parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="f8028-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="f8028-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f8028-117">0x8004101d</span></span> | <span data-ttu-id="f8028-118">Una seconda chiamata a `QualifierSet_BeginEnumeration` è stato eseguito senza una corrispondente chiamata a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f8028-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f8028-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f8028-119">0x80041006</span></span> | <span data-ttu-id="f8028-120">Memoria insufficiente è disponibile per avviare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f8028-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f8028-121">0</span><span class="sxs-lookup"><span data-stu-id="f8028-121">0</span></span> | <span data-ttu-id="f8028-122">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="f8028-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f8028-123">Note</span><span class="sxs-lookup"><span data-stu-id="f8028-123">Remarks</span></span>

<span data-ttu-id="f8028-124">Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="f8028-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="f8028-125">Per enumerare tutti i qualificatori su un oggetto, questo metodo deve essere chiamato prima della prima chiamata a [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="f8028-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="f8028-126">L'ordine in cui vengono enumerati i qualificatori è invariante per un'enumerazione specificata.</span><span class="sxs-lookup"><span data-stu-id="f8028-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="f8028-127">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="f8028-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="f8028-128">Costante</span><span class="sxs-lookup"><span data-stu-id="f8028-128">Constant</span></span>  |<span data-ttu-id="f8028-129">Valore</span><span class="sxs-lookup"><span data-stu-id="f8028-129">Value</span></span>  |<span data-ttu-id="f8028-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8028-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="f8028-131">0</span><span class="sxs-lookup"><span data-stu-id="f8028-131">0</span></span> | <span data-ttu-id="f8028-132">Restituisce i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="f8028-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="f8028-133">0x10</span><span class="sxs-lookup"><span data-stu-id="f8028-133">0x10</span></span> | <span data-ttu-id="f8028-134">Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8028-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="f8028-135">Per una proprietà: restituire solo i qualificatori specifici per la proprietà (inclusi sostituzioni) e non i qualificatori propagate dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="f8028-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="f8028-136">Ad esempio: restituire solo i nomi di qualificatore specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="f8028-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="f8028-137">Per una classe: restituire solo i qualificatori specifico beiong la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f8028-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="f8028-138">0x20</span><span class="sxs-lookup"><span data-stu-id="f8028-138">0x20</span></span> | <span data-ttu-id="f8028-139">Restituire solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8028-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="f8028-140">Per una proprietà: restituiscono solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli di proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="f8028-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="f8028-141">Ad esempio: restituzione solo tali qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="f8028-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="f8028-142">Per una classe: restituiscono solo i nomi di qualificatore ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="f8028-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f8028-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8028-143">Requirements</span></span>  
 <span data-ttu-id="f8028-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8028-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8028-145">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f8028-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f8028-146">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8028-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8028-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8028-147">See also</span></span>  
[<span data-ttu-id="f8028-148">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f8028-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
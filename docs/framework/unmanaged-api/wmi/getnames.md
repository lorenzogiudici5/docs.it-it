---
title: Funzione GetNames (riferimenti alle API non gestite)
description: "La funzione GetNames recupera i nomi delle proprietà di un oggetto."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetNames
helpviewer_keywords: GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2ba2530dd43e6924187c80214d5efa13ebc548de
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getnames-function"></a><span data-ttu-id="38431-103">GetNames (funzione)</span><span class="sxs-lookup"><span data-stu-id="38431-103">GetNames function</span></span>
<span data-ttu-id="38431-104">Recupera un subset o tutti i nomi delle proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="38431-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="38431-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38431-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="38431-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="38431-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="38431-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="38431-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="38431-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="38431-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="38431-109">[in] Un puntatore a un oggetto valido `LPCWSTR` che specifica un nome di qualificatore che agisce come parte di un filtro.</span><span class="sxs-lookup"><span data-stu-id="38431-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="38431-110">Per ulteriori informazioni, vedere il [osservazioni](#remarks) sezione.</span><span class="sxs-lookup"><span data-stu-id="38431-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="38431-111">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="38431-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="38431-112">[in] Una combinazione dei campi di bit.</span><span class="sxs-lookup"><span data-stu-id="38431-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="38431-113">Per ulteriori informazioni, vedere il [osservazioni](#remarks) sezione.</span><span class="sxs-lookup"><span data-stu-id="38431-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="38431-114">[in] Un puntatore a un oggetto valido `VARIANT` struttura inizializzato con un valore di filtro.</span><span class="sxs-lookup"><span data-stu-id="38431-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="38431-115">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="38431-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="38431-116">[out] Oggetto `SAFEARRAY` struttura che contiene i nomi delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="38431-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="38431-117">In ingresso, questo parametro deve essere sempre un puntatore a `null`.</span><span class="sxs-lookup"><span data-stu-id="38431-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="38431-118">Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="38431-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="38431-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="38431-119">Return value</span></span>

<span data-ttu-id="38431-120">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="38431-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="38431-121">Costante</span><span class="sxs-lookup"><span data-stu-id="38431-121">Constant</span></span>  |<span data-ttu-id="38431-122">Valore</span><span class="sxs-lookup"><span data-stu-id="38431-122">Value</span></span>  |<span data-ttu-id="38431-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38431-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="38431-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="38431-124">0x80041001</span></span> | <span data-ttu-id="38431-125">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="38431-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="38431-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="38431-126">0x80041008</span></span> | <span data-ttu-id="38431-127">Uno o più parametri non vengono o è stata specificata una combinazione dei flag e i parametri non corretta.</span><span class="sxs-lookup"><span data-stu-id="38431-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="38431-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="38431-128">0x80041006</span></span> | <span data-ttu-id="38431-129">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="38431-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="38431-130">0</span><span class="sxs-lookup"><span data-stu-id="38431-130">0</span></span> | <span data-ttu-id="38431-131">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="38431-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="38431-132">Note</span><span class="sxs-lookup"><span data-stu-id="38431-132">Remarks</span></span>

<span data-ttu-id="38431-133">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="38431-133">This function wraps a call to the [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="38431-134">Viene controllata denominata restituito da una combinazione di flag e i parametri.</span><span class="sxs-lookup"><span data-stu-id="38431-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="38431-135">Ad esempio, la funzione può restituire i nomi di tutte le proprietà o solo i nomi delle proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="38431-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="38431-136">Filtro primario è incluso il `lFlags` parametro e gli altri parametri dipendono.</span><span class="sxs-lookup"><span data-stu-id="38431-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="38431-137">I valori di flag `lFlags` sono campi di bit</span><span class="sxs-lookup"><span data-stu-id="38431-137">The flag values in `lFlags` are bit fields</span></span>


<span data-ttu-id="38431-138">I flag che possono essere passati come i `lEnumFlags` argomento sono campi di bit che sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="38431-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="38431-139">È possibile combinare un flag di ogni gruppo con un flag da qualsiasi altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="38431-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="38431-140">Tuttavia, i flag dello stesso gruppo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="38431-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="38431-141">Flag di gruppo 1</span><span class="sxs-lookup"><span data-stu-id="38431-141">Group 1 flags</span></span> |<span data-ttu-id="38431-142">Valore</span><span class="sxs-lookup"><span data-stu-id="38431-142">Value</span></span>  |<span data-ttu-id="38431-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38431-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="38431-144">0</span><span class="sxs-lookup"><span data-stu-id="38431-144">0</span></span> | <span data-ttu-id="38431-145">Restituisce i nomi delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="38431-145">Return all property names.</span></span> <span data-ttu-id="38431-146">`strQualifierName`e `pQualifierVal` inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="38431-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="38431-147">1</span><span class="sxs-lookup"><span data-stu-id="38431-147">1</span></span> | <span data-ttu-id="38431-148">Restituire solo le proprietà che hanno un qualificatore del nome specificato per il `strQualifierName` parametro.</span><span class="sxs-lookup"><span data-stu-id="38431-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="38431-149">Se questo flag viene utilizzato, è necessario specificare `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="38431-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="38431-150">2</span><span class="sxs-lookup"><span data-stu-id="38431-150">2</span></span> |  <span data-ttu-id="38431-151">Restituire solo le proprietà che non dispongono di un qualificatore del nome specificato per il `strQualifierName` parametro.</span><span class="sxs-lookup"><span data-stu-id="38431-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="38431-152">Se questo flag viene utilizzato, è necessario specificare `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="38431-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="38431-153">3</span><span class="sxs-lookup"><span data-stu-id="38431-153">3</span></span> | <span data-ttu-id="38431-154">Restituire solo le proprietà che dispongono di un qualificatore del nome specificato per il `wszQualifierName` parametro e avere un valore identico a quello specificato dal `pQualifierVal` struttura.</span><span class="sxs-lookup"><span data-stu-id="38431-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="38431-155">Se questo flag viene utilizzato, è necessario specificare sia un `wszQualifierName` e `pQualifierValue`.</span><span class="sxs-lookup"><span data-stu-id="38431-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="38431-156">Gruppo 2 flag</span><span class="sxs-lookup"><span data-stu-id="38431-156">Group 2 flags</span></span> |<span data-ttu-id="38431-157">Valore</span><span class="sxs-lookup"><span data-stu-id="38431-157">Value</span></span>  |<span data-ttu-id="38431-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38431-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="38431-159">0x4</span><span class="sxs-lookup"><span data-stu-id="38431-159">0x4</span></span> | <span data-ttu-id="38431-160">Restituire solo i nomi di proprietà che definiscono le chiavi.</span><span class="sxs-lookup"><span data-stu-id="38431-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="38431-161">0x8</span><span class="sxs-lookup"><span data-stu-id="38431-161">0x8</span></span> | <span data-ttu-id="38431-162">Restituito solo nomi di proprietà che sono riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="38431-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="38431-163">Gruppo 3 flag</span><span class="sxs-lookup"><span data-stu-id="38431-163">Group 3 flags</span></span> |<span data-ttu-id="38431-164">Valore</span><span class="sxs-lookup"><span data-stu-id="38431-164">Value</span></span>  |<span data-ttu-id="38431-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38431-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="38431-166">0x10</span><span class="sxs-lookup"><span data-stu-id="38431-166">0x10</span></span> | <span data-ttu-id="38431-167">Restituire solo i nomi di proprietà che appartengono alla classe più derivata.</span><span class="sxs-lookup"><span data-stu-id="38431-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="38431-168">Escludere le proprietà delle classi padre.</span><span class="sxs-lookup"><span data-stu-id="38431-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="38431-169">0x20</span><span class="sxs-lookup"><span data-stu-id="38431-169">0x20</span></span> | <span data-ttu-id="38431-170">Restituire solo i nomi di proprietà che appartengono alle classi padre.</span><span class="sxs-lookup"><span data-stu-id="38431-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="38431-171">0x30</span><span class="sxs-lookup"><span data-stu-id="38431-171">0x30</span></span> | <span data-ttu-id="38431-172">Restituire solo i nomi di proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="38431-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="38431-173">0x40</span><span class="sxs-lookup"><span data-stu-id="38431-173">0x40</span></span> | <span data-ttu-id="38431-174">Restituire solo i nomi di proprietà non di sistema.</span><span class="sxs-lookup"><span data-stu-id="38431-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="38431-175">La funzione alloca sempre un nuovo `SAFEARRAY` se restituisce `WBEM_S_NO_ERROR`, e `pstrNames` è sempre impostata su di esso.</span><span class="sxs-lookup"><span data-stu-id="38431-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="38431-176">La matrice restituita può essere 0 elementi se non esistono proprietà corrispondenti ai filtri specificati.</span><span class="sxs-lookup"><span data-stu-id="38431-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="38431-177">Se la funzione restituisce un valore diverso da `WBM_S_NO_ERROR`, un nuovo `SAFEARRAY` struttura non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="38431-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="38431-178">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38431-178">Requirements</span></span>  
 <span data-ttu-id="38431-179">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38431-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38431-180">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="38431-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="38431-181">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="38431-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38431-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38431-182">See also</span></span>  
[<span data-ttu-id="38431-183">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="38431-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
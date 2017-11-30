---
title: Funzione GetPropertyHandle (riferimenti alle API non gestite)
description: "La funzione GetPropertyHandle restituisce un handle univoco che una proprietà di identità."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="b30e9-103">GetPropertyHandle (funzione)</span><span class="sxs-lookup"><span data-stu-id="b30e9-103">GetPropertyHandle function</span></span>
<span data-ttu-id="b30e9-104">Restituisce un handle univoco che identifica una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b30e9-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b30e9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b30e9-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="b30e9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b30e9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b30e9-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b30e9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b30e9-108">[in] Un puntatore a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="b30e9-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="b30e9-109">[in] Una stringa con terminazione null di characaters codificata in formato UTF16 che contiene il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b30e9-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="b30e9-110">[out] Un puntatore a un [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) membro di enumerazione che rappresenta il tipo CIM della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b30e9-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="b30e9-111">[out] Un puntatore a un intero che contiene l'handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="b30e9-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="b30e9-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b30e9-112">Return value</span></span>

<span data-ttu-id="b30e9-113">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b30e9-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b30e9-114">Costante</span><span class="sxs-lookup"><span data-stu-id="b30e9-114">Constant</span></span>  |<span data-ttu-id="b30e9-115">Valore</span><span class="sxs-lookup"><span data-stu-id="b30e9-115">Value</span></span>  |<span data-ttu-id="b30e9-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b30e9-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="b30e9-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b30e9-117">0x80041002</span></span> | <span data-ttu-id="b30e9-118">Il nome della proprietà specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="b30e9-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b30e9-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b30e9-119">0x80041008</span></span> | <span data-ttu-id="b30e9-120">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="b30e9-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="b30e9-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="b30e9-121">0x8004100c</span></span> | <span data-ttu-id="b30e9-122">La proprietà richiesta è di tipo sono `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b30e9-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b30e9-123">0</span><span class="sxs-lookup"><span data-stu-id="b30e9-123">0</span></span> | <span data-ttu-id="b30e9-124">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b30e9-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b30e9-125">Note</span><span class="sxs-lookup"><span data-stu-id="b30e9-125">Remarks</span></span>

<span data-ttu-id="b30e9-126">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="b30e9-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b30e9-127">È possibile utilizzare questo handle per identificare le proprietà quando si utilizza [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) metodi per leggere o scrivere i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b30e9-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="b30e9-128">Handle possono essere recuperati per le proprietà di tutti i tipi di dati diverso da `CIM_OBJECT` e `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b30e9-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="b30e9-129">Restituito lavoro handle per tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="b30e9-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="b30e9-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b30e9-130">Requirements</span></span>  
<span data-ttu-id="b30e9-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b30e9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b30e9-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b30e9-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b30e9-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b30e9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30e9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b30e9-134">See also</span></span>  
[<span data-ttu-id="b30e9-135">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b30e9-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
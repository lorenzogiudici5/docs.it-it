---
title: Funzione GetMethodQualifierSet (riferimenti alle API non gestite)
description: La funzione GetMethodQualifierSet recupera set di qualificatore di un metodo.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodQualifierSet
helpviewer_keywords: GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79a19d3bb40dd4d435bd7cf97eb0b4071020648e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="c23c4-103">GetMethodQualifierSet (funzione)</span><span class="sxs-lookup"><span data-stu-id="c23c4-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="c23c4-104">Recupera il qualificatore impostato per un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="c23c4-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c23c4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c23c4-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="c23c4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c23c4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c23c4-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c23c4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c23c4-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="c23c4-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="c23c4-109">[in] Il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="c23c4-109">[in] The method  name.</span></span> <span data-ttu-id="c23c4-110">`wszMethod`deve puntare a un oggetto valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="c23c4-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="c23c4-111">[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori del metodo.</span><span class="sxs-lookup"><span data-stu-id="c23c4-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="c23c4-112">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="c23c4-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="c23c4-113">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore è impostato in modo che punti a `null`.</span><span class="sxs-lookup"><span data-stu-id="c23c4-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c23c4-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c23c4-114">Return value</span></span>

<span data-ttu-id="c23c4-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c23c4-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c23c4-116">Costante</span><span class="sxs-lookup"><span data-stu-id="c23c4-116">Constant</span></span>  |<span data-ttu-id="c23c4-117">Valore</span><span class="sxs-lookup"><span data-stu-id="c23c4-117">Value</span></span>  |<span data-ttu-id="c23c4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c23c4-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c23c4-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c23c4-119">0x80041002</span></span> | <span data-ttu-id="c23c4-120">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="c23c4-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c23c4-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c23c4-121">0x80041008</span></span> | <span data-ttu-id="c23c4-122">È un parametro `null`.</span><span class="sxs-lookup"><span data-stu-id="c23c4-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c23c4-123">0</span><span class="sxs-lookup"><span data-stu-id="c23c4-123">0</span></span> | <span data-ttu-id="c23c4-124">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c23c4-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c23c4-125">Note</span><span class="sxs-lookup"><span data-stu-id="c23c4-125">Remarks</span></span>

<span data-ttu-id="c23c4-126">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="c23c4-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="c23c4-127">Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="c23c4-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="c23c4-128">Modifica di metodo non è disponibile per [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="c23c4-128">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="c23c4-129">Poiché ogni metodo può avere un proprio qualificatori, il [IWbemQualifierSet puntatore](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="c23c4-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c23c4-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c23c4-130">Requirements</span></span>  
<span data-ttu-id="c23c4-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c23c4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c23c4-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c23c4-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c23c4-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c23c4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23c4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c23c4-134">See also</span></span>  
[<span data-ttu-id="c23c4-135">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c23c4-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
---
title: Funzione EnumerateCLRs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EnumerateCLRs
api_location: dbgshim.dll
api_type: COM
f1_keywords: EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4d4c9502b52f521b9faa8e8d352f0721af68314
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="enumerateclrs-function"></a><span data-ttu-id="a3260-102">Funzione EnumerateCLRs</span><span class="sxs-lookup"><span data-stu-id="a3260-102">EnumerateCLRs Function</span></span>
<span data-ttu-id="a3260-103">Fornisce un meccanismo per l'enumerazione di CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="a3260-103">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3260-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3260-104">Syntax</span></span>  
  
```  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3260-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3260-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="a3260-106">[in] Identificatore del processo da cui verranno enumerati i CLR caricati.</span><span class="sxs-lookup"><span data-stu-id="a3260-106">[in] Process identifier of the process from which loaded CLRs will be enumerated.</span></span>  
  
 `ppHandleArrayOut`  
 <span data-ttu-id="a3260-107">[out] Puntatore a una matrice contenente handle di evento usati per continuare un avvio di CLR.</span><span class="sxs-lookup"><span data-stu-id="a3260-107">[out] Pointer to an array containing event handles that are used to continue a CLR startup.</span></span> <span data-ttu-id="a3260-108">Non è garantito che ogni handle nella matrice sia valido.</span><span class="sxs-lookup"><span data-stu-id="a3260-108">Each handle in the array is not guaranteed to be valid.</span></span> <span data-ttu-id="a3260-109">Se valido, l'handle deve essere usato come evento di avvio-continuazione per il rispettivo runtime presente nello stesso indice di `ppStringArrayOut`.</span><span class="sxs-lookup"><span data-stu-id="a3260-109">If valid, the handle is to be used as the continue-startup event for the corresponding runtime located in the same index of `ppStringArrayOut`.</span></span>  
  
 `ppStringArrayOut`  
 <span data-ttu-id="a3260-110">[out] Puntatore a una matrice di stringhe che specificano i percorsi completi di CLR caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="a3260-110">[out] Pointer to an array of strings that specify full paths to CLRs loaded in the process.</span></span>  
  
 `pdwArrayLengthOut`  
 <span data-ttu-id="a3260-111">[out] Puntatore a un valore DWORD che contiene la lunghezza di `ppHandleArrayOut` e `pdwArrayLengthOut` con dimensioni identiche.</span><span class="sxs-lookup"><span data-stu-id="a3260-111">[out] Pointer to a DWORD that contains the length of the equally sized `ppHandleArrayOut` and `pdwArrayLengthOut`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3260-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3260-112">Return Value</span></span>  
 <span data-ttu-id="a3260-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3260-113">S_OK</span></span>  
 <span data-ttu-id="a3260-114">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="a3260-114">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="a3260-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a3260-115">E_INVALIDARG</span></span>  
 <span data-ttu-id="a3260-116">`ppHandleArrayOut` o `ppStringArrayOut` è Null oppure `pdwArrayLengthOut` è Null.</span><span class="sxs-lookup"><span data-stu-id="a3260-116">Either `ppHandleArrayOut` or `ppStringArrayOut` is null, or `pdwArrayLengthOut` is null.</span></span>  
  
 <span data-ttu-id="a3260-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a3260-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="a3260-118">La funzione non è in grado di allocare memoria sufficiente per le matrici di percorsi e di handle.</span><span class="sxs-lookup"><span data-stu-id="a3260-118">The function is unable to allocate enough memory for the handle and path arrays.</span></span>  
  
 <span data-ttu-id="a3260-119">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="a3260-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a3260-120">Impossibile enumerare i CLR caricati.</span><span class="sxs-lookup"><span data-stu-id="a3260-120">Unable to enumerate loaded CLRs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3260-121">Note</span><span class="sxs-lookup"><span data-stu-id="a3260-121">Remarks</span></span>  
 <span data-ttu-id="a3260-122">Per un processo di destinazione identificato da `debuggeePID`, la funzione restituisce una matrice di percorsi (`ppStringArrayOut`) ai CLR caricati nel processo, una matrice di handle di evento (`ppHandleArrayOut`) che può contenere un evento di avvio-continuazione del CLR per lo stesso indice, oltre alle dimensioni delle matrici (`pdwArrayLengthOut`) che specificano il numero di CLR caricati.</span><span class="sxs-lookup"><span data-stu-id="a3260-122">For a target process that is identified by `debuggeePID`, the function returns an array of paths, `ppStringArrayOut`, to CLRs loaded in the process; an array of event handles, `ppHandleArrayOut`, which may contain a continue-startup event for the CLR at the same index; and the size of the arrays, `pdwArrayLengthOut`, which specifies the number of CLRs that are loaded.</span></span>  
  
 <span data-ttu-id="a3260-123">Nel sistema operativo Windows `debuggeePID` esegue il mapping a un identificatore di processo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a3260-123">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="a3260-124">La memoria per `ppHandleArrayOut` e `ppStringArrayOut` viene allocata da questa funzione.</span><span class="sxs-lookup"><span data-stu-id="a3260-124">The memory for `ppHandleArrayOut` and `ppStringArrayOut` are allocated by this function.</span></span> <span data-ttu-id="a3260-125">Per liberare la memoria allocata, è necessario chiamare [funzione CloseCLREnumeration](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).</span><span class="sxs-lookup"><span data-stu-id="a3260-125">To free the memory allocated, you must call [CloseCLREnumeration Function](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).</span></span>  
  
 <span data-ttu-id="a3260-126">Questa funzione può essere chiamata con entrambi i parametri di matrice impostati su Null per restituire il conteggio di CLR nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a3260-126">This function can be called with both array parameters set to null in order to return the count of CLRs in the target process.</span></span> <span data-ttu-id="a3260-127">Da questo conteggio un chiamante è in grado di dedurre le dimensioni del buffer che verrà creato: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span><span class="sxs-lookup"><span data-stu-id="a3260-127">From this count, a caller can infer the size of the buffer that will be created: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3260-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3260-128">Requirements</span></span>  
 <span data-ttu-id="a3260-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3260-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3260-130">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="a3260-130">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="a3260-131">**Libreria:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="a3260-131">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="a3260-132">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a3260-132">**.NET Framework Versions:** 3.5 SP1</span></span>
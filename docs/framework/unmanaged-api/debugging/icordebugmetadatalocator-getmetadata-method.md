---
title: Metodo ICorDebugMetaDataLocator::GetMetaData
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMetaDataLocator.GetMetaData
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42c0548a626d43592184efa92619e74446058d58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="9f82e-102">Metodo ICorDebugMetaDataLocator::GetMetaData</span><span class="sxs-lookup"><span data-stu-id="9f82e-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="9f82e-103">Chiede al debugger di restituire il percorso completo di un modulo i cui metadati sono necessari per completare un'operazione richiesta dal debugger.</span><span class="sxs-lookup"><span data-stu-id="9f82e-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f82e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f82e-104">Syntax</span></span>  
  
```  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f82e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f82e-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="9f82e-106">[in] Stringa con terminazione null che rappresenta il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="9f82e-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="9f82e-107">Se il percorso completo non è disponibile, il nome e l'estensione del file (*filename*. *estensione*).</span><span class="sxs-lookup"><span data-stu-id="9f82e-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="9f82e-108">[in] Timestamp dalle intestazioni del file PE dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="9f82e-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="9f82e-109">Questo parametro può essere potenzialmente usato per un server di simboli ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) ricerca.</span><span class="sxs-lookup"><span data-stu-id="9f82e-109">This parameter can potentially be used for a symbol server ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="9f82e-110">[in] Dimensioni dell'immagine dalle intestazioni del file PE.</span><span class="sxs-lookup"><span data-stu-id="9f82e-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="9f82e-111">Questo parametro può essere potenzialmente usato per una ricerca in SymSrv.</span><span class="sxs-lookup"><span data-stu-id="9f82e-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="9f82e-112">[in] Numero di caratteri in `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9f82e-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="9f82e-113">[out] Numero di `WCHAR` scritto in `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9f82e-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="9f82e-114">Se il metodo restituisce E_NOT_SUFFICIENT_BUFFER, contiene il numero di `WCHAR` necessario per archiviare il percorso.</span><span class="sxs-lookup"><span data-stu-id="9f82e-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="9f82e-115">[out] Puntatore a un buffer in cui il debugger copierà il percorso completo del file che contiene i metadati richiesti.</span><span class="sxs-lookup"><span data-stu-id="9f82e-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="9f82e-116">Il `ofReadOnly` flag dal [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione viene utilizzata per richiedere l'accesso in sola lettura ai metadati in questo file.</span><span class="sxs-lookup"><span data-stu-id="9f82e-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f82e-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f82e-117">Return Value</span></span>  
 <span data-ttu-id="9f82e-118">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9f82e-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="9f82e-119">Tutti gli altri HRESULT di errore indicano che il file non è recuperabile.</span><span class="sxs-lookup"><span data-stu-id="9f82e-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="9f82e-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f82e-120">HRESULT</span></span>|<span data-ttu-id="9f82e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f82e-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f82e-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f82e-122">S_OK</span></span>|<span data-ttu-id="9f82e-123">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9f82e-123">The method completed successfully.</span></span> <span data-ttu-id="9f82e-124">`wszPathBuffer` contiene il percorso completo del file ed è con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="9f82e-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="9f82e-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9f82e-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9f82e-126">Le dimensioni correnti di `wszPathBuffer` non sono sufficienti a contenere il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="9f82e-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="9f82e-127">In questo caso, `pcchPathBuffer` contiene il numero necessario di `WCHAR`s, incluso il carattere di terminazione null e `GetMetaData` viene chiamato una seconda volta con le dimensioni del buffer richiesto.</span><span class="sxs-lookup"><span data-stu-id="9f82e-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f82e-128">Note</span><span class="sxs-lookup"><span data-stu-id="9f82e-128">Remarks</span></span>  
 <span data-ttu-id="9f82e-129">Se `wszImagePath` contiene un percorso completo di un modulo da un dump, specifica il percorso dal computer in cui è stato recuperato il dump.</span><span class="sxs-lookup"><span data-stu-id="9f82e-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="9f82e-130">Il file può non esistere in questa posizione oppure un file errato con lo stesso nome può essere archiviato nel percorso.</span><span class="sxs-lookup"><span data-stu-id="9f82e-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f82e-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f82e-131">Requirements</span></span>  
 <span data-ttu-id="9f82e-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f82e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f82e-133">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9f82e-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f82e-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f82e-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f82e-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f82e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f82e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f82e-136">See Also</span></span>  
 [<span data-ttu-id="9f82e-137">ICorDebugThread4 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9f82e-137">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="9f82e-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9f82e-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9f82e-139">Debug</span><span class="sxs-lookup"><span data-stu-id="9f82e-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
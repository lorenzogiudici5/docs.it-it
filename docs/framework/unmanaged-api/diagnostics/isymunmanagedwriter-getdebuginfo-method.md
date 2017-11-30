---
title: Metodo ISymUnmanagedWriter::GetDebugInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.GetDebugInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 562e9015f2aa402a90a7b31e4b7002e68893a812
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="5d66f-102">Metodo ISymUnmanagedWriter::GetDebugInfo</span><span class="sxs-lookup"><span data-stu-id="5d66f-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="5d66f-103">Restituisce le informazioni necessarie per un compilatore per scrivere la voce di directory di debug nell'intestazione del file (PE) eseguibile portabile.</span><span class="sxs-lookup"><span data-stu-id="5d66f-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="5d66f-104">Il writer di simboli compila tutti i campi, ad eccezione di `TimeDateStamp` e `PointerToRawData`.</span><span class="sxs-lookup"><span data-stu-id="5d66f-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="5d66f-105">(Il compilatore è responsabile dell'impostazione di questi due campi in modo appropriato).</span><span class="sxs-lookup"><span data-stu-id="5d66f-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="5d66f-106">Un compilatore deve chiamare questo metodo, creare il blob di dati per il file PE, impostare il `PointerToRawData` campo la IMAGE_DEBUG_DIRECTORY ai dati e scrivere la IMAGE_DEBUG_DIRECTORY file PE.</span><span class="sxs-lookup"><span data-stu-id="5d66f-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="5d66f-107">Il compilatore deve inoltre impostare il `TimeDateStamp` campo deve essere uguale al `TimeDateStamp` del file PE in corso la generazione.</span><span class="sxs-lookup"><span data-stu-id="5d66f-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d66f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d66f-108">Syntax</span></span>  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d66f-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d66f-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="5d66f-110">[in, out] Un puntatore a una IMAGE_DEBUG_DIRECTORY che verrà compilato il writer di simboli.</span><span class="sxs-lookup"><span data-stu-id="5d66f-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="5d66f-111">[in] Oggetto `DWORD` che contiene la dimensione dei dati di debug.</span><span class="sxs-lookup"><span data-stu-id="5d66f-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="5d66f-112">[out] Un puntatore a un `DWORD` che riceve le dimensioni del buffer necessaria per contenere i dati di debug.</span><span class="sxs-lookup"><span data-stu-id="5d66f-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="5d66f-113">[out] Un puntatore a un buffer che è sufficientemente grande da contenere i dati per l'archivio dei simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="5d66f-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d66f-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5d66f-114">Return Value</span></span>  
 <span data-ttu-id="5d66f-115">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5d66f-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d66f-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d66f-116">Requirements</span></span>  
 <span data-ttu-id="5d66f-117">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5d66f-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d66f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d66f-118">See Also</span></span>  
 [<span data-ttu-id="5d66f-119">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5d66f-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
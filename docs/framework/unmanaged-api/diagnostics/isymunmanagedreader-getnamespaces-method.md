---
title: Metodo ISymUnmanagedReader::GetNamespaces
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c4404977fab42fb46292440473cd30f6cb162d6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="4c4b4-102">Metodo ISymUnmanagedReader::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="4c4b4-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="4c4b4-103">Ottiene gli spazi dei nomi definiti in ambito globale all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="4c4b4-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c4b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c4b4-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c4b4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c4b4-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="4c4b4-106">[in] Le dimensioni della matrice di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4c4b4-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="4c4b4-107">[out] Un puntatore a una variabile che riceve la lunghezza dell'elenco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4c4b4-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="4c4b4-108">[out] Un puntatore a una variabile che riceve l'elenco di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4c4b4-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c4b4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4c4b4-109">Return Value</span></span>  
 <span data-ttu-id="4c4b4-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4c4b4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c4b4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c4b4-111">Requirements</span></span>  
 <span data-ttu-id="4c4b4-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4c4b4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c4b4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c4b4-113">See Also</span></span>  
 [<span data-ttu-id="4c4b4-114">ISymUnmanagedReader (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4c4b4-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
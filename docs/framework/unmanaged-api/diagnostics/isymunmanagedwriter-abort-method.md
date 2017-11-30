---
title: Metodo ISymUnmanagedWriter::Abort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29dd11972e8db80f36820bba1eb679070d02146e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="00da7-102">Metodo ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="00da7-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="00da7-103">Chiude il writer di simboli senza eseguire il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="00da7-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="00da7-104">Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="00da7-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="00da7-105">Per eseguire il commit i simboli e chiudere il writer di simboli, utilizzare il [ISymUnmanagedWriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="00da7-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00da7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00da7-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="00da7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00da7-107">Return Value</span></span>  
 <span data-ttu-id="00da7-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="00da7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00da7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00da7-109">Requirements</span></span>  
 <span data-ttu-id="00da7-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="00da7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00da7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00da7-111">See Also</span></span>  
 [<span data-ttu-id="00da7-112">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="00da7-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
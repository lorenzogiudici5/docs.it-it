---
title: Metodo GetWin32ResBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4456757c56440463010d4adc3d3eed90dbc07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="f8f0c-102">Metodo GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="f8f0c-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="f8f0c-103">Recupera il blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="f8f0c-104">Chiamare questo metodo dopo l'impostazione di opzioni per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f0c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8f0c-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8f0c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8f0c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f8f0c-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f8f0c-108">Token di file utilizzato per recuperare il nome del file da utilizzare quando si crea la risorsa di versione Win32</span><span class="sxs-lookup"><span data-stu-id="f8f0c-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="f8f0c-109">TRUE se è un file DLL, false per un file EXE.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="f8f0c-110">Icona facoltativa da inserire nel blob di risorse.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="f8f0c-111">Riceve il blob di risorse.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="f8f0c-112">Riceve le dimensioni del blob.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8f0c-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f8f0c-113">Return Value</span></span>  
 <span data-ttu-id="f8f0c-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="f8f0c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f0c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8f0c-115">Requirements</span></span>  
 <span data-ttu-id="f8f0c-116">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="f8f0c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f0c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f0c-117">See Also</span></span>  
 [<span data-ttu-id="f8f0c-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f8f0c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f8f0c-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f8f0c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f8f0c-120">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="f8f0c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
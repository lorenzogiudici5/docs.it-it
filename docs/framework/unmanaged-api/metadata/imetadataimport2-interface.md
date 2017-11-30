---
title: Interfaccia IMetaDataImport2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2
helpviewer_keywords: IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1b00879f1d22d49e5f0dc3bdb072e0545feda68d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="53bf6-102">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="53bf6-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="53bf6-103">Estende il [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per consentire l'utilizzo dei tipi generici.</span><span class="sxs-lookup"><span data-stu-id="53bf6-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53bf6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="53bf6-104">Methods</span></span>  
  
|<span data-ttu-id="53bf6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="53bf6-105">Method</span></span>|<span data-ttu-id="53bf6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53bf6-107">EnumGenericParamConstraints (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="53bf6-108">Ottiene un enumeratore per una matrice di vincoli del parametro generico associato al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="53bf6-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="53bf6-109">EnumGenericParams (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="53bf6-110">Ottiene un enumeratore per una matrice di token di parametri generici associati il TypeDef o MethodDef specificato token.</span><span class="sxs-lookup"><span data-stu-id="53bf6-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="53bf6-111">EnumMethodSpecs (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="53bf6-112">Ottiene un enumeratore per una matrice di MethodSpec token associato al specificato MethodDef o MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="53bf6-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="53bf6-113">GetGenericParamConstraintProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="53bf6-114">Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.</span><span class="sxs-lookup"><span data-stu-id="53bf6-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="53bf6-115">GetGenericParamProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="53bf6-116">Ottiene i metadati associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="53bf6-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="53bf6-117">GetMethodSpecProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="53bf6-118">Ottiene la firma dei metadati del metodo di MethodSpec specificato a cui fa riferimento token.</span><span class="sxs-lookup"><span data-stu-id="53bf6-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="53bf6-119">GetPEKind (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="53bf6-120">Ottiene un valore che identifica il tipo di codice in un file eseguibile portabile (PE) di file, in genere un file DLL o EXE, definito nell'ambito dei metadati corrente</span><span class="sxs-lookup"><span data-stu-id="53bf6-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="53bf6-121">GetVersionString (metodo)</span><span class="sxs-lookup"><span data-stu-id="53bf6-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="53bf6-122">Ottiene il numero di versione del runtime che è stato utilizzato per compilare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="53bf6-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53bf6-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53bf6-123">Requirements</span></span>  
 <span data-ttu-id="53bf6-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53bf6-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53bf6-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="53bf6-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53bf6-126">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53bf6-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53bf6-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53bf6-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53bf6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53bf6-128">See Also</span></span>  
 <xref:System.Reflection.PortableExecutableKinds>  
 [<span data-ttu-id="53bf6-129">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="53bf6-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="53bf6-130">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="53bf6-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
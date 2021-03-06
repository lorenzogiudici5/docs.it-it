---
title: Metodo IMetaDataEmit::SetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e22cf8e540bfdb53ad243640dac110b5750e53e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449121"
---
# <a name="imetadataemitsetclasslayout-method"></a>Metodo IMetaDataEmit::SetClassLayout
Completa il layout dei campi per una classe che è stato definito da una precedente chiamata a [metodo DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Un `mdTypeDef` token che specifica la classe a disposizione.  
  
 `dwPackSize`  
 [in] La dimensione di compressione: 1, 2, 4, 8 o 16 byte. La dimensione di compressione è il numero di byte tra campi adiacenti.  
  
 `rFieldOffsets`  
 [in] Matrice di [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) strutture, ognuno dei quali specifica un campo della classe e il campo dell'offset all'interno della classe. Terminare la matrice con `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Le dimensioni in byte, della classe.  
  
## <a name="remarks"></a>Note  
 Inizialmente è definita la classe chiamando il [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) metodo e specificando uno dei tre layout per i campi della classe: automatico, sequenziale o esplicito. In genere, si usano il layout automatico e consentire il runtime di scegliere il modo migliore per disporre i campi.  
  
 Tuttavia, è consigliabile che i campi disposti in base alla disposizione non gestito a codice viene utilizzato. In questo caso, scegliere il layout sequenziale o esplicito e chiamare `SetClassLayout` per completare il layout dei campi:  
  
-   Layout sequenziale: specificare la dimensione di compressione. Un campo è allineato in base alle dimensioni naturali o la dimensione di compressione, a seconda del valore comporta l'offset del campo inferiore. Impostare `rFieldOffsets` e `ulClassSize` a zero.  
  
-   Layout esplicito: specificare l'offset di ogni campo o specificare le dimensioni di classe e la dimensione di compressione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

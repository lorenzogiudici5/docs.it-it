---
title: Metodo ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8a87fb05a49c2813cf4d299c3663419be1640b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>Metodo ICorProfilerCallback::ExceptionCatcherEnter
Notifica al profiler che viene passato a appropriato controllo `catch` blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'identificatore di funzione che contiene il `catch` blocco.  
  
 `objectId`  
 [in] Identificatore dell'eccezione gestita.  
  
## <a name="remarks"></a>Note  
 Il `ExceptionCatcherEnter` metodo viene chiamato solo se il punto di catch nel codice compilato con il compilatore just-in-time (JIT). Un'eccezione che viene rilevata nel codice non gestito o nel codice di runtime interno non chiama questa notifica. Il `objectId` valore viene passato nuovamente dopo un'operazione di garbage collection potrebbe essere stato spostato l'oggetto perché il `ExceptionThrown` notifica.  
  
 Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection. Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.  
  
 Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)

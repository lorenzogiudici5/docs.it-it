---
title: Metodo ICorProfilerCallback3::ProfilerAttachComplete
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8397900e2dafb69807417090cbb30c85dd884c59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a>Metodo ICorProfilerCallback3::ProfilerAttachComplete
Chiamato da common language runtime (CLR) per indicare che il profiler può chiamare il [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) e [ICorProfilerInfo3:: EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) metodi di aggiornamento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a>Note  
 Il `ProfilerAttachComplete` callback viene generato dopo il [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) metodo viene chiamato. Indica quanto segue:  
  
-   I callback richiesti dal profiler in `InitializeForAttach` sono stati attivati.  
  
-   Il profiler può eseguire l'aggiornamento degli ID associati senza doversi preoccupare delle notifiche mancanti.  
  
 Il valore restituito da questo callback viene ignorato da CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)

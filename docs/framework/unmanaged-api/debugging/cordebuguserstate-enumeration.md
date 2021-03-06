---
title: Enumerazione CorDebugUserState
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f489ab29726292f6c55151169ad9efc6f0fbfbcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407794"
---
# <a name="cordebuguserstate-enumeration"></a>Enumerazione CorDebugUserState
Indica lo stato utente di un thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>Membri  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|È stata richiesta la terminazione del thread.|  
|`USER_SUSPEND_REQUESTED`|È stata richiesta una sospensione del thread.|  
|`USER_BACKGROUND`|Il thread è in esecuzione in background.|  
|`USER_UNSTARTED`|Il thread non ha avviato l'esecuzione.|  
|`USER_STOPPED`|Il thread è stato terminato.|  
|`USER_WAIT_SLEEP_JOIN`|Il thread è in attesa di un altro thread completare un'attività.|  
|`USER_SUSPENDED`|Il thread è stata sospesa.|  
|`USER_UNSAFE_POINT`|Il thread è in un punto unsafe. Il thread è in esecuzione un punto in cui potrebbe bloccare l'operazione di garbage collection.<br /><br /> Eseguire il debug sia possibile inviare eventi da punti non sicuri, ma la sospensione di un thread in un punto unsafe molto probabile che un deadlock fino alla ripresa del thread. I punti sicuri e sono determinati dal just-in-time (JIT) e implementazione di garbage collection.|  
|`USER_THREADPOOL`|Il thread è dal pool di thread.|  
  
## <a name="remarks"></a>Note  
 Lo stato utente di un thread è lo stato in cui il thread è presente quando si esamina il debugger. Un thread può avere una combinazione di stati utente.  
  
 Utilizzare il [GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) metodo per recuperare lo stato utente di un thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

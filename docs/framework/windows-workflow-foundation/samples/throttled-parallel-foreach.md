---
title: ThrottledParallelForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 8691edb8a5a61204b187be8def553f2f06be0f0d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581862"
---
# <a name="throttled-parallel-foreach"></a>ThrottledParallelForEach
Il `ThrottleParallelForEach` è simile all'attività la <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` attività con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire. L'attività `ThrottleParallelForEach` deriva dall'oggetto <xref:System.Activities.NativeActivity>, poiché deve pianificare altre attività (le attività figlio) ed è accessibile solo tramite la classe <xref:System.Activities.NativeActivityContext>.

## <a name="projects"></a>Progetti

|**ProjectName**|**Descrizione**|**File principali.**|
|-|-|-|
|ThrottledParallelForEach|Contiene l'attività `ThrottledParallelForEach` e la relativa finestra di progettazione.|ThrottledParallelForEach.cs<br /><br /> Definizione dell'attività `ThrottledParallelForEach`.|
|CodeTestClient|Applicazione client di esempio che configura ed esegue un flusso di lavoro con un oggetto `ThrottledParallelForEach` usando il codice imperativo.|Program.cs<br /><br /> Definisce ed esegue un'istanza del flusso di lavoro di esempio.|

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Con Visual Studio 2010, aprire il file Throttledparallelforeach.

2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.

3.  Per eseguire la soluzione, premere F5.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`
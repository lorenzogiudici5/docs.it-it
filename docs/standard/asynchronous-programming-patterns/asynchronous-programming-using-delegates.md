---
title: Programmazione asincrona tramite delegati
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bad5372af1d771dc93a20e61090ef84126f3e1eb
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033324"
---
# <a name="asynchronous-programming-using-delegates"></a>Programmazione asincrona tramite delegati
I delegati consentono di chiamare un metodo sincrono in modo asincrono. Quando si chiama un delegato in modo sincrono, il metodo `Invoke` chiama il metodo di destinazione direttamente sul thread corrente. Se viene chiamato il metodo `BeginInvoke`, Common Language Runtime (CLR) accoda la richiesta e restituisce immediatamente il controllo al chiamante. Il metodo di destinazione viene chiamato in modo asincrono in un thread del pool di thread. Il thread originale, che ha inviato la richiesta, può di continuare l'esecuzione in parallelo con il metodo di destinazione. Se nella chiamata al metodo `BeginInvoke`, è stato specificato un metodo di callback, quest'ultimo verrà chiamato al termine del metodo di destinazione. Nel metodo di callback il metodo `EndInvoke` ottiene il valore restituito e tutti i parametri di input/output o solo di output. Se nella chiamata a `BeginInvoke` non viene specificato alcun metodo di callback, `EndInvoke` può essere chiamato dal thread che ha effettuato la chiamata a `BeginInvoke`.  
  
> [!IMPORTANT]
>  I compilatori devono creare classi delegate con metodi `Invoke`, `BeginInvoke`e `EndInvoke` usando la firma del delegato specificata dall'utente. I metodi `BeginInvoke` e `EndInvoke` devono essere contrassegnati come nativi. Poiché tali metodi sono contrassegnati come nativi, Common Language Runtime ne specifica automaticamente l'implementazione in fase di caricamento della classe. Il caricatore garantisce anche che non ne venga eseguito l'override.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Chiamata sincrona dei metodi asincroni](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Descrive l'uso di delegati per eseguire chiamate asincrone a metodi comuni e contiene semplici esempi di codice in cui si illustrano i quattro modi disponibili per attendere la risposta di una chiamata asincrona.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)  
 Descrive la programmazione asincrona con .NET Framework.  
  
## <a name="see-also"></a>Vedere anche

* <xref:System.Delegate>

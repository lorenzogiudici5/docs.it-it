---
title: dati di marshalling con interoperabilità COM
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0d94223223568efe921af3a340815a966cc6c6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388355"
---
# <a name="marshaling-data-with-com-interop"></a>dati di marshalling con interoperabilità COM
Grazie all'interoperabilità COM, è possibile usare oggetti COM dal codice gestito ed esporre oggetti gestiti a COM. Il supporto per il marshalling dei dati verso e da COM è estensivo e garantisce sempre il comportamento di marshalling corretto.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] include i seguenti strumenti di interoperabilità COM:  
  
-   [Utilità di importazione della libreria dei tipi (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), che consente di convertire una libreria dei tipi COM in un assembly di interoperabilità, dal quale, con il servizio di marshalling di interoperabilità, vengono generati wrapper per il marshalling dei dati tra memoria gestita e non gestita.  
  
-   [Utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che consente di generare una libreria dei tipi COM da un assembly e un wrapper per l'esecuzione del marshalling durante le chiamate ai metodi.  
  
 Le sezioni seguenti riportano collegamenti ad argomenti che descrivono i processi per la personalizzazione dei wrapper di interoperabilità quando è possibile o necessario fornire altre informazioni sui tipi al gestore di marshalling.  
  
## <a name="in-this-section"></a>In questa sezione  
[Procedura: Creare wrapper manualmente](how-to-create-wrappers-manually.md)   
Descrive come creare manualmente un wrapper COM nel codice sorgente gestito. 
 
 [Procedura: Eseguire la migrazione di codice gestito da DCOM a WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Descrive come eseguire la migrazione di codice gestito DCOM in WCF per la soluzione più sicura.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Tipi di dati COM](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)  
 Fornisce i tipi di dati gestiti e non gestiti corrispondenti.  
  
 [Personalizzazione di wrapper COM richiamabili](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)  
 Descrive come effettuare esplicitamente il marshalling dei tipi di dati tramite l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> in fase di progettazione.  
  
 [Personalizzazione dei Runtime Callable Wrapper](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)  
 Descrive come regolare il comportamento del marshalling dei tipi in un assembly di interoperabilità e come definire manualmente i tipi COM.  
  
 [Interoperabilità COM avanzata](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)  
 Contiene collegamenti per accedere ad altre informazioni sull'inclusione di componenti COM nell'applicazione .NET Framework.  
  
 [Riepilogo della conversione da assembly a libreria dei tipi](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)  
 Descrive il processo di conversione eseguito in caso di esportazione da assembly a libreria dei tipi.  
  
 [Riepilogo della conversione da libreria dei tipi ad assembly](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)  
 Descrive il processo di conversione eseguito in caso di importazione da libreria dei tipi ad assembly.  
  
 [Interoperabilità tramite tipi generici](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)  
 Descrive le azioni supportate quando si usano tipi generici per l'interoperabilità COM.

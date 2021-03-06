---
title: Risoluzione dell'overload (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: d95589eb16f45eeff10692cdc897bf65ebe2d84e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653429"
---
# <a name="overload-resolution-visual-basic"></a>Risoluzione dell'overload (Visual Basic)
Quando il compilatore Visual Basic rileva una chiamata a una routine definito in diverse versioni di overload, il compilatore deve decidere quale overload da chiamare. A tale scopo, eseguire la procedura seguente:  
  
1.  **Accessibilità.** Elimina tutti gli overload con un livello di accesso che impedisce la chiamata al codice chiamante.  
  
2.  **Numero di parametri.** Eliminazione di eventuali overload che definisce un numero di parametri diverso rispetto a quello fornito nella chiamata.  
  
3.  **Tipi di dati di parametro.** Il compilatore assegna delle preferenze di metodi di istanza sui metodi di estensione. Se viene trovato alcun metodo di istanza che richiede solo di ampliamento per rispondere alla chiamata di procedura, vengono eliminati tutti i metodi di estensione e il compilatore continua con solo i candidati di metodo di istanza. Se tale metodo di istanza non viene trovato, ma continua con l'istanza sia metodi di estensione.  
  
     In questo passaggio, essa elimina alcun overload per il quale i tipi di dati degli argomenti di chiamata non possono essere convertiti per i tipi di parametro definiti nell'overload.  
  
4.  **Conversioni di restrizione.** Eliminazione di eventuali overload che richiede una conversione dai tipi di argomento chiamante per i tipi di parametro definito. È true se il controllo dei tipi di passare ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `On` o `Off`.  
  
5.  **Minore di ampliamento.** Il compilatore considera gli overload rimanenti nelle coppie. Per ogni coppia, confronta i tipi di dati dei parametri definiti. Se i tipi in uno degli overload tutti vengono ampliati ai tipi corrispondenti negli altri, il compilatore elimina quest'ultimo. Vale a dire, viene mantenuto l'overload che richiede il minor grado di ampliamento.  
  
6.  **Singolo candidato.** Vengono presi in considerazione gli overload nelle coppie finché l'unico overload rimane e viene risolta la chiamata all'overload. Se il compilatore non è possibile ridurre gli overload a uno solo, viene generato un errore.  
  
 Nella figura seguente viene illustrato il processo che determina quale versione di un set di versioni di overload da chiamare.  
  
 ![Diagramma di flusso del processo di risoluzione dell'overload](./media/overloadres.gif "OverloadRes")  
Risoluzione tra le versioni di overload  
  
 Nell'esempio seguente viene illustrato questo processo di risoluzione di overload.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 Nella prima chiamata, il compilatore elimina il primo overload poiché il tipo del primo argomento (`Short`) viene convertito nel tipo del parametro corrispondente (`Byte`). Viene quindi eliminato il terzo overload poiché ogni tipo di argomento nel secondo overload (`Short` e `Single`) viene ampliato al tipo corrispondente del terzo overload (`Integer` e `Single`). Il secondo overload richiede un ampliamento minore, pertanto verrà utilizzato dal compilatore per la chiamata.  
  
 Nella seconda chiamata, il compilatore non è possibile eliminare uno degli overload sulla base di restrizione. Viene eliminato il terzo overload per lo stesso motivo della prima chiamata, poiché è possibile chiamare il secondo overload con un ampliamento minore dei tipi di argomento. Tuttavia, il compilatore non è possibile risolvere tra il primo e secondo overload. Ognuno presenta un tipo di parametro definito che viene ampliato al tipo corrispondente in altro (`Byte` a `Short`, ma `Single` a `Double`). Pertanto, il compilatore genera un errore di risoluzione dell'overload.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Di overload facoltativo e argomenti ParamArray  
 Se i due overload di una stored procedure hanno firme identiche ad eccezione del fatto che l'ultimo parametro è dichiarato [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) in uno e [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in altro, il compilatore risolve una chiamata a procedura come di seguito:  
  
|Se la chiamata viene fornito come ultimo argomento|Il compilatore risolve la chiamata dell'overload dichiarando l'ultimo argomento come|  
|---|---|  
|Nessun valore (argomento omesso)|`Optional`|  
|un singolo valore|`Optional`|  
|Due o più valori in un elenco delimitato da virgole|`ParamArray`|  
|Matrice di qualsiasi lunghezza (inclusa una matrice vuota)|`ParamArray`|  
  
## <a name="see-also"></a>Vedere anche  
 [Parametri facoltativi](./optional-parameters.md)  
 [Matrici di parametri](./parameter-arrays.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)  
 [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)  
 [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Metodi di estensione](./extension-methods.md)

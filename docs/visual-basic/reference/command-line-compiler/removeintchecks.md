---
title: -/removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: f061497083dc23fd07f61108938a4129c0af5f3a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188533"
---
# <a name="-removeintchecks"></a>-/removeintchecks
Attiva il controllo per operazioni con numeri interi o disattivare l'errore di overflow.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Il `-removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di interi per gli errori di overflow. Il valore predefinito è `-removeintchecks-`.<br /><br /> Che specifica `-removeintchecks` o `-removeintchecks+` impedisce il controllo degli errori e può rendere più veloci i calcoli di integer. Tuttavia, senza il controllo degli errori, e se le capacità di tipo di dati sono ha causato l'overflow, risultati non corretti potrebbero essere archiviati senza generare un errore.|  
  
|Per impostare - /removeintchecks nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il valore dei **Rimuovi controllo dell'overflow integer** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Test.vb` e consente di disattivare il controllo dell'overflow integer.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

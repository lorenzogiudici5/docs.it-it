---
title: 'Procedura: convertire stringhe esadecimali in numeri (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: 65184bbb742ad549a8398d55dc7bdeed05a9d973
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197549"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Procedura: convertire stringhe esadecimali in numeri (Visual Basic)
In questo esempio converte una stringa esadecimale in un numero intero usando la <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> (metodo).  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Per convertire una stringa esadecimale in un numero  
  
-   Usare il <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo per convertire il numero espresso in base 16 per un numero intero.  
  
     Il primo argomento del <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo è la stringa da convertire. Il secondo argomento viene descritto il numero viene espresso in; base esadecimale è base 16.  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- Si noti che la stringa esadecimale presenta le restrizioni seguenti:

   - Non può includere il `&h` prefisso.
   - Non può includere il `_` separatore di cifre.

   Se il prefisso o un separatore di cifra è presente, la chiamata per il <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo genera un <xref:System.FormatException>.

## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>

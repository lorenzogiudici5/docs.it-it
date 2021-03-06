---
title: . (Accesso ai membri) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: fdcd026d245b3f6d6ecaccc0f828f3d77fd6ce1a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764632"
---
# <a name="-member-access-entity-sql"></a>. (Accesso ai membri) (Entity SQL)
L'operatore punto (.) è il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatore di accesso al membro. L'operatore di accesso ai membri viene usato per produrre il valore di una proprietà o di un campo di un'istanza del tipo di modello concettuale strutturale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Istanza di un tipo di modello concettuale strutturale.  
  
 `identifier`  
 Proprietà o campo che appartiene a un'istanza dell'oggetto.  
  
## <a name="remarks"></a>Note  
 L'operatore punto (.) può essere usato per estrarre campi da un record, analogamente all'estrazione di proprietà di un tipo di entità o complesso. Se, ad esempio, un oggetto n di tipo Name è un membro del tipo Person e p è un'istanza del tipo Person, p.n è un'espressione di accesso ai membri valida che restituisce un valore di tipo Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

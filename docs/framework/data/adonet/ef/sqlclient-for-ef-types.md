---
title: SqlClient per tipi Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: f5b471cea4f26c06e8af77298c256bff97ef21de
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766543"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient per tipi Entity Framework
Il file manifesto del provider di dati .NET Framework per SQL Server (SqlClient) include l'elenco dei tipi primitivi del provider, facet per ogni tipo, mapping tra i tipi primitivi del modello concettuale e del modello di archiviazione e regole di promozione e conversione tra i tipi primitivi del modello concettuale e del modello di archiviazione.  
  
 Nella tabella seguente vengono descritti i tipi per SQL Server 2008, [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], e [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] tipi di modello di database e il mapping a concettuale tra questi tipi. Alcuni nuovi tipi sono stati introdotti in versioni successive di SQL Server e non sono supportati nelle versioni precedente di SQL Server. Tali tipi sono segnalati nella tabella riportata di seguito.  
  
|Tipo di provider:<br /><br /> name|Tipo di provider:<br /><br /> attributi|`EDMSimpleType`<br /><br /> name|Facet|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|n/d|`Edm.Boolean`|n/d|  
|`tinyint`|n/d|`Edm.Byte`|n/d|  
|`smallint`|n/d|`Edm.Int16`|n/d|  
|`int`|n/d|`Edm.Int32`|n/d|  
|`bigint`|n/d|`Edm.Int64`|n/d|  
|`float`|n/d|`Edm.Double`|n/d|  
|`real`|n/d|`Edm.Double`|n/d|  
|`decimal`|N/D|`Edm.Decimal`|Precisione:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 38<br /><br /> -Il valore predefinito: 18<br /><br /> -Costante: False<br /><br /> Scala:<br /><br /> -Minimo: 0<br /><br /> -Massimo: 38<br /><br /> -Il valore predefinito: 0<br /><br /> -Costante: False|  
|`numeric`|N/D|`Edm.Decimal`|Precisione:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 38<br /><br /> -Il valore predefinito: 18<br /><br /> -Costante: False<br /><br /> Scala:<br /><br /> -Minimo: 0<br /><br /> -Massimo: 38<br /><br /> -Il valore predefinito: 0<br /><br /> -Costante: False|  
|`smallmoney`|N/D|`Edm.Decimal`|Precisione:<br /><br /> -Il valore predefinito: 10<br /><br /> -Costante: True<br /><br /> Scala:<br /><br /> -Il valore predefinito: 4<br /><br /> -Costante: True|  
|`money`|N/D|`Edm.Decimal`|Precisione:<br /><br /> -Il valore predefinito: 19<br /><br /> -Costante: True<br /><br /> Scala:<br /><br /> -Il valore predefinito: 4<br /><br /> -Costante: True|  
|`binary`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Il valore predefinito: 8000<br /><br /> -Costante: False<br /><br /> Stringa:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True|  
|`varbinary`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Il valore predefinito: 8000<br /><br /> -Costante: False<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`varbinary(max)`<br /><br /> Nota: Questo tipo non supportato [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Il valore predefinito: 214748364780<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`image`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Il valore predefinito: 2147483647<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`timestamp`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Il valore predefinito: 8<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True|  
|`rowversion`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Il valore predefinito: 8<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True|  
|`smalldatetime`|N/D|`Edm.DateTime`|Precisione:<br /><br /> -Il valore predefinito: 0<br /><br /> -Costante: True|  
|`datetime`|N/D|`Edm.DateTime`|Precisione:<br /><br /> -Il valore predefinito: 3<br /><br /> -Costante: True|  
|`date`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.DateTime`|Precisione:<br /><br /> -Il valore predefinito: 0<br /><br /> -Costante: False|  
|`time`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.Time`|Precisione:<br /><br /> -Il valore predefinito: 7<br /><br /> -Costante: False|  
|`datetime2`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.DateTime`|Precisione:<br /><br /> -Il valore predefinito: 7<br /><br /> -Costante: False|  
|`datetimeoffset`<br /><br /> Nota: Questo tipo non è supportato in SQL Server 2005 e SQL Server 2000.|N/D|`Edm.DateTimeOffset`|Precisione:<br /><br /> -Il valore predefinito: 7<br /><br /> -Costante: False|  
|`nvarchar`<br /><br /> Nota: Questo tipo non supportato [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.String`|MaxLength:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 4000<br /><br /> -Il valore predefinito: 4000<br /><br /> -Costante: False<br /><br /> Unicode:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`varchar`<br /><br /> Nota: Questo tipo non supportato [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.String`|MaxLength:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Il valore predefinito: 8000<br /><br /> -Costante: False<br /><br /> Unicode:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`char`|N/D|`Edm.String`|MaxLength:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 8000<br /><br /> -Il valore predefinito: 8000<br /><br /> -Costante: False<br /><br /> Unicode:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True|  
|`nchar`|N/D|`Edm.String`|MaxLength:<br /><br /> -Minimo: 1<br /><br /> -Massimo: 4000<br /><br /> -Il valore predefinito: 4000<br /><br /> -Costante: False<br /><br /> Unicode:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True|  
|`varchar`(`max`)|N/D|`Edm.String`|MaxLength:<br /><br /> -Il valore predefinito: 2147483647<br /><br /> -Costante: True<br /><br /> Unicode:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`nvarchar`(`max`)|N/D|`Edm.String`|MaxLength:<br /><br /> -Il valore predefinito: 1073741823<br /><br /> -Costante: True<br /><br /> Unicode:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`ntext`|Uguale confrontabili: False<br /><br /> Confrontabile: False|`Edm.String`|MaxLength:<br /><br /> -Il valore predefinito: 1073741823<br /><br /> -Costante: True<br /><br /> Unicode:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`text`|Uguale confrontabili: False<br /><br /> Confrontabile: False|`Edm.String`|MaxLength:<br /><br /> -Il valore predefinito: 2147483647<br /><br /> -Costante: True<br /><br /> Unicode:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
|`Unique`<br /><br /> `identifier`|Uguale confrontabili: True<br /><br /> Confrontabile: True|`Edm.Guid`|N/D|  
|`xml`|Uguale confrontabili: False<br /><br /> Confrontabile: False|`Edm.String`|MaxLength:<br /><br /> -Il valore predefinito: 1073741823<br /><br /> -Costante: True<br /><br /> Unicode:<br /><br /> -Il valore predefinito: True<br /><br /> -Costante: True<br /><br /> Stringa:<br /><br /> -Il valore predefinito: False<br /><br /> -Costante: True|  
  
## <a name="see-also"></a>Vedere anche  
 [Specifiche CSDL, SSDL e MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)

---
title: 'Procedura: cercare dati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588054"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a>Procedura: cercare dati in un controllo DataRepeater (Visual Studio)
Quando si utilizza un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo contenente molti record, è possibile consentire agli utenti di ricerca per un record specifico. Invece di cercare i dati nel controllo stesso, è possibile implementare una ricerca eseguendo una query sottostante <xref:System.Windows.Forms.BindingSource>. Se l'elemento viene trovato, è possibile utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> proprietà selezionare l'elemento e scorrerlo nella visualizzazione.  
  
### <a name="to-implement-search"></a>Per implementare la ricerca  
  
1.  Trascinare il controllo <xref:System.Windows.Forms.TextBox> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  Nella finestra Proprietà modificare la proprietà **Name** in **SearchTextBox**.  
  
3.  Trascinare il controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
4.  Nella finestra Proprietà modificare la proprietà **Name** in **SearchButton**. Impostare la proprietà **Text** su **Search**.  
  
5.  Fare doppio clic sul controllo <xref:System.Windows.Forms.Button> per aprire l'editor di codice e aggiungere il codice seguente al gestore dell'evento `SearchButton_Click` .  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     Sostituire *ProductsBindingSource* con il nome del <xref:System.Windows.Forms.BindingSource> per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e sostituire *ProductID* con il nome del campo che si desidera cercare.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)

---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 7951a545fd8cbd0ae30907922551216161171a8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531264"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form
Il <xref:System.Windows.Forms.ToolStrip> controllo supporta pienamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura di <xref:System.Windows.Forms.ToolStripItem> ai controlli reciprocamente, la disposizione dei controlli il <xref:System.Windows.Forms.ToolStrip>e la spaziatura tra i controlli rispetto al <xref:System.Windows.Forms.ToolStrip>.  
  
 Poiché il valore predefinito del <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà è `true`, i controlli vengono ridimensionati automaticamente a meno che non si imposta la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Per ridimensionare manualmente un ToolStripItem  
  
1.  Impostare il <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà `false` per il controllo associato.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  Impostare il <xref:System.Windows.Forms.ToolStripItem.Size%2A> proprietà nel modo desiderato per la proprietà associata <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Per impostare la spaziatura di un controllo ToolStripItem  
  
1.  Inserire i valori desiderati, in pixel, di <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà del controllo associato.  
  
     I valori del <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà specificare la spaziatura tra l'elemento e gli elementi adiacenti nell'ordine indicato: sinistro, superiore, destro e inferiore.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Per allineare un controllo ToolStripItem sul lato destro dell'oggetto ToolStrip  
  
1.  Impostare il <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà <xref:System.Windows.Forms.ToolStripItemAlignment.Right> per il controllo associato. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, quali controlli sono allineati a sinistra del <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Per disporre gli elementi di ToolStrip di ToolStrip  
  
-   Impostare il <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> il valore di proprietà <xref:System.Windows.Forms.ToolStripLayoutStyle> desiderati.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)

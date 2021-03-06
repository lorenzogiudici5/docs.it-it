---
title: 'Procedura: spostare i ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 69ef2bbaa05155532887897a0aef79a778594169
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384900"
---
# <a name="how-to-move-toolstripmenuitems"></a>Procedura: spostare i ToolStripMenuItems
In fase di progettazione, è possibile passare interi menu di primo livello e i relativi elementi in un'altra posizione di <xref:System.Windows.Forms.MenuStrip>. È anche possibile spostare singole voci di menu tra menu di primo livello o modificare la posizione delle voci di menu all'interno di un menu.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Per spostare un menu di primo livello e le voci di menu in un'altra posizione di primo livello  
  
1.  Fare clic e tenere premuto il pulsante sinistro del mouse sul menu da spostare.  
  
2.  Trascinare il punto di inserimento per il menu di primo livello che precede la nuova posizione e rilasciare il pulsante sinistro del mouse.  
  
     Menu selezionato viene spostato a destra del punto di inserimento.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Per spostare un menu di primo livello e le voci di menu in un percorso di elenco a discesa  
  
1.  Fare clic sul menu che si desidera spostare e premere CTRL + X, o il menu di scelta rapida e selezionare **Taglia** dal menu di scelta rapida.  
  
2.  Nel menu di primo livello di destinazione, fare clic sulla voce di menu precede la nuova posizione e premere CTRL + V, o la voce di menu precede la nuova posizione e scegliere **Incolla** dal menu di scelta rapida.  
  
     Il menu che si taglia viene inserito dopo la voce di menu selezionata.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Per spostare una voce di menu all'interno di un menu con l'Editor della raccolta Items  
  
1.  Menu di scelta rapida che contiene la voce di menu da spostare.  
  
2.  Dal menu di scelta rapida, scegliere **Modifica DropDownItems**.  
  
3.  Nel **Editor della raccolta Items**, fare clic sulla voce di menu da spostare.  
  
4.  Fare clic sui tasti di direzione su e giù per spostare la voce di menu all'interno del menu.  
  
5.  Fare clic su **OK**.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Per spostare una voce di menu all'interno di un menu con la tastiera  
  
1.  Premere e tenere premuto il tasto ALT.  
  
2.  Fare clic e tenere premuto il pulsante sinistro del mouse sulla voce di menu che si desidera spostare.  
  
3.  Trascinare la voce di menu al nuovo percorso e rilasciare il pulsante sinistro del mouse.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>Per spostare una voce di menu in un altro menu  
  
1.  Fare clic sulla voce di menu che si desidera spostare e premere CTRL + X, oppure fare doppio clic la voce di menu e scegliere **Taglia** dal menu di scelta rapida.  
  
2.  Fare clic sul menu di scelta che conterrà la voce di menu che si taglia.  
  
3.  Fare clic sulla voce di menu che precede la nuova posizione e premere CTRL + V oppure fare clic sulla voce di menu che precede la nuova posizione e selezionare **Incolla** dal menu di scelta rapida.  
  
     La voce di menu che si taglia viene inserita dopo la voce di menu selezionata.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)

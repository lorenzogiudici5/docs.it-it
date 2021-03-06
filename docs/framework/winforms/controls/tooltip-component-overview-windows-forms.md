---
title: Cenni preliminari sul componente ToolTip (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: e31bb1169eeedd85a92e3bf96318623696020f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535538"
---
# <a name="tooltip-component-overview-windows-forms"></a>Cenni preliminari sul componente ToolTip (Windows Form)
Il componente <xref:System.Windows.Forms.ToolTip> di Windows Form visualizza un testo quando l'utente posiziona il puntatore sui controlli. Una descrizione comando può essere associata a qualsiasi controllo. Un esempio di questo componente: per risparmiare spazio in un form, è possibile visualizzare una piccola icona su un pulsante e utilizzare una descrizione comando per illustrare la funzione del pulsante.  
  
## <a name="working-with-the-tooltip-component"></a>Utilizzo del componente ToolTip  
 Oggetto <xref:System.Windows.Forms.ToolTip> componente fornisce un `ToolTip` proprietà a più controlli in un Windows Form o un altro contenitore. Ad esempio, se si inserisce uno <xref:System.Windows.Forms.ToolTip> componente in un form, è possibile visualizzare il testo "Digitare qui il nome" per un <xref:System.Windows.Forms.TextBox> controllare e "Fare clic qui per salvare le modifiche" per un <xref:System.Windows.Forms.Button> controllo.  
  
 I metodi principali del <xref:System.Windows.Forms.ToolTip> componente sono <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> e <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. È possibile utilizzare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> per impostare le descrizioni comandi visualizzate per i controlli. Per ulteriori informazioni, vedere [procedura: impostare le descrizioni di comandi per i controlli in un Windows Form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Le proprietà principali sono <xref:System.Windows.Forms.ToolTip.Active%2A>, che deve essere impostata su `true` per la descrizione comando viene visualizzata, e <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, che imposta il periodo di tempo che la stringa di descrizione comandi, quanto tempo l'utente deve fare riferimento al controllo per la descrizione comando viene visualizzata e come tempo accetta per finestre di descrizione comando successive. Per ulteriori informazioni, vedere [procedura: modificare il ritardo del componente ToolTip di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolTip>  
 [Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [Procedura: Modifica del ritardo del componente ToolTip di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)

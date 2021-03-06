---
title: 'Procedura: inserire controlli in celle del controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 29ffcc205d8175551aee5184cf44306fa5d3b5a0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799814"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a>Procedura: inserire controlli in celle del controllo DataGridView di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> fornisce diversi tipi di colonna, consentendo agli utenti di immettere e modificare i valori in modi differenti. Tuttavia, se questi tipi di colonna non soddisfano le esigenze di immissione di dati, è possibile creare tipi di colonna personalizzati con celle che contengono i controlli desiderati. A questo scopo è necessario definire classi derivanti dalle classi <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewCell>. È anche necessario definire una classe che derivi dalla classe <xref:System.Windows.Forms.Control> e implementi l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>.  
  
 Nell'esempio di codice seguente viene illustrato come creare una colonna di calendario. Le celle di questa colonna visualizzano le date in normali celle di caselle di testo, ma quanto l'utente modifica una cella, viene visualizzato un controllo <xref:System.Windows.Forms.DateTimePicker>. Per evitare di dover implementare di nuovo la funzionalità di visualizzazione delle caselle di testo, la classe `CalendarCell` deriva dalla classe <xref:System.Windows.Forms.DataGridViewTextBoxCell> invece di ereditare direttamente la classe <xref:System.Windows.Forms.DataGridViewCell>.  
  
> [!NOTE]
>  Quando si deriva dalla classe <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> e si aggiungono nuove proprietà alla classe derivata, accertarsi di eseguire l'override del metodo `Clone` per copiare le nuove proprietà durante le operazioni di clonazione. È anche necessario chiamare il metodo `Clone` della classe base in modo che le proprietà della classe base vengano copiate nella nuova cella o colonna.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per l'esempio seguente sono necessari i requisiti seguenti:  
  
-   Riferimenti agli assembly System e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.DateTimePicker>  
 [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Architettura del controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Tipi di colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)

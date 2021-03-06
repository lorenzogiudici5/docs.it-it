---
title: 'Procedura: impostare il testo visualizzato da un controllo di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: d9c9bea26cfc3d5b2cfc4484173a7680ff2fc34d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525035"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Procedura: impostare il testo visualizzato da un controllo di Windows Form
I controlli Windows Form in genere visualizzano il testo relativo alla funzione principale del controllo. Un controllo <xref:System.Windows.Forms.Button>, ad esempio, solitamente visualizza una didascalia indicante l'azione che verrà eseguita quando si sceglie il pulsante. Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>. È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>. È anche possibile impostare il testo nella finestra di progettazione.  Vedere anche [come: creare l'accesso delle chiavi per Windows Form controlli usando la finestra di progettazione](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [procedura: impostare il testo visualizzato da un controllo Form di Windows usando la finestra di progettazione](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [come: impostare l'immagine Visualizzato da un Windows Form mediante la finestra di progettazione](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>Per impostare il testo visualizzato da un controllo a livello di codice  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.  
  
     Per creare un tasto di scelta sottolineato, includere una e commerciale (&) prima della lettera che corrisponderà al tasto di scelta.  
  
2.  Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu. Nella riga di codice seguente, ad esempio, il testo della voce di menu viene impostato in modo che appaia come "& Now For Something Completely Different":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [Procedura: Creare tasti di scelta per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)

---
title: 'Procedura: aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: b4131504e5c5d7f2075c72c72b98153c783000d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527417"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>Procedura: aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)
È possibile creare un nodo derivato in un Windows Form <xref:System.Windows.Forms.TreeView> controllo o un elemento derivato in una <xref:System.Windows.Forms.ListView> controllo. La derivazione consente di aggiungere eventuali campi necessari, nonché metodi personalizzati e costruttori per gestirli. Un utilizzo di questa funzionalità consiste nel collegare un oggetto Customer a ogni nodo di una struttura ad albero o voce di elenco. Negli esempi seguenti sono per un <xref:System.Windows.Forms.TreeView> il controllo, ma lo stesso approccio può essere utilizzato per un <xref:System.Windows.Forms.ListView> controllo.  
  
### <a name="to-derive-a-tree-node"></a>Per derivare un nodo della struttura ad albero  
  
-   Creare una nuova classe di nodo, derivata dal <xref:System.Windows.Forms.TreeNode> (classe), che presenta un campo personalizzato per registrare un percorso di file.  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a>Per usare un nodo di struttura ad albero derivato  
  
1.  È possibile usare il nuovo nodo della struttura ad albero derivato come parametro per le chiamate di funzione.  
  
     Nell'esempio seguente il percorso impostato per la posizione del file di testo è la cartella Documenti. Si procede in questo modo perché si presume che la maggior parte dei computer con il sistema operativo Windows avrà questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2.  Se è stato passato il nodo dell'albero e viene indicato come un <xref:System.Windows.Forms.TreeNode> classe, sarà necessario eseguire il cast di una classe derivata. Il cast è una conversione esplicita da un tipo di oggetto a un altro. Per ulteriori informazioni sul cast, vedere [conversioni implicite ed esplicite](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [() Operator](~/docs/csharp/language-reference/operators/invocation-operator.md) (Visual c#) o [operatore Cast: ()](/cpp/cpp/cast-operator-parens) ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]).  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)

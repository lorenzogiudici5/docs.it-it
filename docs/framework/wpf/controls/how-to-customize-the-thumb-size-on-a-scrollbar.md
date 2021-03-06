---
title: 'Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 689b73eb58cdfceb2ce5d4e76cbbc3d6c5af8967
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento
In questo argomento viene illustrato come impostare il <xref:System.Windows.Controls.Primitives.Thumb> di un <xref:System.Windows.Controls.Primitives.ScrollBar> a una dimensione fissa e come specificare la dimensione minima per il <xref:System.Windows.Controls.Primitives.Thumb> di un <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Primitives.ScrollBar> che ha un <xref:System.Windows.Controls.Primitives.Thumb> con dimensioni fisse. Nell'esempio viene impostata la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> proprietà del <xref:System.Windows.Controls.Primitives.Thumb> a <xref:System.Double.NaN> e imposta l'altezza del <xref:System.Windows.Controls.Primitives.Thumb>.  Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> che ha una larghezza fissa, impostare la larghezza del <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## <a name="code"></a>Codice  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Descrizione  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Primitives.ScrollBar> che ha un <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione minima. Nell'esempio viene impostato il valore di <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>. Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> con una larghezza minima, impostare il <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## <a name="code"></a>Codice  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Stili e modelli di ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)

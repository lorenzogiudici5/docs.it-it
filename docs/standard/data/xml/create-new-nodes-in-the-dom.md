---
title: Creazione di nuovi nodi nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 390ffa1dd9f2e76372b0e4fcbf2916918b64d748
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260097"
---
# <a name="create-new-nodes-in-the-dom"></a>Creazione di nuovi nodi nel DOM
Il tipo <xref:System.Xml.XmlDocument> dispone di un metodo di creazione per tutti i tipi di nodo. Per creare il nodo, è sufficiente fornire al metodo un nome, se necessario, e un contenuto o altri parametri per i nodi che hanno un contenuto, ad esempio un nodo di tipo text. I metodi seguenti necessitano di un nome e di pochi altri parametri per creare un nodo appropriato.  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 Per altri tipi di nodi è necessario fornire più informazioni dei soli dati per i parametri.  
  
 Per informazioni sugli attributi, vedere [Creazione di nuovi attributi per gli elementi nel DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md). Per informazioni sulla convalida dei nomi di elementi e attributi, vedere [Verifica dei nomi di attributi ed elementi XML durante la creazione di nuovi nodi](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md). Per creare riferimenti alle entità, vedere [Creazione di nuovi riferimenti alle entità](../../../../docs/standard/data/xml/creating-new-entity-references.md). Per informazioni su come gli spazi dei nomi incidono sull'espansione dei riferimenti alle entità, vedere [Effetto degli spazi dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).  
  
 Una volta creati i nuovi nodi, sono disponibili vari metodi per inserirli nell'albero. Nella seguente tabella sono elencati i metodi con una descrizione del punto in cui il nodo viene visualizzato nel DOM XML.  
  
|Metodo|Posizione del nodo|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|Inserito prima del nodo di riferimento. Ad esempio, per inserire il nuovo nodo ad esempio nella posizione 5:<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.InsertBefore%2A>.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|Inserito dopo il nodo di riferimento. Ad esempio:<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.InsertAfter%2A>.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|Il nodo viene aggiunto alla fine dell'elenco di nodi figlio per il nodo specificato. Se il nodo aggiunto è un <xref:System.Xml.XmlDocumentFragment>, l'intero contenuto del frammento del documento viene spostato nell'elenco figlio di questo nodo. Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.AppendChild%2A>.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|Il nodo viene aggiunto all'inizio dell'elenco di nodi figlio per il nodo specificato. Se il nodo aggiunto è un <xref:System.Xml.XmlDocumentFragment>, l'intero contenuto del frammento del documento viene spostato nell'elenco figlio di questo nodo. Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.PrependChild%2A>.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|Il nodo <xref:System.Xml.XmlAttribute> viene aggiunto alla fine della raccolta di attributi associata all'elemento. Per altre informazioni, vedere il metodo <xref:System.Xml.XmlAttributeCollection.Append%2A>.|  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

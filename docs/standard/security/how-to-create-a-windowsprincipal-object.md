---
title: 'Procedura: creare un oggetto WindowsPrincipal'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET Framework], creating a WindowsPrincipal object
- security [.NET Framework], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 016f19c7141ebaf9b5c1f03adc263b689489119b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198036"
---
# <a name="how-to-create-a-windowsprincipal-object"></a>Procedura: creare un oggetto WindowsPrincipal
Vi sono due metodi per creare un oggetto <xref:System.Security.Principal.WindowsPrincipal>, a seconda che il codice debba eseguire ripetutamente la convalida basata sui ruoli o solo una alla volta.  
  
 Se è necessario che il codice esegua ripetutamente la convalida basata sui ruoli, la prima delle procedure riportate di seguito implica un minor sovraccarico. Quando è necessario che il codice esegua convalide basate sui ruoli solo una volta, è possibile creare un oggetto <xref:System.Security.Principal.WindowsPrincipal> usando la seconda delle seguenti procedure.  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a>Per creare un oggetto WindowsPrincipal per una convalida ripetuta  
  
1.  Chiamare il metodo <xref:System.AppDomain.SetPrincipalPolicy%2A> sull'oggetto <xref:System.AppDomain> restituito dalla proprietà statica <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType>, passando il metodo a un valore di enumerazione <xref:System.Security.Principal.PrincipalPolicy> che indica quale dovrebbero essere i nuovi criteri. I valori supportati sono <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> e <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>. Il codice seguente illustra questa chiamata al metodo.  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2.  Con i criteri impostati usare la proprietà statica <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> per richiamare l'entità che incapsula l'utente Windows corrente. Poiché il tipo restituito della proprietà è <xref:System.Security.Principal.IPrincipal>, si deve eseguire il cast del risultato a un tipo <xref:System.Security.Principal.WindowsPrincipal>. Il codice seguente inizializza un nuovo oggetto <xref:System.Security.Principal.WindowsPrincipal> al valore dell'entità associata con il thread corrente.  
  
    ```csharp  
    WindowsPrincipal MyPrincipal =   
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim MyPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)   
    ```  
  
3.  Quando l'oggetto Principal è stato creato, è possibile usare uno dei diversi metodi per convalidarlo.  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a>Per creare un oggetto WindowsPrincipal per una singola convalida  
  
1.  Inizializzare un nuovo oggetto <xref:System.Security.Principal.WindowsIdentity> chiamando il metodo statico <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType>, che sottopone a query l'account Windows corrente e inserisce le informazioni relative all'account in un oggetto Identity appena creato. Il codice seguente crea un nuovo oggetto <xref:System.Security.Principal.WindowsIdentity> e lo inizializza per l'utente autenticato corrente.  
  
    ```csharp  
    WindowsIdentity MyIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim MyIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2.  Creare un nuovo oggetto <xref:System.Security.Principal.WindowsPrincipal> e passargli il valore dell'oggetto <xref:System.Security.Principal.WindowsIdentity> creato nel passaggio precedente.  
  
    ```csharp  
    WindowsPrincipal MyPrincipal = new WindowsPrincipal(MyIdentity);  
    ```  
  
    ```vb  
    Dim MyPrincipal As New WindowsPrincipal(MyIdentity)  
    ```  
  
3.  Quando l'oggetto Principal è stato creato, è possibile usare uno dei diversi metodi per convalidarlo.  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md)

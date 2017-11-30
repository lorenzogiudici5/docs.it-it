---
title: 'Eccezioni: funzione failwith (F#)'
description: 'Informazioni su come la funzione ''failwith'' genera un''eccezione F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2e0c1f28-cc6c-4ecd-bb93-3816c4dd7cd3
ms.openlocfilehash: 295a4d754e0df015ba67daa9cf80d7df5b40199c
ms.sourcegitcommit: ffb9aa26cd5211dc6d96ebb42968d8357048880e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2017
---
# <a name="exceptions-the-failwith-function"></a><span data-ttu-id="47993-104">Eccezioni: funzione failwith</span><span class="sxs-lookup"><span data-stu-id="47993-104">Exceptions: The failwith Function</span></span>

<span data-ttu-id="47993-105">Il `failwith` funzione genera un'eccezione F #.</span><span class="sxs-lookup"><span data-stu-id="47993-105">The `failwith` function generates an F# exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="47993-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47993-106">Syntax</span></span>

```fsharp
failwith error-message-string
```

## <a name="remarks"></a><span data-ttu-id="47993-107">Note</span><span class="sxs-lookup"><span data-stu-id="47993-107">Remarks</span></span>
<span data-ttu-id="47993-108">Il *stringa di messaggio di errore* nella sintassi precedente è una stringa letterale o un valore di tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="47993-108">The *error-message-string* in the previous syntax is a literal string or a value of type `string`.</span></span> <span data-ttu-id="47993-109">Diventa il `Message` proprietà dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="47993-109">It becomes the `Message` property of the exception.</span></span>

<span data-ttu-id="47993-110">L'eccezione generata da `failwith` è un `System.Exception` eccezione, che è un riferimento con il nome `Failure` nel codice F #.</span><span class="sxs-lookup"><span data-stu-id="47993-110">The exception that is generated by `failwith` is a `System.Exception` exception, which is a reference that has the name `Failure` in F# code.</span></span> <span data-ttu-id="47993-111">Il codice seguente viene illustrato l'utilizzo di `failwith` per generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="47993-111">The following code illustrates the use of `failwith` to throw an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a><span data-ttu-id="47993-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47993-112">See Also</span></span>
[<span data-ttu-id="47993-113">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="47993-113">Exception Handling</span></span>](index.md)

[<span data-ttu-id="47993-114">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="47993-114">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="47993-115">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="47993-115">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="47993-116">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="47993-116">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="47993-117">Eccezioni: funzione `raise`</span><span class="sxs-lookup"><span data-stu-id="47993-117">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
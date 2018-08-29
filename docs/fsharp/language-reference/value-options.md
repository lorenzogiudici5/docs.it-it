---
title: 'Opzioni di valori (F #)'
description: 'Informazioni sul tipo di opzione valore F #, vale a dire una versione di uno struct del tipo di opzione.'
ms.date: 06/16/2018
ms.openlocfilehash: 4c255cbbcfd9cb480230de09cd370a401c87343a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936571"
---
# <a name="value-options"></a><span data-ttu-id="fbd78-103">Opzioni di valori</span><span class="sxs-lookup"><span data-stu-id="fbd78-103">Value Options</span></span>

<span data-ttu-id="fbd78-104">Il tipo di valore opzione in F # viene usato quando contengono due situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbd78-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="fbd78-105">Uno scenario è appropriato per un [F # opzione](options.md).</span><span class="sxs-lookup"><span data-stu-id="fbd78-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="fbd78-106">Usando un tipo struct offre un miglioramento delle prestazioni nel proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="fbd78-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="fbd78-107">Non tutti gli scenari sensibili alle prestazioni sono "risolto" utilizzo di struct.</span><span class="sxs-lookup"><span data-stu-id="fbd78-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="fbd78-108">È necessario considerare il costo aggiuntivo di copia quando vengono utilizzati invece i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="fbd78-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="fbd78-109">Tuttavia, grande programmi F # comunemente creare un'istanza di molti tipi facoltativi che passano attraverso i percorsi critici, poiché gli struct in alcuni casi possono produrre migliore prestazioni complessive in base alla durata di un programma.</span><span class="sxs-lookup"><span data-stu-id="fbd78-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, because structs can sometimes yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="fbd78-110">Definizione</span><span class="sxs-lookup"><span data-stu-id="fbd78-110">Definition</span></span>

<span data-ttu-id="fbd78-111">Opzione valore viene definito come un [unione discriminata di struct](discriminated-unions.md#struct-discriminated-unions) che è simile al tipo di opzione di riferimento:</span><span class="sxs-lookup"><span data-stu-id="fbd78-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpValueOption`1")>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone: 'T voption
    | ValueSome: 'T -> 'T voption

    member Value : 'T

and 'T voption = ValueOption<'T>
```

<span data-ttu-id="fbd78-112">Opzione valore conforme a confronto e uguaglianza strutturale.</span><span class="sxs-lookup"><span data-stu-id="fbd78-112">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="fbd78-113">La differenza principale è che il nome compilato, nome del tipo e tutti i nomi dei casi a indicare che si tratta di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="fbd78-113">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="fbd78-114">Utilizzo delle opzioni di valore</span><span class="sxs-lookup"><span data-stu-id="fbd78-114">Using Value Options</span></span>

<span data-ttu-id="fbd78-115">Opzioni di valore vengono utilizzate allo stesso modo [opzioni](options.md).</span><span class="sxs-lookup"><span data-stu-id="fbd78-115">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="fbd78-116">`ValueSome` viene utilizzato per indicare che un valore è presente, e `ValueNone` viene usato quando non è presente un valore:</span><span class="sxs-lookup"><span data-stu-id="fbd78-116">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="fbd78-117">Come per gli [le opzioni](options.md), la convenzione di denominazione per una funzione che restituisce `ValueOption` consiste nel prefisso `try`.</span><span class="sxs-lookup"><span data-stu-id="fbd78-117">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="fbd78-118">Valore opzione proprietà e metodi</span><span class="sxs-lookup"><span data-stu-id="fbd78-118">Value Option properties and methods</span></span>

<span data-ttu-id="fbd78-119">Al momento non è una proprietà per le opzioni di valore: `Value`.</span><span class="sxs-lookup"><span data-stu-id="fbd78-119">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="fbd78-120">Un <xref:System.InvalidOperationException> viene generata se nessun valore è presente quando viene richiamata questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbd78-120">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="fbd78-121">Funzioni con valori di opzione</span><span class="sxs-lookup"><span data-stu-id="fbd78-121">Value Option functions</span></span>

<span data-ttu-id="fbd78-122">È attualmente disponibile una funzione associata al modulo per le opzioni di valore, `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="fbd78-122">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="fbd78-123">Come con la `defaultArg` funzione, `defaultValueArg` restituisce il valore sottostante dell'opzione di valore specificato se presente; in caso contrario, restituisce il valore predefinito specificato.</span><span class="sxs-lookup"><span data-stu-id="fbd78-123">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="fbd78-124">In questo momento, non sono presenti altre funzioni associata al modulo per le opzioni di valore.</span><span class="sxs-lookup"><span data-stu-id="fbd78-124">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbd78-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd78-125">See also</span></span>

[<span data-ttu-id="fbd78-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fbd78-126">Options</span></span>](options.md)
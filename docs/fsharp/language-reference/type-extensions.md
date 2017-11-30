---
title: Estensioni di tipo (F#)
description: 'Informazioni su come estensioni di tipo F # consentono che aggiungere nuovi membri a un tipo di oggetto definita in precedenza.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c9d7ce27-f5ad-4766-b9e9-34187da5bc24
ms.openlocfilehash: f78f8689e95fc1547f1a2b17c615592c00051f7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-extensions"></a><span data-ttu-id="2af4f-104">Estensioni di tipo</span><span class="sxs-lookup"><span data-stu-id="2af4f-104">Type Extensions</span></span>

<span data-ttu-id="2af4f-105">Le estensioni di tipo consentono di aggiungere nuovi membri a un tipo di oggetto definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2af4f-105">Type extensions let you add new members to a previously defined object type.</span></span>

## <a name="syntax"></a><span data-ttu-id="2af4f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2af4f-106">Syntax</span></span>

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a><span data-ttu-id="2af4f-107">Note</span><span class="sxs-lookup"><span data-stu-id="2af4f-107">Remarks</span></span>
<span data-ttu-id="2af4f-108">Esistono due tipi di estensioni di tipo che presentano comportamenti e sintassi leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="2af4f-108">There are two forms of type extensions that have slightly different syntax and behavior.</span></span> <span data-ttu-id="2af4f-109">Un *estensione intrinseca* è un'estensione che viene visualizzata nello stesso spazio dei nomi o modulo, nello stesso file di origine e nello stesso assembly (DLL o file eseguibile) del tipo esteso.</span><span class="sxs-lookup"><span data-stu-id="2af4f-109">An *intrinsic extension* is an extension that appears in the same namespace or module, in the same source file, and in the same assembly (DLL or executable file) as the type being extended.</span></span> <span data-ttu-id="2af4f-110">Un *estensione facoltativa* è un'estensione che viene visualizzata all'esterno dello spazio dei nomi, modulo o assembly del tipo esteso originale.</span><span class="sxs-lookup"><span data-stu-id="2af4f-110">An *optional extension* is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span> <span data-ttu-id="2af4f-111">Le estensioni intrinseche appaiono sul tipo quando il tipo viene esaminato tramite reflection, ma non le estensioni facoltative.</span><span class="sxs-lookup"><span data-stu-id="2af4f-111">Intrinsic extensions appear on the type when the type is examined by reflection, but optional extensions do not.</span></span> <span data-ttu-id="2af4f-112">Le estensioni facoltative devono trovarsi nei moduli e sono solo nell'ambito quando il modulo che contiene l'estensione è aperto.</span><span class="sxs-lookup"><span data-stu-id="2af4f-112">Optional extensions must be in modules, and they are only in scope when the module that contains the extension is open.</span></span>

<span data-ttu-id="2af4f-113">Nella sintassi precedente, *typename* rappresenta il tipo da estendere.</span><span class="sxs-lookup"><span data-stu-id="2af4f-113">In the previous syntax, *typename* represents the type that is being extended.</span></span> <span data-ttu-id="2af4f-114">È possibile estendere qualsiasi tipo che è possibile accedere, ma il nome del tipo deve essere un nome di tipo effettivo, non è un'abbreviazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="2af4f-114">Any type that can be accessed can be extended, but the type name must be an actual type name, not a type abbreviation.</span></span> <span data-ttu-id="2af4f-115">È possibile definire più membri in un'estensione del tipo.</span><span class="sxs-lookup"><span data-stu-id="2af4f-115">You can define multiple members in one type extension.</span></span> <span data-ttu-id="2af4f-116">Il *autoidentificatore* rappresenta l'istanza dell'oggetto, come membri ordinari in cui viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="2af4f-116">The *self-identifier* represents the instance of the object being invoked, just as in ordinary members.</span></span>

<span data-ttu-id="2af4f-117">Il `end` parola chiave è facoltativa nella sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="2af4f-117">The `end` keyword is optional in lightweight syntax.</span></span>

<span data-ttu-id="2af4f-118">Membri definiti nelle estensioni di tipo possono essere utilizzati come gli altri membri in un tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="2af4f-118">Members defined in type extensions can be used just like other members on a class type.</span></span> <span data-ttu-id="2af4f-119">Analogamente agli altri membri, possono essere statici o membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="2af4f-119">Like other members, they can be static or instance members.</span></span> <span data-ttu-id="2af4f-120">Questi metodi sono noti anche come *metodi di estensione*; proprietà sono note come *le proprietà di estensione*e così via.</span><span class="sxs-lookup"><span data-stu-id="2af4f-120">These methods are also known as *extension methods*; properties are known as *extension properties*, and so on.</span></span> <span data-ttu-id="2af4f-121">Membri di estensione facoltative vengono compilati per i membri statici per il quale l'istanza dell'oggetto viene passata in modo implicito come primo parametro.</span><span class="sxs-lookup"><span data-stu-id="2af4f-121">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="2af4f-122">Tuttavia, funzionano come se fossero membri di istanza o i membri statici in base alla modalità di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-122">However, they act as if they were instance members or static members according to how they are declared.</span></span> <span data-ttu-id="2af4f-123">I membri impliciti delle estensioni sono inclusi come membri del tipo e possono essere utilizzati senza alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-123">Implicit extension members are included as members of the type and can be used without restriction.</span></span>

<span data-ttu-id="2af4f-124">Metodi di estensione non possono essere metodi virtuali o astratti.</span><span class="sxs-lookup"><span data-stu-id="2af4f-124">Extension methods cannot be virtual or abstract methods.</span></span> <span data-ttu-id="2af4f-125">È possibile eseguire l'overload di altri metodi con lo stesso nome, ma il compilatore assegna la priorità per i metodi di estensione nel caso di una chiamata ambigua.</span><span class="sxs-lookup"><span data-stu-id="2af4f-125">They can overload other methods of the same name, but the compiler gives preference to non-extension methods in the case of an ambiguous call.</span></span>

<span data-ttu-id="2af4f-126">In presenza di più estensioni di tipo intrinseco per un tipo, tutti i membri devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="2af4f-126">If multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="2af4f-127">Per le estensioni di tipo facoltativi, i membri di diverse estensioni di tipo nello stesso tipo possono avere gli stessi nomi.</span><span class="sxs-lookup"><span data-stu-id="2af4f-127">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="2af4f-128">Solo se il codice client apre due ambiti diversi che definiscono gli stessi nomi di membro, si verificano errori di ambiguità.</span><span class="sxs-lookup"><span data-stu-id="2af4f-128">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

<span data-ttu-id="2af4f-129">Nell'esempio seguente, un tipo in un modulo ha un'estensione di tipo intrinseco.</span><span class="sxs-lookup"><span data-stu-id="2af4f-129">In the following example, a type in a module has an intrinsic type extension.</span></span> <span data-ttu-id="2af4f-130">Al codice client di fuori del modulo, l'estensione del tipo viene visualizzato come un membro regolare del tipo per tutti gli aspetti.</span><span class="sxs-lookup"><span data-stu-id="2af4f-130">To client code outside the module, the type extension appears as a regular member of the type in all respects.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

<span data-ttu-id="2af4f-131">È possibile utilizzare le estensioni di tipo intrinseco di separare la definizione di un tipo in sezioni.</span><span class="sxs-lookup"><span data-stu-id="2af4f-131">You can use intrinsic type extensions to separate the definition of a type into sections.</span></span> <span data-ttu-id="2af4f-132">Può essere utile nella gestione delle definizioni di tipi di grandi dimensioni, ad esempio, per separare generato dal compilatore di codice e codice creato o per raggruppare il codice creato da persone diverse o associata a una funzionalità diversa.</span><span class="sxs-lookup"><span data-stu-id="2af4f-132">This can be useful in managing large type definitions, for example, to keep compiler-generated code and authored code separate or to group together code created by different people or associated with different functionality.</span></span>

<span data-ttu-id="2af4f-133">Nell'esempio seguente, un'estensione di tipo facoltativi estende il `System.Int32` tipo con un metodo di estensione `FromString` che chiama il membro statico `Parse`.</span><span class="sxs-lookup"><span data-stu-id="2af4f-133">In the following example, an optional type extension extends the `System.Int32` type with an extension method `FromString` that calls the static member `Parse`.</span></span> <span data-ttu-id="2af4f-134">Il `testFromString` metodo dimostra che il nuovo membro viene chiamato come qualsiasi membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="2af4f-134">The `testFromString` method demonstrates that the new member is called just like any instance member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

<span data-ttu-id="2af4f-135">Verrà visualizzato il nuovo membro di istanza come qualsiasi altro metodo del `Int32` tipo IntelliSense, ma solo quando il modulo che contiene l'estensione è aperto o in caso contrario nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="2af4f-135">The new instance member will appear like any other method of the `Int32` type in IntelliSense, but only when the module that contains the extension is open or otherwise in scope.</span></span>

## <a name="generic-extension-methods"></a><span data-ttu-id="2af4f-136">Metodi di estensione generico</span><span class="sxs-lookup"><span data-stu-id="2af4f-136">Generic Extension Methods</span></span>
<span data-ttu-id="2af4f-137">Prima di F # 3.1, il compilatore F # non supporta l'uso di c#-metodi di estensione con una variabile di tipo generico, tipo di matrice, il tipo di tupla o un tipo di funzione F # come "this" parametro di stile.</span><span class="sxs-lookup"><span data-stu-id="2af4f-137">Before F# 3.1, the F# compiler didn't support the use of C#-style extension methods with a generic type variable, array type, tuple type, or an F# function type as the "this" parameter.</span></span> <span data-ttu-id="2af4f-138">3.1 F # supporta l'utilizzo di questi membri di estensione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-138">F# 3.1 supports the use of these extension members.</span></span>

<span data-ttu-id="2af4f-139">Nel codice F # 3.1, ad esempio, è possibile utilizzare i metodi di estensione con firme che sono simili alla sintassi seguente in c#:</span><span class="sxs-lookup"><span data-stu-id="2af4f-139">For example, in F# 3.1 code, you can use extension methods with signatures that resemble the following syntax in C#:</span></span>

```csharp
static member Method<T>(this T input, T other)
```

<span data-ttu-id="2af4f-140">Questo approccio è particolarmente utile quando il parametro di tipo generico è vincolato.</span><span class="sxs-lookup"><span data-stu-id="2af4f-140">This approach is particularly useful when the generic type parameter is constrained.</span></span> <span data-ttu-id="2af4f-141">Inoltre, è possibile dichiarare i membri di estensione simile al seguente nel codice F # e definire un set aggiuntivi e semanticamente complesse di metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-141">Further, you can now declare extension members like this in F# code and define an additional, semantically rich set of extension methods.</span></span> <span data-ttu-id="2af4f-142">In F #, in genere è necessario definire i membri di estensione come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2af4f-142">In F#, you usually define extension members as the following example shows:</span></span>

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

<span data-ttu-id="2af4f-143">Tuttavia, per un tipo generico, la variabile di tipo potrebbe non essere vincolata.</span><span class="sxs-lookup"><span data-stu-id="2af4f-143">However, for a generic type, the type variable may not be constrained.</span></span> <span data-ttu-id="2af4f-144">Sarà quindi possibile dichiarare c#-membro di estensione di stile in F # per aggirare questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-144">You can now declare a C#-style extension member in F# to work around this limitation.</span></span> <span data-ttu-id="2af4f-145">Quando si combina questo tipo di dichiarazione con la funzionalità di inline di F #, è possibile presentare algoritmi generici come membri di estensione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-145">When you combine this kind of declaration with the inline feature of F#, you can present generic algorithms as extension members.</span></span>

<span data-ttu-id="2af4f-146">Si consideri la seguente dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="2af4f-146">Consider the following declaration:</span></span>

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="2af4f-147">Tramite questa dichiarazione, è possibile scrivere codice simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="2af4f-147">By using this declaration, you can write code that resembles the following sample.</span></span>

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

<span data-ttu-id="2af4f-148">In questo codice, lo stesso codice generico di aritmetico applicato agli elenchi di due tipi senza l'overload, definendo un membro unica estensione.</span><span class="sxs-lookup"><span data-stu-id="2af4f-148">In this code, the same generic arithmetic code is applied to lists of two types without overloading, by defining a single extension member.</span></span>


## <a name="see-also"></a><span data-ttu-id="2af4f-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2af4f-149">See Also</span></span>
[<span data-ttu-id="2af4f-150">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="2af4f-150">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="2af4f-151">Membri</span><span class="sxs-lookup"><span data-stu-id="2af4f-151">Members</span></span>](members/index.md)
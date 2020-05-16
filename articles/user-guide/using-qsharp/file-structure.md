---
title: 'Struktura souborů Q #'
description: 'Popisuje strukturu a syntaxi souboru Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430964"
---
# <a name="q-file-structure"></a><span data-ttu-id="d1870-103">Struktura souborů Q #</span><span class="sxs-lookup"><span data-stu-id="d1870-103">Q# File Structure</span></span>

<span data-ttu-id="d1870-104">Každá operace Q #, funkce a uživatelsky definovaný typ je definována v rámci oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="d1870-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="d1870-105">Soubor Q # se skládá z sekvence *deklarací oboru názvů*.</span><span class="sxs-lookup"><span data-stu-id="d1870-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="d1870-106">Každá deklarace oboru názvů obsahuje deklarace pro uživatelsky definované typy, operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="d1870-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="d1870-107">Deklarace oboru názvů může obsahovat libovolný počet každého typu deklarace a v libovolném pořadí.</span><span class="sxs-lookup"><span data-stu-id="d1870-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="d1870-108">Pomocí těchto odkazů můžete zobrazit další podrobnosti o deklaraci [uživatelsky definovaných typů](xref:microsoft.quantum.guide.types#user-defined-types), [operací](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)a [funkcí](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) v rámci oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="d1870-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="d1870-109">Jediný text, který se může zobrazit mimo deklaraci oboru názvů, je komentáře.</span><span class="sxs-lookup"><span data-stu-id="d1870-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="d1870-110">Konkrétně dokumentační komentáře (další podrobnosti níže) pro obor názvů předchází deklaraci.</span><span class="sxs-lookup"><span data-stu-id="d1870-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="d1870-111">Deklarace oboru názvů</span><span class="sxs-lookup"><span data-stu-id="d1870-111">Namespace Declarations</span></span>

<span data-ttu-id="d1870-112">Soubor Q # má obvykle přesně jednu deklaraci oboru názvů, ale může mít hodnotu None (a být prázdný nebo obsahovat pouze komentáře) nebo může obsahovat více oborů názvů.</span><span class="sxs-lookup"><span data-stu-id="d1870-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="d1870-113">Deklarace oboru názvů nesmí být vnořené.</span><span class="sxs-lookup"><span data-stu-id="d1870-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="d1870-114">Stejný obor názvů může být deklarován ve více souborech Q #, které jsou kompilovány společně, pokud neexistují deklarace typu, operace nebo funkce se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="d1870-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="d1870-115">Konkrétně je neplatný pro definování stejného typu ve stejném oboru názvů ve více souborech, a to i v případě, že deklarace jsou identické.</span><span class="sxs-lookup"><span data-stu-id="d1870-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="d1870-116">Deklarace oboru názvů se skládá z klíčového slova `namespace` , za kterým následuje název oboru názvů, levou složenou závorku `{` , deklarace obsažená v oboru názvů a uzavírací závorka `}` .</span><span class="sxs-lookup"><span data-stu-id="d1870-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="d1870-117">Názvy oborů názvů následují podle vzoru .NET sekvence jednoho nebo více přípustných symbolů oddělených tečkami `.` .</span><span class="sxs-lookup"><span data-stu-id="d1870-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="d1870-118">Například `MyQuantumStuff` a `Microsoft.Quantum.Intrinsic` jsou platné názvy oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="d1870-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="d1870-119">Podle konvence jsou symboly v názvu oboru názvů velkými písmeny, ale to není vyžadováno.</span><span class="sxs-lookup"><span data-stu-id="d1870-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="d1870-120">Odkazy na typy nebo volat deklarované níže v souboru jsou správně vyřešeny. není nutné, aby deklarace typu, operace nebo funkce předcházely odkaz na ni.</span><span class="sxs-lookup"><span data-stu-id="d1870-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="d1870-121">Otevřít direktivy</span><span class="sxs-lookup"><span data-stu-id="d1870-121">Open Directives</span></span>

<span data-ttu-id="d1870-122">V rámci bloku oboru názvů `open` lze direktivu použít k importu všech typů a volání deklarovaných v určitém oboru názvů a jejich odkazování podle jejich nekvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="d1870-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="d1870-123">Taková `open` direktiva se skládá z `open` klíčového slova, za nímž následuje obor názvů, který se má otevřít a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="d1870-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="d1870-124">Všechny `open` direktivy musí být uvedeny před všemi `function` `operation` `newtype` deklaracemi, nebo v bloku Namespace.</span><span class="sxs-lookup"><span data-stu-id="d1870-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="d1870-125">Volitelně může být definován krátký název pro otevřený obor názvů tak, aby všechny elementy z tohoto oboru názvů mohly (a musí) být kvalifikovány definovaným krátkým názvem.</span><span class="sxs-lookup"><span data-stu-id="d1870-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="d1870-126">Například s ohledem na následující deklaraci oboru názvů a direktivy Open,</span><span class="sxs-lookup"><span data-stu-id="d1870-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="d1870-127">Pokud operace, kterou deklarujeme, používá operaci `Op` z `Microsoft.Quantum.Intrinsic` , budeme ji volat jednoduše pomocí `Op` .</span><span class="sxs-lookup"><span data-stu-id="d1870-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="d1870-128">Nicméně, pokud jsme chtěli zavolat určitou funkci `Fn` z `Microsoft.Quantum.Math` , museli byste ji volat pomocí `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="d1870-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="d1870-129">`open`Direktiva se vztahuje na celý blok oboru názvů v rámci souboru.</span><span class="sxs-lookup"><span data-stu-id="d1870-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="d1870-130">Proto pokud jsme museli definovat další obor názvů ve stejném souboru Q # jako v `NS` předchozím kroku, pak všechny operace, funkce/typy definované v druhém oboru názvů nebudou mít přístup k cokoli z `Microsoft.Quantum.Intrinsic` nebo `Microsoft.Quantum.Math` , pokud jsme neopakovali otevřené direktivy Open v rámci.</span><span class="sxs-lookup"><span data-stu-id="d1870-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="d1870-131">Typ nebo volat, který je definován v jiném oboru názvů, *který není otevřen* v aktuálním oboru názvů, musí být odkazován pomocí jeho plně kvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="d1870-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="d1870-132">Například operace s názvem `Op` z `X.Y` oboru názvů musí být odkazována pomocí plně kvalifikovaného názvu `X.Y.Op` , pokud `X.Y` obor názvů nebyl otevřen dříve v aktuálním bloku.</span><span class="sxs-lookup"><span data-stu-id="d1870-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="d1870-133">Jak je uvedeno výše, i když byl `X` obor názvů otevřen, není možné odkazovat na operaci jako `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="d1870-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="d1870-134">Pokud byl `Z` `X.Y` v tomto oboru názvů a souboru definován krátký název, `Op` musí být odkazován jako `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="d1870-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="d1870-135">Je obvykle lepší zahrnout obor názvů pomocí `open` direktivy.</span><span class="sxs-lookup"><span data-stu-id="d1870-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="d1870-136">Použití plně kvalifikovaného názvu je vyžadováno, pokud dva obory názvů definují konstrukce se stejným názvem a aktuální zdroj používá konstrukce z obou.</span><span class="sxs-lookup"><span data-stu-id="d1870-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="d1870-137">Q # se řídí stejnými pravidly pro pojmenování jako jiné jazyky .NET.</span><span class="sxs-lookup"><span data-stu-id="d1870-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="d1870-138">Q # ale nepodporuje relativní odkazy na obory názvů.</span><span class="sxs-lookup"><span data-stu-id="d1870-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="d1870-139">To znamená, že pokud byl obor názvů `a.b` otevřen, odkaz na operaci s názvem `c.d` nebude přeložen *not* na operaci s úplným názvem `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="d1870-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="d1870-140">Formátování</span><span class="sxs-lookup"><span data-stu-id="d1870-140">Formatting</span></span>

<span data-ttu-id="d1870-141">Většina příkazů Q # a direktiv končí zakončeným středníkem, `;` .</span><span class="sxs-lookup"><span data-stu-id="d1870-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="d1870-142">Příkazy a deklarace, jako například `for` a `operation` , které končí blokem příkazu (viz níže), nevyžadují ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="d1870-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="d1870-143">Každý Popis příkazu Poznamenejte, zda je nutný ukončovací středník.</span><span class="sxs-lookup"><span data-stu-id="d1870-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="d1870-144">Příkazy, jako jsou výrazy, deklarace a direktivy, mohou být rozděleny na více řádků.</span><span class="sxs-lookup"><span data-stu-id="d1870-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="d1870-145">Je třeba zabránit více příkazům na jednom řádku.</span><span class="sxs-lookup"><span data-stu-id="d1870-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="d1870-146">Bloky příkazů</span><span class="sxs-lookup"><span data-stu-id="d1870-146">Statement Blocks</span></span>

<span data-ttu-id="d1870-147">Příkazy Q # jsou seskupeny do bloků příkazů.</span><span class="sxs-lookup"><span data-stu-id="d1870-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="d1870-148">Blok příkazu začíná levou `{` a ukončenou uzávěrkou `}` .</span><span class="sxs-lookup"><span data-stu-id="d1870-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="d1870-149">Blok příkazu, který je vložený v jiném bloku, se považuje za dílčí blok obsahujícího bloku. obsahující a dílčí bloky se označují také jako vnější a vnitřní bloky.</span><span class="sxs-lookup"><span data-stu-id="d1870-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="d1870-150">Komentáře</span><span class="sxs-lookup"><span data-stu-id="d1870-150">Comments</span></span>

<span data-ttu-id="d1870-151">Komentáře začínají dvěma lomítky, `//` a pokračují až do konce řádku.</span><span class="sxs-lookup"><span data-stu-id="d1870-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="d1870-152">Komentář se může objevit kdekoli ve zdrojovém souboru Q #.</span><span class="sxs-lookup"><span data-stu-id="d1870-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="d1870-153">Komentáře dokumentace</span><span class="sxs-lookup"><span data-stu-id="d1870-153">Documentation Comments</span></span>

<span data-ttu-id="d1870-154">Komentáře, které začínají třemi lomítky, `///` , jsou zpracovány speciálně kompilátorem, když se objeví bezprostředně před definicí oboru názvů, operace, specializace, funkce nebo typu.</span><span class="sxs-lookup"><span data-stu-id="d1870-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="d1870-155">V takovém případě je jejich obsah považován za dokumentaci pro definovaný typ s možnou podporou nebo uživatelem, jako u jiných jazyků .NET.</span><span class="sxs-lookup"><span data-stu-id="d1870-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="d1870-156">V rámci `///` komentářů se text, který se má zobrazit jako součást dokumentace k rozhraní API, formátuje jako [Markdownu](https://daringfireball.net/projects/markdown/syntax), s různými částmi dokumentace, které jsou označeny pomocí hlaviček se speciálně jmenovanými.</span><span class="sxs-lookup"><span data-stu-id="d1870-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="d1870-157">V rámci rozšíření na Markdownu mohou být křížové odkazy na operace, funkce a uživatelsky definované typy v Q # zahrnuty pomocí `@"<ref target>"` , kde `<ref target>` je nahrazen plně kvalifikovaným názvem odkazovaného objektu kódu.</span><span class="sxs-lookup"><span data-stu-id="d1870-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="d1870-158">V případě potřeby může také modul dokumentace podporovat další rozšíření Markdownu.</span><span class="sxs-lookup"><span data-stu-id="d1870-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="d1870-159">Příklad:</span><span class="sxs-lookup"><span data-stu-id="d1870-159">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="d1870-160">Následující názvy se rozpoznávají jako hlavičky komentářů k dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="d1870-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="d1870-161">**Summary**: stručný souhrn chování funkce nebo operace nebo účelu typu.</span><span class="sxs-lookup"><span data-stu-id="d1870-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="d1870-162">První odstavec souhrnu se používá pro informace o přechodu myší.</span><span class="sxs-lookup"><span data-stu-id="d1870-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="d1870-163">Měl by být prostý text.</span><span class="sxs-lookup"><span data-stu-id="d1870-163">It should be plain text.</span></span>
- <span data-ttu-id="d1870-164">**Popis**: Popis chování funkce nebo operace nebo účelu typu.</span><span class="sxs-lookup"><span data-stu-id="d1870-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="d1870-165">Souhrn a popis jsou zřetězeny, aby tvořily vygenerovaný soubor dokumentace pro funkci, operaci nebo typ.</span><span class="sxs-lookup"><span data-stu-id="d1870-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="d1870-166">Popis může obsahovat symboly a rovnice ve formátu LaTeX v řádcích.</span><span class="sxs-lookup"><span data-stu-id="d1870-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="d1870-167">**Input**: Popis vstupní řazené kolekce členů pro operaci nebo funkci.</span><span class="sxs-lookup"><span data-stu-id="d1870-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="d1870-168">Může obsahovat další pododdíly Markdownu označující jednotlivé prvky vstupní řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="d1870-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="d1870-169">**Výstup**: Popis řazené kolekce členů vrácený operací nebo funkcí.</span><span class="sxs-lookup"><span data-stu-id="d1870-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="d1870-170">**Parametry typu**: prázdný oddíl, který obsahuje jeden další pododdíl pro každý parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="d1870-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="d1870-171">**Příklad**: krátký příklad operace, funkce nebo typu se používá.</span><span class="sxs-lookup"><span data-stu-id="d1870-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="d1870-172">**Poznámky**: různé prose popisující nějaký aspekt operace, funkce nebo typu.</span><span class="sxs-lookup"><span data-stu-id="d1870-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="d1870-173">**Viz také**: seznam plně kvalifikovaných názvů, které označují související funkce, operace nebo uživatelsky definované typy.</span><span class="sxs-lookup"><span data-stu-id="d1870-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="d1870-174">**Odkazy**: seznam odkazů a citace pro položku, která je popsána.</span><span class="sxs-lookup"><span data-stu-id="d1870-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="whats-next"></a><span data-ttu-id="d1870-175">A co dál?</span><span class="sxs-lookup"><span data-stu-id="d1870-175">What's Next?</span></span>
<span data-ttu-id="d1870-176">Přečtěte si o [operacích a funkcích](xref:microsoft.quantum.guide.operationsfunctions) v Q #.</span><span class="sxs-lookup"><span data-stu-id="d1870-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>
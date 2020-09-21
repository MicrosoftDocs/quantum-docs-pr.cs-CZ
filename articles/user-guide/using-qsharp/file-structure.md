---
title: Q# Struktura souborů
description: Popisuje strukturu a syntaxi Q# souboru.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833302"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="8aa94-103">Q# Struktura souborů</span><span class="sxs-lookup"><span data-stu-id="8aa94-103">Q# File Structure</span></span>

<span data-ttu-id="8aa94-104">Q#Soubor se skládá z sekvence *deklarací oboru názvů*.</span><span class="sxs-lookup"><span data-stu-id="8aa94-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="8aa94-105">Každá deklarace oboru názvů obsahuje deklarace pro uživatelsky definované typy, operace a funkce a může obsahovat libovolný počet každého typu deklarace a v libovolném pořadí.</span><span class="sxs-lookup"><span data-stu-id="8aa94-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="8aa94-106">Další informace o deklaracích v rámci oboru názvů najdete v tématu [uživatelsky definované typy](xref:microsoft.quantum.guide.types#user-defined-types), [operace](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)a [funkce](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span><span class="sxs-lookup"><span data-stu-id="8aa94-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="8aa94-107">Jediný text, který se může zobrazit mimo deklaraci oboru názvů, je komentáře.</span><span class="sxs-lookup"><span data-stu-id="8aa94-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="8aa94-108">Konkrétně dokumentační komentáře pro obor názvů předcházejí deklaraci.</span><span class="sxs-lookup"><span data-stu-id="8aa94-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="8aa94-109">Další informace najdete v [dokumentačních komentářích](#documentation-comments) v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="8aa94-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="8aa94-110">Deklarace oboru názvů</span><span class="sxs-lookup"><span data-stu-id="8aa94-110">Namespace Declarations</span></span>

<span data-ttu-id="8aa94-111">Q#Soubor obvykle obsahuje pouze jednu deklaraci oboru názvů, ale může mít hodnotu None (a být prázdný nebo obsahovat pouze komentáře) nebo může obsahovat více oborů názvů.</span><span class="sxs-lookup"><span data-stu-id="8aa94-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="8aa94-112">Deklarace oboru názvů nelze vnořovat.</span><span class="sxs-lookup"><span data-stu-id="8aa94-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="8aa94-113">Můžete deklarovat stejný obor názvů ve více Q# souborech, které jsou kompilovány společně, pokud neexistují deklarace typu, operace nebo funkce se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="8aa94-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="8aa94-114">Konkrétně je neplatný pro definování stejného typu ve stejném oboru názvů ve více souborech, a to i v případě, že deklarace jsou identické.</span><span class="sxs-lookup"><span data-stu-id="8aa94-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="8aa94-115">Deklarace oboru názvů se skládá z klíčového slova `namespace` , následovaný názvem oboru názvů a deklaracemi obsaženými v oboru názvů uzavřenými ve složených závorkách `{ }` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="8aa94-116">Názvy oborů názvů následují podle vzoru .NET sekvence jednoho nebo více přípustných symbolů oddělených tečkami `.` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="8aa94-117">Například `MyQuantumStuff` a `Microsoft.Quantum.Intrinsic` jsou platné názvy oborů názvů.</span><span class="sxs-lookup"><span data-stu-id="8aa94-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="8aa94-118">Podle konvence na velká písmena v názvu oboru názvů to ale není potřeba.</span><span class="sxs-lookup"><span data-stu-id="8aa94-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="8aa94-119">Odkazy na typy nebo volat deklarované níže v souboru jsou správně přeloženy; není nutné, aby deklarace typu, operace nebo funkce předcházely odkaz na ni.</span><span class="sxs-lookup"><span data-stu-id="8aa94-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="8aa94-120">Otevřít direktivy</span><span class="sxs-lookup"><span data-stu-id="8aa94-120">Open Directives</span></span>

<span data-ttu-id="8aa94-121">V rámci bloku oboru názvů použijte `open` direktivu pro import všech typů a volání deklarované v určitém oboru názvů a odkazujte na ně podle jejich nekvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="8aa94-122">Taková `open` direktiva se skládá z `open` klíčového slova, za nímž následuje obor názvů, který se má otevřít a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="8aa94-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="8aa94-123">Všechny `open` direktivy musí být uvedeny před všemi `function` `operation` `newtype` deklaracemi, nebo v bloku Namespace.</span><span class="sxs-lookup"><span data-stu-id="8aa94-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="8aa94-124">Volitelně můžete definovat krátký název pro otevřený obor názvů.</span><span class="sxs-lookup"><span data-stu-id="8aa94-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="8aa94-125">Pokud je definován krátký název, je nutné kvalifikovat všechny prvky z oboru názvů pomocí definovaného krátkého názvu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="8aa94-126">Například s ohledem na následující deklaraci oboru názvů a direktivy Open,</span><span class="sxs-lookup"><span data-stu-id="8aa94-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="8aa94-127">Pokud deklarovaná operace používá operaci `Op` z `Microsoft.Quantum.Intrinsic` , zavolejte ji jednoduše pomocí `Op` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="8aa94-128">Chcete-li však volat určitou funkci `Fn` z `Microsoft.Quantum.Math` , je nutné ji volat pomocí `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="8aa94-129">`open`Direktiva se vztahuje na celý blok oboru názvů v rámci souboru.</span><span class="sxs-lookup"><span data-stu-id="8aa94-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="8aa94-130">Proto pokud definujete další obor názvů ve stejném Q# souboru jako `NS` dříve, pak všechny operace, funkce/typy definované v druhém oboru názvů nebudou mít přístup k cokoli z `Microsoft.Quantum.Intrinsic` nebo, `Microsoft.Quantum.Math` Pokud jste neopakovali direktivy Open v rámci.</span><span class="sxs-lookup"><span data-stu-id="8aa94-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="8aa94-131">Chcete-li odkazovat na typ nebo volat, který je definován v jiném oboru názvů, *který není otevřen* v aktuálním oboru názvů, je nutné na něj odkazovat pomocí plně kvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="8aa94-132">Například s ohledem na operaci s názvem `Op` z `X.Y` oboru názvů:</span><span class="sxs-lookup"><span data-stu-id="8aa94-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="8aa94-133">Je nutné na něj odkazovat pomocí plně kvalifikovaného názvu `X.Y.Op` , pokud `X.Y` obor názvů nebyl otevřen dříve v aktuálním bloku.</span><span class="sxs-lookup"><span data-stu-id="8aa94-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="8aa94-134">I v případě `X` , že je obor názvů otevřený, není možné odkazovat na operaci jako `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="8aa94-135">Pokud jste definovali krátký název `Z` `X.Y` v tomto oboru názvů a souboru, musíte odkazovat na `Op` `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="8aa94-136">Je obvykle lepší zahrnout obor názvů pomocí `open` direktivy.</span><span class="sxs-lookup"><span data-stu-id="8aa94-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="8aa94-137">Použití plně kvalifikovaného názvu je vyžadováno, pokud dva obory názvů definují konstrukce se stejným názvem a aktuální zdroj používá konstrukce z obou.</span><span class="sxs-lookup"><span data-stu-id="8aa94-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="8aa94-138">Q# řídí se stejnými pravidly pro pojmenování jako jiné jazyky .NET.</span><span class="sxs-lookup"><span data-stu-id="8aa94-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="8aa94-139">Nicméně nepodporuje Q# relativní odkazy na obory názvů.</span><span class="sxs-lookup"><span data-stu-id="8aa94-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="8aa94-140">Například pokud je obor názvů `a.b` otevřený, odkaz na operaci s názvem se `c.d` nevyřeší na *not* operaci s úplným názvem `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="8aa94-141">Formátování</span><span class="sxs-lookup"><span data-stu-id="8aa94-141">Formatting</span></span>

<span data-ttu-id="8aa94-142">Většina Q# příkazů a direktiv končí zakončeným středníkem, `;` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="8aa94-143">Příkazy a deklarace, jako například `for` a `operation` , které končí blokem příkazu (viz následující oddíl), nevyžadují ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="8aa94-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="8aa94-144">Každý Popis příkazu Poznamenejte, zda je nutný ukončovací středník.</span><span class="sxs-lookup"><span data-stu-id="8aa94-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="8aa94-145">Příkazy, jako jsou výrazy, deklarace a direktivy, mohou být rozděleny na více řádků.</span><span class="sxs-lookup"><span data-stu-id="8aa94-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="8aa94-146">Vyhněte se vložení více příkazů na jeden řádek.</span><span class="sxs-lookup"><span data-stu-id="8aa94-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="8aa94-147">Bloky příkazů</span><span class="sxs-lookup"><span data-stu-id="8aa94-147">Statement Blocks</span></span>

<span data-ttu-id="8aa94-148">Q# příkazy jsou seskupeny do bloků příkazů, které jsou obsaženy ve složených závorkách `{ }` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="8aa94-149">Blok příkazu začíná levou `{` a ukončenou uzávěrkou `}` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="8aa94-150">Blok příkazu, který je vložený v jiném bloku, se považuje za dílčí blok obsahujícího bloku. obsahující a dílčí bloky se označují také jako vnější a vnitřní bloky.</span><span class="sxs-lookup"><span data-stu-id="8aa94-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="8aa94-151">Komentáře</span><span class="sxs-lookup"><span data-stu-id="8aa94-151">Comments</span></span>

<span data-ttu-id="8aa94-152">Komentáře začínají dvěma lomítky, `//` a pokračují až do konce řádku.</span><span class="sxs-lookup"><span data-stu-id="8aa94-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="8aa94-153">Komentář se může objevit kdekoli ve Q# zdrojovém souboru.</span><span class="sxs-lookup"><span data-stu-id="8aa94-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="8aa94-154">Komentáře dokumentace</span><span class="sxs-lookup"><span data-stu-id="8aa94-154">Documentation Comments</span></span>

<span data-ttu-id="8aa94-155">Komentáře, které začínají třemi lomítky, `///` , jsou zpracovány speciálně kompilátorem, když se objeví bezprostředně před definicí oboru názvů, operace, specializace, funkce nebo typu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="8aa94-156">V takovém případě ho kompilátor považuje za dokumentaci pro definovaný typ, který je k nebo uživatelsky definovaný, stejně jako ostatní jazyky .NET.</span><span class="sxs-lookup"><span data-stu-id="8aa94-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="8aa94-157">V rámci `///` komentářů se text, který se má zobrazit jako součást dokumentace k rozhraní API, formátuje jako [Markdownu](https://daringfireball.net/projects/markdown/syntax), s různými částmi dokumentace, které jsou označeny pomocí hlaviček se speciálně jmenovanými.</span><span class="sxs-lookup"><span data-stu-id="8aa94-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="8aa94-158">V Markdownu použijte `@"<ref target>"` rozšíření pro operace křížového odkazu, funkce a uživatelsky definované typy v Q# .</span><span class="sxs-lookup"><span data-stu-id="8aa94-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="8aa94-159">Nahraďte `<ref target>` plně kvalifikovaným názvem odkazovaného objektu kódu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="8aa94-160">Různé moduly dokumentace můžou podporovat i další rozšíření Markdownu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="8aa94-161">Příklad:</span><span class="sxs-lookup"><span data-stu-id="8aa94-161">For example:</span></span>

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

<span data-ttu-id="8aa94-162">Následující názvy jsou platné jako hlavičky komentáře k dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="8aa94-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="8aa94-163">**Summary**: stručný souhrn chování funkce nebo operace nebo účelu typu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="8aa94-164">První odstavec souhrnu se používá pro informace o přechodu myší.</span><span class="sxs-lookup"><span data-stu-id="8aa94-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="8aa94-165">Měl by být prostý text.</span><span class="sxs-lookup"><span data-stu-id="8aa94-165">It should be plain text.</span></span>
- <span data-ttu-id="8aa94-166">**Popis**: Popis chování funkce nebo operace nebo účelu typu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="8aa94-167">Souhrn a popis společně tvoří vygenerovaný soubor dokumentace pro funkci, operaci nebo typ.</span><span class="sxs-lookup"><span data-stu-id="8aa94-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="8aa94-168">Popis podporuje vložené symboly a rovnice ve formátu LaTeX.</span><span class="sxs-lookup"><span data-stu-id="8aa94-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="8aa94-169">**Input**: Popis vstupní řazené kolekce členů pro operaci nebo funkci.</span><span class="sxs-lookup"><span data-stu-id="8aa94-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="8aa94-170">Může obsahovat další pododdíly Markdownu označující jednotlivé prvky vstupní řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8aa94-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="8aa94-171">**Výstup**: Popis řazené kolekce členů vrácený operací nebo funkcí.</span><span class="sxs-lookup"><span data-stu-id="8aa94-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="8aa94-172">**Parametry typu**: prázdný oddíl, který obsahuje jeden další pododdíl pro každý parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="8aa94-173">**Příklad**: krátký příklad operace, funkce nebo typu, který se používá.</span><span class="sxs-lookup"><span data-stu-id="8aa94-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="8aa94-174">**Poznámky**: různé prose popisující nějaký aspekt operace, funkce nebo typu.</span><span class="sxs-lookup"><span data-stu-id="8aa94-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="8aa94-175">**Viz také**: seznam plně kvalifikovaných názvů, které označují související funkce, operace nebo uživatelsky definované typy.</span><span class="sxs-lookup"><span data-stu-id="8aa94-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="8aa94-176">**Odkazy**: seznam odkazů a citace pro popsanou položku.</span><span class="sxs-lookup"><span data-stu-id="8aa94-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8aa94-177">Další kroky</span><span class="sxs-lookup"><span data-stu-id="8aa94-177">Next steps</span></span>

<span data-ttu-id="8aa94-178">Přečtěte si o [operacích a funkcích](xref:microsoft.quantum.guide.operationsfunctions) v Q# .</span><span class="sxs-lookup"><span data-stu-id="8aa94-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>
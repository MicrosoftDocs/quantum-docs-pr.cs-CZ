---
title: 'Příkazy Q # | Microsoft Docs'
description: 'Příkazy Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9a6f5d53ec21090d0c13f4369e0270d264cd1e9b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036487"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="7b91e-103">Příkazy a další konstrukce</span><span class="sxs-lookup"><span data-stu-id="7b91e-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="7b91e-104">Komentáře</span><span class="sxs-lookup"><span data-stu-id="7b91e-104">Comments</span></span>

<span data-ttu-id="7b91e-105">Komentáře začínají dvěma lomítky, `//`a pokračují až do konce řádku.</span><span class="sxs-lookup"><span data-stu-id="7b91e-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="7b91e-106">Komentář se může objevit kdekoli ve zdrojovém souboru Q #.</span><span class="sxs-lookup"><span data-stu-id="7b91e-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="7b91e-107">Dokumentační komentáře</span><span class="sxs-lookup"><span data-stu-id="7b91e-107">Documentation Comments</span></span>

<span data-ttu-id="7b91e-108">Komentáře, které začínají třemi lomítky, `///`, jsou zpracovány speciálně kompilátorem, když se objeví bezprostředně před oborem názvů, operací, specializací, funkcí nebo definicí typu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="7b91e-109">V takovém případě je jejich obsah považován za dokumentaci pro definovaný typ s možnou podporou nebo uživatelem, jako u jiných jazyků .NET.</span><span class="sxs-lookup"><span data-stu-id="7b91e-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="7b91e-110">V rámci `///` komentáře je text, který se zobrazí jako součást dokumentace k rozhraní API, formátován jako [Markdownu](https://daringfireball.net/projects/markdown/syntax), s různými částmi dokumentace, které jsou označeny pomocí hlaviček se speciálně jmenovanými.</span><span class="sxs-lookup"><span data-stu-id="7b91e-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="7b91e-111">Jako rozšíření pro Markdownu mohou být křížové odkazy na operace, funkce a uživatelsky definované typy v Q # zahrnuty pomocí `@"<ref target>"`, kde `<ref target>` je nahrazen plně kvalifikovaným názvem odkazovaného objektu kódu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="7b91e-112">V případě potřeby může také modul dokumentace podporovat další rozšíření Markdownu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="7b91e-113">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-113">For example:</span></span>

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

<span data-ttu-id="7b91e-114">Následující názvy se rozpoznávají jako hlavičky komentářů k dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="7b91e-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="7b91e-115">**Summary**: stručný souhrn chování funkce nebo operace nebo účelu typu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="7b91e-116">První odstavec souhrnu se používá pro informace o přechodu myší.</span><span class="sxs-lookup"><span data-stu-id="7b91e-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="7b91e-117">Měl by být prostý text.</span><span class="sxs-lookup"><span data-stu-id="7b91e-117">It should be plain text.</span></span>
- <span data-ttu-id="7b91e-118">**Popis**: Popis chování funkce nebo operace nebo účelu typu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="7b91e-119">Souhrn a popis jsou zřetězeny, aby tvořily vygenerovaný soubor dokumentace pro funkci, operaci nebo typ.</span><span class="sxs-lookup"><span data-stu-id="7b91e-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="7b91e-120">Popis může obsahovat symboly a rovnice ve formátu LaTeX v řádcích.</span><span class="sxs-lookup"><span data-stu-id="7b91e-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="7b91e-121">**Input**: Popis vstupní řazené kolekce členů pro operaci nebo funkci.</span><span class="sxs-lookup"><span data-stu-id="7b91e-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="7b91e-122">Může obsahovat další pododdíly Markdownu označující jednotlivé prvky vstupní řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="7b91e-123">**Výstup**: Popis řazené kolekce členů vrácený operací nebo funkcí.</span><span class="sxs-lookup"><span data-stu-id="7b91e-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="7b91e-124">**Parametry typu**: prázdný oddíl, který obsahuje jeden další pododdíl pro každý parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="7b91e-125">**Příklad**: krátký příklad operace, funkce nebo typu se používá.</span><span class="sxs-lookup"><span data-stu-id="7b91e-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="7b91e-126">**Poznámky**: různé prose popisující nějaký aspekt operace, funkce nebo typu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="7b91e-127">**Viz také**: seznam plně kvalifikovaných názvů, které označují související funkce, operace nebo uživatelsky definované typy.</span><span class="sxs-lookup"><span data-stu-id="7b91e-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="7b91e-128">**Odkazy**: seznam odkazů a citace pro položku, která je popsána.</span><span class="sxs-lookup"><span data-stu-id="7b91e-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="7b91e-129">Obory názvů</span><span class="sxs-lookup"><span data-stu-id="7b91e-129">Namespaces</span></span>

<span data-ttu-id="7b91e-130">Každá operace Q #, funkce a uživatelsky definovaný typ je definována v rámci oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="7b91e-131">Q # se řídí stejnými pravidly pro pojmenování jako jiné jazyky .NET.</span><span class="sxs-lookup"><span data-stu-id="7b91e-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="7b91e-132">Q # ale nepodporuje relativní odkazy na obory názvů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="7b91e-133">To znamená, že pokud byl obor názvů `a.b` otevřen, odkaz na název operace `c.d` nebude přeložen na operaci s úplným názvem `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="7b91e-134">V rámci bloku oboru názvů lze pomocí direktivy `open` importovat všechny typy a volat deklarované v určitém oboru názvů a odkazovat na ně podle jejich nekvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="7b91e-135">Volitelně může být definován krátký název pro otevřený obor názvů tak, aby všechny elementy z tohoto oboru názvů mohly (a musí) být kvalifikovány definovaným krátkým názvem.</span><span class="sxs-lookup"><span data-stu-id="7b91e-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="7b91e-136">Direktiva `open` se vztahuje na celý blok oboru názvů v rámci souboru.</span><span class="sxs-lookup"><span data-stu-id="7b91e-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="7b91e-137">Typ nebo volat, který je definován v jiném oboru názvů, který není otevřen v aktuálním oboru názvů, musí být odkazován pomocí jeho plně kvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="7b91e-138">Například operace s názvem `Op` v oboru názvů `X.Y` musí být odkazována pomocí plně kvalifikovaného názvu `X.Y.Op`, pokud obor názvů `X.Y` nebyl otevřen dříve v aktuálním bloku.</span><span class="sxs-lookup"><span data-stu-id="7b91e-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="7b91e-139">Jak je uvedeno výše, i když byl otevřen obor názvů `X`, není možné odkazovat na operaci jako `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="7b91e-140">Pokud byl v tomto oboru názvů a souboru definován krátký název `Z` pro `X.Y`, `Op` musí být odkazována jako `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="7b91e-141">Je obvykle lepší zahrnout obor názvů pomocí direktivy `open`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="7b91e-142">Použití plně kvalifikovaného názvu je vyžadováno, pokud dva obory názvů definují konstrukce se stejným názvem a aktuální zdroj používá konstrukce z obou.</span><span class="sxs-lookup"><span data-stu-id="7b91e-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="7b91e-143">Formátování</span><span class="sxs-lookup"><span data-stu-id="7b91e-143">Formatting</span></span>

<span data-ttu-id="7b91e-144">Většina příkazů Q # a direktiv končí zakončeným středníkem, `;`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="7b91e-145">Příkazy a deklarace, jako `for` a `operation`, které končí blokem příkazu, nevyžadují ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="7b91e-146">Každý Popis příkazu Poznamenejte, zda je nutný ukončovací středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="7b91e-147">Příkazy, jako jsou výrazy, deklarace a direktivy, mohou být rozděleny na více řádků.</span><span class="sxs-lookup"><span data-stu-id="7b91e-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="7b91e-148">Je třeba zabránit více příkazům na jednom řádku.</span><span class="sxs-lookup"><span data-stu-id="7b91e-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="7b91e-149">Bloky příkazů</span><span class="sxs-lookup"><span data-stu-id="7b91e-149">Statement Blocks</span></span>

<span data-ttu-id="7b91e-150">Příkazy Q # jsou seskupeny do bloků příkazů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="7b91e-151">Blok příkazu začíná levou `{` a končí uzavíracím `}`em.</span><span class="sxs-lookup"><span data-stu-id="7b91e-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="7b91e-152">Blok příkazu, který je vložený v jiném bloku, se považuje za dílčí blok obsahujícího bloku. obsahující a dílčí bloky se označují také jako vnější a vnitřní bloky.</span><span class="sxs-lookup"><span data-stu-id="7b91e-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="7b91e-153">Vazba symbolů a přiřazení</span><span class="sxs-lookup"><span data-stu-id="7b91e-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="7b91e-154">Q # rozlišuje proměnlivé a neproměnlivé symboly.</span><span class="sxs-lookup"><span data-stu-id="7b91e-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="7b91e-155">Obecně platí, že použití neměnných symbolů je doporučováno, protože umožňuje kompilátoru provádět větší optimalizace.</span><span class="sxs-lookup"><span data-stu-id="7b91e-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="7b91e-156">Levá strana vazby se skládá ze symbolů řazené kolekce členů a pravé strany výrazu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="7b91e-157">Vzhledem k tomu, že všechny typy Q # jsou typy hodnot – s qubits, které pobírají trochu speciální roli, je vytvořena, když je hodnota vázána na symbol nebo když je symbol převázán.</span><span class="sxs-lookup"><span data-stu-id="7b91e-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="7b91e-158">To znamená, že chování Q # je stejné jako při vytvoření kopie při přiřazení.</span><span class="sxs-lookup"><span data-stu-id="7b91e-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="7b91e-159">Konkrétně to zahrnuje také pole.</span><span class="sxs-lookup"><span data-stu-id="7b91e-159">This in particular also includes arrays.</span></span> <span data-ttu-id="7b91e-160">Samozřejmě v praxi jsou ve skutečnosti v případě potřeby znovu vytvořeny pouze relevantní součásti.</span><span class="sxs-lookup"><span data-stu-id="7b91e-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="7b91e-161">Dekonstrukce řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="7b91e-161">Tuple Deconstruction</span></span>

<span data-ttu-id="7b91e-162">Pokud je pravá strana vazby řazená kolekce členů, pak je možné po přiřazení dekonstruovat tuto řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="7b91e-163">Tato dekonstrukce může zahrnovat vnořené řazené kolekce členů a jakákoli úplná nebo částečná dekonstrukce je platná, pokud je tvar řazené kolekce členů na pravé straně kompatibilní s obrazcem řazené kolekce členů symbolů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="7b91e-164">Dekonstrukci řazené kolekce členů se dá použít taky v případě, že je pravá strana `=` výraz vracející řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="7b91e-165">Neměnné symboly</span><span class="sxs-lookup"><span data-stu-id="7b91e-165">Immutable Symbols</span></span>

<span data-ttu-id="7b91e-166">Neměnné symboly jsou vázány pomocí příkazu `let`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="7b91e-167">To zhruba odpovídá deklaraci proměnné a inicializaci v jazycích, jako C#například, s výjimkou toho, že po svázání se symboly Q # nedají změnit; vazby `let` jsou neměnné.</span><span class="sxs-lookup"><span data-stu-id="7b91e-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="7b91e-168">Neproměnlivá vazba se skládá z klíčového slova `let`následovaný symbolem nebo řazenou kolekcí členů symbolu, znak rovná se `=`, výrazu, na který se symboly mají svázat, a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="7b91e-169">Typ vázaných symbolů je odvozený na základě výrazu na pravé straně.</span><span class="sxs-lookup"><span data-stu-id="7b91e-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="7b91e-170">Proměnlivé symboly</span><span class="sxs-lookup"><span data-stu-id="7b91e-170">Mutable Symbols</span></span>

<span data-ttu-id="7b91e-171">Proměnlivé symboly jsou definovány a inicializovány pomocí příkazu `mutable`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="7b91e-172">Symboly deklarované a svázané jako součást příkazu `mutable` mohou být později v kódu převázány na jinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="7b91e-173">Proměnlivý výraz vazby se skládá z klíčového slova `mutable`následovaný symbolem nebo řazenou kolekcí členů symbolu, znak rovná se `=`, výrazu, na který se symboly mají svázat, a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="7b91e-174">Typ vázaných symbolů je odvozený na základě výrazu na pravé straně.</span><span class="sxs-lookup"><span data-stu-id="7b91e-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="7b91e-175">Pokud je symbol znovu svázán později v kódu, jeho typ se nemění a vázaná hodnota musí být kompatibilní s tímto typem.</span><span class="sxs-lookup"><span data-stu-id="7b91e-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="7b91e-176">Obnovení vazby proměnlivých symbolů</span><span class="sxs-lookup"><span data-stu-id="7b91e-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="7b91e-177">Proměnlivou proměnnou lze znovu svázat pomocí příkazu `set`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="7b91e-178">Taková revazba se skládá z klíčového slova `set`následovaný symbolem nebo řazenou kolekcí členů symbolu, znaménkem rovná se `=`, výrazu pro zpětný vazbu symbolů na a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="7b91e-179">Hodnota musí být kompatibilní s typy (y) symbolů, ke kterým je vázáno.</span><span class="sxs-lookup"><span data-stu-id="7b91e-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="7b91e-180">Příkaz Apply a Reassign</span><span class="sxs-lookup"><span data-stu-id="7b91e-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="7b91e-181">Konkrétní druh příkazu set-Statement, který označujeme jako příkaz Apply a Reassign, poskytuje pohodlný způsob zřetězení, pokud se pravá strana skládá z aplikace binárního operátoru a výsledek je převázán na levý argument operátoru.</span><span class="sxs-lookup"><span data-stu-id="7b91e-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="7b91e-182">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="7b91e-183">zvýší hodnotu čítače `counter` v každé iteraci `for` smyčky.</span><span class="sxs-lookup"><span data-stu-id="7b91e-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="7b91e-184">Výše uvedený kód je stejný jako</span><span class="sxs-lookup"><span data-stu-id="7b91e-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="7b91e-185">Podobné příkazy jsou k dispozici pro všechny binární operátory, ve kterých typ levé strany odpovídá typu výrazu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="7b91e-186">To poskytuje například pohodlný způsob, jak shromáždit hodnoty:</span><span class="sxs-lookup"><span data-stu-id="7b91e-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="7b91e-187">Update-a-Reassign – příkaz</span><span class="sxs-lookup"><span data-stu-id="7b91e-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="7b91e-188">Pro výrazy kopírování a aktualizace na pravé straně existuje podobný zřetězení.</span><span class="sxs-lookup"><span data-stu-id="7b91e-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="7b91e-189">Odpovídající příkazy Update-a-Reassign existují pro pojmenované položky v uživatelsky definovaných typech a také pro položky pole.</span><span class="sxs-lookup"><span data-stu-id="7b91e-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="7b91e-190">V případě polí mají naše standardní knihovny k disměrnému nástroji pro řadu běžných požadavků na inicializaci a manipulaci s poli, takže se tak můžou vyhnout nutnosti aktualizovat položky pole na prvním místě.</span><span class="sxs-lookup"><span data-stu-id="7b91e-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="7b91e-191">Příkazy Update a Reassign poskytují v případě potřeby alternativu:</span><span class="sxs-lookup"><span data-stu-id="7b91e-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="7b91e-192">Vyhněte se zbytečnému použití příkazů Update a Reassign pomocí nástrojů, které jsou k dispozici v <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="7b91e-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="7b91e-193">Funkce</span><span class="sxs-lookup"><span data-stu-id="7b91e-193">The function</span></span>
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="7b91e-194">Například je možné jednoduše zjednodušit pomocí funkce `ConstantArray` v `Microsoft.Quantum.Arrays`a vrácení výrazu Copy-and-Update:</span><span class="sxs-lookup"><span data-stu-id="7b91e-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="7b91e-195">Rozsahy vazeb</span><span class="sxs-lookup"><span data-stu-id="7b91e-195">Binding Scopes</span></span>

<span data-ttu-id="7b91e-196">Obecně se vazby symbolů přestanou přecházet z oboru a stanou se nefunkčními na konci příkazu, ke kterým dojde v.</span><span class="sxs-lookup"><span data-stu-id="7b91e-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="7b91e-197">Toto pravidlo obsahuje dvě výjimky:</span><span class="sxs-lookup"><span data-stu-id="7b91e-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="7b91e-198">Vazba proměnné smyčky smyčky `for` je v rozsahu pro tělo smyčky for, ale ne za koncem smyčky.</span><span class="sxs-lookup"><span data-stu-id="7b91e-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="7b91e-199">Všechny tři části `repeat`/`until` smyčka (tělo, test a oprava) se považují za jeden obor, takže symboly, které jsou svázané s textem, jsou k dispozici v testu a v opravě.</span><span class="sxs-lookup"><span data-stu-id="7b91e-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="7b91e-200">U obou typů smyček projde smyčka ve vlastním oboru, takže vazby z dřívějšího průchodu nejsou k dispozici v pozdější fázi.</span><span class="sxs-lookup"><span data-stu-id="7b91e-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="7b91e-201">Vazby symbolů z vnějších bloků jsou děděny pomocí vnitřních bloků.</span><span class="sxs-lookup"><span data-stu-id="7b91e-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="7b91e-202">Symbol může být vázaný jenom jednou na blok; není povoleno definovat symbol se stejným názvem jako jiný symbol, který je v oboru (bez "stínování").</span><span class="sxs-lookup"><span data-stu-id="7b91e-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="7b91e-203">Následující sekvence by byly platné:</span><span class="sxs-lookup"><span data-stu-id="7b91e-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="7b91e-204">a</span><span class="sxs-lookup"><span data-stu-id="7b91e-204">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

<span data-ttu-id="7b91e-205">Ale to by bylo neplatné:</span><span class="sxs-lookup"><span data-stu-id="7b91e-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="7b91e-206">Jak by to bylo:</span><span class="sxs-lookup"><span data-stu-id="7b91e-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="7b91e-207">Tok řízení</span><span class="sxs-lookup"><span data-stu-id="7b91e-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="7b91e-208">Smyčka for</span><span class="sxs-lookup"><span data-stu-id="7b91e-208">For Loop</span></span>

<span data-ttu-id="7b91e-209">Příkaz `for` podporuje iteraci v rozsahu celého čísla nebo nad polem.</span><span class="sxs-lookup"><span data-stu-id="7b91e-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="7b91e-210">Příkaz obsahuje klíčové slovo `for`, levou závorku `(`následovaný symbolem nebo řazenou kolekcí členů, klíčové slovo `in`, výraz typu `Range` nebo Array, uzavírací závorka `)`a blok příkazu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="7b91e-211">Blok příkazu (tělo smyčky) je proveden opakovaně s definovanými symboly (proměnné smyčky) svázané s každou hodnotou v rozsahu nebo poli.</span><span class="sxs-lookup"><span data-stu-id="7b91e-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="7b91e-212">Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, text nebude proveden vůbec.</span><span class="sxs-lookup"><span data-stu-id="7b91e-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="7b91e-213">Výraz je plně vyhodnocen před vstupem do smyčky a při provádění smyčky se nemění.</span><span class="sxs-lookup"><span data-stu-id="7b91e-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="7b91e-214">Vazba deklarovaného symbolu je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných.</span><span class="sxs-lookup"><span data-stu-id="7b91e-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="7b91e-215">Konkrétně je možné destrukci například položky pole pro iteraci nad polem při přiřazení k proměnným smyčky.</span><span class="sxs-lookup"><span data-stu-id="7b91e-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="7b91e-216">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-216">For example,</span></span>

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="7b91e-217">Proměnná smyčky je svázána s každým vchodem do těla smyčky a na konci těla není svázána.</span><span class="sxs-lookup"><span data-stu-id="7b91e-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="7b91e-218">Konkrétně proměnná smyčky není svázána po dokončení smyčky for.</span><span class="sxs-lookup"><span data-stu-id="7b91e-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="7b91e-219">Opakování do smyčky po úspěšném dokončení</span><span class="sxs-lookup"><span data-stu-id="7b91e-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="7b91e-220">Příkaz `repeat` podporuje vzorek "opakovat až do úspěchu".</span><span class="sxs-lookup"><span data-stu-id="7b91e-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="7b91e-221">Skládá se z klíčového slova `repeat`následovaný blokem příkazu (tělo _smyčky_ ), klíčovým slovem `until`, logickým výrazem a buď ukončující středník, nebo klíčovým slovem `fixup` následovaným jiným blokem příkazu ( _opravou_).</span><span class="sxs-lookup"><span data-stu-id="7b91e-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="7b91e-222">Tělo smyčky, podmínka a oprava jsou považovány za jeden obor, takže symboly svázané v těle jsou k dispozici v podmínce a opravě.</span><span class="sxs-lookup"><span data-stu-id="7b91e-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

<span data-ttu-id="7b91e-223">Tělo smyčky se provede a podmínka se vyhodnotí.</span><span class="sxs-lookup"><span data-stu-id="7b91e-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="7b91e-224">Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava provede a příkaz se znovu spustí počínaje textem smyčky.</span><span class="sxs-lookup"><span data-stu-id="7b91e-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="7b91e-225">Všimněte si, že dokončení provádění opravy končí rozsahem příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou k dispozici v následných opakováních.</span><span class="sxs-lookup"><span data-stu-id="7b91e-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="7b91e-226">Například následující kód je okruh pravděpodobnostní, který implementuje důležitou bránu pro otočení $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ pomocí brány Hadamard a T.</span><span class="sxs-lookup"><span data-stu-id="7b91e-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="7b91e-227">V průměru končí smyčka v $ \frac{8}{5}$.</span><span class="sxs-lookup"><span data-stu-id="7b91e-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="7b91e-228">Podrobnosti najdete v tématu [*opakování až po úspěch: nedeterministické rozklady Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick a Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="7b91e-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="7b91e-229">Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch.</span><span class="sxs-lookup"><span data-stu-id="7b91e-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="7b91e-230">Odpovídající funkce jsou k dispozici v průběhu cyklů ve funkcích.</span><span class="sxs-lookup"><span data-stu-id="7b91e-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="7b91e-231">Smyčka while</span><span class="sxs-lookup"><span data-stu-id="7b91e-231">While Loop</span></span>

<span data-ttu-id="7b91e-232">Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="7b91e-233">Jsou běžně používány v určitých třídách algoritmů pro stav, a proto je konstrukce vyhrazeného jazyka v Q #.</span><span class="sxs-lookup"><span data-stu-id="7b91e-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="7b91e-234">Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka spuštění je tudíž neznámá v době kompilace, je nutné zpracovat zvláštní péčí v modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="7b91e-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="7b91e-235">Jejich použití v rámci funkcí na druhé straně je neproblematické, protože obsahují pouze kód, který bude spuštěn na konvenčním (nestránkovaném) hardwaru.</span><span class="sxs-lookup"><span data-stu-id="7b91e-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="7b91e-236">Q # proto podporuje použití smyčky while pouze v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="7b91e-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="7b91e-237">Příkaz `while` se skládá z `while`klíčového slova, otevřené závorky `(`, podmínky (tj. logický výraz), uzavírací závorky `)`a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="7b91e-238">Blok příkazu (tělo smyčky) je proveden, dokud je podmínka vyhodnocena jako `true`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="7b91e-239">Podmíněný příkaz</span><span class="sxs-lookup"><span data-stu-id="7b91e-239">Conditional Statement</span></span>

<span data-ttu-id="7b91e-240">Příkaz `if` podporuje podmíněné spuštění.</span><span class="sxs-lookup"><span data-stu-id="7b91e-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="7b91e-241">Skládá se z klíčového slova `if`, otevírací závorky `(`, logického výrazu, uzavírací závorky `)`a bloku příkazu (blok _then_ ).</span><span class="sxs-lookup"><span data-stu-id="7b91e-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="7b91e-242">Za tímto může následovat libovolný počet klauzulí else-if, každý z nich se skládá z klíčového slova `elif`, otevírací závorky `(`, logického výrazu, uzavírací závorky `)`a bloku příkazu (blok _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="7b91e-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="7b91e-243">Nakonec může být příkaz volitelně dokončen s klauzulí else, která se skládá z klíčového slova `else` následovaný jiným blokem příkazu (blok _Else_ ).</span><span class="sxs-lookup"><span data-stu-id="7b91e-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="7b91e-244">Podmínka je vyhodnocena a je-li nastavena na hodnotu true, je spuštěn blok po.</span><span class="sxs-lookup"><span data-stu-id="7b91e-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="7b91e-245">Pokud je podmínka NEPRAVDA, vyhodnotí se první podmínka else if; Pokud má hodnotu true, je spuštěn blok else-if.</span><span class="sxs-lookup"><span data-stu-id="7b91e-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="7b91e-246">V opačném případě se otestuje druhý blok else-if a třetí a tak dále, dokud není zjištěna buď klauzule s podmínkou true, nebo nejsou k dispozici další klauzule else-if.</span><span class="sxs-lookup"><span data-stu-id="7b91e-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="7b91e-247">Pokud je původní podmínka IF a všechny klauzule else-if vyhodnoceny jako NEPRAVDA, je spuštěn blok else, pokud byl poskytnut jeden.</span><span class="sxs-lookup"><span data-stu-id="7b91e-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="7b91e-248">Všimněte si, že libovolný blok je spuštěný ve svém vlastním oboru.</span><span class="sxs-lookup"><span data-stu-id="7b91e-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="7b91e-249">Vazby provedené uvnitř bloku then, else-if nebo else nejsou viditelné po konci příkazu if.</span><span class="sxs-lookup"><span data-stu-id="7b91e-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="7b91e-250">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="7b91e-251">nebo</span><span class="sxs-lookup"><span data-stu-id="7b91e-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="7b91e-252">Vrátit</span><span class="sxs-lookup"><span data-stu-id="7b91e-252">Return</span></span>

<span data-ttu-id="7b91e-253">Příkaz return ukončí provádění operace nebo funkce a vrátí hodnotu volajícímu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="7b91e-254">Skládá se z klíčového slova `return`následovaný výrazem příslušného typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="7b91e-255">Nelze volat, která vrací prázdnou řazenou kolekci členů, `()`, nevyžaduje příkaz return.</span><span class="sxs-lookup"><span data-stu-id="7b91e-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="7b91e-256">Pokud je žádoucí předčasné ukončení, `return ()` možné v tomto případě použít.</span><span class="sxs-lookup"><span data-stu-id="7b91e-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="7b91e-257">Volat, které vracejí jiný typ, vyžadují konečný návratový příkaz.</span><span class="sxs-lookup"><span data-stu-id="7b91e-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="7b91e-258">V rámci operace není maximální počet návratových příkazů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="7b91e-259">Kompilátor může vygenerovat upozornění, pokud příkazy následují příkaz return v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="7b91e-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="7b91e-260">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="7b91e-261">nebo</span><span class="sxs-lookup"><span data-stu-id="7b91e-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="7b91e-262">nebo</span><span class="sxs-lookup"><span data-stu-id="7b91e-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="7b91e-263">Chyba</span><span class="sxs-lookup"><span data-stu-id="7b91e-263">Fail</span></span>

<span data-ttu-id="7b91e-264">Příkaz selhání ukončí provádění operace a vrátí volajícímu hodnotu chyby.</span><span class="sxs-lookup"><span data-stu-id="7b91e-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="7b91e-265">Skládá se z klíčového slova `fail`následovaný řetězcem a zakončeným středníkem.</span><span class="sxs-lookup"><span data-stu-id="7b91e-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="7b91e-266">Řetězec se vrátí do ovladače klasického rozhraní jako chybová zpráva.</span><span class="sxs-lookup"><span data-stu-id="7b91e-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="7b91e-267">Počet příkazů selhání v rámci operace není nijak omezen.</span><span class="sxs-lookup"><span data-stu-id="7b91e-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="7b91e-268">Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="7b91e-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="7b91e-269">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="7b91e-270">nebo</span><span class="sxs-lookup"><span data-stu-id="7b91e-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="7b91e-271">Správa qubit</span><span class="sxs-lookup"><span data-stu-id="7b91e-271">Qubit Management</span></span>

<span data-ttu-id="7b91e-272">Všimněte si, že žádný z těchto příkazů není povolen v rámci těla funkce.</span><span class="sxs-lookup"><span data-stu-id="7b91e-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="7b91e-273">Jsou platné pouze v rámci operací.</span><span class="sxs-lookup"><span data-stu-id="7b91e-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="7b91e-274">Vyčistit Qubits</span><span class="sxs-lookup"><span data-stu-id="7b91e-274">Clean Qubits</span></span>

<span data-ttu-id="7b91e-275">Příkaz `using` slouží k získání nového qubits pro použití během bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="7b91e-276">Qubits je zaručeno, že budou inicializovány do výpočetního `Zero`ho stavu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="7b91e-277">Qubits by měl být ve stavu výpočtu `Zero` na konci bloku příkazu; simulátory se doporučuje vyhovět.</span><span class="sxs-lookup"><span data-stu-id="7b91e-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="7b91e-278">Příkaz se skládá z klíčového slova `using`následovaný levou kulatou závorkou `(`, vazbou, uzavírací závorkou `)`a blok příkazů, ve kterém bude qubits k dispozici.</span><span class="sxs-lookup"><span data-stu-id="7b91e-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="7b91e-279">Vazba se řídí stejným vzorem jako `let` příkazy: buď jeden symbol, nebo záznamovou sadu symbolů, následovaný znaménkem rovná se `=`a buď jednou hodnotou, nebo porovnáním řazené kolekce členů inicializátorů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="7b91e-280">Inicializátory jsou k dispozici buď pro jeden qubit, který je označen jako `Qubit()`, nebo pole qubits, označeno `Qubit[`, výraz `Int` a `]`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="7b91e-281">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="7b91e-282">Vypůjčený Qubits</span><span class="sxs-lookup"><span data-stu-id="7b91e-282">Borrowed Qubits</span></span>

<span data-ttu-id="7b91e-283">Příkaz `borrowing` slouží k získání qubits pro dočasné použití.</span><span class="sxs-lookup"><span data-stu-id="7b91e-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="7b91e-284">Příkaz se skládá z klíčového slova `borrowing`následovaný levou kulatou závorkou `(`, vazbou, uzavírací závorkou `)`a blok příkazů, ve kterém bude qubits k dispozici.</span><span class="sxs-lookup"><span data-stu-id="7b91e-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="7b91e-285">Vazba následuje stejný vzor a pravidla jako ta v příkazu `using`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="7b91e-286">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="7b91e-287">Vypůjčený qubits je v neznámém stavu a na konci bloku příkazu se překročí rozsah.</span><span class="sxs-lookup"><span data-stu-id="7b91e-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="7b91e-288">Dlužník se zavazuje, že opustí qubits ve stejném stavu, ve kterém byly ve chvíli, kdy byly vypůjčené, tj. jejich stav na začátku a na konci bloku příkazu by měl být stejný.</span><span class="sxs-lookup"><span data-stu-id="7b91e-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="7b91e-289">Konkrétně se nejedná o klasický stav, což znamená, že ve většině případů by výpůjční rozsahy neměly obsahovat měření.</span><span class="sxs-lookup"><span data-stu-id="7b91e-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="7b91e-290">Příklad vypůjčeného Roettelerho použití najdete v tématu věnovaném [*faktorování pomocí 2n + 2 qubits s Toffoli modulárním násobení*](https://arxiv.org/abs/1611.07995) (Haner, Svore a qubit 2017).</span><span class="sxs-lookup"><span data-stu-id="7b91e-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="7b91e-291">Při výpůjční qubits se systém nejprve pokusí vyplňovat požadavek z qubits, které se používají, ale nejsou k dispozici během těla `borrowing`ho příkazu.</span><span class="sxs-lookup"><span data-stu-id="7b91e-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="7b91e-292">Pokud není dostatečná taková qubits, přidělí se nové qubits, aby se žádost dokončila.</span><span class="sxs-lookup"><span data-stu-id="7b91e-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="7b91e-293">Conjugations</span><span class="sxs-lookup"><span data-stu-id="7b91e-293">Conjugations</span></span>

<span data-ttu-id="7b91e-294">Na rozdíl od klasických bitů, uvolňování paměti je trochu více zapojeno, protože nevidomé resetující qubits může mít nežádoucí důsledky zbývajícího výpočtu, pokud qubits stále entangled.</span><span class="sxs-lookup"><span data-stu-id="7b91e-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="7b91e-295">K tomu je možné se vyhnout tím, že před uvolněním paměti vykonává správné "rušení".</span><span class="sxs-lookup"><span data-stu-id="7b91e-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="7b91e-296">Běžným vzorem pro výpočetní výkon je následující:</span><span class="sxs-lookup"><span data-stu-id="7b91e-296">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="7b91e-297">: NOVINKA: od naší verze 0,9 podporujeme příkaz conjugation, který implementuje výše uvedenou transformaci.</span><span class="sxs-lookup"><span data-stu-id="7b91e-297">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="7b91e-298">Pomocí tohoto příkazu lze operaci `ApplyWith` implementovat následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="7b91e-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="7b91e-299">Takový příkaz conjugation zjevně je mnohem užitečnější, pokud vnější a vnitřní transformace nejsou snadno dostupné jako operace, ale místo toho jsou vhodnější pro popis pomocí bloku skládajícího se z několika příkazů.</span><span class="sxs-lookup"><span data-stu-id="7b91e-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="7b91e-300">Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a provedena po dokončení bloku Apply.</span><span class="sxs-lookup"><span data-stu-id="7b91e-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="7b91e-301">Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku.</span><span class="sxs-lookup"><span data-stu-id="7b91e-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="7b91e-302">Příkazy vyhodnocení výrazu</span><span class="sxs-lookup"><span data-stu-id="7b91e-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="7b91e-303">Jako příkaz lze použít jakýkoli výraz volání typu `Unit`.</span><span class="sxs-lookup"><span data-stu-id="7b91e-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="7b91e-304">To je primárně použito při volání operací na qubits, které vracejí `Unit` vzhledem k tomu, že účelem příkazu je upravit implicitní stav.</span><span class="sxs-lookup"><span data-stu-id="7b91e-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="7b91e-305">Příkazy vyhodnocení výrazu vyžadují ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="7b91e-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="7b91e-306">Například:</span><span class="sxs-lookup"><span data-stu-id="7b91e-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```

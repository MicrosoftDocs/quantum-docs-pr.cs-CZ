---
title: Spuštění Groverova vyhledávacího algoritmu v jazyku Q# – Quantum Development Kit
description: Sestavte projekt v jazyku Q#, který demonstruje Groverův algoritmus – jeden z kanonických kvantových algoritmů.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c1fd578fdb3d56a7b48972e6ccc9b1605047fe36
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820347"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="0d3cd-103">Rychlý start: Implementace Groverova vyhledávacího algoritmu v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="0d3cd-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="0d3cd-104">V tomto rychlém startu se dozvíte, jak zkompilovat a spustit Groverovo hledání a urychlit hledání nestrukturovaných dat.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="0d3cd-105">Groverovo hledání je jedním z nejoblíbenějších kvantových výpočetních algoritmů a tato poměrně malá implementace v jazyce Q# poskytuje představu o některých výhodách programování kvantových řešení pomocí kvantového programovacího jazyka Q# vysoké úrovně při vyjádření kvantových algoritmů.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="0d3cd-106">Na konci průvodce se zobrazí výstup simulace, který ukazuje úspěšné vyhledání konkrétního řetězce v seznamu neuspořádaných položek za zlomek času, než by trvalo prohledání celého seznamu v klasickém počítači.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="0d3cd-107">Groverův algoritmus hledá konkrétní položky v seznamu nestrukturovaných dat.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="0d3cd-108">Může například odpovědět na otázku: Je tato karta vytažená z balíčku karet srdcové eso?</span><span class="sxs-lookup"><span data-stu-id="0d3cd-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="0d3cd-109">Popisek konkrétní položky se nazývá _označený vstup_.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="0d3cd-110">S použitím Groverova vyhledávacího algoritmu je zaručeno, že kvantový počítač toto hledání spustí v méně krocích, než je počet položek seznamu, ve kterém hledáte – něco, co žádný klasický algoritmus nedokáže.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="0d3cd-111">Zvýšení rychlosti je v případě balíčku karet zanedbatelné; u seznamů obsahujících milióny nebo miliardy položek je však značné.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="0d3cd-112">Groverův vyhledávací algoritmus je možné sestavit s pouhými několika řádky kódu.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d3cd-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0d3cd-113">Prerequisites</span></span>

- <span data-ttu-id="0d3cd-114">Sada Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="0d3cd-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="0d3cd-115">Co Groverův vyhledávací algoritmus dělá?</span><span class="sxs-lookup"><span data-stu-id="0d3cd-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="0d3cd-116">Groverův algoritmus se ptá, jestli je určitá položka v seznamu tou, kterou hledáme.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="0d3cd-117">Dosáhne toho sestrojením kvantové superpozice indexů seznamu s každým koeficientem (amplitudou pravděpodobnosti), který představuje pravděpodobnost toho, že daný index je hledaným indexem.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="0d3cd-118">Jádrem algoritmu jsou dva kroky, které postupně zvyšují koeficient indexu, který hledáme, dokud se amplituda pravděpodobnosti tohoto koeficientu nepřiblíží k hodnotě 1.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="0d3cd-119">Počet postupných zvýšení je menší než počet položek v seznamu.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="0d3cd-120">Proto Groverův algoritmus provádí hledání v méně krocích než jakýkoli klasický algoritmus.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Funkční schéma Groverova vyhledávacího algoritmu](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="0d3cd-122">Psaní kódu</span><span class="sxs-lookup"><span data-stu-id="0d3cd-122">Write the code</span></span>

1. <span data-ttu-id="0d3cd-123">S použitím sady Quantum Development Kit [vytvořte nový projekt v jazyku Q#](xref:microsoft.quantum.howto.createproject) s názvem `Grover` ve vývojovém prostředí podle vašeho výběru.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="0d3cd-124">Do souboru `Operations.qs` v projektu přidejte tento kód:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-23" highlight="5,27":::

1. <span data-ttu-id="0d3cd-125">Definujte seznam, ve kterém hledáme, tak, že vytvoříte nový soubor `Reflections.qs` a vložíte do něj tento kód:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="0d3cd-126">Operace `ReflectAboutMarked` definuje označený vstup, který hledáte: řetězec střídajících se nul a jedniček.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="0d3cd-127">V tomto příkladu je zadán pevný označený vstup. Je možné rozšířit ho a hledat jiné vstupy nebo obecně jakýkoli vstup.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="0d3cd-128">Dále spusťte nový program v jazyku Q# a vyhledejte položku označenou operací `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="0d3cd-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="0d3cd-129">Python s Visual Studio Code nebo příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="0d3cd-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="0d3cd-130">Pokud chcete nový program v jazyku Q# spustit z Pythonu, uložte jako soubor `host.py` tento kód:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    <span data-ttu-id="0d3cd-131">Pak můžete hostitelský program Pythonu spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="0d3cd-132">C# s Visual Studio Code nebo příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="0d3cd-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="0d3cd-133">Pokud chcete nový program v jazyku Q# spustit z C#, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="0d3cd-134">Pak můžete hostitelský program C# spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="0d3cd-135">C# s Visual Studiem 2019</span><span class="sxs-lookup"><span data-stu-id="0d3cd-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="0d3cd-136">Pokud chcete nový program v jazyku Q# spustit z C# v sadě Visual Studio, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="0d3cd-137">Pak stiskněte klávesu F5, program se spustí a automaticky se zobrazí nové okno s následujícími výsledky:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="0d3cd-138">Operace `ReflectAboutMarked` se volá jen čtyřikrát, program v jazyku Q# však našel vstup „01010“ mezi $2^{5} = 32$ možnými vstupy!</span><span class="sxs-lookup"><span data-stu-id="0d3cd-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d3cd-139">Další kroky</span><span class="sxs-lookup"><span data-stu-id="0d3cd-139">Next steps</span></span>

<span data-ttu-id="0d3cd-140">Pokud se vám tento rychlý start líbil, podívejte se na některé prostředky níže, ze kterých se dozvíte víc o tom, jak můžete v jazyku Q# psát vlastní kvantové aplikace:</span><span class="sxs-lookup"><span data-stu-id="0d3cd-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="0d3cd-141">Zpět na Začínáme pomocí průvodce sady QDK</span><span class="sxs-lookup"><span data-stu-id="0d3cd-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="0d3cd-142">Vyzkoušejte [ukázku](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) obecnějšího Groverova vyhledávacího algoritmu</span><span class="sxs-lookup"><span data-stu-id="0d3cd-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="0d3cd-143">Další informace o Groverově vyhledávání v kvantových katách</span><span class="sxs-lookup"><span data-stu-id="0d3cd-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="0d3cd-144">Další informace o [zvětšování amplitudy](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), technice kvantových výpočtů, která stojí za Groverovým vyhledávacím algoritmem</span><span class="sxs-lookup"><span data-stu-id="0d3cd-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="0d3cd-145">Koncepce kvantových výpočtů</span><span class="sxs-lookup"><span data-stu-id="0d3cd-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="0d3cd-146">Ukázky sady Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="0d3cd-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install

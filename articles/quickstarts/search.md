---
title: Spuštění Groverova vyhledávacího algoritmu v jazyku Q# – Quantum Development Kit
description: Sestavte projekt v jazyku Q#, který demonstruje Groverův algoritmus – jeden z kanonických kvantových algoritmů.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c67ccd16957ceef694552bdd9c073ba5a35d8aaf
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686828"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="61339-103">Rychlý start: Implementace Groverova vyhledávacího algoritmu v jazyku Q\#</span><span class="sxs-lookup"><span data-stu-id="61339-103">Quickstart: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="61339-104">V tomto rychlém startu se dozvíte, jak zkompilovat a spustit Groverovo hledání a urychlit hledání nestrukturovaných dat.</span><span class="sxs-lookup"><span data-stu-id="61339-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="61339-105">Groverovo hledání je jedním z nejoblíbenějších kvantových výpočetních algoritmů a tato poměrně malá implementace v jazyce Q# poskytuje představu o některých výhodách programování kvantových řešení pomocí kvantového programovacího jazyka Q# vysoké úrovně při vyjádření kvantových algoritmů.</span><span class="sxs-lookup"><span data-stu-id="61339-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="61339-106">Na konci průvodce se zobrazí výstup simulace, který ukazuje úspěšné vyhledání konkrétního řetězce v seznamu neuspořádaných položek za zlomek času, než by trvalo prohledání celého seznamu v klasickém počítači.</span><span class="sxs-lookup"><span data-stu-id="61339-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="61339-107">Groverův algoritmus hledá konkrétní položky v seznamu nestrukturovaných dat.</span><span class="sxs-lookup"><span data-stu-id="61339-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="61339-108">Může například odpovědět na otázku: Je tato karta vytažená z balíčku karet srdcové eso?</span><span class="sxs-lookup"><span data-stu-id="61339-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="61339-109">Popisek konkrétní položky se nazývá _označený vstup_.</span><span class="sxs-lookup"><span data-stu-id="61339-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="61339-110">S použitím Groverova vyhledávacího algoritmu je zaručeno, že kvantový počítač toto hledání spustí v méně krocích, než je počet položek seznamu, ve kterém hledáte – něco, co žádný klasický algoritmus nedokáže.</span><span class="sxs-lookup"><span data-stu-id="61339-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="61339-111">Zvýšení rychlosti je v případě balíčku karet zanedbatelné; u seznamů obsahujících milióny nebo miliardy položek je však značné.</span><span class="sxs-lookup"><span data-stu-id="61339-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="61339-112">Groverův vyhledávací algoritmus je možné sestavit s pouhými několika řádky kódu.</span><span class="sxs-lookup"><span data-stu-id="61339-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61339-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="61339-113">Prerequisites</span></span>

- <span data-ttu-id="61339-114">Sada Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="61339-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="61339-115">Co Groverův vyhledávací algoritmus dělá?</span><span class="sxs-lookup"><span data-stu-id="61339-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="61339-116">Groverův algoritmus se ptá, jestli je určitá položka v seznamu tou, kterou hledáme.</span><span class="sxs-lookup"><span data-stu-id="61339-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="61339-117">Dosáhne toho sestrojením kvantové superpozice indexů seznamu s každým koeficientem (amplitudou pravděpodobnosti), který představuje pravděpodobnost toho, že daný index je hledaným indexem.</span><span class="sxs-lookup"><span data-stu-id="61339-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="61339-118">Jádrem algoritmu jsou dva kroky, které postupně zvyšují koeficient indexu, který hledáme, dokud se amplituda pravděpodobnosti tohoto koeficientu nepřiblíží k hodnotě 1.</span><span class="sxs-lookup"><span data-stu-id="61339-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="61339-119">Počet postupných zvýšení je menší než počet položek v seznamu.</span><span class="sxs-lookup"><span data-stu-id="61339-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="61339-120">Proto Groverův algoritmus provádí hledání v méně krocích než jakýkoli klasický algoritmus.</span><span class="sxs-lookup"><span data-stu-id="61339-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Funkční schéma Groverova vyhledávacího algoritmu](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="61339-122">Psaní kódu</span><span class="sxs-lookup"><span data-stu-id="61339-122">Write the code</span></span>

1. <span data-ttu-id="61339-123">S použitím sady Quantum Development Kit [vytvořte nový projekt v jazyku Q#](xref:microsoft.quantum.howto.createproject) s názvem `Grover` ve vývojovém prostředí podle vašeho výběru.</span><span class="sxs-lookup"><span data-stu-id="61339-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="61339-124">Do souboru `Program.qs` v projektu přidejte tento kód:</span><span class="sxs-lookup"><span data-stu-id="61339-124">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="61339-125">Definujte seznam, ve kterém hledáme, tak, že vytvoříte nový soubor `Reflections.qs` a vložíte do něj tento kód:</span><span class="sxs-lookup"><span data-stu-id="61339-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="61339-126">Operace `ReflectAboutMarked` definuje označený vstup, který hledáte: řetězec střídajících se nul a jedniček.</span><span class="sxs-lookup"><span data-stu-id="61339-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="61339-127">V tomto příkladu je zadán pevný označený vstup. Je možné rozšířit ho a hledat jiné vstupy nebo obecně jakýkoli vstup.</span><span class="sxs-lookup"><span data-stu-id="61339-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="61339-128">Dále spusťte nový program v jazyku Q# a vyhledejte položku označenou operací `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="61339-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="61339-129">Aplikace příkazového řádku v Q# s využitím sady Visual Studio nebo editoru Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="61339-129">Q# command line applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="61339-130">Spustitelný soubor spustí operaci nebo funkci označenou atributem `@EntryPoint()` na simulátoru nebo v estimátoru prostředků, a to v závislosti na konfiguraci projektu a možnostech příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="61339-130">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="61339-131">V sadě Visual Studio se skript jednoduše spustí stisknutím Ctrl + F5.</span><span class="sxs-lookup"><span data-stu-id="61339-131">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="61339-132">V editoru VS Code při prvním použití sestavte `Program.qs` zadáním následujícího příkazu na terminálu:</span><span class="sxs-lookup"><span data-stu-id="61339-132">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="61339-133">Pro následná spuštění není potřeba ho sestavovat znovu.</span><span class="sxs-lookup"><span data-stu-id="61339-133">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="61339-134">Pokud ho chcete spustit, zadejte následující příkaz a stiskněte Enter:</span><span class="sxs-lookup"><span data-stu-id="61339-134">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="61339-135">Na terminálu by se měla zobrazit následující zpráva:</span><span class="sxs-lookup"><span data-stu-id="61339-135">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="61339-136">Důvodem je to, že jste nezadali počet qubitů, které chcete použít, takže terminál vás upozorní na příkazy, které jsou pro spustitelný soubor k dispozici.</span><span class="sxs-lookup"><span data-stu-id="61339-136">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="61339-137">Pokud chcete použít 5 qubitů, měli byste zadat:</span><span class="sxs-lookup"><span data-stu-id="61339-137">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="61339-138">Po stisknutí klávesy Enter by se měl zobrazit následující výstup:</span><span class="sxs-lookup"><span data-stu-id="61339-138">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="61339-139">Další kroky</span><span class="sxs-lookup"><span data-stu-id="61339-139">Next steps</span></span>

<span data-ttu-id="61339-140">Pokud se vám tento rychlý start líbil, podívejte se na některé prostředky níže, ze kterých se dozvíte víc o tom, jak můžete v jazyku Q# psát vlastní kvantové aplikace:</span><span class="sxs-lookup"><span data-stu-id="61339-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="61339-141">Zpět na Začínáme pomocí průvodce sady QDK</span><span class="sxs-lookup"><span data-stu-id="61339-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="61339-142">Vyzkoušejte [ukázku](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) obecnějšího Groverova vyhledávacího algoritmu</span><span class="sxs-lookup"><span data-stu-id="61339-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="61339-143">Další informace o Groverově vyhledávání v kvantových katách</span><span class="sxs-lookup"><span data-stu-id="61339-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="61339-144">Další informace o [zvětšování amplitudy][amplitude-amplification], technice kvantových výpočtů, která stojí za Groverovým vyhledávacím algoritmem</span><span class="sxs-lookup"><span data-stu-id="61339-144">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="61339-145">Koncepce kvantových výpočtů</span><span class="sxs-lookup"><span data-stu-id="61339-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="61339-146">Ukázky sady Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="61339-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification

---
title: Vytvoření kvantového generátoru náhodných čísel
description: Vytvořte projekt v jazyku Q#, který ilustruje základní kvantové koncepce, jako je například superpozice, vytvořením kvantového generátoru náhodných čísel.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820900"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="becb4-103">Rychlý start: Implementace kvantového generátoru náhodných čísel v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="becb4-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="becb4-104">Jednoduchým příkladem kvantového algoritmu implementovaného v jazyku Q# je kvantový generátor náhodných čísel.</span><span class="sxs-lookup"><span data-stu-id="becb4-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="becb4-105">Tento algoritmus využívá charakter kvantové mechaniky a vytváří náhodné číslo.</span><span class="sxs-lookup"><span data-stu-id="becb4-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="becb4-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="becb4-106">Prerequisites</span></span>

- <span data-ttu-id="becb4-107">Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="becb4-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="becb4-108">Vytvořte projekt v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="becb4-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="becb4-109">Napište operaci Q#</span><span class="sxs-lookup"><span data-stu-id="becb4-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="becb4-110">Kód operace Q#</span><span class="sxs-lookup"><span data-stu-id="becb4-110">Q# operation code</span></span>

1. <span data-ttu-id="becb4-111">Obsah souboru Operation.qs nahraďte následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="becb4-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="becb4-112">Jak je uvedeno v článku [Co jsou kvantové výpočty?](xref:microsoft.quantum.overview.what), qubit je jednotka kvantových informací, které můžou být v superpozici.</span><span class="sxs-lookup"><span data-stu-id="becb4-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="becb4-113">Při změření může mít qubit jenom hodnotu 0 nebo 1.</span><span class="sxs-lookup"><span data-stu-id="becb4-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="becb4-114">Během zpracování však stav qubitu představuje pravděpodobnost přečtení hodnoty 0 anebo 1 při měření.</span><span class="sxs-lookup"><span data-stu-id="becb4-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="becb4-115">Tento pravděpodobnostní stav se nazývá superpozice.</span><span class="sxs-lookup"><span data-stu-id="becb4-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="becb4-116">Na základě této pravděpodobnosti můžeme generovat náhodná čísla.</span><span class="sxs-lookup"><span data-stu-id="becb4-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="becb4-117">V rámci operace v jazyku Q # zavádíme datový typ `Qubit`, který je pro jazyk Q# nativní.</span><span class="sxs-lookup"><span data-stu-id="becb4-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="becb4-118">Typ `Qubit` je možné přidělit jen pomocí příkazu `using`.</span><span class="sxs-lookup"><span data-stu-id="becb4-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="becb4-119">Qubit je po přidělení vždycky ve stavu `Zero`.</span><span class="sxs-lookup"><span data-stu-id="becb4-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="becb4-120">Pomocí operace `H` můžeme `Qubit` převést do superpozice.</span><span class="sxs-lookup"><span data-stu-id="becb4-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="becb4-121">Ke změření qubitu a přečtení jeho hodnoty použijte vnitřní operaci `M`.</span><span class="sxs-lookup"><span data-stu-id="becb4-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="becb4-122">Když `Qubit` převedeme do superpozice a změříme ho, bude výsledkem při každém vyvolání kódu jiná hodnota.</span><span class="sxs-lookup"><span data-stu-id="becb4-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="becb4-123">Když je pro `Qubit` zrušeno přidělení, musí pro něj být znovu nastaven stav `Zero`, jinak simulátor ohlásí běhovou chybu.</span><span class="sxs-lookup"><span data-stu-id="becb4-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="becb4-124">Snadný způsob, jak toho dosáhnout, je vyvolat operaci `Reset`.</span><span class="sxs-lookup"><span data-stu-id="becb4-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="becb4-125">Vizualizace kódu pomocí Blochovy koule</span><span class="sxs-lookup"><span data-stu-id="becb4-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="becb4-126">Severní pól na Blochově kouli představuje klasickou hodnotu **0** a jižní pól představuje klasickou hodnotu **1**.</span><span class="sxs-lookup"><span data-stu-id="becb4-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="becb4-127">Každá superpozice může být reprezentována bodem na kouli (reprezentovaný šipkou).</span><span class="sxs-lookup"><span data-stu-id="becb4-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="becb4-128">Čím blíž je konec šipky k pólu, tím vyšší je pravděpodobnost, že se qubit při změření převede na klasickou hodnotu přiřazenou k příslušnému pólu.</span><span class="sxs-lookup"><span data-stu-id="becb4-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="becb4-129">Příklad: Stav qubitu reprezentovaného červenou šipkou na obrázku níže má vyšší pravděpodobnost, že při změření bude mít hodnotu **0**.</span><span class="sxs-lookup"><span data-stu-id="becb4-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="becb4-130">Tuto reprezentaci můžeme použít k vizualizaci toho, co kód dělá:</span><span class="sxs-lookup"><span data-stu-id="becb4-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="becb4-131">Nejdřív začneme s qubitem inicializovaným ve stavu **0** a pomocí funkce `H` vytvoříme superpozici, ve které jsou pravděpodobnosti hodnot **0** a **1** stejné.</span><span class="sxs-lookup"><span data-stu-id="becb4-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="becb4-132">Pak qubit změříme a výstup uložíme:</span><span class="sxs-lookup"><span data-stu-id="becb4-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="becb4-133">Jelikož je výsledek měření zcela náhodný, získali jsme náhodný bit.</span><span class="sxs-lookup"><span data-stu-id="becb4-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="becb4-134">Pokud chceme generovat celá čísla, můžeme tuto operaci volat vícekrát.</span><span class="sxs-lookup"><span data-stu-id="becb4-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="becb4-135">Pokud například budeme tuto operaci volat třikrát a získáme tři náhodné bity, můžeme generovat náhodná 3-bitová čísla (tedy náhodné číslo v rozsahu 0 až 7).</span><span class="sxs-lookup"><span data-stu-id="becb4-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="becb4-136">Vytvoření kompletního generátoru náhodných čísel s využitím hostitelského programu</span><span class="sxs-lookup"><span data-stu-id="becb4-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="becb4-137">Teď když máme operaci Q#, která generuje náhodné bity, můžeme ji použít k sestavení kompletního generátoru náhodných čísel s využitím hostitelského programu.</span><span class="sxs-lookup"><span data-stu-id="becb4-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="becb4-138">Python s Visual Studio Code nebo příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="becb4-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="becb4-139">Pokud chcete nový program v jazyku Q# spustit z Pythonu, uložte jako soubor `host.py` tento kód:</span><span class="sxs-lookup"><span data-stu-id="becb4-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="becb4-140">Pak můžete hostitelský program Pythonu spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="becb4-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="becb4-141">C# s Visual Studio Code nebo příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="becb4-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="becb4-142">Pokud chcete nový program v jazyku Q# spustit z C#, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:</span><span class="sxs-lookup"><span data-stu-id="becb4-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="becb4-143">Pak můžete hostitelský program C# spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="becb4-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="becb4-144">C# s Visual Studiem 2019</span><span class="sxs-lookup"><span data-stu-id="becb4-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="becb4-145">Pokud chcete nový program v jazyku Q# spustit z C# v sadě Visual Studio, upravte soubor `Driver.cs` tak, aby obsahoval tento kód C#:</span><span class="sxs-lookup"><span data-stu-id="becb4-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="becb4-146">Pak stiskněte klávesu F5, program se spustí a automaticky se zobrazí nové okno s vygenerovaným náhodným číslem:</span><span class="sxs-lookup"><span data-stu-id="becb4-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***

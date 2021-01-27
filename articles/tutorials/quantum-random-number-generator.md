---
title: Vytvoření kvantového generátoru náhodných čísel
description: Sestavte Q# projekt, který ukazuje základní koncepty, jako je například nadpozice, vytvořením generátor náhodných čísel.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: f36db426a8f0479580117cce44a67ad3a053d5de
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856352"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="9b903-103">Kurz: Implementace kvantového generátoru náhodných čísel v jazyku Q\#</span><span class="sxs-lookup"><span data-stu-id="9b903-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="9b903-104">Jednoduchý příklad algoritmu, který je v systému napsaný, Q# je generátor náhodných čísel.</span><span class="sxs-lookup"><span data-stu-id="9b903-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="9b903-105">Tento algoritmus využívá charakter kvantové mechaniky a vytváří náhodné číslo.</span><span class="sxs-lookup"><span data-stu-id="9b903-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9b903-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="9b903-106">Prerequisites</span></span>

- <span data-ttu-id="9b903-107">Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="9b903-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="9b903-108">Vytvořte Q# projekt pro [ Q# aplikaci](xref:microsoft.quantum.install.standalone), pomocí [hostitelského programu Pythonu](xref:microsoft.quantum.install.python)nebo [hostitelského programu jazyka C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="9b903-108">Create a Q# project for either a [Q# application](xref:microsoft.quantum.install.standalone), with a [Python host program](xref:microsoft.quantum.install.python), or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="9b903-109">Zápis Q# operace</span><span class="sxs-lookup"><span data-stu-id="9b903-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="9b903-110">Q# kód operace</span><span class="sxs-lookup"><span data-stu-id="9b903-110">Q# operation code</span></span>

1. <span data-ttu-id="9b903-111">Obsah souboru Program.qs nahraďte následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="9b903-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="9b903-112">Jak je uvedeno v článku [Principy kvantových výpočtů](xref:microsoft.quantum.overview.understanding), qubit je jednotka kvantových informací, která může být v superpozici různých stavů.</span><span class="sxs-lookup"><span data-stu-id="9b903-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="9b903-113">Při změření může mít qubit jenom hodnotu 0 nebo 1.</span><span class="sxs-lookup"><span data-stu-id="9b903-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="9b903-114">Před měřením ale stav qubit představuje pravděpodobnost čtení 0 nebo 1 s měřením.</span><span class="sxs-lookup"><span data-stu-id="9b903-114">However, before measurement, the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="9b903-115">Tento pravděpodobnostní stav se nazývá superpozice.</span><span class="sxs-lookup"><span data-stu-id="9b903-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="9b903-116">Na základě této pravděpodobnosti můžeme generovat náhodná čísla.</span><span class="sxs-lookup"><span data-stu-id="9b903-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="9b903-117">V naší Q# operaci zavádíme `Qubit` datový typ, který je nativní pro Q# .</span><span class="sxs-lookup"><span data-stu-id="9b903-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="9b903-118">Typ `Qubit` je možné přidělit jen pomocí příkazu `using`.</span><span class="sxs-lookup"><span data-stu-id="9b903-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="9b903-119">Qubit je po přidělení vždycky ve stavu `Zero`.</span><span class="sxs-lookup"><span data-stu-id="9b903-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="9b903-120">Pomocí operace `H` můžeme `Qubit` převést do superpozice.</span><span class="sxs-lookup"><span data-stu-id="9b903-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="9b903-121">Ke změření qubitu a přečtení jeho hodnoty použijte vnitřní operaci `M`.</span><span class="sxs-lookup"><span data-stu-id="9b903-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="9b903-122">Když `Qubit` převedeme do superpozice a změříme ho, bude výsledkem při každém vyvolání kódu jiná hodnota.</span><span class="sxs-lookup"><span data-stu-id="9b903-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="9b903-123">Když je pro `Qubit` zrušeno přidělení, musí pro něj být znovu nastaven stav `Zero`, jinak simulátor ohlásí běhovou chybu.</span><span class="sxs-lookup"><span data-stu-id="9b903-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="9b903-124">Snadný způsob, jak toho dosáhnout, je vyvolat operaci `Reset`.</span><span class="sxs-lookup"><span data-stu-id="9b903-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="9b903-125">Vizualizace kódu pomocí Blochovy koule</span><span class="sxs-lookup"><span data-stu-id="9b903-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="9b903-126">Severní pól na Blochově kouli představuje klasickou hodnotu **0** a jižní pól představuje klasickou hodnotu **1**.</span><span class="sxs-lookup"><span data-stu-id="9b903-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="9b903-127">Každá superpozice může být reprezentována bodem na kouli (reprezentovaný šipkou).</span><span class="sxs-lookup"><span data-stu-id="9b903-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="9b903-128">Čím blíž je konec šipky k pólu, tím vyšší je pravděpodobnost, že se qubit při změření převede na klasickou hodnotu přiřazenou k příslušnému pólu.</span><span class="sxs-lookup"><span data-stu-id="9b903-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="9b903-129">Příklad: Stav qubitu reprezentovaného červenou šipkou na obrázku níže má vyšší pravděpodobnost, že při změření bude mít hodnotu **0**.</span><span class="sxs-lookup"><span data-stu-id="9b903-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="9b903-130">Tuto reprezentaci můžeme použít k vizualizaci toho, co kód dělá:</span><span class="sxs-lookup"><span data-stu-id="9b903-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="9b903-131">Nejdřív začneme s qubitem inicializovaným ve stavu **0** a pomocí funkce `H` vytvoříme superpozici, ve které jsou pravděpodobnosti hodnot **0** a **1** stejné.</span><span class="sxs-lookup"><span data-stu-id="9b903-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="9b903-132">Pak qubit změříme a výstup uložíme:</span><span class="sxs-lookup"><span data-stu-id="9b903-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="9b903-133">Jelikož je výsledek měření zcela náhodný, získali jsme náhodný bit.</span><span class="sxs-lookup"><span data-stu-id="9b903-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="9b903-134">Pokud chceme generovat celá čísla, můžeme tuto operaci volat vícekrát.</span><span class="sxs-lookup"><span data-stu-id="9b903-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="9b903-135">Pokud například budeme tuto operaci volat třikrát a získáme tři náhodné bity, můžeme generovat náhodná 3-bitová čísla (tedy náhodné číslo v rozsahu 0 až 7).</span><span class="sxs-lookup"><span data-stu-id="9b903-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="9b903-136">Vytvoření kompletního generátoru náhodných čísel</span><span class="sxs-lookup"><span data-stu-id="9b903-136">Creating a complete random number generator</span></span>

<span data-ttu-id="9b903-137">Teď, když máme Q# operaci, která generuje náhodné bity, můžeme ji použít k sestavení kompletního generátoru náhodných čísel.</span><span class="sxs-lookup"><span data-stu-id="9b903-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="9b903-138">Můžeme použít Q# aplikaci nebo použít hostitelský program.</span><span class="sxs-lookup"><span data-stu-id="9b903-138">We can use a Q# application or use a host program.</span></span>



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="9b903-139">Q# aplikace se sadou Visual Studio nebo Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9b903-139">Q# applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="9b903-140">Chcete-li vytvořit úplnou Q# aplikaci, přidejte do programu následující vstupní bod Q# :</span><span class="sxs-lookup"><span data-stu-id="9b903-140">To create the full Q# application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="9b903-141">Program spustí operaci nebo funkci označenou `@EntryPoint()` atributem simulátoru nebo Estimator prostředku v závislosti na konfiguraci projektu a možnostech příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="9b903-141">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="9b903-142">V aplikaci Visual Studio stačí stisknout kombinaci kláves CTRL + F5 ke spuštění skriptu.</span><span class="sxs-lookup"><span data-stu-id="9b903-142">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="9b903-143">V editoru VS Code při prvním použití sestavte Program.qs zadáním následujícího příkazu na terminálu:</span><span class="sxs-lookup"><span data-stu-id="9b903-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="9b903-144">Pro následná spuštění není potřeba ho sestavovat znovu.</span><span class="sxs-lookup"><span data-stu-id="9b903-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="9b903-145">Pokud ho chcete spustit, zadejte následující příkaz a stiskněte Enter:</span><span class="sxs-lookup"><span data-stu-id="9b903-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[<span data-ttu-id="9b903-146">Python s Visual Studio Code nebo příkazový řádek</span><span class="sxs-lookup"><span data-stu-id="9b903-146">Python with Visual Studio Code or the command prompt</span></span>](#tab/tabid-python)

<span data-ttu-id="9b903-147">Chcete-li spustit nový Q# program z Pythonu, uložte následující kód jako `host.py` :</span><span class="sxs-lookup"><span data-stu-id="9b903-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="9b903-148">Hostitelský program Pythonu pak můžete spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="9b903-148">You can then run your Python host program from the command prompt:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="9b903-149">C# s využitím editoru Visual Studio Code nebo sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b903-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="9b903-150">Chcete-li spustit nový Q# program z c#, upravte `Driver.cs` tak, aby obsahovalo následující kód C#:</span><span class="sxs-lookup"><span data-stu-id="9b903-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="9b903-151">Pak můžete spustit hostitelský program C# z příkazového řádku (v aplikaci Visual Studio byste měli stisknout klávesu F5):</span><span class="sxs-lookup"><span data-stu-id="9b903-151">You can then run your C# host program from the command prompt (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***

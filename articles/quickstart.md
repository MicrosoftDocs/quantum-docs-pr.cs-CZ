---
title: Zkoumání provázání s využitím Q#
description: Naučte se psát kvantové programy v jazyce Q#. Vývoj aplikace demonstrující Bellovy stavy pomocí nástroje Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 7836e39227fa2282c6e2faa039f6e625103d5403
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426846"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="c4046-104">Kurz: Zkoumání provázání s využitím Q\#</span><span class="sxs-lookup"><span data-stu-id="c4046-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="c4046-105">V tomto kurzu vám ukážeme, jak v jazyce Q# napsat program, který manipuluje s qubity, měří je a demonstruje efekty superpozice a provázání.</span><span class="sxs-lookup"><span data-stu-id="c4046-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="c4046-106">Tento dokument vás provede instalací sady QDK, sestavením programu a spuštěním programu na kvantovém simulátoru.</span><span class="sxs-lookup"><span data-stu-id="c4046-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="c4046-107">Vytvoříme aplikaci nazvanou Bell, která demonstruje kvantové provázání.</span><span class="sxs-lookup"><span data-stu-id="c4046-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="c4046-108">Název Bell odkazuje na Bellovy stavy, což jsou specifické kvantové stavy 2 qubitů používané k demonstraci nejjednodušších příkladů superpozice a provázání.</span><span class="sxs-lookup"><span data-stu-id="c4046-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c4046-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c4046-109">Pre-requisites</span></span>

<span data-ttu-id="c4046-110">Chcete-li se pustit do kódování, nejprve proveďte tyto kroky:</span><span class="sxs-lookup"><span data-stu-id="c4046-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="c4046-111">[Instalace](xref:microsoft.quantum.install) vývojové sady s použitím preferovaného jazykového a vývojového prostředí</span><span class="sxs-lookup"><span data-stu-id="c4046-111">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment</span></span>
* <span data-ttu-id="c4046-112">Pokud už máte sadu QDK nainstalovanou, zkontrolujte, že je [aktualizovaná na nejnovější verzi](xref:microsoft.quantum.update)</span><span class="sxs-lookup"><span data-stu-id="c4046-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="c4046-113">Pokud se chcete jen seznámit se základy, můžete si článek přečíst i bez instalace sady QDK. Získáte tak přehled o programovacím jazyku Q# a základních koncepcích kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="c4046-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="c4046-114">Demonstrace chování qubitů pomocí Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="c4046-115">Připomeňme si naši jednoduchou definici [qubitu](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="c4046-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="c4046-116">Zatímco klasické bity obsahují jednu binární hodnotu (tj. 0 nebo 1), qubit se může současně nacházet v **superpozici** stavů 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="c4046-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  <span data-ttu-id="c4046-117">Qubit si můžete představit jako směr v prostoru (označuje se také jako vektor).</span><span class="sxs-lookup"><span data-stu-id="c4046-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="c4046-118">Qubit může být natočený do libovolného směru.</span><span class="sxs-lookup"><span data-stu-id="c4046-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="c4046-119">Dva **klasické stavy** odpovídají dvěma směrům. Představují 100% šanci na změření 0 a 100% šanci na změření 1.</span><span class="sxs-lookup"><span data-stu-id="c4046-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="c4046-120">Tuto reprezentaci je možné formálněji vizualizovat [Blochovou koulí](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="c4046-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>


<span data-ttu-id="c4046-121">Akce měření poskytuje binární výsledek a mění stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="c4046-122">Měřením získáme binární hodnotu, buď 0, nebo 1.</span><span class="sxs-lookup"><span data-stu-id="c4046-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="c4046-123">V důsledku měření přejde qubit ze superpozice (libovolného směru) do jednoho z klasických stavů.</span><span class="sxs-lookup"><span data-stu-id="c4046-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="c4046-124">Všechna následná opakovaná měření bez provedení dalších operací už budou poskytovat shodný binární výsledek.</span><span class="sxs-lookup"><span data-stu-id="c4046-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="c4046-125">Několik qubitů může být také **provázáno**.</span><span class="sxs-lookup"><span data-stu-id="c4046-125">Multiple qubits can be **entangled**.</span></span> <span data-ttu-id="c4046-126">Když změříme jeden provázaný qubit, změní se tím naše znalost stavu ostatních qubitů.</span><span class="sxs-lookup"><span data-stu-id="c4046-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="c4046-127">Nyní jsme připraveni ukázat, jak se toto chování vyjadřuje v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="c4046-128">Začneme s nejjednodušším možným programem a sestavíme ho tak, abychom demonstrovali kvantovou superpozici a provázání.</span><span class="sxs-lookup"><span data-stu-id="c4046-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="c4046-129">Nastavení</span><span class="sxs-lookup"><span data-stu-id="c4046-129">Setup</span></span>

<span data-ttu-id="c4046-130">Aplikace vyvinuté pomocí nástroje Microsoft Quantum Development Kit se skládají ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="c4046-130">Applications developed with Microsoft's Quantum Development Kit consist of two parts:</span></span>

1. <span data-ttu-id="c4046-131">Jeden nebo více kvantových algoritmů, implementovaných v kvantovém programovacím jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-131">One or more quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="c4046-132">Hostitelský program implementovaný v programovacím jazyce jako Python nebo C#, který slouží jako hlavní vstupní bod a vyvolává kvantové algoritmy jako operace Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-132">A host program, implemented in a programming language like Python or C# that serves as the main entry point and invokes Q# operations to execute a quantum algorithm.</span></span>

#### <a name="python"></a>[<span data-ttu-id="c4046-133">Python</span><span class="sxs-lookup"><span data-stu-id="c4046-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="c4046-134">Vyberte umístění aplikace.</span><span class="sxs-lookup"><span data-stu-id="c4046-134">Choose a location for your application</span></span>

1. <span data-ttu-id="c4046-135">Vytvořte soubor s názvem `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="c4046-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="c4046-136">Tento soubor bude obsahovat váš kód Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="c4046-137">Vytvořte soubor s názvem `host.py`.</span><span class="sxs-lookup"><span data-stu-id="c4046-137">Create a file called `host.py`.</span></span> <span data-ttu-id="c4046-138">Tento soubor bude obsahovat váš hostitelský kód v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="c4046-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="c4046-139">Příkazový řádek C#</span><span class="sxs-lookup"><span data-stu-id="c4046-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="c4046-140">Vytvoření nového projektu Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-140">Create a new Q# project:</span></span>

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="c4046-141">Měli byste vidět soubor `.csproj`, soubor Q# s názvem `Operations.qs` a soubor hostitelského programu s názvem `Driver.cs`.</span><span class="sxs-lookup"><span data-stu-id="c4046-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="c4046-142">Přejmenování souboru Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-142">Rename the Q# file</span></span>

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="c4046-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4046-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="c4046-144">Vytvoření nového projektu</span><span class="sxs-lookup"><span data-stu-id="c4046-144">Create a new project</span></span>

   * <span data-ttu-id="c4046-145">Otevřete sadu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c4046-145">Open Visual Studio</span></span>
   * <span data-ttu-id="c4046-146">V nabídce **Soubor** vyberte **Nový** -> **Projekt...** .</span><span class="sxs-lookup"><span data-stu-id="c4046-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="c4046-147">V průzkumníku šablon projektu zadejte do vyhledávacího pole `Q#` a vyberte šablonu `Q# Application`.</span><span class="sxs-lookup"><span data-stu-id="c4046-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="c4046-148">Dejte projektu název `Bell`.</span><span class="sxs-lookup"><span data-stu-id="c4046-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="c4046-149">Přejmenování souboru Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-149">Rename the Q# file</span></span>

   * <span data-ttu-id="c4046-150">Přejděte na **Průzkumníka řešení**.</span><span class="sxs-lookup"><span data-stu-id="c4046-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="c4046-151">Klikněte pravým tlačítkem na soubor `Operations.qs`.</span><span class="sxs-lookup"><span data-stu-id="c4046-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="c4046-152">Přejmenujte ho na `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="c4046-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="c4046-153">Napište operaci Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-153">Write a Q# operation</span></span>

<span data-ttu-id="c4046-154">Naším cílem je připravit dva qubity v určitém kvantovém stavu a demonstrovat tak, jak v Q# pracovat s qubity, měnit jejich stav a využívat efekty superpozice a provázání.</span><span class="sxs-lookup"><span data-stu-id="c4046-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="c4046-155">Program sestavíme krok za krokem a předvedeme si stavy, operace a měření spojené s qubity.</span><span class="sxs-lookup"><span data-stu-id="c4046-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="c4046-156">**Přehled:**  V prvním kódu níže si ukážeme, jak v jazyce Q# pracovat s qubity.</span><span class="sxs-lookup"><span data-stu-id="c4046-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="c4046-157">Zavedeme dvě operace `M` a `X`, které mění stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="c4046-158">V tomto fragmentu kódu je použita operace `Set`, která přijímá jako parametr qubit a další parametr `desired` označující stav, do kterého chceme qubit převést.</span><span class="sxs-lookup"><span data-stu-id="c4046-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="c4046-159">Operace `Set` provádí měření qubitu pomocí operace `M`.</span><span class="sxs-lookup"><span data-stu-id="c4046-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="c4046-160">V Q# vrací měření qubitu vždy buď `Zero`, nebo `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="c4046-161">Pokud měření vrátí hodnotu, která není rovna požadované hodnotě, operace Set qubit „překlopí“. To znamená, že provede operaci `X`, která změní stav qubit na nový stav, ve kterém jsou pravděpodobnosti změření `Zero` a `One` převrácené.</span><span class="sxs-lookup"><span data-stu-id="c4046-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="c4046-162">Pro předvedení efektu operace `Set` je pak přidána operace `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="c4046-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="c4046-163">Tato operace jako vstup přebírá `Zero` nebo `One`, několikrát s tímto vstupem zavolá operaci `Set` a spočítá, kolikrát byla z měření qubitu vrácena hodnota `Zero` a kolikrát `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="c4046-164">Samozřejmě v této první simulaci operace `TestBellState` očekáváme, že všechna měření qubitu nastaveného pomocí vstupního parametru `Zero` vrátí hodnotu `Zero` a všechna měření qubitu nastaveného pomocí parametru `One` vrátí `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="c4046-165">Dále do operace `TestBellState` přidáme kód pro demonstraci superpozice a provázání.</span><span class="sxs-lookup"><span data-stu-id="c4046-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="c4046-166">Kód operace Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-166">Q# operation code</span></span>

1. <span data-ttu-id="c4046-167">Obsah souboru Bell.qs nahraďte následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="c4046-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="c4046-168">Teď můžeme zavolat tuto operaci, aby nastavila qubit do klasického stavu a vrátila buď hodnotu `Zero` ve 100 % případů, nebo hodnotu `One` ve 100 % případů.</span><span class="sxs-lookup"><span data-stu-id="c4046-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="c4046-169">`Zero` a `One` jsou konstanty, které představují pouze dva možné výsledky měření stavu qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="c4046-170">Operace `Set` měří qubit.</span><span class="sxs-lookup"><span data-stu-id="c4046-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="c4046-171">Pokud je qubit ve stavu, který chceme, `Set` ho nechá být, v opačném případě provedením operace `X` změní stav qubitu na požadovaný stav.</span><span class="sxs-lookup"><span data-stu-id="c4046-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="c4046-172">Operace v jazyce Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-172">About Q# operations</span></span>

<span data-ttu-id="c4046-173">Operace Q # je vlastně kvantový podprogram.</span><span class="sxs-lookup"><span data-stu-id="c4046-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="c4046-174">To znamená, že se jedná o volanou rutinu, která obsahuje kvantové operace.</span><span class="sxs-lookup"><span data-stu-id="c4046-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="c4046-175">Argumenty operace jsou zadány jako řazené kolekce členů v závorkách.</span><span class="sxs-lookup"><span data-stu-id="c4046-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="c4046-176">Návratový typ operace je určen za dvojtečkou.</span><span class="sxs-lookup"><span data-stu-id="c4046-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="c4046-177">V našem případě operace `Set` nic nevrací, takže je označena jako vracející `Unit`.</span><span class="sxs-lookup"><span data-stu-id="c4046-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="c4046-178">Toto je v jazyce Q# ekvivalentem pojmu `unit` v F#, což je hrubá analogie `void` v C# a prázdné řazené kolekci členů v Pythonu (`Tuple[()]`).</span><span class="sxs-lookup"><span data-stu-id="c4046-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="c4046-179">V naší první operaci Q# jsme použili dvě kvantové operace:</span><span class="sxs-lookup"><span data-stu-id="c4046-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="c4046-180">Operaci [M](xref:microsoft.quantum.intrinsic.m), která měří stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="c4046-181">Operaci [X](xref:microsoft.quantum.intrinsic.x), která převrací stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="c4046-182">Kvantová operace mění stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="c4046-183">Někdy se mluví o kvantových hradlech místo kvantových operacích, je totiž možná i analogie s klasickými logickými hradly.</span><span class="sxs-lookup"><span data-stu-id="c4046-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="c4046-184">Tento koncept pochází z raných dob kvantových výpočtů, kdy byly algoritmy jen teoretické konstrukce a vizualizovaly se ve formě schémat odpovídacích obvodovým schématům klasických počítačů.</span><span class="sxs-lookup"><span data-stu-id="c4046-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="c4046-185">Přidání testovacího kódu Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-185">Add Q# test code</span></span>

1. <span data-ttu-id="c4046-186">Přidejte do souboru `Bell.qs` následující operaci, do oboru názvů za konec operace `Set`:</span><span class="sxs-lookup"><span data-stu-id="c4046-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="c4046-187">Tato operace (`TestBellState`) se zopakuje v `count` iteracích, v každé nastaví zadanou hodnotu qubitu `initial` a pak změří výsledek (`M`).</span><span class="sxs-lookup"><span data-stu-id="c4046-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="c4046-188">Shromáždí statistiku o počtu naměřených nul a jedniček a vrátí je volajícímu.</span><span class="sxs-lookup"><span data-stu-id="c4046-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="c4046-189">Provede ale ještě jednu důležitou operaci.</span><span class="sxs-lookup"><span data-stu-id="c4046-189">It performs one other necessary operation.</span></span> <span data-ttu-id="c4046-190">Před návratem resetuje qubit do známého stavu (`Zero`), aby ostatní mohli tento qubit použít ve známém stavu.</span><span class="sxs-lookup"><span data-stu-id="c4046-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="c4046-191">To je provedeno příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="c4046-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="c4046-192">Proměnné v jazyce Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-192">About variables in Q#</span></span>

<span data-ttu-id="c4046-193">Ve výchozím nastavení jsou proměnné v Q# neměnné; po jejich svázání už je nelze změnit.</span><span class="sxs-lookup"><span data-stu-id="c4046-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="c4046-194">Klíčové slovo `let` slouží k označení vazby neměnné proměnné.</span><span class="sxs-lookup"><span data-stu-id="c4046-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="c4046-195">Argumenty operace jsou vždycky neměnné.</span><span class="sxs-lookup"><span data-stu-id="c4046-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="c4046-196">Pokud potřebujete proměnnou, jejíž hodnotu je možné změnit, například `numOnes` v našem příkladu, můžete proměnnou deklarovat pomocí klíčového slova `mutable`.</span><span class="sxs-lookup"><span data-stu-id="c4046-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="c4046-197">Hodnotu proměnlivé proměnné lze změnit pomocí příkazu `set`.</span><span class="sxs-lookup"><span data-stu-id="c4046-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="c4046-198">V obou případech je typ proměnné odvozen kompilátorem.</span><span class="sxs-lookup"><span data-stu-id="c4046-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="c4046-199">Q# nevyžaduje pro proměnné žádné specifikace typu.</span><span class="sxs-lookup"><span data-stu-id="c4046-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="c4046-200">Příkazy `using` v Q#</span><span class="sxs-lookup"><span data-stu-id="c4046-200">About `using` statements in Q#</span></span>

<span data-ttu-id="c4046-201">Příkaz `using` je také jedinečný pro jazyk Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="c4046-202">Slouží k přidělení qubitů pro použití v bloku kódu.</span><span class="sxs-lookup"><span data-stu-id="c4046-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="c4046-203">V Q# se všechny qubity dynamicky přidělují a uvolňují, protože se nejedná o pevné prostředky, které jsou k dispozici pro celou dobu běhu složitého algoritmu.</span><span class="sxs-lookup"><span data-stu-id="c4046-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="c4046-204">Příkaz `using` přidělí sadu qubitů na začátku a uvolní je na konci bloku.</span><span class="sxs-lookup"><span data-stu-id="c4046-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="c4046-205">Vytvořte kód hostitelské aplikace</span><span class="sxs-lookup"><span data-stu-id="c4046-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="c4046-206">Python</span><span class="sxs-lookup"><span data-stu-id="c4046-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="c4046-207">Otevřete soubor `host.py` a přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="c4046-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="c4046-208">C#</span><span class="sxs-lookup"><span data-stu-id="c4046-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="c4046-209">Obsah souboru `Driver.cs` nahraďte následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="c4046-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="c4046-210">Kód hostitelské aplikace</span><span class="sxs-lookup"><span data-stu-id="c4046-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="c4046-211">Python</span><span class="sxs-lookup"><span data-stu-id="c4046-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="c4046-212">Hostitelská aplikace v jazyce Python má tři části:</span><span class="sxs-lookup"><span data-stu-id="c4046-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="c4046-213">Vypočítá všechny argumenty vyžadované pro kvantový algoritmus.</span><span class="sxs-lookup"><span data-stu-id="c4046-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="c4046-214">V příkladu je proměnná `count` nastavena pevně na 1000 a počáteční hodnota qubitu je `initial`.</span><span class="sxs-lookup"><span data-stu-id="c4046-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="c4046-215">Spusťte kvantový algoritmus zavoláním metody `simulate()` importované operace Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="c4046-216">Zpracujte výsledek operace.</span><span class="sxs-lookup"><span data-stu-id="c4046-216">Process the result of the operation.</span></span> <span data-ttu-id="c4046-217">V příkladu bude `res` obsahovat výsledek operace.</span><span class="sxs-lookup"><span data-stu-id="c4046-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="c4046-218">Zde je výsledkem řazená kolekce členů – počet nul (`num_zeros`) a počet jedniček (`num_ones`) změřených simulátorem.</span><span class="sxs-lookup"><span data-stu-id="c4046-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="c4046-219">Z řazené kolekce členů získáme dvě pole a vytiskneme výsledky.</span><span class="sxs-lookup"><span data-stu-id="c4046-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="c4046-220">C#</span><span class="sxs-lookup"><span data-stu-id="c4046-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="c4046-221">Hostitelská aplikace C# má čtyři části:</span><span class="sxs-lookup"><span data-stu-id="c4046-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="c4046-222">Vytvoření kvantového simulátoru.</span><span class="sxs-lookup"><span data-stu-id="c4046-222">Construct a quantum simulator.</span></span> <span data-ttu-id="c4046-223">V tomto příkladu je simulátorem `qsim`.</span><span class="sxs-lookup"><span data-stu-id="c4046-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="c4046-224">Vypočítá všechny argumenty vyžadované pro kvantový algoritmus.</span><span class="sxs-lookup"><span data-stu-id="c4046-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="c4046-225">V příkladu je proměnná `count` nastavena pevně na 1000 a počáteční hodnota qubitu je `initial`.</span><span class="sxs-lookup"><span data-stu-id="c4046-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="c4046-226">Spusťte kvantový algoritmus.</span><span class="sxs-lookup"><span data-stu-id="c4046-226">Run the quantum algorithm.</span></span> <span data-ttu-id="c4046-227">Každá operace Q# vygeneruje třídu C# se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="c4046-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="c4046-228">Tato třída má metodu `Run`, která operaci **asynchronně** provede.</span><span class="sxs-lookup"><span data-stu-id="c4046-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="c4046-229">Spuštění je asynchronní, protože asynchronní bude i spuštění na skutečném hardwaru.</span><span class="sxs-lookup"><span data-stu-id="c4046-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="c4046-230">Vzhledem k tomu, že metoda `Run` je asynchronní, načteme vlastnost `Result`; tím se běh zastaví do doby, dokud se úloha nedokončí a nevrátí výsledek synchronně.</span><span class="sxs-lookup"><span data-stu-id="c4046-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="c4046-231">Zpracujte výsledek operace.</span><span class="sxs-lookup"><span data-stu-id="c4046-231">Process the result of the operation.</span></span> <span data-ttu-id="c4046-232">V příkladu bude `res` obsahovat výsledek operace.</span><span class="sxs-lookup"><span data-stu-id="c4046-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="c4046-233">Zde je výsledkem řazená kolekce členů – počet nul (`numZeros`) a počet jedniček (`numOnes`) změřených simulátorem.</span><span class="sxs-lookup"><span data-stu-id="c4046-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="c4046-234">To se vrátí v C# jako ValueTuple.</span><span class="sxs-lookup"><span data-stu-id="c4046-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="c4046-235">Z řazené kolekce členů získáme dvě pole, vytiskneme výsledky a počkáme na stisk klávesy.</span><span class="sxs-lookup"><span data-stu-id="c4046-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="c4046-236">Sestavení a spuštění</span><span class="sxs-lookup"><span data-stu-id="c4046-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="c4046-237">Python</span><span class="sxs-lookup"><span data-stu-id="c4046-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="c4046-238">Zadejte v okně terminálu následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="c4046-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="c4046-239">Tento příkaz spustí hostitelskou aplikaci, která provede simulaci operace Q#.</span><span class="sxs-lookup"><span data-stu-id="c4046-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="c4046-240">Výsledky by měly být:</span><span class="sxs-lookup"><span data-stu-id="c4046-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c4046-241">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4046-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="c4046-242">Spusťte v okně terminálu následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="c4046-242">Run the following at your terminal:</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="c4046-243">Tento příkaz automaticky stáhne všechny požadované balíčky, sestaví aplikaci a pak ji spustí na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="c4046-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="c4046-244">Případně můžete stisknutím **F1** otevřít paletu příkazů a vybrat **Ladění: Spustit bez ladění.**</span><span class="sxs-lookup"><span data-stu-id="c4046-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="c4046-245">Může se zobrazit výzva k vytvoření nového souboru ``launch.json`` popisujícího spuštění programu.</span><span class="sxs-lookup"><span data-stu-id="c4046-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="c4046-246">Výchozí ``launch.json`` by měl dobře fungovat pro většinu aplikací.</span><span class="sxs-lookup"><span data-stu-id="c4046-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="c4046-247">Výsledky by měly být:</span><span class="sxs-lookup"><span data-stu-id="c4046-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="c4046-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4046-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="c4046-249">Stiskněte `F5` a váš program by měl sestavit a spustit!</span><span class="sxs-lookup"><span data-stu-id="c4046-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="c4046-250">Výsledky by měly být:</span><span class="sxs-lookup"><span data-stu-id="c4046-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="c4046-251">Program se ukončí po stisknutí klávesy.</span><span class="sxs-lookup"><span data-stu-id="c4046-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="c4046-252">Příprava superpozice</span><span class="sxs-lookup"><span data-stu-id="c4046-252">Prepare superposition</span></span>

<span data-ttu-id="c4046-253">**Přehled** Nyní se podíváme na to, jak Q# vyjadřuje způsoby, jak uvést qubity do superpozice.</span><span class="sxs-lookup"><span data-stu-id="c4046-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="c4046-254">Připomeňme si, že stav qubitu může být superpozicí hodnot 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="c4046-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="c4046-255">Dosáhneme toho operací `Hadamard`.</span><span class="sxs-lookup"><span data-stu-id="c4046-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="c4046-256">Pokud je qubit v některém z klasických stavů (kdy měření vrátí vždy `Zero` nebo vždy `One`), pak operace `Hadamard` nebo `H` převede qubit do stavu, ve kterém měření vrátí v 50 % případů `Zero` a v 50 % případů `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="c4046-257">Můžete si to představit tak, že qubit je uprostřed mezi `Zero` a `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="c4046-258">Když teď budeme simulovat operaci `TestBellState`, uvidíme, že jednotlivá měření vrátí přibližně stejný počet hodnot `Zero` a `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="c4046-259">Nejdřív zkusíme qubit překlopit (pokud je qubit ve stavu `Zero`, překlopíme ho na `One` a naopak).</span><span class="sxs-lookup"><span data-stu-id="c4046-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="c4046-260">Toho se dosáhne použitím operace `X` před změřením v operaci `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="c4046-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="c4046-261">Nyní jsou výsledky (po stisknutí `F5`) obrácené:</span><span class="sxs-lookup"><span data-stu-id="c4046-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="c4046-262">Ovšem všechno, co jsme doposud viděli, je klasické.</span><span class="sxs-lookup"><span data-stu-id="c4046-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="c4046-263">Pojďme se dostat ke kvantovým výsledkům.</span><span class="sxs-lookup"><span data-stu-id="c4046-263">Let's get a quantum result.</span></span> <span data-ttu-id="c4046-264">Stačí k tomu nahradit operaci `X` v předchozím běhu operací `H` (Hadamard).</span><span class="sxs-lookup"><span data-stu-id="c4046-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="c4046-265">Místo úplného překlopení qubitu z 0 na 1 ho můžeme překlopit jen napůl.</span><span class="sxs-lookup"><span data-stu-id="c4046-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="c4046-266">Změněné řádky v `TestBellState` teď vypadají takto:</span><span class="sxs-lookup"><span data-stu-id="c4046-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="c4046-267">Teď už výsledky budou zajímavější:</span><span class="sxs-lookup"><span data-stu-id="c4046-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="c4046-268">Každým měřením požádáme o klasickou hodnotu, ale qubit je uprostřed mezi 0 a 1, takže (statisticky) dostaneme v polovině případů 0 a v polovině případů 1.</span><span class="sxs-lookup"><span data-stu-id="c4046-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="c4046-269">To se označuje jako __superpozice__ a je to naše první seznámení s kvantovými stavy.</span><span class="sxs-lookup"><span data-stu-id="c4046-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="c4046-270">Příprava provázání</span><span class="sxs-lookup"><span data-stu-id="c4046-270">Prepare entanglement</span></span>

<span data-ttu-id="c4046-271">**Přehled:**  Teď se podíváme na to, jak se v Q# vyjadřuje kvantové provázání qubitů.</span><span class="sxs-lookup"><span data-stu-id="c4046-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="c4046-272">Nejdřív uvedeme první qubit do počátečního stavu a pak ho pomocí operace `H` převedeme do superpozice.</span><span class="sxs-lookup"><span data-stu-id="c4046-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="c4046-273">Pak před změřením prvního qubitu použijeme novou operaci `CNOT`, což je zkratka pro Controlled-Not, kontrolovanou negaci.</span><span class="sxs-lookup"><span data-stu-id="c4046-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="c4046-274">Výsledkem provedení této operace na dvou qubitech je překlopení druhého qubitu, pokud je první ve stavu `One`.</span><span class="sxs-lookup"><span data-stu-id="c4046-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="c4046-275">Nyní máme dva provázané qubity.</span><span class="sxs-lookup"><span data-stu-id="c4046-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="c4046-276">Statistika prvního qubitu se nezměnila (stále šance 50-50, že měřením získáme `Zero` nebo `One`), ale když teď změříme stav druhého qubitu, bude __vždy__ stejný jako stav naměřený u toho prvního.</span><span class="sxs-lookup"><span data-stu-id="c4046-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="c4046-277">Operace `CNOT` provázala oba qubity, takže cokoli se stane jednomu, stane se i druhému.</span><span class="sxs-lookup"><span data-stu-id="c4046-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="c4046-278">Když pořadí měření otočíme (změříme nejprve druhý a pak první qubit), dostaneme úplně stejný výsledek.</span><span class="sxs-lookup"><span data-stu-id="c4046-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="c4046-279">První měření bude náhodné, ale druhé bude přesně kopírovat výsledek toho prvního.</span><span class="sxs-lookup"><span data-stu-id="c4046-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="c4046-280">První věc, kterou je potřeba udělat, je přidělit v operaci `TestBellState` dva qubity místo jednoho:</span><span class="sxs-lookup"><span data-stu-id="c4046-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="c4046-281">To nám umožní přidat novou operaci (`CNOT`) před změřením (`M`) v operaci `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="c4046-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="c4046-282">Přidali jsme další operaci `Set` inicializující první qubit, abychom se ujistili, že je vždy v počátečním stavu `Zero`.</span><span class="sxs-lookup"><span data-stu-id="c4046-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="c4046-283">Stejně tak musíme resetovat druhý qubit, než ho na konci uvolníme.</span><span class="sxs-lookup"><span data-stu-id="c4046-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="c4046-284">Úplná rutina teď vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="c4046-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="c4046-285">Když ji spustíme, získáme přesně stejný výsledek 50-50, jako předtím.</span><span class="sxs-lookup"><span data-stu-id="c4046-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="c4046-286">Co nás ale zajímá je způsob, jakým druhý qubit reaguje na první měřenou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="c4046-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="c4046-287">Tuto statistiku přidáme s novou verzí operace `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="c4046-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="c4046-288">Nová návratová hodnota (`agree`) počítá případy, kdy se měření prvního qubitu shodovalo s měřením druhého qubitu.</span><span class="sxs-lookup"><span data-stu-id="c4046-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="c4046-289">Také je potřeba odpovídajícím způsobem aktualizovat hostitelskou aplikaci:</span><span class="sxs-lookup"><span data-stu-id="c4046-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="c4046-290">Python</span><span class="sxs-lookup"><span data-stu-id="c4046-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="c4046-291">C#</span><span class="sxs-lookup"><span data-stu-id="c4046-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="c4046-292">Po spuštění dostaneme moc zajímavý výsledek:</span><span class="sxs-lookup"><span data-stu-id="c4046-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="c4046-293">Jak jsme uvedli v přehledu, statistika prvního qubitu se nezměnila (stále šance 50:50, že získáme 0 nebo 1), ale teď když změříme stav druhého qubitu, bude __vždy__ stejný, jako změřený stav toho prvního, protože jsou provázané!</span><span class="sxs-lookup"><span data-stu-id="c4046-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="c4046-294">Blahopřejeme, napsali jste svůj první kvantový program!</span><span class="sxs-lookup"><span data-stu-id="c4046-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="whats-next"></a><span data-ttu-id="c4046-295">Co dále?</span><span class="sxs-lookup"><span data-stu-id="c4046-295">What's next?</span></span>

<span data-ttu-id="c4046-296">Kurz [Groverův vyhledávací algoritmus](xref:microsoft.quantum.quickstarts.search) vám ukáže, jak implementovat a spustit Groverovo vyhledávání, jeden z nejoblíbenějších kvantových výpočetních algoritmů, a nabízí dobrý příklad programu Q#, který se dá použít k řešení reálných problémů pomocí kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="c4046-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="c4046-297">Dokument [Začínáme se sadou Quantum Development Kit](xref:microsoft.quantum.welcome) vám nabídne další způsoby, jak se seznámit s jazykem Q# a kvantovými programy.</span><span class="sxs-lookup"><span data-stu-id="c4046-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>


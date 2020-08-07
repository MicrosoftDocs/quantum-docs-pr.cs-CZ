---
title: Zápis a simulace programů na úrovni qubit v nástrojiQ#
description: Podrobný návod k psaní a simulaci programu pro období, který funguje na úrovni jednotlivých qubit
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 22c79e4e01db1a0d0c291d0dcff81dbfa8df5cd3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869711"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="b7c02-103">Kurz: zápis a simulace programů qubit na úrovni Q\#</span><span class="sxs-lookup"><span data-stu-id="b7c02-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="b7c02-104">Vítá vás kurz pro vývoj všech automobilů při psaní a simulaci základního programu pro vyhlašování do více období, který funguje na jednotlivých qubits.</span><span class="sxs-lookup"><span data-stu-id="b7c02-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="b7c02-105">I když Q# byl primárně vytvořen jako programovací jazyk vysoké úrovně pro velké množství procesorových procesorů, může to být stejně snadné použít k prozkoumávání nižší úrovně programů, které jsou určeny k tomu, že přímo řeší konkrétní qubits.</span><span class="sxs-lookup"><span data-stu-id="b7c02-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="b7c02-106">Flexibilita Q# umožňuje uživatelům přístup k systémům z nedostatku z jakékoli takové úrovně abstrakce a v tomto kurzu jsme podrobněi qubits sami.</span><span class="sxs-lookup"><span data-stu-id="b7c02-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="b7c02-107">Konkrétně se podívejme na digestoři [Fourierova transformace](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), která je nedílnou součástí mnoha větších algoritmů.</span><span class="sxs-lookup"><span data-stu-id="b7c02-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="b7c02-108">Všimněte si, že tento přehled zpracování informací o nedostatku na více procesorů je často popsaný v části "[okruhy](xref:microsoft.quantum.concepts.circuits)v obdobích", což představuje sekvenční použití bran na konkrétní qubits systému.</span><span class="sxs-lookup"><span data-stu-id="b7c02-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="b7c02-109">Operace typu Single-a qubit, které se účtují sekvenčně, se proto dají snadno reprezentovat v "diagramu okruhu".</span><span class="sxs-lookup"><span data-stu-id="b7c02-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="b7c02-110">V našem případě definujeme Q# operaci, která provede úplnou qubitou transformaci na tři procesory, která má následující reprezentaci jako okruh:</span><span class="sxs-lookup"><span data-stu-id="b7c02-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="b7c02-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b7c02-111">Prerequisites</span></span>

* <span data-ttu-id="b7c02-112">[Nainstalujte](xref:microsoft.quantum.install) sadu pro vývoj pro práci s více jazyky pomocí vašeho preferovaného jazykového a vývojového prostředí.</span><span class="sxs-lookup"><span data-stu-id="b7c02-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="b7c02-113">Pokud už máte sadu QDK nainstalovanou, zkontrolujte, že je [aktualizovaná na nejnovější verzi](xref:microsoft.quantum.update)</span><span class="sxs-lookup"><span data-stu-id="b7c02-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="b7c02-114">V tomto kurzu se naučíte:</span><span class="sxs-lookup"><span data-stu-id="b7c02-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b7c02-115">Definování operací s více operačními operacemi vQ#</span><span class="sxs-lookup"><span data-stu-id="b7c02-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="b7c02-116">Volání Q# operací přímo z příkazového řádku nebo pomocí klasického hostitelského programu</span><span class="sxs-lookup"><span data-stu-id="b7c02-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="b7c02-117">Simulace operace s příchodem z přidělení qubit na výstup měření</span><span class="sxs-lookup"><span data-stu-id="b7c02-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="b7c02-118">Sledujte, jak se v průběhu operace vyvíjí simulovaný wavefunction systému</span><span class="sxs-lookup"><span data-stu-id="b7c02-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="b7c02-119">Běh programu pro práci s více operačními systémy od Microsoftu se bude obvykle skládat ze dvou částí:</span><span class="sxs-lookup"><span data-stu-id="b7c02-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="b7c02-120">Samotný program, který je implementován pomocí programovacího jazyka pro práci po sobě Q# a následně vyvolán ke spuštění na počítači s více operačními systémy nebo simulátoru provozu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="b7c02-121">Ty se skládají z</span><span class="sxs-lookup"><span data-stu-id="b7c02-121">These consist of</span></span> 
    - <span data-ttu-id="b7c02-122">Q#operace: podrutiny fungující na registrech v případě nečinnosti</span><span class="sxs-lookup"><span data-stu-id="b7c02-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="b7c02-123">Q#Functions: klasické podrutiny používané v rámci algoritmu doby.</span><span class="sxs-lookup"><span data-stu-id="b7c02-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="b7c02-124">Vstupní bod, který slouží k volání programu pro práci s poli, a určení cílového počítače, na kterém by měl být spuštěn.</span><span class="sxs-lookup"><span data-stu-id="b7c02-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="b7c02-125">To lze provést přímo z příkazového řádku nebo prostřednictvím hostitelského programu napsaného v klasickém programovacím jazyce, jako je Python nebo C#.</span><span class="sxs-lookup"><span data-stu-id="b7c02-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="b7c02-126">Tento kurz obsahuje pokyny pro libovolný způsob, kterým dáváte přednost.</span><span class="sxs-lookup"><span data-stu-id="b7c02-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="b7c02-127">Přidělte qubits a definujte operace</span><span class="sxs-lookup"><span data-stu-id="b7c02-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="b7c02-128">První část tohoto kurzu se skládá z definice Q# operace `Perform3qubitQFT` , která provádí funkci Fourierova transformace na třech qubits.</span><span class="sxs-lookup"><span data-stu-id="b7c02-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="b7c02-129">Kromě toho budeme pomocí této [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) funkce sledovat, jak se simulované wavefunctiony našeho tří systémů qubit v rámci operace vyvíjely.</span><span class="sxs-lookup"><span data-stu-id="b7c02-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="b7c02-130">Prvním krokem je vytvoření Q# projektu a souboru.</span><span class="sxs-lookup"><span data-stu-id="b7c02-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="b7c02-131">Postup pro tyto kroky závisí na prostředí, které použijete pro volání programu, a podrobnosti najdete v příslušných [pokynech k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b7c02-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b7c02-132">Provedeme vás jednotlivými komponentami souboru, ale kód je také k dispozici jako úplný blok níže.</span><span class="sxs-lookup"><span data-stu-id="b7c02-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-no-locq-operations"></a><span data-ttu-id="b7c02-133">Obory názvů pro přístup k jiným Q# operacím</span><span class="sxs-lookup"><span data-stu-id="b7c02-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="b7c02-134">V souboru nejdřív nadefinujeme obor názvů, ke `NamespaceQFT` kterému bude mít kompilátor přistup.</span><span class="sxs-lookup"><span data-stu-id="b7c02-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="b7c02-135">Abychom mohli využít stávající Q# operace, otevřou se příslušné `Microsoft.Quantum.<>` obory názvů.</span><span class="sxs-lookup"><span data-stu-id="b7c02-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="b7c02-136">Definovat operace s argumenty a vrácení</span><span class="sxs-lookup"><span data-stu-id="b7c02-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="b7c02-137">Dále definujeme `Perform3qubitQFT` operaci:</span><span class="sxs-lookup"><span data-stu-id="b7c02-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="b7c02-138">V současné době operace přebírá žádné argumenty a nevrátí nic---v tomto případě zapíšeme, že vrátí `Unit` objekt, který je podobají `void` v jazyce C# nebo prázdná řazená kolekce členů `Tuple[()]` v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="b7c02-139">Později ji Upravme, aby vracela pole výsledků měření. v tomto okamžiku se `Unit` nahradí `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="b7c02-140">Přidělit qubits pomocí`using`</span><span class="sxs-lookup"><span data-stu-id="b7c02-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="b7c02-141">V rámci naší Q# operace nejprve přidělíme registraci tří qubits pomocí `using` příkazu:</span><span class="sxs-lookup"><span data-stu-id="b7c02-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="b7c02-142">V `using` případě se qubits automaticky přiřazují ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b7c02-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="b7c02-143">Můžete to ověřit pomocí [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) a [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , který vypíše řetězec a aktuální stav systému do konzoly.</span><span class="sxs-lookup"><span data-stu-id="b7c02-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c02-144">`Message(<string>)`Funkce a `DumpMachine()` (v [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) uvedeném pořadí) se tisknou přímo do konzoly.</span><span class="sxs-lookup"><span data-stu-id="b7c02-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="b7c02-145">Stejně jako u reálných výpočetních Q# stavů neumožňuje přímý přístup ke qubit státům.</span><span class="sxs-lookup"><span data-stu-id="b7c02-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="b7c02-146">`DumpMachine`Když ale vytisknete aktuální stav cílového počítače, může poskytnout cenné informace pro ladění a učení při použití ve spojení s simulátorem úplného stavu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="b7c02-147">Použití jednoduchých qubit a řízených bran</span><span class="sxs-lookup"><span data-stu-id="b7c02-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="b7c02-148">V dalším kroku použijeme brány, které tvoří samotnou operaci.</span><span class="sxs-lookup"><span data-stu-id="b7c02-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="b7c02-149">Q#již obsahuje mnoho základních bran jako operací v [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) oboru názvů a nejsou to žádné výjimky.</span><span class="sxs-lookup"><span data-stu-id="b7c02-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="b7c02-150">V rámci Q# operace se příkazy, které volají volání, spustí v sekvenčním pořadí.</span><span class="sxs-lookup"><span data-stu-id="b7c02-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="b7c02-151">Proto první brána, která se má použít, je [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) na první qubit:</span><span class="sxs-lookup"><span data-stu-id="b7c02-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="b7c02-152">Pro použití operace na konkrétní qubit z registru (tj. jedna `Qubit` z pole `Qubit[]` ) používáme zápis standardního indexu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="b7c02-153">Proto použití pro na [`H`](xref:microsoft.quantum.intrinsic.h) první qubit našeho registru má `qs` podobu:</span><span class="sxs-lookup"><span data-stu-id="b7c02-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="b7c02-154">Kromě použití `H` brány (Hadamard) pro jednotlivé qubits se okruh QFT skládá hlavně z řízených [`R1`](xref:microsoft.quantum.intrinsic.r1) otočení.</span><span class="sxs-lookup"><span data-stu-id="b7c02-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="b7c02-155">`R1(θ, <qubit>)`Operace obecně ponechá součást $ \ket {0} $ qubit beze změny a při použití rotace $e ^ {i\theta} $ na součást $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="b7c02-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="b7c02-156">Kontrolované operace</span><span class="sxs-lookup"><span data-stu-id="b7c02-156">Controlled operations</span></span>

<span data-ttu-id="b7c02-157">Q#je velmi snadné podmínkou provedení operace na jednom nebo několika qubits ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="b7c02-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="b7c02-158">Obecně jsme zavedli pouze volání s `Controlled` a argumenty operace se mění jako:</span><span class="sxs-lookup"><span data-stu-id="b7c02-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="b7c02-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="b7c02-160">Všimněte si, že qubits ovládacího prvku musí být poskytnut jako pole, i když se jedná o jediný qubit.</span><span class="sxs-lookup"><span data-stu-id="b7c02-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="b7c02-161">Po `H` , uvidíme, že další brány jsou `R1` brány působící na první qubit (a řízená druhou/třetí):</span><span class="sxs-lookup"><span data-stu-id="b7c02-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="b7c02-162">Budeme je volat pomocí</span><span class="sxs-lookup"><span data-stu-id="b7c02-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="b7c02-163">Všimněte si, že používáme [`PI()`](xref:microsoft.quantum.math.pi) funkci z [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) oboru názvů k definování otočení v souvislosti s pí radiány.</span><span class="sxs-lookup"><span data-stu-id="b7c02-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="b7c02-164">Kromě toho jsme vydělíme `Double` (např. `2.0` ), protože rozdělením pomocí celého čísla `2` by vyvolalo chybu typu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="b7c02-165">`R1(π/2)`a `R1(π/4)` jsou ekvivalentem `S` operací a `T` (také v `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="b7c02-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="b7c02-166">Po použití relevantních `H` operací a řízených otočení na druhý a třetí qubits:</span><span class="sxs-lookup"><span data-stu-id="b7c02-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="b7c02-167">[`SWAP`](xref:microsoft.quantum.intrinsic.swap)pro dokončení okruhu musíme použít jenom bránu:</span><span class="sxs-lookup"><span data-stu-id="b7c02-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="b7c02-168">To je nezbytné vzhledem k tomu, že povaha Fourierova transformace vrací qubits v obráceném pořadí, takže swapy umožňují bezproblémovou integraci subrutiny do větších algoritmů.</span><span class="sxs-lookup"><span data-stu-id="b7c02-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="b7c02-169">Proto jsme dokončili vytváření qubit operací na úrovni, které je potřeba transformovat, do naší Q# operace:</span><span class="sxs-lookup"><span data-stu-id="b7c02-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="b7c02-170">Nemůžeme ho ale ještě zavolat na den.</span><span class="sxs-lookup"><span data-stu-id="b7c02-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="b7c02-171">Naše qubits byly ve stavu $ \ket {0} $, když je jsme jim přiřadili a podobně jako v životě Q# byste měli mít stejné možnosti jako v případě, že jsme je našli (nebo lepší!).</span><span class="sxs-lookup"><span data-stu-id="b7c02-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="b7c02-172">Zrušit přidělení qubits</span><span class="sxs-lookup"><span data-stu-id="b7c02-172">Deallocate qubits</span></span>

<span data-ttu-id="b7c02-173">Znovu se zavoláme [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , aby se zobrazil stav po operaci, a nakonec se v [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) registru qubit resetuje náš qubits na $ \ket {0} $, než se dokončí operace:</span><span class="sxs-lookup"><span data-stu-id="b7c02-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="b7c02-174">Vyžadování, aby všechny navrácené qubits byly explicitně nastavené na $ \ket {0} $, je základní funkcí Q# nástroje, protože umožňuje jiným operacím přesně znát jejich stav, když začnou používat stejné qubits (prostředek omezených).</span><span class="sxs-lookup"><span data-stu-id="b7c02-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="b7c02-175">Navíc to zaručuje, že nebudou entangled s žádným jiným qubits v systému.</span><span class="sxs-lookup"><span data-stu-id="b7c02-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="b7c02-176">Pokud se resetování neprovede na konci `using` bloku přidělení, bude vyvolána Běhová chyba.</span><span class="sxs-lookup"><span data-stu-id="b7c02-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="b7c02-177">Úplný Q# soubor by teď měl vypadat takto:</span><span class="sxs-lookup"><span data-stu-id="b7c02-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="b7c02-178">Po Q# dokončení souboru a operace je náš program pro práci s více operačními systémem připravený k volání a simulaci.</span><span class="sxs-lookup"><span data-stu-id="b7c02-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="b7c02-179">Spuštění programu</span><span class="sxs-lookup"><span data-stu-id="b7c02-179">Execute the program</span></span>

<span data-ttu-id="b7c02-180">Po definování naší Q# operace v `.qs` souboru teď musíme tuto operaci zavolat a sledovat všechna vrácená klasická data.</span><span class="sxs-lookup"><span data-stu-id="b7c02-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="b7c02-181">V současné době se nevrátí nic (odvolání této operace definované výše `Unit` ), ale když později tuto operaci upravíte, Q# aby vracela pole výsledků měření ( `Result[]` ), budeme na to řešit.</span><span class="sxs-lookup"><span data-stu-id="b7c02-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="b7c02-182">I když Q# je program všudypřítomný napříč prostředími používanými k jeho volání, tak se takovým způsobem bude samozřejmě lišit.</span><span class="sxs-lookup"><span data-stu-id="b7c02-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="b7c02-183">Stačí postupovat podle pokynů na kartě, která odpovídá vaší instalaci: pracuje z Q# aplikace příkazového řádku nebo používá hostitelský program v Pythonu nebo C#.</span><span class="sxs-lookup"><span data-stu-id="b7c02-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="b7c02-184">Příkazový řádek</span><span class="sxs-lookup"><span data-stu-id="b7c02-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b7c02-185">Spuštění Q# programu z příkazového řádku vyžaduje pouze malou změnu Q# souboru.</span><span class="sxs-lookup"><span data-stu-id="b7c02-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="b7c02-186">Jednoduše přidejte `@EntryPoint()` na řádek před definici operace:</span><span class="sxs-lookup"><span data-stu-id="b7c02-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="b7c02-187">Chcete-li spustit program, otevřete terminál ve složce projektu a zadejte</span><span class="sxs-lookup"><span data-stu-id="b7c02-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="b7c02-188">Po spuštění byste měli vidět `Message` `DumpMachine` výstupy a níže vytisknuté ve vaší konzole.</span><span class="sxs-lookup"><span data-stu-id="b7c02-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="b7c02-189">Python</span><span class="sxs-lookup"><span data-stu-id="b7c02-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="b7c02-190">Vytvořit soubor hostitele Pythonu: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="b7c02-191">Hostitelský soubor je vytvořen takto:</span><span class="sxs-lookup"><span data-stu-id="b7c02-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="b7c02-192">Nejdřív naimportujeme `qsharp` modul, který registruje zavaděč modulu pro Q# interoperabilitu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="b7c02-193">To umožňuje Q# obory názvů (například `NamespaceQFT` jsme definovali v našem Q# souboru), aby se zobrazily jako moduly Pythonu, ze kterých můžeme importovat Q# operace.</span><span class="sxs-lookup"><span data-stu-id="b7c02-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="b7c02-194">Pak importujte Q# operace, které v tomto případě přímo vyvoláme--- `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="b7c02-195">Je potřeba importovat vstupní bod do Q# programu (tj. _nejedná_ se o operace `H` , jako `R1` jsou a, které jsou volány jinými Q# operacemi, ale nikdy klasickým hostitelem).</span><span class="sxs-lookup"><span data-stu-id="b7c02-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="b7c02-196">Při simulaci Q# operací nebo funkcí použijte formulář `<Q#callable>.simulate(<args>)` ke spuštění na `QuantumSimulator()` cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="b7c02-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7c02-197">Pokud jsme chtěli volat operaci na jiném počítači, například `ResourceEstimator()` prostě, můžeme použít `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="b7c02-198">Obecně platí, Q# že operace se nezávislá na počítače, na kterých jsou spuštěny, ale některé funkce se `DumpMachine` mohou chovat jinak.</span><span class="sxs-lookup"><span data-stu-id="b7c02-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="b7c02-199">Po vykonání simulace vrátí volání operace hodnoty, jak je definováno v Q# souboru.</span><span class="sxs-lookup"><span data-stu-id="b7c02-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="b7c02-200">V případě, že se teď nic nevrátí, ale později se vám zobrazí příklad přiřazení a zpracování těchto hodnot.</span><span class="sxs-lookup"><span data-stu-id="b7c02-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="b7c02-201">Díky tomu, že jsou výsledná data v našich rukou i zcela klasická, můžeme s ní dělat jakékoli věci.</span><span class="sxs-lookup"><span data-stu-id="b7c02-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="b7c02-202">Úplný `host.py` soubor by měl být následující:</span><span class="sxs-lookup"><span data-stu-id="b7c02-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="b7c02-203">Spusťte soubor Pythonu a vytisknutý ve vaší konzole byste měli vidět `Message` `DumpMachine` níže uvedené výstupy a.</span><span class="sxs-lookup"><span data-stu-id="b7c02-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="b7c02-204">C#</span><span class="sxs-lookup"><span data-stu-id="b7c02-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b7c02-205">Podle stejných pokynů jako v [instalační příručce](xref:microsoft.quantum.install.cs)vytvořte soubor hostitele v jazyce C# a přejmenujte ho na `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="b7c02-206">Hostitel C# má čtyři části:</span><span class="sxs-lookup"><span data-stu-id="b7c02-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="b7c02-207">Vytvoření kvantového simulátoru.</span><span class="sxs-lookup"><span data-stu-id="b7c02-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="b7c02-208">V následujícím kódu je to proměnná `qsim` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="b7c02-209">Vypočítá všechny argumenty vyžadované pro kvantový algoritmus.</span><span class="sxs-lookup"><span data-stu-id="b7c02-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="b7c02-210">V tomto příkladu nejsou žádné.</span><span class="sxs-lookup"><span data-stu-id="b7c02-210">There are none in this example.</span></span>
3. <span data-ttu-id="b7c02-211">Spusťte kvantový algoritmus.</span><span class="sxs-lookup"><span data-stu-id="b7c02-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="b7c02-212">Každá Q# operace vygeneruje třídu jazyka C# se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="b7c02-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="b7c02-213">Tato třída má metodu `Run`, která operaci **asynchronně** provede.</span><span class="sxs-lookup"><span data-stu-id="b7c02-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="b7c02-214">Spuštění je asynchronní, protože asynchronní bude i spuštění na skutečném hardwaru.</span><span class="sxs-lookup"><span data-stu-id="b7c02-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="b7c02-215">Vzhledem k tomu `Run` , že metoda je asynchronní, zavoláme `Wait()` metodu; tyto bloky se spustí, dokud se úloha nedokončí a výsledek vrátí synchronně.</span><span class="sxs-lookup"><span data-stu-id="b7c02-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="b7c02-216">Zpracování vráceného výsledku operace.</span><span class="sxs-lookup"><span data-stu-id="b7c02-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="b7c02-217">V současné době operace nevrátí žádnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="b7c02-218">Spusťte aplikaci a váš výstup by měl odpovídat následujícímu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="b7c02-219">Program se ukončí po stisknutí klávesy.</span><span class="sxs-lookup"><span data-stu-id="b7c02-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="b7c02-220">Při volání na plný stav simulátoru `DumpMachine()` poskytuje tyto několik reprezentace wavefunction stavu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="b7c02-221">Možné stavy $n $-qubit systému můžou být reprezentovány pomocí výpočetních stavů $2 ^ n $, každý s odpovídajícím komplexním koeficientem (jenom amplitudou a fází).</span><span class="sxs-lookup"><span data-stu-id="b7c02-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="b7c02-222">Výpočetní stavy odpovídají všem možným binárním řetězcům s délkou $n $---to znamená všechny možné kombinace qubit stavů $ \ket {0} $ a $ \ket {1} $, kde každá binární číslice odpovídá individuálnímu qubit.</span><span class="sxs-lookup"><span data-stu-id="b7c02-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="b7c02-223">První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.</span><span class="sxs-lookup"><span data-stu-id="b7c02-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="b7c02-224">Qubit je `2` "nejvýznamnější" jednoduše znamená, že v binárním vyjádření základního stavu Vector $ \ket{i} $ je stav qubit `2` odpovídá číslici vlevo.</span><span class="sxs-lookup"><span data-stu-id="b7c02-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="b7c02-225">Například $ \ket {6} = \ket {110} $ zahrnuje qubits `2` a v $ `1` \ket {1} $ a qubit `0` v $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b7c02-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="b7c02-226">Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{i} $ v kartézském a polárních formátech.</span><span class="sxs-lookup"><span data-stu-id="b7c02-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="b7c02-227">Podrobnosti o prvním řádku našeho vstupního stavu $ \ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="b7c02-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="b7c02-228">**`|0>:`** Tento řádek odpovídá `0` výpočetnímu stavu (vzhledem k tomu, že naše počáteční přidělení stavu bylo $ \ket {000} $, očekávalo se, že by to byl jediný stav s amplitudou pravděpodobnosti v tomto okamžiku).</span><span class="sxs-lookup"><span data-stu-id="b7c02-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="b7c02-229">**`1.000000 +  0.000000 i`**: amplituda pravděpodobnosti ve formátu kartézském.</span><span class="sxs-lookup"><span data-stu-id="b7c02-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="b7c02-230">**` == `**: `equal` znaménko odděluje rovnocenné reprezentace.</span><span class="sxs-lookup"><span data-stu-id="b7c02-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="b7c02-231">**`********************`**: Grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="b7c02-232">**`[ 1.000000 ]`**: číselná hodnota velikosti</span><span class="sxs-lookup"><span data-stu-id="b7c02-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="b7c02-233">**`    ---`**: Grafická reprezentace fáze amplitudy.</span><span class="sxs-lookup"><span data-stu-id="b7c02-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="b7c02-234">**`[ 0.0000 rad ]`**: číselná hodnota fáze (v radiánech).</span><span class="sxs-lookup"><span data-stu-id="b7c02-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="b7c02-235">Velikost i fáze se zobrazí s grafickým znázorněním.</span><span class="sxs-lookup"><span data-stu-id="b7c02-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="b7c02-236">Reprezentace velikosti je jednoduchá: zobrazuje pruh `*` a čím vyšší je pravděpodobnost, tím větší bude pruh.</span><span class="sxs-lookup"><span data-stu-id="b7c02-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="b7c02-237">Pro fázi si přečtěte téma [testování a ladění: funkce výpisu](xref:microsoft.quantum.guide.testingdebugging#dump-functions) pro možné reprezentace symbolů na základě rozsahů úhlů.</span><span class="sxs-lookup"><span data-stu-id="b7c02-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="b7c02-238">Vytištěný výstup tedy ilustruje, že naše naprogramované brány transformují náš stav z</span><span class="sxs-lookup"><span data-stu-id="b7c02-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="b7c02-239">$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="b7c02-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="b7c02-240">na</span><span class="sxs-lookup"><span data-stu-id="b7c02-240">to</span></span> 

<span data-ttu-id="b7c02-241">$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n} \sum \ket{j} \_ {j = 0} ^ {2 ^ n-1} \end{align}, $ $</span><span class="sxs-lookup"><span data-stu-id="b7c02-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="b7c02-242">což je přesné chování 3-qubit Fourierova transformace.</span><span class="sxs-lookup"><span data-stu-id="b7c02-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="b7c02-243">Pokud jste zajímái o tom, jak jsou ovlivněny další vstupní stavy, doporučujeme, abyste se přehráli s použitím operací qubit před transformací.</span><span class="sxs-lookup"><span data-stu-id="b7c02-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="b7c02-244">Přidávání měření</span><span class="sxs-lookup"><span data-stu-id="b7c02-244">Adding measurements</span></span>

<span data-ttu-id="b7c02-245">Bohužel, na základě základu nečinnosti oznamujeme, že skutečný systém pro plnění do něj nemůže mít takovou `DumpMachine` funkci.</span><span class="sxs-lookup"><span data-stu-id="b7c02-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="b7c02-246">Místo toho je nutné extrahovat informace prostřednictvím měření, což obecně nestačí pouze v plném rozsahu, ale může také významně změnit samotný systém.</span><span class="sxs-lookup"><span data-stu-id="b7c02-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="b7c02-247">Existuje mnoho druhů měření doby plnění, ale u jednotlivých qubits se zaměříme na nejvíc základní: měření při projekci.</span><span class="sxs-lookup"><span data-stu-id="b7c02-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="b7c02-248">Po měření v daném základu (např. výpočetního základu $ \{ \ket {0} , \ket {1} \} $) se stav qubit prochází na základě stavu, který se měří,---proto zničení všech dvou míst.</span><span class="sxs-lookup"><span data-stu-id="b7c02-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="b7c02-249">K implementaci měření v rámci Q# programu používáme `M` operaci (z `Microsoft.Quantum.Intrinsic` ), která vrací `Result` typ.</span><span class="sxs-lookup"><span data-stu-id="b7c02-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="b7c02-250">Nejdřív jsme tuto operaci změnili `Perform3QubitQFT` tak, aby vracela pole výsledků měření, `Result[]` a ne `Unit` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="b7c02-251">Definovat a inicializovat `Result[]` pole</span><span class="sxs-lookup"><span data-stu-id="b7c02-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="b7c02-252">Před tím, než se přidělí qubits (tj. před `using` příkazem), deklarujeme a navážeme toto pole length-3 (jedna `Result` pro každý qubit):</span><span class="sxs-lookup"><span data-stu-id="b7c02-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="b7c02-253">`mutable`Klíčové slovo `resultArray` , které předkládá, umožňuje, aby proměnná byla později převázána v kódu---například při přidávání výsledků měření.</span><span class="sxs-lookup"><span data-stu-id="b7c02-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="b7c02-254">Provádění měření ve `for` smyčce a přidání výsledků do pole</span><span class="sxs-lookup"><span data-stu-id="b7c02-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="b7c02-255">Po operacích Fourierova transformace uvnitř `using` bloku vložte následující kód:</span><span class="sxs-lookup"><span data-stu-id="b7c02-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="b7c02-256">[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Funkce volaná na poli (například naše pole qubits, `qs` ) vrací rozsah v rámci indexů pole.</span><span class="sxs-lookup"><span data-stu-id="b7c02-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="b7c02-257">Tady ho v naší smyčce používáme `for` k sekvenčnímu měření jednotlivých qubit pomocí `M(qs[i])` příkazu.</span><span class="sxs-lookup"><span data-stu-id="b7c02-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="b7c02-258">Každý měřený `Result` typ (buď `Zero` nebo `One` ) je poté přidán do odpovídající pozice indexu v `resultArray` příkazu s příkazem Update-a-Reassign.</span><span class="sxs-lookup"><span data-stu-id="b7c02-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c02-259">Syntaxe tohoto příkazu je jedinečná pro Q# , ale odpovídá podobné změně přiřazení proměnné `resultArray[i] <- M(qs[i])` v jiných jazycích, například F # a R.</span><span class="sxs-lookup"><span data-stu-id="b7c02-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="b7c02-260">Klíčové slovo `set` se vždycky používá k opětovnému přiřazení proměnných vázaných pomocí `mutable` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="b7c02-261">Vrátit`resultArray`</span><span class="sxs-lookup"><span data-stu-id="b7c02-261">Return `resultArray`</span></span>

<span data-ttu-id="b7c02-262">Se všemi třemi qubitsy změřenými a výsledky přidanými do je `resultArray` bezpečné resetování a navrácení qubits jako dříve.</span><span class="sxs-lookup"><span data-stu-id="b7c02-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="b7c02-263">Po `using` zavření bloku vložte</span><span class="sxs-lookup"><span data-stu-id="b7c02-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="b7c02-264">nakonec vrátí výstup naší operace.</span><span class="sxs-lookup"><span data-stu-id="b7c02-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="b7c02-265">Porozumění efektům měření</span><span class="sxs-lookup"><span data-stu-id="b7c02-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="b7c02-266">Pojďme změnit umístění našich `DumpMachine` funkcí na výstup stavu před a po měření.</span><span class="sxs-lookup"><span data-stu-id="b7c02-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="b7c02-267">Kód poslední operace by měl vypadat takto:</span><span class="sxs-lookup"><span data-stu-id="b7c02-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="b7c02-268">Pokud pracujete z příkazového řádku, vrácené pole bude jednoduše vytištěno přímo do konzoly na konci provádění.</span><span class="sxs-lookup"><span data-stu-id="b7c02-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="b7c02-269">V opačném případě aktualizujte hostitelský program pro zpracování vráceného pole.</span><span class="sxs-lookup"><span data-stu-id="b7c02-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="b7c02-270">Příkazový řádek</span><span class="sxs-lookup"><span data-stu-id="b7c02-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b7c02-271">Aby bylo možné porozumět vrácenému poli, které bude vytištěno v konzole, můžeme do souboru přidat další `Message` do Q# příkazu těsně před `return` příkazem:</span><span class="sxs-lookup"><span data-stu-id="b7c02-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="b7c02-272">Spusťte projekt a váš výstup by měl vypadat nějak takto:</span><span class="sxs-lookup"><span data-stu-id="b7c02-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="b7c02-273">Python</span><span class="sxs-lookup"><span data-stu-id="b7c02-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="b7c02-274">Aktualizujte program Pythonu následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="b7c02-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="b7c02-275">Spusťte soubor a váš výstup by měl vypadat nějak takto:</span><span class="sxs-lookup"><span data-stu-id="b7c02-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="b7c02-276">C#</span><span class="sxs-lookup"><span data-stu-id="b7c02-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b7c02-277">Teď, když naše operace vrací výsledek, nahraďte volání metody `Wait()` načtením `Result` Vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b7c02-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="b7c02-278">Tím se stále doplní stejný synchronicity, který jsme projednali dříve, a můžeme přímo navazovat tuto hodnotu na proměnnou `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="b7c02-279">Spusťte projekt a váš výstup by měl vypadat nějak takto:</span><span class="sxs-lookup"><span data-stu-id="b7c02-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="b7c02-280">Tento výstup znázorňuje několik různých věcí:</span><span class="sxs-lookup"><span data-stu-id="b7c02-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="b7c02-281">Porovnání vráceného výsledku s předměřením `DumpMachine` jasně neilustruje QFTou polohu nad základními stavy. _not_</span><span class="sxs-lookup"><span data-stu-id="b7c02-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="b7c02-282">Měření vrací jenom jeden základní stav s pravděpodobností určenou amplitudou tohoto stavu v wavefunction systému.</span><span class="sxs-lookup"><span data-stu-id="b7c02-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="b7c02-283">Od po měření `DumpMachine` vidíte, že měření _mění_ samotný stav a prochází je od počátečního umístění v rámci jednotlivých stavů do jediného základního stavu, který odpovídá měřené hodnotě.</span><span class="sxs-lookup"><span data-stu-id="b7c02-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="b7c02-284">Pokud bychom tuto operaci opakovali mnohokrát, poznamenali jsme, že se výsledky začnou začínat, aby se zobrazila rovnoměrně vážená pozice stavu post-QFT. Výsledkem je náhodný výsledek u každého snímku.</span><span class="sxs-lookup"><span data-stu-id="b7c02-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="b7c02-285">_Nicméně_, kromě neefektivních a stále dokonalé, by však došlo pouze k reprodukování relativních amplitud základních stavů, nikoli mezi jejich relativními fázemi.</span><span class="sxs-lookup"><span data-stu-id="b7c02-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="b7c02-286">V tomto příkladu se nejedná o problém, ale v případě složitějšího vstupu do QFT než $ \ket $ by se zobrazily relativní fáze {000} .</span><span class="sxs-lookup"><span data-stu-id="b7c02-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="b7c02-287">Částečná měření</span><span class="sxs-lookup"><span data-stu-id="b7c02-287">Partial measurements</span></span> 
<span data-ttu-id="b7c02-288">Chcete-li prozkoumat, jak měření pouze některých qubits registru může ovlivnit stav systému, zkuste přidat následující dovnitř `for` smyčky za řádek měření:</span><span class="sxs-lookup"><span data-stu-id="b7c02-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="b7c02-289">Všimněte si, že pro přístup k této `IntAsString` funkci budete muset přidat</span><span class="sxs-lookup"><span data-stu-id="b7c02-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="b7c02-290">se zbytkem příkazů oboru názvů `open` .</span><span class="sxs-lookup"><span data-stu-id="b7c02-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="b7c02-291">Ve výsledném výstupu se při měření jednotlivých qubit zobrazí postupná projekce na podprostory.</span><span class="sxs-lookup"><span data-stu-id="b7c02-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-no-locq-libraries"></a><span data-ttu-id="b7c02-292">Použití Q# knihoven</span><span class="sxs-lookup"><span data-stu-id="b7c02-292">Use the Q# libraries</span></span>
<span data-ttu-id="b7c02-293">Jak jsme se už zmínili v úvodu, mnoho z Q# nich je ve skutečnosti, že vám umožní abstrakci vypořádat se s jednotlivými qubits.</span><span class="sxs-lookup"><span data-stu-id="b7c02-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="b7c02-294">V případě, že chcete vyvíjet plně škálovatelné programy pro práci s více procesory, je třeba se obávat, zda `H` operace proběhne před nebo po určitém otočení, pouze zpomalení.</span><span class="sxs-lookup"><span data-stu-id="b7c02-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="b7c02-295">Q#Knihovny obsahují operaci [QFT](xref:microsoft.quantum.canon.qft) , kterou můžete jednoduše použít a použít pro libovolný počet qubits.</span><span class="sxs-lookup"><span data-stu-id="b7c02-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="b7c02-296">Pokud to chcete vyzkoušet, definujte novou operaci v Q# souboru, která má stejný obsah `Perform3QubitQFT` , ale s vše od prvního `H` až po `SWAP` nahrazené dvěma jednoduchými řádky:</span><span class="sxs-lookup"><span data-stu-id="b7c02-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="b7c02-297">První řádek jednoduše vytvoří [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) výraz přiděleného pole qubits, `qs` což je to, co operace [QFT](xref:microsoft.quantum.canon.qft) přijímá jako argument.</span><span class="sxs-lookup"><span data-stu-id="b7c02-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="b7c02-298">To odpovídá pořadí indexu qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="b7c02-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="b7c02-299">Chcete-li mít přístup k těmto operacím, přidejte `open` příkazy pro příslušné obory názvů na začátku Q# souboru:</span><span class="sxs-lookup"><span data-stu-id="b7c02-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="b7c02-300">Nyní upravte hostitelský program tak, aby volal název vaší nové operace (např. `PerformIntrinsicQFT` ), a pojmenujte ho whirl.</span><span class="sxs-lookup"><span data-stu-id="b7c02-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="b7c02-301">Chcete-li zjistit skutečnou výhodu použití Q# operací knihovny, změňte počet qubits na jinou než `3` :</span><span class="sxs-lookup"><span data-stu-id="b7c02-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="b7c02-302">Proto můžete použít správný QFT pro libovolný počet qubits, aniž byste se museli starat o práci s novými `H` operacemi a rotacemi na jednotlivých qubit.</span><span class="sxs-lookup"><span data-stu-id="b7c02-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="b7c02-303">Všimněte si, že simulátor provozu má exponenciálně víc času na spuštění, protože narostete počet qubits---přesně, proč se podíváme na skutečný hardware.</span><span class="sxs-lookup"><span data-stu-id="b7c02-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>














---
title: Kvantové simulátory a klasické ovladače | Microsoft Docs
description: Tento článek popisuje, jak ovládat kvantové simulátory z klasického jazyka .NET, obvykle buď C#, nebo Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 5ac79280669ae0acfe993a1c2ae1c069b0c01848
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035122"
---
# <a name="classical-drivers-and-machines"></a><span data-ttu-id="83248-103">Klasické ovladače a počítače</span><span class="sxs-lookup"><span data-stu-id="83248-103">Classical Drivers and Machines</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="83248-104">Co se naučíte</span><span class="sxs-lookup"><span data-stu-id="83248-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="83248-105">Jak se spouštějí kvantové algoritmy</span><span class="sxs-lookup"><span data-stu-id="83248-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="83248-106">Jaké kvantové simulátory jsou součástí této verze</span><span class="sxs-lookup"><span data-stu-id="83248-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="83248-107">Jak napsat ovladač v C# pro váš kvantový algoritmus</span><span class="sxs-lookup"><span data-stu-id="83248-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="83248-108">Spouštěcí model sady Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="83248-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="83248-109">V článku [Jak napsat kvantový program](xref:microsoft.quantum.write-program) jsme spustili kvantový algoritmus tak, že jsme předali objekt `QuantumSimulator` metodě `Run` třídy algoritmu.</span><span class="sxs-lookup"><span data-stu-id="83248-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="83248-110">Třída `QuantumSimulator` provádí kvantový algoritmus úplnou simulací kvantového stavového vektoru, což je ideální pro spouštění a testování programu `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="83248-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="83248-111">Další informace o kvantových stavových vektorech najdete v článku [Průvodce koncepty](xref:microsoft.quantum.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="83248-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="83248-112">Ke spuštění kvantového algoritmu se dají použít i jiné cílové počítače.</span><span class="sxs-lookup"><span data-stu-id="83248-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="83248-113">Počítač odpovídá za poskytnutí implementací kvantových primitiv pro daný algoritmus.</span><span class="sxs-lookup"><span data-stu-id="83248-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="83248-114">Mezi ně patří primitivní operace, jako je H, CNOT a M (měření), a také nástroje pro správu a sledování qubitů.</span><span class="sxs-lookup"><span data-stu-id="83248-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="83248-115">Různé třídy kvantových počítačů představují různé modely spuštění pro stejný kvantový algoritmus.</span><span class="sxs-lookup"><span data-stu-id="83248-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="83248-116">Každý typ kvantového počítače může zajišťovat odlišnou implementaci těchto primitiv.</span><span class="sxs-lookup"><span data-stu-id="83248-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="83248-117">Například trasovací simulátor kvantového počítače, zahrnutý ve vývojové sadě, neprovádí vůbec žádnou simulaci.</span><span class="sxs-lookup"><span data-stu-id="83248-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="83248-118">Místo toho sleduje hradla, qubity a další prostředky použité v algoritmu.</span><span class="sxs-lookup"><span data-stu-id="83248-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="83248-119">Kvantové počítače</span><span class="sxs-lookup"><span data-stu-id="83248-119">Quantum Machines</span></span>

<span data-ttu-id="83248-120">V budoucnu budeme definovat další třídy kvantových počítačů s podporou jiných typů simulace a s podporou spouštění algoritmů na topologických kvantových počítačích.</span><span class="sxs-lookup"><span data-stu-id="83248-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="83248-121">Díky tomu, že umožňujeme neměnnost algoritmů při změnách implementace samotného počítače, usnadňujeme testování a ladění algoritmů v simulaci a následné spouštění na reálném hardwaru s jistotou, že se algoritmus nezměnil.</span><span class="sxs-lookup"><span data-stu-id="83248-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="83248-122">Co je zahrnuto v této verzi</span><span class="sxs-lookup"><span data-stu-id="83248-122">What's Included in this Release</span></span>

<span data-ttu-id="83248-123">Tato vydaná verze kvantové vývojové sady zahrnuje několik tříd kvantových počítačů.</span><span class="sxs-lookup"><span data-stu-id="83248-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="83248-124">Všechny jsou definovány v oboru názvů `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="83248-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="83248-125">[Úplný simulátor stavových vektorů](xref:microsoft.quantum.machines.full-state-simulator), třída `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="83248-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="83248-126">[Jednoduchý estimátor prostředků](xref:microsoft.quantum.machines.resources-estimator), třída `ResourcesEstimator`, umožňuje na nejvyšší úrovni analýzu prostředků vyžadovaných ke spuštění kvantového algoritmu.</span><span class="sxs-lookup"><span data-stu-id="83248-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="83248-127">[Trasovací estimátor prostředků](xref:microsoft.quantum.machines.qc-trace-simulator.intro), třída `QCTraceSimulator` umožňuje pokročilejší analýzu vyžadovaných prostředků v rámci celého grafu volání.</span><span class="sxs-lookup"><span data-stu-id="83248-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="83248-128">[Simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), třída `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="83248-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-classical-driver-program"></a><span data-ttu-id="83248-129">Psaní programu klasického ovladače</span><span class="sxs-lookup"><span data-stu-id="83248-129">Writing a Classical Driver Program</span></span>

<span data-ttu-id="83248-130">V článku [Jak napsat kvantový program](xref:microsoft.quantum.write-program) jsme pro náš teleportovací algoritmus napsali jednoduchý ovladač v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="83248-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="83248-131">Ovladač C# má 4 hlavní úkoly:</span><span class="sxs-lookup"><span data-stu-id="83248-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="83248-132">Sestavení cílového počítače</span><span class="sxs-lookup"><span data-stu-id="83248-132">Constructing the target machine</span></span>
* <span data-ttu-id="83248-133">Výpočet všech argumentů vyžadovaných pro kvantový algoritmus</span><span class="sxs-lookup"><span data-stu-id="83248-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="83248-134">Spuštění kvantového algoritmu v simulátoru</span><span class="sxs-lookup"><span data-stu-id="83248-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="83248-135">Zpracování výsledku operace</span><span class="sxs-lookup"><span data-stu-id="83248-135">Processing the result of the operation</span></span>

<span data-ttu-id="83248-136">Teď se podíváme na každý krok podrobněji.</span><span class="sxs-lookup"><span data-stu-id="83248-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="83248-137">Sestavení cílového počítače</span><span class="sxs-lookup"><span data-stu-id="83248-137">Constructing the Target Machine</span></span>

<span data-ttu-id="83248-138">Kvantové počítače jsou instancemi normálních tříd .NET, takže jsou vytvořeny vyvoláním jejich konstruktoru stejně jako u jakékoli jiné třídy .NET.</span><span class="sxs-lookup"><span data-stu-id="83248-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="83248-139">Některé simulátory, včetně `QuantumSimulator`, implementují rozhraní .NET <xref:System.IDisposable?displayProperty=nameWithType>, a proto je třeba je zabalit do příkazu C# `using`.</span><span class="sxs-lookup"><span data-stu-id="83248-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="83248-140">Výpočet argumentů pro algoritmus</span><span class="sxs-lookup"><span data-stu-id="83248-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="83248-141">V našem příkladu `Teleport` jsme vypočítali některé poměrně umělé argumenty, které předáme našemu kvantovému algoritmu.</span><span class="sxs-lookup"><span data-stu-id="83248-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="83248-142">Častěji ale kvantový algoritmus vyžaduje mnoho vstupních dat a je jednodušší poskytnout mu je z klasického ovladače.</span><span class="sxs-lookup"><span data-stu-id="83248-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="83248-143">Například u chemických simulací vyžaduje kvantový algoritmus velké tabulky integrálů molekulárních orbitálních interakcí.</span><span class="sxs-lookup"><span data-stu-id="83248-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="83248-144">Obecně se načítají ze souboru, který je k dispozici při spuštění algoritmu.</span><span class="sxs-lookup"><span data-stu-id="83248-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="83248-145">Protože jazyk Q# nemá mechanismy pro přístup k systému souborů, je shromáždění takovýchto dat a jejich předání metodě `Run` kvantového algoritmu úlohou pro klasický ovladač.</span><span class="sxs-lookup"><span data-stu-id="83248-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="83248-146">Další případ, kdy klasický ovladač hraje klíčovou roli, je u variačních metod.</span><span class="sxs-lookup"><span data-stu-id="83248-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="83248-147">V této třídě algoritmů se kvantový stav připravuje na základě klasických parametrů, a teprve tento stav se pak použije k výpočtu požadované výsledné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="83248-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="83248-148">Parametry se pak upraví na základě určitého gradientního algoritmu nebo strojového učení a kvantový výpočet se spustí znovu.</span><span class="sxs-lookup"><span data-stu-id="83248-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="83248-149">V takových případech je nejlepší implementovat samotný gradientní algoritmus čistě klasicky a volat ho z klasického ovladače. Výsledky gradientního algoritmu se pak předají k dalšímu výpočtu kvantovému algoritmu.</span><span class="sxs-lookup"><span data-stu-id="83248-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="83248-150">Spuštění kvantového algoritmu</span><span class="sxs-lookup"><span data-stu-id="83248-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="83248-151">Tato část je obecně velmi přímočará.</span><span class="sxs-lookup"><span data-stu-id="83248-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="83248-152">Každá operace Q# se zkompiluje do třídy, která poskytuje statickou metodu `Run`.</span><span class="sxs-lookup"><span data-stu-id="83248-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="83248-153">Argumenty se této metodě předávají jako zploštěná řazená kolekce argumentů samotné operace, plus dodatečný první argument, který specifikuje požadovaný simulátor.</span><span class="sxs-lookup"><span data-stu-id="83248-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="83248-154">Pro operaci, která očekává pojmenovanou řazenou kolekci členů typu `(a: String, (b: Double, c: Double))` bude mít její zploštěný protějšek typ `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="83248-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="83248-155">Při předávání argumentů metodě `Run` je třeba brát v úvahu určité detaily:</span><span class="sxs-lookup"><span data-stu-id="83248-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="83248-156">Pole musí být vždy zabalena v objektu `Microsoft.Quantum.Simulation.Core.QArray<T>`.</span><span class="sxs-lookup"><span data-stu-id="83248-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="83248-157">Třída `QArray` má konstruktor, kterému je možné předat jakoukoli uspořádanou kolekci vhodných objektů (`IEnumerable<T>`).</span><span class="sxs-lookup"><span data-stu-id="83248-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="83248-158">Prázdná řazená kolekce členů, `()` v jazyce Q#, je v C# reprezentována výrazem `QVoid.Instance`.</span><span class="sxs-lookup"><span data-stu-id="83248-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="83248-159">Neprázdné řazené kolekce členů jsou reprezentovány jako .NET instance `ValueType`.</span><span class="sxs-lookup"><span data-stu-id="83248-159">Non-empty tuples are represented as .NET `ValueType` instances.</span></span>
* <span data-ttu-id="83248-160">Uživatelem definované typy se v Q# předávají jako jejich základní typy.</span><span class="sxs-lookup"><span data-stu-id="83248-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="83248-161">Chcete-li metodě `Run` předat operaci nebo funkci, musíte získat instanci třídy operace nebo funkce pomocí metody `Get<>` simulátoru.</span><span class="sxs-lookup"><span data-stu-id="83248-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="83248-162">Zpracování výsledků</span><span class="sxs-lookup"><span data-stu-id="83248-162">Processing the Results</span></span>

<span data-ttu-id="83248-163">Výsledek kvantového výpočtu je vrácen v návratové hodnotě metody `Run`.</span><span class="sxs-lookup"><span data-stu-id="83248-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="83248-164">Metoda `Run` se spouští asynchronně a proto vrací instanci třídy <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="83248-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="83248-165">Samotné výsledky operace je možné získat několika způsoby.</span><span class="sxs-lookup"><span data-stu-id="83248-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="83248-166">Nejjednodušší je použít z třídy `Task` vlastnost [`Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span><span class="sxs-lookup"><span data-stu-id="83248-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="83248-167">ale fungovat budou i jiné techniky, třeba použití metody [`Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) nebo klíčového slova C# [`await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await).</span><span class="sxs-lookup"><span data-stu-id="83248-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="83248-168">Stejně jako u argumentů jsou v Q# řazené kolekce členů reprezentovány jako instance `ValueTuple` a pole jako instance `QArray`.</span><span class="sxs-lookup"><span data-stu-id="83248-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="83248-169">Uživatelem definované typy se vracejí jako jejich základní typy.</span><span class="sxs-lookup"><span data-stu-id="83248-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="83248-170">Prázdná řazená kolekce členů `()` se vrací jako instance třídy `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="83248-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="83248-171">Mnoho kvantových algoritmů vyžaduje k získání smysluplné odpovědi podstatné zpracování výsledků.</span><span class="sxs-lookup"><span data-stu-id="83248-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="83248-172">Například kvantová část Shorova algoritmu je jen začátkem náročného výpočtu, který najde samotný rozklad čísla.</span><span class="sxs-lookup"><span data-stu-id="83248-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="83248-173">Ve většině případů je jednodušší a snazší tento typ výpočtů provádět v klasickém ovladači.</span><span class="sxs-lookup"><span data-stu-id="83248-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="83248-174">Pouze klasický ovladač může tyto výsledky zobrazit uživateli a zapsat je na disk.</span><span class="sxs-lookup"><span data-stu-id="83248-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="83248-175">Klasický ovladač bude mít také přístup k analytickým knihovnám a dalším matematickým funkcím, které nejsou v Q# dostupné.</span><span class="sxs-lookup"><span data-stu-id="83248-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="83248-176">Selhání</span><span class="sxs-lookup"><span data-stu-id="83248-176">Failures</span></span>

<span data-ttu-id="83248-177">Když se při provádění operace narazí na příkaz `fail` jazyka Q#, vyvolá se výjimka `ExecutionFailException`.</span><span class="sxs-lookup"><span data-stu-id="83248-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="83248-178">Vzhledem k použití třídy `System.Task` v metodě `Run` se výjimka vyvolaná v důsledku příkazu `fail` zabalí do objektu `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="83248-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="83248-179">Chcete-li zjistit skutečnou příčinu selhání, je třeba iterovat přes  
`InnerExceptions` objektu `AggregateException`, například:</span><span class="sxs-lookup"><span data-stu-id="83248-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="83248-180">Další klasické jazyky</span><span class="sxs-lookup"><span data-stu-id="83248-180">Other Classical Languages</span></span>

<span data-ttu-id="83248-181">Uvedené příklady jsou sice v C#, F# a Pythonu, ale Quantum Development Kit podporuje psaní klasických hostitelů i v jiných jazycích.</span><span class="sxs-lookup"><span data-stu-id="83248-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="83248-182">Například když budete chtít napsat hostitelský program ve Visual Basicu, [není to žádný problém](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="83248-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>

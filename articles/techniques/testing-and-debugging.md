---
title: 'Techniky Q # – testování a ladění | Microsoft Docs'
description: 'Techniky Q # – testování a ladění'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183484"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="f0921-103">Testování a ladění</span><span class="sxs-lookup"><span data-stu-id="f0921-103">Testing and Debugging</span></span>

<span data-ttu-id="f0921-104">Stejně jako v případě klasického programování je nutné mít na úmysl kontrolu nad tím, že se programy budou chovat podle účelu a že je možné diagnostiku nesprávného programu.</span><span class="sxs-lookup"><span data-stu-id="f0921-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="f0921-105">V této části se zaměříme na nástroje, které Q # nabízí pro testování a ladění programů v oblasti.</span><span class="sxs-lookup"><span data-stu-id="f0921-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="f0921-106">Testování částí</span><span class="sxs-lookup"><span data-stu-id="f0921-106">Unit Tests</span></span>

<span data-ttu-id="f0921-107">Jedním z běžných způsobů testování klasických programů je psaní malých programů s názvem *testy jednotek* , které spouštějí kód v knihovně, a porovnání jeho výstupu s očekávaným výstupem.</span><span class="sxs-lookup"><span data-stu-id="f0921-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="f0921-108">Můžeme třeba zajistit, aby `Square(2)` vracela `4`, protože víme předem, že *je* to $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="f0921-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="f0921-109">Q # podporuje vytváření testů jednotek pro programy na více procesorech a to, které mohou být provedeny jako testy v rámci testovacího rozhraní [xUnit](https://xunit.github.io/) jednotek.</span><span class="sxs-lookup"><span data-stu-id="f0921-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="f0921-110">Vytvoření testovacího projektu</span><span class="sxs-lookup"><span data-stu-id="f0921-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f0921-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f0921-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f0921-112">Otevřete Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f0921-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="f0921-113">Přejděte do nabídky `File` a vyberte `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="f0921-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="f0921-114">V Průzkumníku šablon projektu v části `Installed` > `Visual C#`vyberte šablonu `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="f0921-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f0921-115">Příkazový řádek/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f0921-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f0921-116">Z oblíbeného příkazového řádku spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="f0921-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="f0921-117">V obou případech budou mít nový projekt otevřené dva soubory.</span><span class="sxs-lookup"><span data-stu-id="f0921-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="f0921-118">První soubor, `Tests.qs`, poskytuje pohodlný místo pro definování nových testů jednotek Q #.</span><span class="sxs-lookup"><span data-stu-id="f0921-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="f0921-119">Zpočátku tento soubor obsahuje jeden vzorový test jednotek `AllocateQubitTest`, který kontroluje, zda je nově přidělená qubit ve stavu $ \ket{0}$ a vytiskne zprávu:</span><span class="sxs-lookup"><span data-stu-id="f0921-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="f0921-120">Jakékoli operace Q # kompatibilní s typem `(Unit => Unit)` nebo funkcí kompatibilními s `(Unit -> Unit)` mohou být provedeny jako test jednotky.</span><span class="sxs-lookup"><span data-stu-id="f0921-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="f0921-121">Druhý soubor `TestSuiteRunner.cs` obsahuje metodu, která zjišťuje a spouští testy jednotek Q #.</span><span class="sxs-lookup"><span data-stu-id="f0921-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="f0921-122">Toto je metoda `TestTarget` s poznámkou s atributem `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="f0921-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="f0921-123">Atribut `OperationDriver` je součástí knihovny rozšíření xUnit Microsoft. simulace. xUnit.</span><span class="sxs-lookup"><span data-stu-id="f0921-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="f0921-124">Rozhraní testování částí volá metodu `TestTarget` pro každý test jednotky Q #, který zjistil.</span><span class="sxs-lookup"><span data-stu-id="f0921-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="f0921-125">Rozhraní předá popis testu jednotek metodě prostřednictvím `op` argumentu.</span><span class="sxs-lookup"><span data-stu-id="f0921-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="f0921-126">Následující řádek kódu:</span><span class="sxs-lookup"><span data-stu-id="f0921-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="f0921-127">provede test jednotky na `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="f0921-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="f0921-128">Ve výchozím nastavení vyhledává mechanismus zjišťování jednotek všechny funkce Q # nebo operace kompatibilního typu, které splňují následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="f0921-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="f0921-129">Nachází se ve stejném sestavení jako metoda s poznámkou s atributem `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="f0921-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="f0921-130">Nachází se ve stejném oboru názvů jako metoda s poznámkou s atributem `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="f0921-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="f0921-131">Má název končící na `Test`.</span><span class="sxs-lookup"><span data-stu-id="f0921-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="f0921-132">Sestavení, obor názvů a přípona pro funkce testování částí a operace lze nastavit pomocí volitelných parametrů atributu `OperationDriver`:</span><span class="sxs-lookup"><span data-stu-id="f0921-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="f0921-133">`AssemblyName` parametr nastaví název sestavení, které je prohledáváno pro testy.</span><span class="sxs-lookup"><span data-stu-id="f0921-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="f0921-134">`TestNamespace` parametr nastaví název oboru názvů, který je prohledáván pro testy.</span><span class="sxs-lookup"><span data-stu-id="f0921-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="f0921-135">`Suffix` nastaví příponu názvů operací nebo funkcí, které se považují za jednotkové testy.</span><span class="sxs-lookup"><span data-stu-id="f0921-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="f0921-136">Kromě toho `TestCasePrefix` volitelný parametr umožňuje nastavit předponu pro název testovacího případu.</span><span class="sxs-lookup"><span data-stu-id="f0921-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="f0921-137">Předpona před názvem operace se zobrazí v seznamu testovacích případů.</span><span class="sxs-lookup"><span data-stu-id="f0921-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="f0921-138">`TestCasePrefix = "QSim:"` například způsobí, že se `AllocateQubitTest` v seznamu nalezených testů zobrazí jako `QSim:AllocateQubitTest`.</span><span class="sxs-lookup"><span data-stu-id="f0921-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="f0921-139">To může být užitečné pro indikaci, například, který simulátor se používá ke spuštění testu.</span><span class="sxs-lookup"><span data-stu-id="f0921-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="f0921-140">Spouštění testů jednotek Q #</span><span class="sxs-lookup"><span data-stu-id="f0921-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f0921-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f0921-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f0921-142">Jako jednorázové nastavení pro každé řešení přejděte do nabídky `Test` a vyberte `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="f0921-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="f0921-143">Výchozí nastavení architektury procesoru pro Visual Studio je uloženo v souboru možností řešení (`.suo`) pro každé řešení.</span><span class="sxs-lookup"><span data-stu-id="f0921-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="f0921-144">Pokud tento soubor odstraníte, budete muset jako architekturu procesoru vybrat `X64`.</span><span class="sxs-lookup"><span data-stu-id="f0921-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="f0921-145">Sestavte projekt, přejděte do nabídky `Test` a vyberte `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="f0921-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="f0921-146">`AllocateQubitTest` se zobrazí v seznamu testů ve `Not Run Tests` skupině.</span><span class="sxs-lookup"><span data-stu-id="f0921-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="f0921-147">Vyberte `Run All` nebo spusťte tento jednotlivý test a měl by být úspěch.</span><span class="sxs-lookup"><span data-stu-id="f0921-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f0921-148">Příkazový řádek/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f0921-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f0921-149">Chcete-li spustit testy, přejděte do složky projektu (složka obsahující `Tests.csproj`) a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="f0921-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="f0921-150">Mělo by se zobrazit výstup podobný následujícímu:</span><span class="sxs-lookup"><span data-stu-id="f0921-150">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

***

## <a name="logging-and-assertions"></a><span data-ttu-id="f0921-151">Protokolování a kontrolní výrazy</span><span class="sxs-lookup"><span data-stu-id="f0921-151">Logging and Assertions</span></span>

<span data-ttu-id="f0921-152">Jedním z důležitých důsledků faktu, že funkce v Q # nemají žádné vedlejší účinky, je, že všechny důsledky spuštění funkce, jejíž výstupní typ je prázdná řazená kolekce členů, `()` v rámci programu Q # nikdy nemusejí být zjištěny.</span><span class="sxs-lookup"><span data-stu-id="f0921-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="f0921-153">To znamená, že cílový počítač se může rozhodnout, že nespustí žádnou funkci, která vrátí `()` s jistotou, že toto opomenutí neupraví chování žádného následujícího kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="f0921-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="f0921-154">To umožňuje funkcím vracet `()` užitečným nástrojem pro vkládání kontrolních výrazů a logiku ladění do programů Q #.</span><span class="sxs-lookup"><span data-stu-id="f0921-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="f0921-155">Protokolování</span><span class="sxs-lookup"><span data-stu-id="f0921-155">Logging</span></span>

<span data-ttu-id="f0921-156">Vnitřní funkce <xref:microsoft.quantum.intrinsic.message> je typu `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.</span><span class="sxs-lookup"><span data-stu-id="f0921-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="f0921-157">Akci `onLog` `QuantumSimulator` lze použít k definování akcí prováděných v případě, že volání Q # Code `Message`.</span><span class="sxs-lookup"><span data-stu-id="f0921-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="f0921-158">Ve výchozím nastavení se zprávy protokolovaných zpráv tisknou do standardního výstupu.</span><span class="sxs-lookup"><span data-stu-id="f0921-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="f0921-159">Při definování sady testů jednotek mohou být protokolované zprávy směrovány na výstup testu.</span><span class="sxs-lookup"><span data-stu-id="f0921-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="f0921-160">Když je projekt vytvořen z šablony projektu Q # test, toto přesměrování je předem nakonfigurováno pro sadu a vytvoří se ve výchozím nastavení následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="f0921-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f0921-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f0921-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f0921-162">Po spuštění testu v Průzkumníku testů a kliknutí na test se zobrazí panel s informacemi o spuštění testu: stav úspěch/selhání, uplynulý čas a "výstup".</span><span class="sxs-lookup"><span data-stu-id="f0921-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="f0921-163">Pokud kliknete na odkaz "výstup", výstup testu se otevře v novém okně.</span><span class="sxs-lookup"><span data-stu-id="f0921-163">If you click the "Output" link, test output will open in a new window.</span></span>

![Výstup testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f0921-165">Příkazový řádek/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f0921-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f0921-166">Stav úspěch/selhání každého testu je vytištěn do konzoly `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f0921-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="f0921-167">V případě neúspěšných testů se výstupy zaznamenané jako výsledek volání `output.WriteLine(msg)` také vytisknou do konzoly nástroje, což vám umožní diagnostikovat selhání.</span><span class="sxs-lookup"><span data-stu-id="f0921-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="f0921-168">Kontrolní výrazy</span><span class="sxs-lookup"><span data-stu-id="f0921-168">Assertions</span></span>

<span data-ttu-id="f0921-169">Stejnou logiku lze použít pro implementaci kontrolních výrazů.</span><span class="sxs-lookup"><span data-stu-id="f0921-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="f0921-170">Pojďme si vzít v úvahu jednoduchý příklad:</span><span class="sxs-lookup"><span data-stu-id="f0921-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="f0921-171">Zde `fail` klíčové slovo indikuje, že výpočet by neměl pokračovat, vyvolání výjimky v cílovém počítači, na kterém běží program Q #.</span><span class="sxs-lookup"><span data-stu-id="f0921-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="f0921-172">Podle definice nemůže být selhání tohoto druhu zjištěno v rámci Q #, protože po dosažení `fail`ho příkazu není spuštěn žádný další kód Q #.</span><span class="sxs-lookup"><span data-stu-id="f0921-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="f0921-173">Proto, pokud budeme pokračovat po volání `AssertPositive`, můžeme mít jistotu, že jeho vstup byl kladný.</span><span class="sxs-lookup"><span data-stu-id="f0921-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="f0921-174">[Předehru](xref:microsoft.quantum.libraries.standard.prelude) na těchto nápadech nabízí dva obzvláště užitečné kontrolní výrazy, <xref:microsoft.quantum.intrinsic.assert> a <xref:microsoft.quantum.intrinsic.assertprob> jak modelovat jako operace na `()`.</span><span class="sxs-lookup"><span data-stu-id="f0921-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="f0921-175">Tyto kontrolní výrazy přebírají operátor Pauli, který popisuje konkrétní měření zájmu, registrující hodnoty, na kterých se má provést měření, a hypotetický výsledek.</span><span class="sxs-lookup"><span data-stu-id="f0921-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="f0921-176">V cílových počítačích, které pracují s simulací, nebudeme vázáni pomocí [věta bez klonování](https://en.wikipedia.org/wiki/No-cloning_theorem)a může provádět taková měření, aniž by došlo k narušení registru předaného do takových kontrolních výrazů.</span><span class="sxs-lookup"><span data-stu-id="f0921-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="f0921-177">Simulátor pak může být podobný funkci `AssertPositive` výše, přerušit výpočet, pokud by se hypotetický výsledek neosvědčil v praxi:</span><span class="sxs-lookup"><span data-stu-id="f0921-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="f0921-178">U fyzických stavových procesorů, kde věta bez klonování brání prověřování stavu nečinnosti, operace `Assert` a `AssertProb` jednoduše vrátí `()` bez dalšího účinku.</span><span class="sxs-lookup"><span data-stu-id="f0921-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="f0921-179">Obor názvů <xref:microsoft.quantum.diagnostics> poskytuje několik dalších funkcí řady `Assert`, které nám umožňují kontrolovat pokročilejší podmínky.</span><span class="sxs-lookup"><span data-stu-id="f0921-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="f0921-180">Funkce výpisu paměti</span><span class="sxs-lookup"><span data-stu-id="f0921-180">Dump Functions</span></span>

<span data-ttu-id="f0921-181">Pro pomoc při řešení potíží s programy, <xref:microsoft.quantum.diagnostics> obor názvů nabízí dvě funkce, které mohou vypsat do souboru aktuální stav cílového počítače: <xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="f0921-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="f0921-182">Vygenerovaný výstup každého z nich závisí na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="f0921-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="f0921-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="f0921-183">DumpMachine</span></span>

<span data-ttu-id="f0921-184">Plný stav simulátoru, který je distribuován jako součást vývojářské sady pro plnění, zapisuje do souboru [funkci Wave](https://en.wikipedia.org/wiki/Wave_function) celého systému pro plnění, jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudu pravděpodobnost měření výpočetního základního stavu $ \ket{n} $, kde $ \ket{n} = \ket{B_{n-1}... b_1b_0} $ pro BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="f0921-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="f0921-185">Například na počítači, který má přiděleno pouze dvě qubits a ve stavu nestavení $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ Call <xref:microsoft.quantum.diagnostics.dumpmachine> generuje tento výstup :</span><span class="sxs-lookup"><span data-stu-id="f0921-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f0921-186">První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.</span><span class="sxs-lookup"><span data-stu-id="f0921-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="f0921-187">Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{n} $ v kartézském a polárních formátech.</span><span class="sxs-lookup"><span data-stu-id="f0921-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="f0921-188">Podrobně pro první řádek:</span><span class="sxs-lookup"><span data-stu-id="f0921-188">In detail for the first row:</span></span>

* <span data-ttu-id="f0921-189">**`∣0❭:`** tento řádek odpovídá průběžnému stavu `0` výpočtu.</span><span class="sxs-lookup"><span data-stu-id="f0921-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="f0921-190">**`0.707107 +  0.000000 i`** : amplituda pravděpodobnosti ve formátu kartézském.</span><span class="sxs-lookup"><span data-stu-id="f0921-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="f0921-191">**` == `** : znaménko `equal` se bude rozkládat se stejnými reprezentacemi.</span><span class="sxs-lookup"><span data-stu-id="f0921-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="f0921-192">**`**********  `** : grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu.</span><span class="sxs-lookup"><span data-stu-id="f0921-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="f0921-193">**`[ 0.500000 ]`** : číselná hodnota velikosti</span><span class="sxs-lookup"><span data-stu-id="f0921-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="f0921-194">**`    ---`** : grafická reprezentace fáze amplitudy (viz níže).</span><span class="sxs-lookup"><span data-stu-id="f0921-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="f0921-195">**`[ 0.0000 rad ]`** : číselná hodnota fáze (v radiánech).</span><span class="sxs-lookup"><span data-stu-id="f0921-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="f0921-196">Velikost i fáze se zobrazí s grafickým znázorněním.</span><span class="sxs-lookup"><span data-stu-id="f0921-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="f0921-197">Reprezentace velikosti je přímá – předána: zobrazuje pruh `*`, tím větší je pravděpodobnost, že se další pruh zvětší.</span><span class="sxs-lookup"><span data-stu-id="f0921-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="f0921-198">Pro tuto fázi zobrazíme následující symboly, které reprezentují úhel na základě rozsahů:</span><span class="sxs-lookup"><span data-stu-id="f0921-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="f0921-199">Následující příklady ukazují `DumpMachine` v některých běžných stavech:</span><span class="sxs-lookup"><span data-stu-id="f0921-199">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="f0921-200">ID qubit se přiřadí za běhu a není nutně zarovnané na pořadí, ve kterém byla qubit přidělena nebo jeho pozice v rámci registru qubit.</span><span class="sxs-lookup"><span data-stu-id="f0921-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f0921-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f0921-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="f0921-202">ID qubit v aplikaci Visual Studio můžete zjistit tak, že do kódu zadáte zarážku a zkontrolujete hodnotu proměnné qubit, například:</span><span class="sxs-lookup"><span data-stu-id="f0921-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Zobrazit ID qubit v aplikaci Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="f0921-204">qubit s index `0` v `register2` má ID =`3`, qubit s index `1` má ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="f0921-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="f0921-205">Příkazový řádek/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f0921-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="f0921-206">ID qubit můžete zjistit pomocí funkce <xref:microsoft.quantum.intrinsic.message> a předáním proměnné qubit ve zprávě, například:</span><span class="sxs-lookup"><span data-stu-id="f0921-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="f0921-207">který může vygenerovat tento výstup:</span><span class="sxs-lookup"><span data-stu-id="f0921-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="f0921-208">To znamená, že qubit s indexem `0` v `register2` má ID =`3`, qubit s index `1` má ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="f0921-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="f0921-209"><xref:microsoft.quantum.diagnostics.dumpmachine> je součástí oboru názvů <xref:microsoft.quantum.diagnostics>, takže pokud ho chcete použít, musíte přidat příkaz `open`:</span><span class="sxs-lookup"><span data-stu-id="f0921-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="f0921-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="f0921-210">DumpRegister</span></span>

<span data-ttu-id="f0921-211"><xref:microsoft.quantum.diagnostics.dumpregister> funguje jako <xref:microsoft.quantum.diagnostics.dumpmachine>s tím rozdílem, že také převezme pole qubits k omezení množství informací pouze na odpovídající qubits.</span><span class="sxs-lookup"><span data-stu-id="f0921-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="f0921-212">Stejně jako u <xref:microsoft.quantum.diagnostics.dumpmachine>jsou informace vygenerované <xref:microsoft.quantum.diagnostics.dumpregister> závislé na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="f0921-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="f0921-213">Pro plný stav simulátoru se zapisuje do souboru, ve kterém je funkce Wave v globální fázi podsystému, vygenerované zadaným qubits ve stejném formátu jako <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="f0921-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="f0921-214">Například znovu proveďte počítač se dvěma přidělenými qubits a ve stavu stavového pole $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ KET{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ Call <xref:microsoft.quantum.diagnostics.dumpregister> pro `qubit[0]` vygeneruje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="f0921-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f0921-215">a volání <xref:microsoft.quantum.diagnostics.dumpregister> pro `qubit[1]` vygeneruje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="f0921-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="f0921-216">Obecně platí, že stav registru, který je entangled s jiným registrem, je smíšeným stavem, nikoli čistým stavem.</span><span class="sxs-lookup"><span data-stu-id="f0921-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="f0921-217">V tomto případě <xref:microsoft.quantum.diagnostics.dumpregister> výstupem následující zprávu:</span><span class="sxs-lookup"><span data-stu-id="f0921-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="f0921-218">Následující příklad ukazuje, jak můžete použít jak <xref:microsoft.quantum.diagnostics.dumpregister>, tak <xref:microsoft.quantum.diagnostics.dumpmachine> ve vašem kódu Q #:</span><span class="sxs-lookup"><span data-stu-id="f0921-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="f0921-219">Ladění</span><span class="sxs-lookup"><span data-stu-id="f0921-219">Debugging</span></span>

<span data-ttu-id="f0921-220">Funkce Q # nad `Assert` a `Dump` funkcí a operací podporuje podmnožinu standardních funkcí ladění sady Visual Studio: [nastavení zarážek řádků](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí nástroje F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) a [Kontrola hodnot klasických proměnných. ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)jsou všechno možné při provádění kódu na simulátoru.</span><span class="sxs-lookup"><span data-stu-id="f0921-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="f0921-221">Ladění v Visual Studio Code ještě není podporováno.</span><span class="sxs-lookup"><span data-stu-id="f0921-221">Debugging in Visual Studio Code is not yet supported.</span></span>


---
title: Testování a ladění
description: Naučte se používat testy jednotek, fakta a kontrolní výrazy a funkce výpisu paměti pro testování a ladění programů v počtu procesorů.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690973"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="0ddfb-103">Testování a ladění</span><span class="sxs-lookup"><span data-stu-id="0ddfb-103">Testing and debugging</span></span>

<span data-ttu-id="0ddfb-104">Stejně jako v případě klasického programování je důležité, abyste měli kontrolu nad tím, že se programy budou chovat podle účelu a že je možné diagnostikovat nesprávné chování.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="0ddfb-105">V této části se zabýváme nástroji, které nabízíme Q# pro testování a ladění programů.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="0ddfb-106">Testování částí</span><span class="sxs-lookup"><span data-stu-id="0ddfb-106">Unit Tests</span></span>

<span data-ttu-id="0ddfb-107">Jedním z běžných způsobů testování klasických programů je psaní malých programů s názvem *testy jednotek* , které spouštějí kód v knihovně, a porovnání jeho výstupu s očekávaným výstupem.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-107">One common approach to testing classical programs is to write small programs called *unit tests* , which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="0ddfb-108">Můžete například zajistit, že se `Square(2)` vrátí, `4` protože víte *předem* , že $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="0ddfb-109">Q# podporuje vytváření testů jednotek pro programy na více procesorech a to, které mohou běžet jako testy v rámci testovacího rozhraní [xUnit](https://xunit.github.io/) jednotek.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="0ddfb-110">Vytvoření testovacího projektu</span><span class="sxs-lookup"><span data-stu-id="0ddfb-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0ddfb-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0ddfb-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0ddfb-112">Otevřete Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="0ddfb-113">Přejděte do nabídky **soubor** a vyberte **Nový > projekt...** . V pravém horním rohu vyhledejte `Q#` a vyberte šablonu **Q# testovacího projektu** .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-113">Go to the **File** menu and select **New > Project...** . In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0ddfb-114">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0ddfb-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0ddfb-115">Z oblíbeného příkazového řádku spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="0ddfb-116">Váš nový projekt obsahuje jeden soubor `Tests.qs` , který poskytuje pohodlný místo pro definování nových Q# testů jednotek.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="0ddfb-117">Zpočátku tento soubor obsahuje jeden ukázkový test jednotek, `AllocateQubit` který kontroluje, zda je nově přidělená qubit ve stavu $ \ket {0} $ a vytiskne zprávu:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="0ddfb-118">Jakákoli Q# operace nebo funkce, která přebírá argument typu `Unit` a vrácení, `Unit` může být označena jako test jednotky prostřednictvím `@Test("...")` atributu.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="0ddfb-119">V předchozím příkladu argument tohoto atributu `"QuantumSimulator"` Určuje cíl, na kterém je test spuštěn.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="0ddfb-120">Jeden test může běžet na více cílech.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="0ddfb-121">Například přidejte atribut `@Test("ResourcesEstimator")` před `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="0ddfb-122">Uložte soubor a spusťte všechny testy.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-122">Save the file and run all tests.</span></span> <span data-ttu-id="0ddfb-123">Nyní by měly být dvě testy jednotek, jedna, kde se spouští v a `AllocateQubit` `QuantumSimulator` druhá, kde se spouští v `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="0ddfb-124">Q#Kompilátor rozpoznává předdefinované cíle `"QuantumSimulator"` , `"ToffoliSimulator"` a `"ResourcesEstimator"` jako platné cíle spuštění pro testování částí.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="0ddfb-125">Je také možné zadat libovolný plně kvalifikovaný název pro definování vlastního cíle spuštění.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="0ddfb-126">Spouštění Q# testů jednotek</span><span class="sxs-lookup"><span data-stu-id="0ddfb-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0ddfb-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0ddfb-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0ddfb-128">Jako jednorázové nastavení pro každé řešení přejděte do nabídky **test** a vyberte **nastavení testu > výchozí architektura procesoru > x64** .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64** .</span></span>

> [!TIP]
> <span data-ttu-id="0ddfb-129">Výchozí nastavení architektury procesoru pro Visual Studio je uloženo v souboru možností řešení ( `.suo` ) pro každé řešení.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="0ddfb-130">Pokud tento soubor odstraníte, budete muset jako architekturu procesoru vybrat **x64** .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="0ddfb-131">Sestavte projekt, otevřete nabídku **test** a vyberte možnost **Windows > Průzkumník testů** .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer** .</span></span> <span data-ttu-id="0ddfb-132">**AllocateQubit** se zobrazí v seznamu testů ve skupině **Nespuštěné testy** .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="0ddfb-133">Vyberte **Spustit vše** nebo spustit tento jednotlivý test.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0ddfb-134">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0ddfb-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0ddfb-135">Chcete-li spustit testy, přejděte do složky projektu (složka obsahující `Tests.csproj` ) a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="0ddfb-136">Mělo by se zobrazit výstup podobný následujícímu:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="0ddfb-137">Testy jednotek lze filtrovat podle jejich názvu nebo cíle spuštění:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="0ddfb-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="0ddfb-138">\*\*_</span></span>

<span data-ttu-id="0ddfb-139">Vnitřní funkce <xref:Microsoft.Quantum.Intrinsic.Message> má typ `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0ddfb-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0ddfb-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0ddfb-141">Po spuštění testu v Průzkumníku testů a kliknutí na test se zobrazí panel s informacemi o testovacím běhu: stav předání/selhání, uplynulý čas a odkaz na výstup.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="0ddfb-142">Kliknutím na tlačítko _ *výstup* \* otevřete výstup testu v novém okně.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-142">Click _ *Output* \* to open the test output in a new window.</span></span>

![Výstup testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0ddfb-144">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0ddfb-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0ddfb-145">Stav předání/selhání každého testu je vytištěn do konzoly nástrojem `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="0ddfb-146">V případě neúspěšných testů jsou výstupy také vytištěny do konzoly nástroje, což vám umožní diagnostikovat selhání.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="0ddfb-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="0ddfb-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="0ddfb-148">Fakta a kontrolní výrazy</span><span class="sxs-lookup"><span data-stu-id="0ddfb-148">Facts and Assertions</span></span>

<span data-ttu-id="0ddfb-149">Vzhledem k tomu, že funkce v Q# nemají žádné _logické_ vedlejší účinky, nemůžete v rámci programu nikdy sledovat Q# jiné druhy efektů od spuštění funkce, jejíž výstupní typ je prázdná řazená kolekce členů `()` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-149">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="0ddfb-150">To znamená, že cílový počítač se může rozhodnout, že nespustí žádnou funkci `()` , která se vrátí se zárukou, že toto opomenutí nebude upravovat chování žádného následujícího Q# kódu.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="0ddfb-151">Toto chování zpřístupňuje funkce `()` (například `Unit` ) užitečným nástrojem pro vkládání kontrolních výrazů a logiku ladění do Q# programů.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="0ddfb-152">Pojďme si vzít v úvahu jednoduchý příklad:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="0ddfb-153">Zde je klíčové slovo `fail` indikuje, že výpočet by neměl pokračovat a vyvolá výjimku v cílovém počítači, na kterém je spuštěný Q# program.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="0ddfb-154">V rámci definice nemůže být tento druh zjištěn v rámci Q# , protože cílový počítač již Q# po dosažení příkazu nespustí kód `fail` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-154">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="0ddfb-155">Takže pokud budeme pokračovat po volání `PositivityFact` , můžeme si být jisti, že jeho vstup byl kladný.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="0ddfb-156">Všimněte si, že můžeme implementovat stejné chování jako při `PositivityFact` použití [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) funkce z <xref:Microsoft.Quantum.Diagnostics> oboru názvů:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="0ddfb-157">_Assertions \* na druhé straně se používají podobně jako fakta, ale můžou záviset na stavu cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="0ddfb-158">Odpovídajícím způsobem jsou definovány jako operace, zatímco fakta jsou definována jako funkce (jako v předchozím příkladu).</span><span class="sxs-lookup"><span data-stu-id="0ddfb-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="0ddfb-159">Pro pochopení rozlišení zvažte následující použití faktu v rámci kontrolního výrazu:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="0ddfb-160">V tomto příkladu používáme operaci <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> k vrácení počtu qubits dostupných k použití.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="0ddfb-161">Vzhledem k tomu, že to závisí na globálním stavu programu a jeho prostředí pro spuštění, `AssertQubitsAreAvailable` musí být naše definice také operace.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="0ddfb-162">Tento globální stav však můžeme použít k získání jednoduché `Bool` hodnoty jako vstupu do `Fact` funkce.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="0ddfb-163">[Předehru](xref:microsoft.quantum.libraries.standard.prelude), sestavování těchto nápadů, nabízí dva obzvláště užitečné kontrolní výrazy <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> a <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> model jako operace na `()` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="0ddfb-164">Tyto kontrolní výrazy přebírají operátor Pauli, který popisuje konkrétní měření zájmu, registrující hodnoty, na kterých je měření prováděno, a hypotetický výsledek.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="0ddfb-165">Cílové počítače, které pracují podle simulace, nejsou vázány [větaem bez klonování](https://en.wikipedia.org/wiki/No-cloning_theorem)a mohou provádět taková měření bez narušení registru, který předává takové kontrolní výrazy.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="0ddfb-166">Simulátor může následně vypadat podobně jako `PositivityFact` předchozí funkce, zastavit výpočty, pokud se hypotetický výsledek nepozoruje v praxi:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="0ddfb-167">U fyzických stavových procesorů, kde věta bez klonování brání prověřování stavu `AssertMeasurement` `AssertMeasurementProbability` nečinnosti, operace a se jednoduše vrátí `()` bez dalšího účinku.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="0ddfb-168"><xref:Microsoft.Quantum.Diagnostics>Obor názvů poskytuje několik funkcí `Assert` řady, se kterými můžete kontrolovat pokročilejší podmínky.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="0ddfb-169">Funkce výpisu paměti</span><span class="sxs-lookup"><span data-stu-id="0ddfb-169">Dump Functions</span></span>

<span data-ttu-id="0ddfb-170">Pro pomoc při řešení potíží s programy, <xref:Microsoft.Quantum.Diagnostics> obor názvů nabízí dvě funkce, které mohou vypsat do souboru aktuální stav cílového počítače: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> a <xref:Microsoft.Quantum.Diagnostics.DumpRegister> .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="0ddfb-171">Vygenerovaný výstup každého z nich závisí na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="0ddfb-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="0ddfb-172">DumpMachine</span></span>

<span data-ttu-id="0ddfb-173">Plný stav simulátoru, který je distribuován jako součást vývojářské sady pro plnění, zapisuje do souboru [funkci Wave](https://en.wikipedia.org/wiki/Wave_function) celého systému pro základní hodnoty, jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudu pravděpodobnosti měření rozdílového stavu výpočtu $ \ket{n} $, kde $ \ket{n} = \ket{B_ {n-1}... b_1b_0} $ pro BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="0ddfb-174">Například na počítači, který má přiděleno pouze dvě qubits a ve stavu nestavení, je $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Call <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generuje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="0ddfb-175">První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="0ddfb-176">Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{n} $ v kartézském a polárních formátech.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="0ddfb-177">Podrobně pro první řádek:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-177">In detail for the first row:</span></span>

* <span data-ttu-id="0ddfb-178">**`∣0❭:`** Tento řádek odpovídá `0` průběžnému stavu výpočtu.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="0ddfb-179">**`0.707107 +  0.000000 i`** : amplituda pravděpodobnosti ve formátu kartézském.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-179">**`0.707107 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="0ddfb-180">**` == `** : `equal` znaménko odděluje rovnocenné reprezentace.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-180">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="0ddfb-181">**`**********  `** : Grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-181">**`**********  `** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="0ddfb-182">**`[ 0.500000 ]`** : číselná hodnota velikosti</span><span class="sxs-lookup"><span data-stu-id="0ddfb-182">**`[ 0.500000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="0ddfb-183">**`    ---`** : Grafická reprezentace fáze amplitudy (viz následující výstup).</span><span class="sxs-lookup"><span data-stu-id="0ddfb-183">**`    ---`** : A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="0ddfb-184">**`[ 0.0000 rad ]`** : číselná hodnota fáze (v radiánech).</span><span class="sxs-lookup"><span data-stu-id="0ddfb-184">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="0ddfb-185">Velikost i fáze se zobrazí s grafickým znázorněním.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="0ddfb-186">Reprezentace velikosti je přímá – předána: zobrazuje pruh, což je `*` větší pravděpodobnost, po který se ovládací panel zvětšuje.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="0ddfb-187">Pro tuto fázi zobrazíme následující symboly, které reprezentují úhel na základě rozsahů:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="0ddfb-188">Následující příklady znázorňují `DumpMachine` některé běžné stavy:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-188">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="0ddfb-189">ID qubit se přiřadí za běhu a není nutně zarovnané na pořadí, ve kterém byla qubit přidělena nebo jeho pozice v rámci registru qubit.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0ddfb-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0ddfb-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="0ddfb-191">ID qubit můžete v aplikaci Visual Studio vyhledat tak, že do kódu zadáte zarážku a zkontrolujete hodnotu proměnné qubit, například:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Zobrazit ID qubit v aplikaci Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="0ddfb-193">qubit s indexem `0` v `register2` má ID = `3` , qubit s indexem `1` má ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0ddfb-194">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0ddfb-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="0ddfb-195">ID qubit můžete vyhledat pomocí <xref:Microsoft.Quantum.Intrinsic.Message> funkce a předáním proměnné qubit ve zprávě, například:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="0ddfb-196">který může vygenerovat tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="0ddfb-197">To znamená, že qubit s indexem `0` na `register2` má ID = `3` , qubit s indexem `1` má ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="0ddfb-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="0ddfb-198">\*\*_</span></span>

<span data-ttu-id="0ddfb-199">Vzhledem k <xref:Microsoft.Quantum.Diagnostics.DumpMachine> tomu, že je součástí  <xref:Microsoft.Quantum.Diagnostics> oboru názvů, je nutné přidat `open` příkaz pro přístup k němu:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="0ddfb-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="0ddfb-200">DumpRegister</span></span>

<span data-ttu-id="0ddfb-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> funguje jako <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , s tím rozdílem, že také přebírá pole qubits k omezení množství informací, které je relevantní pro odpovídající qubits.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="0ddfb-202">Stejně jako u <xref:Microsoft.Quantum.Diagnostics.DumpMachine> jsou informace vygenerované nástrojem <xref:Microsoft.Quantum.Diagnostics.DumpRegister> závislé na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="0ddfb-203">Pro plný stav simulátoru, který zapisuje do souboru, zapíše funkce Wave do globální fáze podsystému, který vygenerovala poskytnutá qubits ve stejném formátu jako <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .</span><span class="sxs-lookup"><span data-stu-id="0ddfb-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="0ddfb-204">Například znovu se přihlaste k počítači jenom se dvěma qubits přidělenými a ve stavu neobsazenosti $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} \ket {2} {1} ) \otimes) {2} {0} , \end{align} $ $ volá se, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> aby se `qubit[0]` vygeneroval tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="0ddfb-205">a voláním metody <xref:Microsoft.Quantum.Diagnostics.DumpRegister> `qubit[1]` generuje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="0ddfb-206">Obecně platí, že stav registru, který je entangled s jiným registrem, je smíšeným stavem, nikoli čistým stavem.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="0ddfb-207">V tomto případě <xref:Microsoft.Quantum.Diagnostics.DumpRegister> výstup zobrazí následující zprávu:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="0ddfb-208">Následující příklad ukazuje, jak lze použít jak <xref:Microsoft.Quantum.Diagnostics.DumpRegister> a <xref:Microsoft.Quantum.Diagnostics.DumpMachine> v Q# kódu:</span><span class="sxs-lookup"><span data-stu-id="0ddfb-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="0ddfb-209">Ladění</span><span class="sxs-lookup"><span data-stu-id="0ddfb-209">Debugging</span></span>

<span data-ttu-id="0ddfb-210">Nad `Assert` a `Dump` funkcemi a operace Q# podporuje podmnožinu standardních funkcí ladění sady Visual Studio: [nastavení zarážek řádků](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí nástroje F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)a [Kontrola hodnot klasických proměnných](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) je dostupná při spuštění kódu na simulátoru.</span><span class="sxs-lookup"><span data-stu-id="0ddfb-210">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="0ddfb-211">Ladění v Visual Studio Code využívá možnosti ladění poskytované v jazyce C# pro Visual Studio Code rozšíření využívající OmniSharp a vyžaduje instalaci [nejnovější verze](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="0ddfb-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 

---
title: Testování a ladění
description: Naučte se používat testy jednotek, fakta a kontrolní výrazy a funkce výpisu paměti pro testování a ladění programů v počtu procesorů.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: 374ac42255ab6b2c5eff8ab7879b3a5103181f7f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430913"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="9f17f-103">Testování a ladění</span><span class="sxs-lookup"><span data-stu-id="9f17f-103">Testing and debugging</span></span>

<span data-ttu-id="9f17f-104">Stejně jako v případě klasického programování je nutné mít na úmysl kontrolu nad tím, že se programy budou chovat podle účelu a že je možné diagnostiku nesprávného programu.</span><span class="sxs-lookup"><span data-stu-id="9f17f-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="9f17f-105">V této části se zaměříme na nástroje, které Q # nabízí pro testování a ladění programů v oblasti.</span><span class="sxs-lookup"><span data-stu-id="9f17f-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="9f17f-106">Testování částí</span><span class="sxs-lookup"><span data-stu-id="9f17f-106">Unit Tests</span></span>

<span data-ttu-id="9f17f-107">Jedním z běžných způsobů testování klasických programů je psaní malých programů s názvem *testy jednotek* , které spouštějí kód v knihovně, a porovnání jeho výstupu s očekávaným výstupem.</span><span class="sxs-lookup"><span data-stu-id="9f17f-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="9f17f-108">Můžeme třeba zajistit, aby se `Square(2)` vracely informace, `4` protože víme *předem* , že $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="9f17f-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="9f17f-109">Q # podporuje vytváření testů jednotek pro programy na více procesorech a to, které mohou být provedeny jako testy v rámci testovacího rozhraní [xUnit](https://xunit.github.io/) jednotek.</span><span class="sxs-lookup"><span data-stu-id="9f17f-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="9f17f-110">Vytvoření testovacího projektu</span><span class="sxs-lookup"><span data-stu-id="9f17f-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9f17f-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9f17f-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="9f17f-112">Otevřete Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="9f17f-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="9f17f-113">Přejděte do `File` nabídky a vyberte `New`  >  `Project...` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="9f17f-114">V pravém horním rohu vyhledejte `Q#` a vyberte `Q# Test Project` šablonu.</span><span class="sxs-lookup"><span data-stu-id="9f17f-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9f17f-115">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9f17f-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9f17f-116">Z oblíbeného příkazového řádku spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="9f17f-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="9f17f-117">Nový projekt bude mít jeden soubor `Tests.qs` , který poskytuje pohodlný místo pro definování nových testů jednotek Q #.</span><span class="sxs-lookup"><span data-stu-id="9f17f-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="9f17f-118">Zpočátku tento soubor obsahuje jeden ukázkový test jednotky `AllocateQubit` , který kontroluje, zda je nově přidělená qubit ve stavu $ \ket {0} $ a vytiskne zprávu:</span><span class="sxs-lookup"><span data-stu-id="9f17f-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="9f17f-119">: New: operace Q # nebo funkce, která přebírá argument typu `Unit` a vrácení, `Unit` může být označena jako test jednotky prostřednictvím `@Test("...")` atributu.</span><span class="sxs-lookup"><span data-stu-id="9f17f-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="9f17f-120">Argument výše uvedeného atributu `"QuantumSimulator"` Určuje cíl, na kterém je test spuštěn.</span><span class="sxs-lookup"><span data-stu-id="9f17f-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="9f17f-121">Jeden test může být proveden na více cílech.</span><span class="sxs-lookup"><span data-stu-id="9f17f-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="9f17f-122">Přidejte například atribut `@Test("ResourcesEstimator")` výše `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="9f17f-123">Uložte soubor a proveďte všechny testy.</span><span class="sxs-lookup"><span data-stu-id="9f17f-123">Save the file and execute all tests.</span></span> <span data-ttu-id="9f17f-124">Nyní by měly být dvě testy jednotek, jedna kde AllocateQubit je spuštěna na QuantumSimulator a druhá, kde se spustí v ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="9f17f-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="9f17f-125">Kompilátor Q # rozpoznává předdefinované cíle "QuantumSimulator", "ToffoliSimulator" a "ResourcesEstimator" jako platné cíle provádění pro testování částí.</span><span class="sxs-lookup"><span data-stu-id="9f17f-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="9f17f-126">Je také možné zadat libovolný plně kvalifikovaný název pro definování vlastního cíle provádění.</span><span class="sxs-lookup"><span data-stu-id="9f17f-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="9f17f-127">Spouštění testů jednotek Q #</span><span class="sxs-lookup"><span data-stu-id="9f17f-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9f17f-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9f17f-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="9f17f-129">Jako jednorázové nastavení jednotlivých řešení přejděte do `Test` nabídky a vyberte `Test Settings`  >  `Default Processor Architecture`  >  `X64` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="9f17f-130">Výchozí nastavení architektury procesoru pro Visual Studio je uloženo v souboru možností řešení ( `.suo` ) pro každé řešení.</span><span class="sxs-lookup"><span data-stu-id="9f17f-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="9f17f-131">Pokud tento soubor odstraníte, budete ho muset `X64` znovu vybrat jako architekturu procesoru.</span><span class="sxs-lookup"><span data-stu-id="9f17f-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="9f17f-132">Sestavte projekt, přejděte do `Test` nabídky a vyberte `Windows`  >  `Test Explorer` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="9f17f-133">`AllocateQubit`zobrazí se v seznamu testů ve `Not Run Tests` skupině.</span><span class="sxs-lookup"><span data-stu-id="9f17f-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="9f17f-134">Vyberte `Run All` nebo spusťte tento jednotlivý test a měl by být úspěch.</span><span class="sxs-lookup"><span data-stu-id="9f17f-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9f17f-135">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9f17f-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9f17f-136">Chcete-li spustit testy, přejděte do složky projektu (složka obsahující `Tests.csproj` ) a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="9f17f-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="9f17f-137">Mělo by se zobrazit výstup podobný následujícímu:</span><span class="sxs-lookup"><span data-stu-id="9f17f-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="9f17f-138">Testy jednotek lze filtrovat podle jejich názvu nebo cíle provádění:</span><span class="sxs-lookup"><span data-stu-id="9f17f-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="9f17f-139">Vnitřní funkce <xref:microsoft.quantum.intrinsic.message> má typ `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.</span><span class="sxs-lookup"><span data-stu-id="9f17f-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9f17f-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9f17f-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="9f17f-141">Po spuštění testu v Průzkumníku testů a kliknutí na test se zobrazí panel s informacemi o spuštění testu: stav úspěch/selhání, uplynulý čas a "výstup".</span><span class="sxs-lookup"><span data-stu-id="9f17f-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="9f17f-142">Pokud kliknete na odkaz "výstup", výstup testu se otevře v novém okně.</span><span class="sxs-lookup"><span data-stu-id="9f17f-142">If you click the "Output" link, test output will open in a new window.</span></span>

![Výstup testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9f17f-144">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9f17f-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9f17f-145">Stav předání/selhání každého testu je vytištěn do konzoly nástrojem `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="9f17f-146">V případě neúspěšných testů jsou výstupy také vytištěny do konzoly nástroje, což vám umožní diagnostikovat selhání.</span><span class="sxs-lookup"><span data-stu-id="9f17f-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="9f17f-147">Fakta a kontrolní výrazy</span><span class="sxs-lookup"><span data-stu-id="9f17f-147">Facts and Assertions</span></span>

<span data-ttu-id="9f17f-148">Vzhledem k tomu, že funkce v Q # nemají žádné _logické_ vedlejší účinky, jakékoliv _jiné druhy_ účinků provádění funkce, jejíž výstupní typ je prázdná řazená kolekce členů, se v `()` programu Q # nikdy neprojeví.</span><span class="sxs-lookup"><span data-stu-id="9f17f-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="9f17f-149">To znamená, že cílový počítač se může rozhodnout, že nespustí žádnou funkci `()` , která se vrátí se zárukou, že toto opomenutí nebude upravovat chování žádného následujícího kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="9f17f-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="9f17f-150">To umožňuje funkcím vracet `()` (tj. `Unit` ) užitečný nástroj pro vkládání kontrolních výrazů a logiku ladění do programů Q #.</span><span class="sxs-lookup"><span data-stu-id="9f17f-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="9f17f-151">Pojďme si vzít v úvahu jednoduchý příklad:</span><span class="sxs-lookup"><span data-stu-id="9f17f-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="9f17f-152">Zde klíčové slovo `fail` označuje, že výpočet by neměl pokračovat, vyvolání výjimky v cílovém počítači, na kterém je spuštěn program Q #.</span><span class="sxs-lookup"><span data-stu-id="9f17f-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="9f17f-153">Podle definice nemůže být selhání tohoto druhu zjištěno v rámci Q #, protože po dosažení příkazu není spuštěn žádný další kód Q # `fail` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="9f17f-154">Proto, pokud budeme pokračovat po volání `PositivityFact` , můžeme si být jisti, že jeho vstup byl kladný.</span><span class="sxs-lookup"><span data-stu-id="9f17f-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="9f17f-155">Všimněte si, že můžeme implementovat stejné chování jako při `PositivityFact` použití [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkce z <xref:microsoft.quantum.diagnostics> oboru názvů:</span><span class="sxs-lookup"><span data-stu-id="9f17f-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="9f17f-156">*Kontrolní výrazy*jsou na druhé straně používány podobně jako fakta, ale mohou být závislé na stavu cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="9f17f-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="9f17f-157">Odpovídajícím způsobem jsou definovány jako operace, zatímco fakta jsou definována jako funkce (jak je uvedeno výše).</span><span class="sxs-lookup"><span data-stu-id="9f17f-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="9f17f-158">Pro pochopení rozlišení zvažte následující použití faktu v rámci kontrolního výrazu:</span><span class="sxs-lookup"><span data-stu-id="9f17f-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="9f17f-159">V tomto příkladu používáme operaci <xref:microsoft.quantum.environment.getqubitsavailabletouse> k vrácení počtu qubits dostupných k použití.</span><span class="sxs-lookup"><span data-stu-id="9f17f-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="9f17f-160">Vzhledem k tomu, že to jasně závisí na globálním stavu programu a jeho prováděcím prostředí, `AssertQubitsAreAvailable` musí být naše definice také operace.</span><span class="sxs-lookup"><span data-stu-id="9f17f-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="9f17f-161">Tento globální stav však můžeme použít k získání jednoduché `Bool` hodnoty jako vstupu do `Fact` funkce.</span><span class="sxs-lookup"><span data-stu-id="9f17f-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="9f17f-162">[Předehru](xref:microsoft.quantum.libraries.standard.prelude) na těchto nápadech nabízí dva obzvláště užitečné kontrolní výrazy, které se <xref:microsoft.quantum.intrinsic.assert> <xref:microsoft.quantum.intrinsic.assertprob> modelují jako operace na `()` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="9f17f-163">Tyto kontrolní výrazy přebírají operátor Pauli, který popisuje konkrétní měření zájmu, registrující hodnoty, na kterých se má provést měření, a hypotetický výsledek.</span><span class="sxs-lookup"><span data-stu-id="9f17f-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="9f17f-164">V cílových počítačích, které pracují s simulací, nebudeme vázáni pomocí [věta bez klonování](https://en.wikipedia.org/wiki/No-cloning_theorem)a může provádět taková měření, aniž by došlo k narušení registru předaného do takových kontrolních výrazů.</span><span class="sxs-lookup"><span data-stu-id="9f17f-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="9f17f-165">Simulátor pak může, podobně jako `PositivityFact` funkce výše, přerušit výpočet, pokud se hypotetický výsledek nepozoruje v praxi:</span><span class="sxs-lookup"><span data-stu-id="9f17f-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="9f17f-166">U fyzických stavových procesorů, kde věta bez klonování brání prověřování stavu `Assert` `AssertProb` nečinnosti, operace a se jednoduše vrátí `()` bez dalšího účinku.</span><span class="sxs-lookup"><span data-stu-id="9f17f-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="9f17f-167"><xref:microsoft.quantum.diagnostics>Obor názvů poskytuje několik dalších funkcí řady, `Assert` které nám umožňují kontrolovat pokročilejší podmínky.</span><span class="sxs-lookup"><span data-stu-id="9f17f-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="9f17f-168">Funkce výpisu paměti</span><span class="sxs-lookup"><span data-stu-id="9f17f-168">Dump Functions</span></span>

<span data-ttu-id="9f17f-169">Pro pomoc při řešení potíží s programy, <xref:microsoft.quantum.diagnostics> obor názvů nabízí dvě funkce, které mohou vypsat do souboru aktuální stav cílového počítače: <xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="9f17f-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="9f17f-170">Vygenerovaný výstup každého z nich závisí na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="9f17f-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="9f17f-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="9f17f-171">DumpMachine</span></span>

<span data-ttu-id="9f17f-172">Plný stav simulátoru, který je distribuován jako součást vývojářské sady pro plnění, zapisuje do souboru [funkci Wave](https://en.wikipedia.org/wiki/Wave_function) celého systému pro základní hodnoty, jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudu pravděpodobnosti měření rozdílového stavu výpočtu $ \ket{n} $, kde $ \ket{n} = \ket{B_ {n-1}... b_1b_0} $ pro BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="9f17f-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="9f17f-173">Například na počítači, který má přiděleno pouze dvě qubits a ve stavu nestavení, je $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Call <xref:microsoft.quantum.diagnostics.dumpmachine> generuje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="9f17f-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="9f17f-174">První řádek poskytuje komentář s ID odpovídající qubits v jejich významném pořadí.</span><span class="sxs-lookup"><span data-stu-id="9f17f-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="9f17f-175">Ostatní řádky popisují amplitudu pravděpodobnosti měření vektoru stavu $ \ket{n} $ v kartézském a polárních formátech.</span><span class="sxs-lookup"><span data-stu-id="9f17f-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="9f17f-176">Podrobně pro první řádek:</span><span class="sxs-lookup"><span data-stu-id="9f17f-176">In detail for the first row:</span></span>

* <span data-ttu-id="9f17f-177">**`∣0❭:`** Tento řádek odpovídá `0` průběžnému stavu výpočtu.</span><span class="sxs-lookup"><span data-stu-id="9f17f-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="9f17f-178">**`0.707107 +  0.000000 i`**: amplituda pravděpodobnosti ve formátu kartézském.</span><span class="sxs-lookup"><span data-stu-id="9f17f-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="9f17f-179">**` == `**: `equal` symbol oddělené reprezentace obou shod.</span><span class="sxs-lookup"><span data-stu-id="9f17f-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="9f17f-180">**`**********  `**: Grafická reprezentace velikosti, počet `*` je úměrný pravděpodobnosti měření tohoto vektoru stavu.</span><span class="sxs-lookup"><span data-stu-id="9f17f-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="9f17f-181">**`[ 0.500000 ]`**: číselná hodnota velikosti</span><span class="sxs-lookup"><span data-stu-id="9f17f-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="9f17f-182">**`    ---`**: Grafická reprezentace fáze amplitudy (viz níže).</span><span class="sxs-lookup"><span data-stu-id="9f17f-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="9f17f-183">**`[ 0.0000 rad ]`**: číselná hodnota fáze (v radiánech).</span><span class="sxs-lookup"><span data-stu-id="9f17f-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="9f17f-184">Velikost i fáze se zobrazí s grafickým znázorněním.</span><span class="sxs-lookup"><span data-stu-id="9f17f-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="9f17f-185">Reprezentace velikosti je přímá – předána: zobrazuje pruh, což je `*` větší pravděpodobnost, po který se ovládací panel zvětšuje.</span><span class="sxs-lookup"><span data-stu-id="9f17f-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="9f17f-186">Pro tuto fázi zobrazíme následující symboly, které reprezentují úhel na základě rozsahů:</span><span class="sxs-lookup"><span data-stu-id="9f17f-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="9f17f-187">Následující příklady znázorňují `DumpMachine` některé běžné stavy:</span><span class="sxs-lookup"><span data-stu-id="9f17f-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="9f17f-188">ID qubit se přiřadí za běhu a není nutně zarovnané na pořadí, ve kterém byla qubit přidělena nebo jeho pozice v rámci registru qubit.</span><span class="sxs-lookup"><span data-stu-id="9f17f-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="9f17f-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9f17f-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="9f17f-190">ID qubit v aplikaci Visual Studio můžete zjistit tak, že do kódu zadáte zarážku a zkontrolujete hodnotu proměnné qubit, například:</span><span class="sxs-lookup"><span data-stu-id="9f17f-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Zobrazit ID qubit v aplikaci Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="9f17f-192">qubit s indexem `0` v `register2` má ID = `3` , qubit s indexem `1` má ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9f17f-193">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9f17f-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="9f17f-194">ID qubit můžete zjistit pomocí <xref:microsoft.quantum.intrinsic.message> funkce a předáním proměnné qubit ve zprávě, například:</span><span class="sxs-lookup"><span data-stu-id="9f17f-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="9f17f-195">který může vygenerovat tento výstup:</span><span class="sxs-lookup"><span data-stu-id="9f17f-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="9f17f-196">To znamená, že qubit s indexem `0` na `register2` má ID = `3` , qubit s indexem `1` má ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="9f17f-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="9f17f-197"><xref:microsoft.quantum.diagnostics.dumpmachine>je součástí <xref:microsoft.quantum.diagnostics> oboru názvů, takže aby ho bylo možné použít, je nutné přidat `open` příkaz:</span><span class="sxs-lookup"><span data-stu-id="9f17f-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="9f17f-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="9f17f-198">DumpRegister</span></span>

<span data-ttu-id="9f17f-199"><xref:microsoft.quantum.diagnostics.dumpregister>funguje podobně jako <xref:microsoft.quantum.diagnostics.dumpmachine> s tím rozdílem, že také přebírá pole qubits, které omezuje množství informací, které je relevantní pro odpovídající qubits.</span><span class="sxs-lookup"><span data-stu-id="9f17f-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="9f17f-200">Stejně jako u <xref:microsoft.quantum.diagnostics.dumpmachine> jsou informace vygenerované nástrojem <xref:microsoft.quantum.diagnostics.dumpregister> závislé na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="9f17f-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="9f17f-201">Pro plný stav simulátoru, který zapisuje do souboru, zapíše funkce Wave do globální fáze podsystému, který vygenerovala poskytnutá qubits ve stejném formátu jako <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="9f17f-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="9f17f-202">Například znovu se přihlaste k počítači jenom se dvěma qubits přidělenými a ve stavu neobsazenosti $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} \ket {2} {1} ) \otimes) {2} {0} , \end{align} $ $ volá se, <xref:microsoft.quantum.diagnostics.dumpregister> aby se `qubit[0]` vygeneroval tento výstup:</span><span class="sxs-lookup"><span data-stu-id="9f17f-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="9f17f-203">a voláním metody <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[1]` generuje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="9f17f-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="9f17f-204">Obecně platí, že stav registru, který je entangled s jiným registrem, je smíšeným stavem, nikoli čistým stavem.</span><span class="sxs-lookup"><span data-stu-id="9f17f-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="9f17f-205">V tomto případě <xref:microsoft.quantum.diagnostics.dumpregister> výstup zobrazí následující zprávu:</span><span class="sxs-lookup"><span data-stu-id="9f17f-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="9f17f-206">Následující příklad ukazuje, jak můžete použít jak <xref:microsoft.quantum.diagnostics.dumpregister> a <xref:microsoft.quantum.diagnostics.dumpmachine> v kódu Q #:</span><span class="sxs-lookup"><span data-stu-id="9f17f-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="9f17f-207">Ladění</span><span class="sxs-lookup"><span data-stu-id="9f17f-207">Debugging</span></span>

<span data-ttu-id="9f17f-208">V rámci `Assert` funkcí a `Dump` operací Q # podporuje podmnožinu standardních možností ladění sady Visual Studio: [nastavení zarážek řádků](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí nástroje F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) a [Kontrola hodnot klasických proměnných](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) je všechno možné při provádění kódu v simulátoru.</span><span class="sxs-lookup"><span data-stu-id="9f17f-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="9f17f-209">Ladění v Visual Studio Code využívá možnosti ladění poskytované v jazyce C# pro Visual Studio Code rozšíření využívající OmniSharp a vyžaduje instalaci [nejnovější verze](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="9f17f-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
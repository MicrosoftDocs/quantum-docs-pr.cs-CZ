---
title: Testování a ladění programů Q#
description: Naučte se používat testy částí, fakta a kontrolní výrazy a výpis funkce pro testování a ladění kvantové programy.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030578"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="0c152-103">Testování a ladění</span><span class="sxs-lookup"><span data-stu-id="0c152-103">Testing and Debugging</span></span>

<span data-ttu-id="0c152-104">Stejně jako u klasického programování, je nezbytné, aby bylo možné zkontrolovat, že kvantové programy působí tak, jak bylo zamýšleno, a aby bylo možné diagnostikovat kvantový program, který je nesprávný.</span><span class="sxs-lookup"><span data-stu-id="0c152-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="0c152-105">V této části se zabýváme nástroji, které nabízí Q# pro testování a ladění kvantových programů.</span><span class="sxs-lookup"><span data-stu-id="0c152-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="0c152-106">Jednotkové testy</span><span class="sxs-lookup"><span data-stu-id="0c152-106">Unit Tests</span></span>

<span data-ttu-id="0c152-107">Jedním z běžných přístupů k testování klasických programů je psaní malých programů nazývaných *testy částí,* které spouštějí kód v knihovně a porovnávají jeho výstup s očekávaným výstupem.</span><span class="sxs-lookup"><span data-stu-id="0c152-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="0c152-108">Například, můžeme chtít zajistit, aby `Square(2)` vrací `4`, protože víme, a *priori,* že $ 2 ^ 2 = 4 $.</span><span class="sxs-lookup"><span data-stu-id="0c152-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="0c152-109">Q# podporuje vytváření testů částí pro kvantové programy, které mohou být provedeny jako testy v rámci testování jednotky [xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="0c152-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="0c152-110">Vytvoření testovacího projektu</span><span class="sxs-lookup"><span data-stu-id="0c152-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0c152-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0c152-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0c152-112">Otevřete Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="0c152-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="0c152-113">Přejděte `File` do nabídky `New`  >  `Project...`a vyberte .</span><span class="sxs-lookup"><span data-stu-id="0c152-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="0c152-114">V pravém horním rohu `Q#`vyhledejte a `Q# Test Project` vyberte šablonu.</span><span class="sxs-lookup"><span data-stu-id="0c152-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0c152-115">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0c152-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0c152-116">Na oblíbeném příkazovém řádku spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="0c152-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="0c152-117">Váš nový projekt bude `Tests.qs`mít jeden soubor , který poskytuje vhodné místo pro definování nových testů jednotek Q#.</span><span class="sxs-lookup"><span data-stu-id="0c152-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="0c152-118">Zpočátku tento soubor obsahuje `AllocateQubit` jeden test vzorkovací jednotky, který zkontroluje,{0}zda nově přidělený qubit je ve stavu $\ket $ a vytiskne zprávu:</span><span class="sxs-lookup"><span data-stu-id="0c152-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: <span data-ttu-id="0c152-119">Všechny Q# operace nebo funkce, `Unit` která `Unit` má argument typu a `@Test("...")` vrátí lze označit jako test jednotky prostřednictvím atributu.</span><span class="sxs-lookup"><span data-stu-id="0c152-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="0c152-120">Argument k tomuto `"QuantumSimulator"` atributu výše určuje cíl, na kterém je test proveden.</span><span class="sxs-lookup"><span data-stu-id="0c152-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="0c152-121">Jeden test lze provést na více cílů.</span><span class="sxs-lookup"><span data-stu-id="0c152-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="0c152-122">Přidejte například `@Test("ResourcesEstimator")` atribut `AllocateQubit`výše .</span><span class="sxs-lookup"><span data-stu-id="0c152-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="0c152-123">Uložte soubor a proveďte všechny testy.</span><span class="sxs-lookup"><span data-stu-id="0c152-123">Save the file and execute all tests.</span></span> <span data-ttu-id="0c152-124">Nyní by měl y být dva testy částí, jeden kde Je spuštěn AllocateQubit na QuantumSimulator a jeden, kde je spuštěn v ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="0c152-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="0c152-125">Kompilátor Q# rozpozná předdefinované cíle "QuantumSimulator", "ToffoliSimulator" a "ResourcesEstimator" jako platné cíle provádění pro testy částí.</span><span class="sxs-lookup"><span data-stu-id="0c152-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="0c152-126">Je také možné zadat libovolný plně kvalifikovaný název pro definování cíle vlastního spuštění.</span><span class="sxs-lookup"><span data-stu-id="0c152-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="0c152-127">Spuštění testů jednotek Q#</span><span class="sxs-lookup"><span data-stu-id="0c152-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0c152-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0c152-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0c152-129">Jako jednorázové nastavení řešení přejděte do `Test` nabídky `Test Settings`  >  `Default Processor Architecture`  >  `X64`a vyberte .</span><span class="sxs-lookup"><span data-stu-id="0c152-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="0c152-130">Výchozí nastavení architektury procesoru pro Visual Studio`.suo`je uloženo v souboru možností řešení ( ) pro každé řešení.</span><span class="sxs-lookup"><span data-stu-id="0c152-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="0c152-131">Pokud odstraníte tento soubor, budete `X64` muset znovu vybrat jako architekturu procesoru.</span><span class="sxs-lookup"><span data-stu-id="0c152-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="0c152-132">Sestavte projekt, `Test` přejděte `Windows`  >  `Test Explorer`do nabídky a vyberte .</span><span class="sxs-lookup"><span data-stu-id="0c152-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="0c152-133">`AllocateQubit`v seznamu testů ve `Not Run Tests` skupině.</span><span class="sxs-lookup"><span data-stu-id="0c152-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="0c152-134">Vyberte `Run All` nebo spusťte tento individuální test, a to by mělo projít!</span><span class="sxs-lookup"><span data-stu-id="0c152-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0c152-135">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0c152-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0c152-136">Chcete-li spustit testy, přejděte do `Tests.csproj`složky projektu (složka, která obsahuje ) a spusťte příkaz:</span><span class="sxs-lookup"><span data-stu-id="0c152-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="0c152-137">Měli byste získat výstup podobný následujícímu:</span><span class="sxs-lookup"><span data-stu-id="0c152-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="0c152-138">Jednotkové testy lze filtrovat podle jejich názvu a/nebo cíle spuštění:</span><span class="sxs-lookup"><span data-stu-id="0c152-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="0c152-139">Vnitřní funkce <xref:microsoft.quantum.intrinsic.message> má typ `(String -> Unit)` a umožňuje vytváření diagnostických zpráv.</span><span class="sxs-lookup"><span data-stu-id="0c152-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0c152-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0c152-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0c152-141">Po provedení testu v Průzkumníkovi testů a kliknutí na test se zobrazí panel s informacemi o spuštění testu: Předané/neúspěšné stav, uplynulý čas a odkaz "Výstup".</span><span class="sxs-lookup"><span data-stu-id="0c152-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="0c152-142">Pokud kliknete na odkaz "Výstup", testovací výstup se otevře v novém okně.</span><span class="sxs-lookup"><span data-stu-id="0c152-142">If you click the "Output" link, test output will open in a new window.</span></span>

![testovací výstup](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0c152-144">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0c152-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0c152-145">Stav průchodu/selhání pro každý test je `dotnet test`vytištěn do konzoly společností .</span><span class="sxs-lookup"><span data-stu-id="0c152-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="0c152-146">Pro selhání testů jsou výstupy také vytištěny do konzoly, aby pomohly diagnostikovat selhání.</span><span class="sxs-lookup"><span data-stu-id="0c152-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="0c152-147">Fakta a tvrzení</span><span class="sxs-lookup"><span data-stu-id="0c152-147">Facts and Assertions</span></span>

<span data-ttu-id="0c152-148">Vzhledem k tomu, že funkce v Q# nemají žádné _logické_ vedlejší účinky, `()` žádné jiné _druhy_ účinků provádění funkce, jejíž výstupní typ je prázdná řazená kolekce členů, nelze nikdy pozorovat z programu Q#.</span><span class="sxs-lookup"><span data-stu-id="0c152-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="0c152-149">To znamená, že cílový počítač může zvolit `()` neprovádět žádnou funkci, která se vrátí se zárukou, že toto opomenutí nezmění chování žádného následujícího kódu Q#.</span><span class="sxs-lookup"><span data-stu-id="0c152-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="0c152-150">Díky funkcím `()` vracejícím se `Unit`(tj. ) jako užitečný nástroj pro vkládání kontrolních výrazů a logiky ladění do programů Q#.</span><span class="sxs-lookup"><span data-stu-id="0c152-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="0c152-151">Podívejme se na jednoduchý příklad:</span><span class="sxs-lookup"><span data-stu-id="0c152-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="0c152-152">Zde klíčové `fail` slovo označuje, že by nemělo pokračovat výpočtu, což vyvolává výjimku v cílovém počítači se spuštěným programem Q#.</span><span class="sxs-lookup"><span data-stu-id="0c152-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="0c152-153">Podle definice selhání tohoto druhu nelze pozorovat z q#, jako žádný další `fail` Q # kód je spuštěn po dosažení příkazu.</span><span class="sxs-lookup"><span data-stu-id="0c152-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="0c152-154">Pokud tedy budeme pokračovat po `PositivityFact`výzvě k , můžeme si být jisti, že jeho vstup byl pozitivní.</span><span class="sxs-lookup"><span data-stu-id="0c152-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="0c152-155">Všimněte si, že můžeme `PositivityFact` implementovat stejné chování jako pomocí [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkce z oboru <xref:microsoft.quantum.diagnostics> názvů:</span><span class="sxs-lookup"><span data-stu-id="0c152-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="0c152-156">*Kontrolní výrazy*, na druhé straně se používají podobně jako fakta, ale může být závislá na stavu cílového stroje.</span><span class="sxs-lookup"><span data-stu-id="0c152-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="0c152-157">Odpovídajícím způsobem jsou definovány jako operace, zatímco fakta jsou definována jako funkce (jak je uvedeno výše).</span><span class="sxs-lookup"><span data-stu-id="0c152-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="0c152-158">Chcete-li pochopit rozdíl, zvažte následující použití skutečnosti v rámci tvrzení:</span><span class="sxs-lookup"><span data-stu-id="0c152-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="0c152-159">Zde používáme operaci <xref:microsoft.quantum.environment.getqubitsavailabletouse> k vrácení počtu qubitů, které jsou k dispozici pro použití.</span><span class="sxs-lookup"><span data-stu-id="0c152-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="0c152-160">Vzhledem k tomu, že to jasně závisí na globálním `AssertQubitsAreAvailable` stavu programu a jeho provádění prostředí, naše definice musí být operace stejně.</span><span class="sxs-lookup"><span data-stu-id="0c152-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="0c152-161">Tento globální stav však můžeme použít `Bool` k zadání `Fact` jednoduché hodnoty jako vstupu do funkce.</span><span class="sxs-lookup"><span data-stu-id="0c152-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="0c152-162">V návaznosti na tyto myšlenky, [předehra](xref:microsoft.quantum.libraries.standard.prelude) nabízí dvě obzvláště užitečná tvrzení, <xref:microsoft.quantum.intrinsic.assert> a <xref:microsoft.quantum.intrinsic.assertprob> to jak modelované jako operace na `()`.</span><span class="sxs-lookup"><span data-stu-id="0c152-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="0c152-163">Tato tvrzení každý vzít Operátor Pauli popisující konkrétní měření zájmu, kvantový registr, na kterém má být provedeno měření, a hypotetický výsledek.</span><span class="sxs-lookup"><span data-stu-id="0c152-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="0c152-164">Na cílových strojích, které pracují simulací, nejsme vázáni [neklonující teorém](https://en.wikipedia.org/wiki/No-cloning_theorem), a může provádět taková měření bez narušení registru předán a tato tvrzení.</span><span class="sxs-lookup"><span data-stu-id="0c152-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="0c152-165">Simulátor pak může, podobně `PositivityFact` jako výše uvedené funkce, přerušit výpočty, pokud hypotetický výsledek by nebyl dodržen v praxi:</span><span class="sxs-lookup"><span data-stu-id="0c152-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="0c152-166">Na fyzickém kvantovém hardwaru, kde neklonující teorém zabraňuje zkoumání kvantového stavu, `Assert` se operace a `AssertProb` jednoduše vrátí `()` bez jiného účinku.</span><span class="sxs-lookup"><span data-stu-id="0c152-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="0c152-167">Obor <xref:microsoft.quantum.diagnostics> názvů poskytuje několik dalších funkcí rodiny, `Assert` které nám umožňují kontrolovat pokročilejší podmínky.</span><span class="sxs-lookup"><span data-stu-id="0c152-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="0c152-168">Funkce výpisu</span><span class="sxs-lookup"><span data-stu-id="0c152-168">Dump Functions</span></span>

<span data-ttu-id="0c152-169">Chcete-li pomoci při <xref:microsoft.quantum.diagnostics> řešení potíží s kvantovými programy, obor názvů nabízí <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister>dvě funkce, které lze vykládat do souboru aktuální stav cílového počítače: a .</span><span class="sxs-lookup"><span data-stu-id="0c152-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="0c152-170">Generovaný výstup každého z nich závisí na cílovém stroji.</span><span class="sxs-lookup"><span data-stu-id="0c152-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="0c152-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="0c152-171">DumpMachine</span></span>

<span data-ttu-id="0c152-172">Full-state kvantový simulátor distribuovaný jako součást Quantum Development Kit zapíše do souboru [vlnovou funkci](https://en.wikipedia.org/wiki/Wave_function) celého kvantového systému, jako jednorozměrné pole komplexních čísel, ve kterém každý prvek představuje amplitudu pravděpodobnosti měření výpočtového základu stavu $\ket{n}$, kde $\ket{n} = \ket{b_{n-1}... b_1b_0}$ za bity $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="0c152-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="0c152-173">Například na počítači s přidělenými pouze dvěma qubity a v kvantovém stavu $${1}\begin{align}{2}\ket{\psi} = \frac {\sqrt } \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ volání <xref:microsoft.quantum.diagnostics.dumpmachine> generuje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0c152-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="0c152-174">První řádek poskytuje komentář s ID odpovídajícíqubity v jejich významné pořadí.</span><span class="sxs-lookup"><span data-stu-id="0c152-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="0c152-175">Zbývající řádky popisují amplitudu pravděpodobnosti měření vektoru stavu základu $\ket{n}$ v kartézském i polárním formátu.</span><span class="sxs-lookup"><span data-stu-id="0c152-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="0c152-176">Podrobně pro první řádek:</span><span class="sxs-lookup"><span data-stu-id="0c152-176">In detail for the first row:</span></span>

* <span data-ttu-id="0c152-177">**`∣0❭:`** tento řádek odpovídá `0` stavu výpočtového základu</span><span class="sxs-lookup"><span data-stu-id="0c152-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="0c152-178">**`0.707107 +  0.000000 i`**: amplituda pravděpodobnosti v kartézské majedře.</span><span class="sxs-lookup"><span data-stu-id="0c152-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="0c152-179">**` == `**: `equal` znaménko sereperates obě ekvivalentní reprezentace.</span><span class="sxs-lookup"><span data-stu-id="0c152-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="0c152-180">**`**********  `**: Grafické znázornění velikosti, `*` počet je úměrný pravděpodobnosti měření tohoto vektoru stavu.</span><span class="sxs-lookup"><span data-stu-id="0c152-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="0c152-181">**`[ 0.500000 ]`**: číselná hodnota velikosti</span><span class="sxs-lookup"><span data-stu-id="0c152-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="0c152-182">**`    ---`**: Grafické znázornění fáze amplitudy (viz níže).</span><span class="sxs-lookup"><span data-stu-id="0c152-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="0c152-183">**`[ 0.0000 rad ]`**: číselná hodnota fáze (v radiánech).</span><span class="sxs-lookup"><span data-stu-id="0c152-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="0c152-184">Velikost i fáze jsou zobrazeny s grafickým znázorněním.</span><span class="sxs-lookup"><span data-stu-id="0c152-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="0c152-185">Velikost reprezentace je rovný-vpřed: ukazuje `*`bar , tím větší je pravděpodobnost, že větší bar bude.</span><span class="sxs-lookup"><span data-stu-id="0c152-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="0c152-186">Pro fázi zobrazujeme následující symboly, které představují úhel založený na rozsahu:</span><span class="sxs-lookup"><span data-stu-id="0c152-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="0c152-187">Následující příklady `DumpMachine` ukazují některé běžné stavy:</span><span class="sxs-lookup"><span data-stu-id="0c152-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="0c152-188">Id qubit je přiřazen za běhu a není nutně zarovnán s pořadím, ve kterém byl qubit přidělen, nebo jeho pozice v registru qubit.</span><span class="sxs-lookup"><span data-stu-id="0c152-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0c152-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0c152-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="0c152-190">Můžete zjistit qubit id v sadě Visual Studio vložením zarážku v kódu a kontrolou hodnoty qubit proměnné, například:</span><span class="sxs-lookup"><span data-stu-id="0c152-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![zobrazit qubit id v sadě Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="0c152-192">qubit s `0` indexem na `register2` `3`má id= `1` , qubit`2`s indexem má id= .</span><span class="sxs-lookup"><span data-stu-id="0c152-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0c152-193">Příkazový řádek / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0c152-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="0c152-194">Můžete zjistit qubit id pomocí <xref:microsoft.quantum.intrinsic.message> funkce a předávání qubit proměnné ve zprávě, například:</span><span class="sxs-lookup"><span data-stu-id="0c152-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="0c152-195">které by mohly tento výstup generovat:</span><span class="sxs-lookup"><span data-stu-id="0c152-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="0c152-196">což `0` znamená, že qubit `register2` s indexem na má`3` `1` id=`2`, qubit s indexem má id= .</span><span class="sxs-lookup"><span data-stu-id="0c152-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="0c152-197"><xref:microsoft.quantum.diagnostics.dumpmachine>je součástí <xref:microsoft.quantum.diagnostics> oboru názvů, takže chcete-li jej `open` použít, musíte přidat příkaz:</span><span class="sxs-lookup"><span data-stu-id="0c152-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="0c152-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="0c152-198">DumpRegister</span></span>

<span data-ttu-id="0c152-199"><xref:microsoft.quantum.diagnostics.dumpregister>funguje <xref:microsoft.quantum.diagnostics.dumpmachine>jako , s výjimkou to také trvá řadu qubits omezit množství informací pouze na to, které jsou relevantní pro odpovídající qubity.</span><span class="sxs-lookup"><span data-stu-id="0c152-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="0c152-200">Stejně <xref:microsoft.quantum.diagnostics.dumpmachine>jako u , <xref:microsoft.quantum.diagnostics.dumpregister> informace generované závisí na cílovém stroji.</span><span class="sxs-lookup"><span data-stu-id="0c152-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="0c152-201">Pro full-state kvantový simulátor zapíše do souboru vlnovou funkci až do globální fáze kvantového subsystému generovaného poskytnutými qubity ve stejném formátu jako <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="0c152-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="0c152-202">Například vezměte znovu stroj s pouze dvěma qubity přidělenými a v kvantovém stavu $${1}\begin{align}{2}\ket{\psi} ={00} \frac{2} {\sqrt } \ket - \frac{(1 + i)} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ volající <xref:microsoft.quantum.diagnostics.dumpregister> generuje `qubit[0]` tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0c152-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="0c152-203">a <xref:microsoft.quantum.diagnostics.dumpregister> volání `qubit[1]` generuje tento výstup:</span><span class="sxs-lookup"><span data-stu-id="0c152-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="0c152-204">Obecně platí, že stav registru, který je zapletený s jiným registrem je smíšený stav, nikoli čistý stav.</span><span class="sxs-lookup"><span data-stu-id="0c152-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="0c152-205">V tomto <xref:microsoft.quantum.diagnostics.dumpregister> případě výstupy následující zprávu:</span><span class="sxs-lookup"><span data-stu-id="0c152-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="0c152-206">Následující příklad ukazuje, jak můžete <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> použít jak a v kódu Q#:</span><span class="sxs-lookup"><span data-stu-id="0c152-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="0c152-207">Ladění</span><span class="sxs-lookup"><span data-stu-id="0c152-207">Debugging</span></span>

<span data-ttu-id="0c152-208">`Assert` Nad a `Dump` funkce a operace Q# podporuje podmnožinu standardních možností ladění Visual Studio: nastavení [zarážky řádku](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokování kódu pomocí F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) a kontrola hodnoty klasické [proměnné](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jsou všechny možné během provádění kódu na simulátoru.</span><span class="sxs-lookup"><span data-stu-id="0c152-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="0c152-209">Ladění v kódu sady Visual Studio využívá možnosti ladění poskytované c# pro rozšíření kódu Visual Studio powered by OmniSharp a vyžaduje instalaci [nejnovější verze](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="0c152-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 

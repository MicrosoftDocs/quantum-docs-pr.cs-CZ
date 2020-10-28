---
title: 'Způsoby spuštění :::no-loc(Q#)::: programu'
description: 'Přehled různých způsobů spouštění :::no-loc(Q#)::: programů. Z příkazového řádku, :::no-loc(Q#)::: poznámkových bloků Jupyter a klasických hostitelských programů v Pythonu nebo v jazyce .NET.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691697"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="ac6ae-104">Způsoby spuštění :::no-loc(Q#)::: programu</span><span class="sxs-lookup"><span data-stu-id="ac6ae-104">Ways to run a :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="ac6ae-105">Jednou z největších silou pro vývojová prostředí pro životní prostředí je jeho flexibilita napříč platformami a vývojovým prostředím.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="ac6ae-106">To ale také znamená, že noví :::no-loc(Q#)::: Uživatelé můžou při [instalaci v instalační příručce](xref:microsoft.quantum.install)najít nebo přesvědčit o mnoha možnostech.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-106">However, this also means that new :::no-loc(Q#)::: users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="ac6ae-107">Na této stránce vysvětlete, co se stane :::no-loc(Q#)::: , když se program spustí, a porovnejte různé způsoby, jak to uživatelé můžou udělat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-107">On this page, we explain what happens when a :::no-loc(Q#)::: program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="ac6ae-108">Primární rozdíl je, že :::no-loc(Q#)::: lze spustit:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-108">A primary distinction is that :::no-loc(Q#)::: can be run:</span></span>
- <span data-ttu-id="ac6ae-109">jako samostatná aplikace, kde :::no-loc(Q#)::: je jediný jazyk, který je součástí jediného jazyka a který program je vyvolán přímo.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-109">as a standalone application, where :::no-loc(Q#)::: is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="ac6ae-110">Do této kategorie ve skutečnosti patří dvě metody:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="ac6ae-111">rozhraní příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="ac6ae-111">the command-line interface</span></span>
  - <span data-ttu-id="ac6ae-112">:::no-loc(Q#)::: Jupyter poznámkové bloky</span><span class="sxs-lookup"><span data-stu-id="ac6ae-112">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
- <span data-ttu-id="ac6ae-113">s dalším *hostitelským programem* , který je napsán v Pythonu nebo v jazyce .NET (například C# nebo F #), který potom vyvolá program a může pokračovat ve zpracování vrácených výsledků.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-113">with an additional *host program* , written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="ac6ae-114">Abychom těmto procesům a jejich rozdílům nejlépe pochopili, Uvažujme o jednoduchém :::no-loc(Q#)::: programu a porovnejte způsob, jakým je možné ho spustit.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-114">To best understand these processes and their differences, we consider a simple :::no-loc(Q#)::: program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="ac6ae-115">Základní :::no-loc(Q#)::: program</span><span class="sxs-lookup"><span data-stu-id="ac6ae-115">Basic :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="ac6ae-116">Základní program pro vystavování se může skládat z přípravy qubit do stejné pozice stavů $ \ket {0} $ a $ \ket {1} $, měření a vrácení výsledku, který bude náhodně buď jedna z těchto dvou stavů, se stejnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="ac6ae-117">Tento proces je skutečně v jádru pro rychlý Start [generátoru náhodných čísel](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="ac6ae-118">V nástroji :::no-loc(Q#)::: by to bylo provedeno následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-118">In :::no-loc(Q#):::, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="ac6ae-119">Samotný kód však nelze spustit pomocí :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-119">However, this code alone can't be run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="ac6ae-120">V takovém případě musí sestavovat tělo [operace](xref:microsoft.quantum.guide.basics#q-operations-and-functions), která je pak spuštěna při volání---buď přímo, nebo jinou operací.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="ac6ae-121">Proto můžete napsat operaci následujícího formuláře:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="ac6ae-122">Definovali jste operaci, `MeasureSuperposition` která nepřijímá žádné vstupy a vrací hodnotu typu [Result](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="ac6ae-123">Zatímco příklady na této stránce se skládají jenom z :::no-loc(Q#)::: *operací* , všechny koncepce, které budeme projednávat, se budou vztahovat i na :::no-loc(Q#)::: *funkce* , a proto jsme na ně odkázali jako *volatelné* .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-123">While the examples on this page only consist of :::no-loc(Q#)::: *operations* , all of the concepts we will discuss pertain equally to :::no-loc(Q#)::: *functions* , and therefore we refer to them collectively as *callables* .</span></span> <span data-ttu-id="ac6ae-124">Jejich rozdíly jsou vysvětleny na [ :::no-loc(Q#)::: základních základech: operace a funkce](xref:microsoft.quantum.guide.basics#q-operations-and-functions)a další podrobnosti o jejich definování najdete v tématu [operace a funkce](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-124">Their differences are discussed at [:::no-loc(Q#)::: basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="ac6ae-125">V souboru se nedá volat definice. :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="ac6ae-125">Callable defined in a :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="ac6ae-126">Volání je přesně to, co se volá a spouští :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-126">The callable is precisely what's called and run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="ac6ae-127">Nicméně vyžaduje několik dalších přídavků, které tvoří úplný `*.qs` :::no-loc(Q#)::: soubor.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-127">However, it requires a few more additions to comprise a full `*.qs` :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="ac6ae-128">Všechny :::no-loc(Q#)::: typy a výzvy (které definujete i u těchto vnitřních objektů) jsou definovány v rámci *oborů názvů* , které poskytují každý úplný název, na který lze odkazovat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-128">All :::no-loc(Q#)::: types and callables (both those you define and those intrinsic to the language) are defined within *namespaces* , which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="ac6ae-129">Například [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operace a se nacházejí v [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) oborech názvů a (součást [ :::no-loc(Q#)::: standardních knihoven](xref:microsoft.quantum.qsharplibintro)).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-129">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [:::no-loc(Q#)::: Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="ac6ae-130">V takovém případě mohou být vždy volány prostřednictvím jejich *úplných* názvů, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ale vždy to vede k tomu, že by to vedlo k velmi zbytečnému kódu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="ac6ae-131">Místo toho `open` příkazy umožňují volat odkazování pomocí výstižnější zkratky, jak jsme udělali v těle operace výše.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="ac6ae-132">Úplný :::no-loc(Q#)::: soubor obsahující naši operaci by se tedy sestávat z definice vlastního oboru názvů, otevřením oborů názvů pro ty, které používá naše operace, a pak naší operace:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-132">The full :::no-loc(Q#)::: file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="ac6ae-133">Obory názvů lze také *aliasovat* při otevření, což může být užitečné v případě konfliktu názvů volat/typu ve dvou oborech názvů.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="ac6ae-134">Například můžeme použít `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` výše a potom zavolat `H` prostřednictvím `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ae-135">Jedna výjimka pro všechny Toto je [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) obor názvů, který je vždy automaticky otevřen.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="ac6ae-136">Proto lze volat jako [`Length`](xref:Microsoft.Quantum.Core.Length) vždy použít přímo.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-136">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="ac6ae-137">Spuštění na cílových počítačích</span><span class="sxs-lookup"><span data-stu-id="ac6ae-137">Running on target machines</span></span>

<span data-ttu-id="ac6ae-138">Nyní se model obecného spuštění :::no-loc(Q#)::: programu bude jasný.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-138">Now the general run model of a :::no-loc(Q#)::: program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt=":::no-loc(Q#)::: program execution diagram" width="400">

<span data-ttu-id="ac6ae-139">Za prvé, konkrétní spuštění, které se dá spustit, má přístup k jakýmkoli jiným volat a typům definovaným ve stejném oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-139">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="ac6ae-140">Také k nim přistupuje z libovolné [ :::no-loc(Q#)::: knihovny](xref:microsoft.quantum.libraries), ale musí být odkazovány buď prostřednictvím jejich úplného názvu, nebo pomocí `open` příkazů popsaných výše.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-140">It also access those from any of the [:::no-loc(Q#)::: libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="ac6ae-141">Samostatně se pak spustí na *[cílovém počítači](xref:microsoft.quantum.machines)* .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-141">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)* .</span></span>
<span data-ttu-id="ac6ae-142">Tyto cílové počítače můžou být skutečným hardwarem nebo s více simulátory, které jsou k dispozici jako součást QDK.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="ac6ae-143">Pro naše účely je nejužitečnější cílový počítač instancí [simulátoru s plným stavem](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` který počítá chování programu, jako kdyby bylo spuštěno na počítači se systémem bezproblémového provozu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="ac6ae-144">Zatím jsme popsali, co se stane, když :::no-loc(Q#)::: se spustí konkrétní volat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-144">So far, we've described what happens when a specific :::no-loc(Q#)::: callable is being run.</span></span>
<span data-ttu-id="ac6ae-145">Bez ohledu na to, jestli :::no-loc(Q#)::: se používá v samostatné aplikaci nebo v hostitelském programu, je tento obecný proces více nebo méně stejný,---QDK, takže flexibilita.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-145">Regardless of whether :::no-loc(Q#)::: is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="ac6ae-146">Rozdíly mezi způsoby volání do vývojové sady pro plnění stavových prostředí se proto odhalují v *tom, jak* :::no-loc(Q#)::: se volá, aby se dala spustit, a v jakém způsobu se vrátí výsledky.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-146">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that :::no-loc(Q#)::: callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="ac6ae-147">Přesněji řečeno, rozdíly obtéká:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-147">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="ac6ae-148">Označuje, který :::no-loc(Q#)::: volat lze spustit.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-148">Indicating which :::no-loc(Q#)::: callable is to be run</span></span>
- <span data-ttu-id="ac6ae-149">Jak jsou k dispozici možné argumenty pro možnost použití</span><span class="sxs-lookup"><span data-stu-id="ac6ae-149">How potential callable arguments are provided</span></span>
- <span data-ttu-id="ac6ae-150">Určení cílového počítače, na kterém se má spustit</span><span class="sxs-lookup"><span data-stu-id="ac6ae-150">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="ac6ae-151">Jak se vrátí výsledky</span><span class="sxs-lookup"><span data-stu-id="ac6ae-151">How any results are returned</span></span>

<span data-ttu-id="ac6ae-152">Nejdřív se podíváme na to, jak se to dělá u :::no-loc(Q#)::: samostatné aplikace z příkazového řádku, a pak budete pokračovat v používání hostitelských programů Pythonu a C#.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-152">First, we discuss how this is done with the :::no-loc(Q#)::: standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="ac6ae-153">Vyhrazujeme si samostatnou aplikaci :::no-loc(Q#)::: Jupyter poznámkových bloků jako poslední, protože na rozdíl od prvních tří nezáleží na tom, že se jedná o primární funkce na střed místního :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-153">We reserve the standalone application of :::no-loc(Q#)::: Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local :::no-loc(Q#)::: file.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ae-154">I když ho v těchto příkladech neilustruje, jedno společné mezi metodami spuštění je, že všechny zprávy vytištěné zevnitř :::no-loc(Q#)::: programu ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) například uživatelem [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ) budou obvykle vždy vytištěny do příslušné konzoly.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-154">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the :::no-loc(Q#)::: program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="ac6ae-155">:::no-loc(Q#)::: z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="ac6ae-155">:::no-loc(Q#)::: from the command prompt</span></span>
<span data-ttu-id="ac6ae-156">Jedním z nejjednodušších způsobů, jak začít psát :::no-loc(Q#)::: programy, je zabránit tomu, aby se nemuseli starat o samostatné soubory a druhý jazyk.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-156">One of the easiest ways to get started writing :::no-loc(Q#)::: programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="ac6ae-157">Pomocí Visual Studio Code nebo sady Visual Studio s rozšířením QDK umožňuje bezproblémové pracovní postup, ve kterém se spouští :::no-loc(Q#)::: volat jenom z jednoho :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run :::no-loc(Q#)::: callables from only a single :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="ac6ae-158">V tomto případě budeme program spouštět tak, že zadáte</span><span class="sxs-lookup"><span data-stu-id="ac6ae-158">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="ac6ae-159">na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-159">at the command prompt.</span></span>
<span data-ttu-id="ac6ae-160">Nejjednodušší pracovní postup je v případě, že je umístění adresáře terminálu stejné jako :::no-loc(Q#)::: soubor, který je možné snadno zpracovávat společně s :::no-loc(Q#)::: úpravami souborů pomocí integrovaného terminálu v vs Code, například.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-160">The simplest workflow is when the terminal's directory location is the same as the :::no-loc(Q#)::: file, which can be easily handled alongside :::no-loc(Q#)::: file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="ac6ae-161">[ `dotnet run` Příkaz](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) však akceptuje mnoho možností a program lze také spustit z jiného umístění pouhým poskytnutím `--project <PATH>` umístění :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the :::no-loc(Q#)::: file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="ac6ae-162">Přidat vstupní bod do :::no-loc(Q#)::: souboru</span><span class="sxs-lookup"><span data-stu-id="ac6ae-162">Add entry point to :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="ac6ae-163">Většina :::no-loc(Q#)::: souborů bude obsahovat více než jednu naužitečnou, takže je potřeba, aby kompilátor věděl, *který* volat, aby se spouštěl při zadání `dotnet run` příkazu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-163">Most :::no-loc(Q#)::: files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="ac6ae-164">To se provádí jednoduchou změnou :::no-loc(Q#)::: samotného souboru:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-164">This is done with a simple change to the :::no-loc(Q#)::: file itself:</span></span> 
    - <span data-ttu-id="ac6ae-165">Přidejte řádek, který `@EntryPoint()` je přímo před volat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="ac6ae-166">Náš soubor výše by se proto stal</span><span class="sxs-lookup"><span data-stu-id="ac6ae-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="ac6ae-167">Nyní volání `dotnet run` z příkazového řádku vede ke `MeasureSuperposition` spuštění a vrácená hodnota je následně vytištěna přímo na terminálu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="ac6ae-168">Zobrazí se buď `One` nebo `Zero` vytištěno.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="ac6ae-169">Mějte na paměti, že pokud máte více než jedno navýšení volat, `MeasureSuperposition` bude spuštěno.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="ac6ae-170">Kromě toho není k dispozici žádný problém, pokud vaše volat obsahuje [dokumentační komentáře](xref:microsoft.quantum.guide.filestructure#documentation-comments) před jeho deklarací, `@EntryPoint()` atribut lze jednoduše umístit nad něj.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="ac6ae-171">Volat argumenty</span><span class="sxs-lookup"><span data-stu-id="ac6ae-171">Callable arguments</span></span>

<span data-ttu-id="ac6ae-172">Zatím jsme se považovali jenom na operace, které přebírají žádné vstupy.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="ac6ae-173">Předpokládejme, že jsme chtěli provést podobnou operaci, ale na více qubits---počet, který je k dispozici jako argument.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="ac6ae-174">Taková operace by mohla být zapsána jako</span><span class="sxs-lookup"><span data-stu-id="ac6ae-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="ac6ae-175">kde vrácená hodnota je pole výsledků měření.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="ac6ae-176">Všimněte si, že [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) a [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) jsou [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) v [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) oborech názvů a, vyžadování dalších `open` příkazů pro každý z nich.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-176">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="ac6ae-177">Pokud přesouváte `@EntryPoint()` atribut tak, aby předchází této nové operaci (Všimněte si, že může být pouze jeden řádek v souboru), pokus o jeho spuštění s jednoduchým `dotnet run` výsledkem je chybová zpráva s informací o tom, jaké další možnosti příkazového řádku jsou vyžadovány a jak je vyjádřit.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="ac6ae-178">Obecný formát příkazového řádku je ve skutečnosti `dotnet run [options]` a k dispozici jsou argumenty, které jsou zde k dispozici.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="ac6ae-179">V tomto případě `n` chybí argument a ukazuje, že je nutné zadat možnost `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="ac6ae-180">Pro spuštění `MeasureSuperpositionArray` pro `n=4` qubits proto používáme</span><span class="sxs-lookup"><span data-stu-id="ac6ae-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="ac6ae-181">získávání výstupu podobného</span><span class="sxs-lookup"><span data-stu-id="ac6ae-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="ac6ae-182">Tento kurz rozšiřuje na více argumentů.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ae-183">Názvy argumentů definované v `camelCase` jsou mírně změněny kompilátorem tak, aby byly přijaty jako :::no-loc(Q#)::: vstupy.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as :::no-loc(Q#)::: inputs.</span></span> <span data-ttu-id="ac6ae-184">Například, pokud místo `n` , jsme použili název `numQubits` uvedený výše, a tento vstup by se zadal na příkazovém řádku pomocí `--num-qubits 4` místo `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="ac6ae-185">Chybová zpráva taky obsahuje další možnosti, které se dají použít, včetně toho, jak změnit cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="ac6ae-186">Různé cílové počítače</span><span class="sxs-lookup"><span data-stu-id="ac6ae-186">Different target machines</span></span>

<span data-ttu-id="ac6ae-187">Vzhledem k tomu, že výstupy z našich operací byly doposud očekávané výsledky jejich akce v reálném qubits, je jasné, že výchozí cílový počítač z příkazového řádku je plný stav simulátoru `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="ac6ae-188">Dá se ale dát pokyn ke spuštění na konkrétním cílovém počítači s možností `--simulator` (nebo zkráceným `-s` ).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="ac6ae-189">Můžete ho například spustit na [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="ac6ae-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="ac6ae-190">Vytištěný výstup je pak</span><span class="sxs-lookup"><span data-stu-id="ac6ae-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="ac6ae-191">Podrobnosti o tom, co tyto metriky naznačují, najdete v tématu věnovaném [Estimator prostředků: metriky se nahlásily](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="ac6ae-192">Souhrn spuštění příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="ac6ae-192">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt=":::no-loc(Q#)::: program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="ac6ae-193">Jiné než :::no-loc(Q#)::: `dotnet run` Možnosti</span><span class="sxs-lookup"><span data-stu-id="ac6ae-193">Non-:::no-loc(Q#)::: `dotnet run` options</span></span>

<span data-ttu-id="ac6ae-194">Jak jsme se na tuto možnost krátce zmínili `--project` , [ `dotnet run` příkaz](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) také přijímá možnosti, které nesouvisí s argumenty, které lze :::no-loc(Q#)::: volat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the :::no-loc(Q#)::: callable arguments.</span></span>
<span data-ttu-id="ac6ae-195">Pokud jsou zadány oba typy možností, `dotnet` musí být nejprve poskytnuty možnosti specifické pro, následované oddělovač `--` a :::no-loc(Q#)::: možnosti specifické pro.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the :::no-loc(Q#):::-specific options.</span></span>
<span data-ttu-id="ac6ae-196">Například zadání cesty spolu s číslem qubits pro operaci výše by bylo spuštěno prostřednictvím `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-196">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="ac6ae-197">:::no-loc(Q#)::: s hostitelskými programy</span><span class="sxs-lookup"><span data-stu-id="ac6ae-197">:::no-loc(Q#)::: with host programs</span></span>

<span data-ttu-id="ac6ae-198">U našeho :::no-loc(Q#)::: souboru je alternativou k volání operace nebo funkce přímo z příkazového řádku použití *hostitelského programu* v jiném klasickém jazyce.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-198">With our :::no-loc(Q#)::: file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="ac6ae-199">Konkrétně to lze provést buď pomocí Pythonu, nebo jazyka .NET, jako je C# nebo F # (za účelem zkrácení budeme podrobnosti pouze C#).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="ac6ae-200">K povolení interoperability je potřeba trochu dalších nastavení, ale tyto podrobnosti najdete v [pokynech k instalaci](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="ac6ae-201">V kostce nyní tato situace zahrnuje soubor hostitelského programu (například `*.py` nebo `*.cs` ) ve stejném umístění jako náš :::no-loc(Q#)::: soubor.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-201">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="ac6ae-202">Nyní je *hostitelský* program, který se spustí, a když je spuštěný, může volat konkrétní :::no-loc(Q#)::: operace a funkce ze :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-202">It's now the *host* program that gets run, and while it is running, it can call specific :::no-loc(Q#)::: operations and functions from the :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="ac6ae-203">Základem interoperability je :::no-loc(Q#)::: vytvoření obsahu :::no-loc(Q#)::: souboru přístupného pro hostitelský program, aby bylo možné je volat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-203">The core of the interoperability is based on the :::no-loc(Q#)::: compiler making the contents of the :::no-loc(Q#)::: file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="ac6ae-204">Jednou z hlavních výhod používání hostitelského programu je to, že klasická data vrácená :::no-loc(Q#)::: programem se pak dají dál zpracovat v jazyce hostitele.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-204">One of the main benefits of using a host program is that the classical data returned by the :::no-loc(Q#)::: program can then be further processed in the host language.</span></span>
<span data-ttu-id="ac6ae-205">Může se jednat o některé pokročilé zpracování dat (například něco, co se v nástroji nedá provést interně :::no-loc(Q#)::: ) a pak na základě těchto výsledků zavoláme další :::no-loc(Q#)::: akce nebo něco jednoduchého jako vykreslení :::no-loc(Q#)::: výsledků.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-205">This could consist of some advanced data processing (for example, something that can't be performed internally in :::no-loc(Q#):::), and then calling further :::no-loc(Q#)::: actions based on those results, or something as simple as plotting the :::no-loc(Q#)::: results.</span></span>

<span data-ttu-id="ac6ae-206">Tady se zobrazí obecné schéma a v následující části se podíváme na konkrétní implementace pro Python a C#.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="ac6ae-207">Ukázku použití hostitelského programu F # najdete v [ukázkách interoperability .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt=":::no-loc(Q#)::: program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="ac6ae-208">`@EntryPoint()`Atribut používaný pro :::no-loc(Q#)::: aplikace nelze použít s hostitelskými programy.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-208">The `@EntryPoint()` attribute used for :::no-loc(Q#)::: applications cannot be used with host programs.</span></span>
> <span data-ttu-id="ac6ae-209">Pokud se nachází v souboru, který :::no-loc(Q#)::: Host volá, bude vyvolána chyba.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-209">An error will be raised if it is present in the :::no-loc(Q#)::: file being called by a host.</span></span> 

<span data-ttu-id="ac6ae-210">Pro práci s různými hostitelskými programy nejsou k dispozici žádné změny `*.qs` :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-210">To work with different host programs, there are no changes required to a `*.qs` :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="ac6ae-211">Následující hostitelské programy implementují všechny práce se stejným :::no-loc(Q#)::: souborem:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-211">The following host program implementations all work with the same :::no-loc(Q#)::: file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="ac6ae-212">Vyberte kartu odpovídající vašemu hostitelskému jazyku, který vás zajímá.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="ac6ae-213">Python</span><span class="sxs-lookup"><span data-stu-id="ac6ae-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="ac6ae-214">Hostitelský program Pythonu je vytvořený takto:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="ac6ae-215">Importujte `qsharp` modul, který registruje zavaděč modulu pro :::no-loc(Q#)::: interoperabilitu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-215">Import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="ac6ae-216">To umožňuje :::no-loc(Q#)::: , aby se obory názvů zobrazovaly jako moduly Pythonu, ze kterých můžeme "importovat" :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-216">This allows :::no-loc(Q#)::: namespaces to appear as Python modules, from which we can "import" :::no-loc(Q#)::: callables.</span></span>
    <span data-ttu-id="ac6ae-217">Všimněte si, že se nejedná o nepřímo :::no-loc(Q#)::: přizpůsobitelné metody, které jsou naimportovány, ale spíše jako zástupné procedury Pythonu, které umožňují</span><span class="sxs-lookup"><span data-stu-id="ac6ae-217">Note that it is technically not the :::no-loc(Q#)::: callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="ac6ae-218">Chovají se jako objekty tříd Pythonu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-218">These behave as objects of Python classes.</span></span> <span data-ttu-id="ac6ae-219">Metody na těchto objektech používáme k určení cílových počítačů, na které odesíláme operace při spuštění programu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-219">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="ac6ae-220">Naimportujte ty :::no-loc(Q#)::: , které budou v tomto případě přímo vyvolány--- `MeasureSuperposition` a `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-220">Import those :::no-loc(Q#)::: callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="ac6ae-221">Pomocí `qsharp` importovaného modulu můžete také naimportovat volatelné přímo z :::no-loc(Q#)::: oboru názvů knihoven.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-221">With the `qsharp` module imported, you can also import callables directly from the :::no-loc(Q#)::: library namespaces.</span></span>

3. <span data-ttu-id="ac6ae-222">V jakémkoli jiném kódu Pythonu teď můžete zavolat tyto výzvy na konkrétní cílové počítače a přiřadit jejich návrat k proměnným (Pokud vrátí hodnotu) pro další použití.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-222">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="ac6ae-223">Určení cílových počítačů</span><span class="sxs-lookup"><span data-stu-id="ac6ae-223">Specifying target machines</span></span>
<span data-ttu-id="ac6ae-224">Volání operace, která se má spustit na konkrétním cílovém počítači, se provádí prostřednictvím různých metod Pythonu u importovaného objektu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-224">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="ac6ae-225">Například `.simulate(<args>)` používá `QuantumSimulator` ke spuštění operace, zatímco `.estimate_resources(<args>)` to dělá na `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-225">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="ac6ae-226">Předání vstupů do Q\#</span><span class="sxs-lookup"><span data-stu-id="ac6ae-226">Passing inputs to Q\#</span></span>
<span data-ttu-id="ac6ae-227">Argumenty pro :::no-loc(Q#)::: volat by měly být zadány ve formě argumentu klíčového slova, kde klíčové slovo je název argumentu v :::no-loc(Q#)::: definici volat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-227">Arguments for the :::no-loc(Q#)::: callable should be provided in the form of a keyword argument, where the keyword is the argument name in the :::no-loc(Q#)::: callable definition.</span></span>
<span data-ttu-id="ac6ae-228">To znamená, že `MeasureSuperpositionArray.simulate(n=4)` je platná, zatímco `MeasureSuperpositionArray.simulate(4)` by vyvolala chybu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-228">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="ac6ae-229">Proto hostitelský program Pythonu</span><span class="sxs-lookup"><span data-stu-id="ac6ae-229">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="ac6ae-230">Výsledkem bude výstup podobný následujícímu:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-230">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="ac6ae-231">Použití :::no-loc(Q#)::: kódu z jiných projektů nebo balíčků</span><span class="sxs-lookup"><span data-stu-id="ac6ae-231">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="ac6ae-232">Ve výchozím nastavení `import qsharp` příkaz načte všechny `.qs` soubory v aktuální složce a zpřístupní jejich :::no-loc(Q#)::: operace a funkce pro použití zevnitř skriptu Pythonu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-232">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="ac6ae-233">Chcete-li načíst :::no-loc(Q#)::: kód z jiné složky, [ `qsharp.projects` rozhraní API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) lze použít k přidání odkazu na `.csproj` soubor pro :::no-loc(Q#)::: projekt (tj. projekt, který odkazuje `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-233">To load :::no-loc(Q#)::: code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="ac6ae-234">Tento příkaz zkompiluje všechny `.qs` soubory ve složce obsahující `.csproj` a jejích podsložkách.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-234">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="ac6ae-235">Bude také rekurzivně načítat jakékoli balíčky, na které se odkazuje přes `PackageReference` :::no-loc(Q#)::: , nebo `ProjectReference` na projekty, na které se odkazuje v tomto `.csproj` souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-235">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="ac6ae-236">Například následující kód Pythonu Importuje externí projekt, odkazuje na jeho cestu relativní vzhledem k aktuální složce a vyvolá jednu z jeho :::no-loc(Q#)::: operací:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-236">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its :::no-loc(Q#)::: operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="ac6ae-237">Výsledkem bude výstup podobný následujícímu:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-237">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="ac6ae-238">Chcete-li načíst externí balíčky obsahující :::no-loc(Q#)::: kód, použijte [ `qsharp.packages` rozhraní API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-238">To load external packages containing :::no-loc(Q#)::: code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="ac6ae-239">Pokud :::no-loc(Q#)::: kód v aktuální složce závisí na externích projektech nebo balíčcích, mohou se při spuštění zobrazit chyby `import qsharp` , protože závislosti ještě nebyly načteny.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-239">If the :::no-loc(Q#)::: code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="ac6ae-240">Pokud chcete načíst požadované externí balíčky nebo :::no-loc(Q#)::: projekty v rámci `import qsharp` příkazu, ujistěte se, že složka se skriptem Pythonu obsahuje `.csproj` soubor, který odkazuje na `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-240">To load required external packages or :::no-loc(Q#)::: projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="ac6ae-241">V takovém `.csproj` případě přidejte vlastnost `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` do `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-241">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="ac6ae-242">Tím se dá dát :::no-loc(Q#)::: k rekurzivnímu načtení libovolných `ProjectReference` `PackageReference` položek nebo nalezených v `.csproj` rámci `import qsharp` příkazu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-242">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="ac6ae-243">Například tady je jednoduchý `.csproj` soubor, který způsobí, že :::no-loc(Q#)::: se má automaticky načíst `Microsoft.Quantum.Chemistry` balíček:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-243">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="ac6ae-244">V současné době `<IQSharpLoadAutomatically>` je tato vlastní vlastnost vyžadována v hostitelích Pythonu, ale v budoucnu se to může stát výchozím chováním pro `.csproj` soubor umístěný ve stejné složce jako skript Pythonu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-244">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ae-245">V současné době `<QsharpCompile>` je nastavení v rozhraní `.csproj` ignorováno hostiteli Pythonu a `.qs` `.csproj` jsou načteny a kompilovány všechny soubory ve složce (včetně podsložek).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-245">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="ac6ae-246">`.csproj`V budoucnu se zlepší podpora nastavení (další podrobnosti najdete v tématu [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-246">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="ac6ae-247">C#</span><span class="sxs-lookup"><span data-stu-id="ac6ae-247">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="ac6ae-248">Hostitelský program v jazyce C# má více komponent a pracuje velmi pečlivě s některými komponentami QDK, jako jsou například simulátory, které jsou samy postaveny na C#.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-248">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="ac6ae-249">:::no-loc(Q#):::Kompilátor tady funguje tak, že generuje ekvivalentně pojmenovaný obor názvů C# z :::no-loc(Q#)::: oboru názvů v našem :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-249">The :::no-loc(Q#)::: compiler works here by generating an equivalently named C# namespace from the :::no-loc(Q#)::: namespace in our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="ac6ae-250">Dále vygeneruje ekvivalentní název třídy jazyka C# pro každý z určených volání :::no-loc(Q#)::: nebo typů, které jsou definovány v rámci.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-250">It further generates an equivalently named C# class for each of the :::no-loc(Q#)::: callables or types defined therein.</span></span>

<span data-ttu-id="ac6ae-251">Nejprve zpřístupníme všechny třídy, které jsou k dispozici v našem hostitelském programu s `using` příkazy, které jsou zhruba analagous na `open` příkazy v našem :::no-loc(Q#)::: souboru:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-251">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our :::no-loc(Q#)::: file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the :::no-loc(Q#)::: namespace available
```

<span data-ttu-id="ac6ae-252">Dále deklarujeme náš obor názvů C#, několik dalších bitů a částí (viz úplný blok kódu níže) a pak jakékoli klasické programování, které bychom chtěli (například výpočetních argumentů pro :::no-loc(Q#)::: volat).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-252">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the :::no-loc(Q#)::: callables).</span></span>
<span data-ttu-id="ac6ae-253">Ta není v našem případě nutná, ale příklad takového použití najdete v  [ukázce interoperability .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-253">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="ac6ae-254">Cílové počítače</span><span class="sxs-lookup"><span data-stu-id="ac6ae-254">Target machines</span></span>

<span data-ttu-id="ac6ae-255">Když se vrátíte zpátky :::no-loc(Q#)::: , musíme vytvořit instanci libovolného cílového počítače, na které budeme provozovat.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-255">Getting back to :::no-loc(Q#):::, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="ac6ae-256">Použití jiných cílových počítačů je stejně jednoduché jako vytvoření instance jiného, přestože způsob, jak to udělat, a zpracování vrácených změn může být mírně odlišné.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-256">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="ac6ae-257">V případě zkrácení se [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) pro teď používáme a zařadíme [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [níže](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-257">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="ac6ae-258">Každá třída jazyka C# vygenerovaná z :::no-loc(Q#)::: operací má `Run` metodu, první argument, který musí být instancí cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-258">Each C# class generated from the :::no-loc(Q#)::: operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="ac6ae-259">Takže pokud chcete spustit `MeasureSuperposition` v `QuantumSimulator` , používáme `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-259">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="ac6ae-260">Vrácené výsledky lze následně přiřadit proměnným v jazyce C#:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-260">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="ac6ae-261">`Run`Metoda je spouštěna asynchronně, protože se jedná o případ reálného hardwaru s `await` více procesory, a proto klíčové slovo zablokuje další zpracování až do dokončení úkolu.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-261">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="ac6ae-262">Pokud je :::no-loc(Q#)::: to možné, že k dispozici nejsou žádné návraty (například má návratový typ `Unit` ), může být spuštění provedeno stejným způsobem bez přiřazení k proměnné.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-262">If the :::no-loc(Q#)::: callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="ac6ae-263">V takovém případě by se celý řádek měl jednoduše skládat z</span><span class="sxs-lookup"><span data-stu-id="ac6ae-263">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="ac6ae-264">Arguments</span><span class="sxs-lookup"><span data-stu-id="ac6ae-264">Arguments</span></span>

<span data-ttu-id="ac6ae-265">Jakékoli argumenty, které lze :::no-loc(Q#)::: volat, jsou jednoduše předány jako další argumenty po cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-265">Any arguments to the :::no-loc(Q#)::: callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="ac6ae-266">Proto výsledky z `MeasureSuperpositionArray` `n=4` qubits by se načetly prostřednictvím</span><span class="sxs-lookup"><span data-stu-id="ac6ae-266">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="ac6ae-267">Úplný hostitelský program v C# by mohl vypadat takto</span><span class="sxs-lookup"><span data-stu-id="ac6ae-267">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="ac6ae-268">V umístění souboru jazyka C# lze hostitelský program spustit z příkazového řádku zadáním</span><span class="sxs-lookup"><span data-stu-id="ac6ae-268">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="ac6ae-269">v tomto případě se zobrazí výstup napsaný do konzoly podobně jako</span><span class="sxs-lookup"><span data-stu-id="ac6ae-269">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="ac6ae-270">Z důvodu interoperability kompilátoru s obory názvů můžeme Alternativně zpřístupnit :::no-loc(Q#)::: k dispozici bez `using NamespaceName;` příkazu a jednoduše tak, aby se k němu přishodoval název oboru názvů C#.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-270">Due to the compiler's interoperability with namespaces, we could alternatively make our :::no-loc(Q#)::: callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="ac6ae-271">To znamená nahrazením `namespace host` pomocí `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-271">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="ac6ae-272">Zahrnutí prostředků Estimator</span><span class="sxs-lookup"><span data-stu-id="ac6ae-272">Including the resources estimator</span></span>

<span data-ttu-id="ac6ae-273">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Pro načtení výstupu vyžaduje poněkud odlišnou implementaci.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-273">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="ac6ae-274">Nejprve místo toho, aby se vytvořila instance jako proměnná s `using` příkazem (stejně jako v případě `QuantumSimulator` ), je více přímo vytvořena instance objektů třídy prostřednictvím</span><span class="sxs-lookup"><span data-stu-id="ac6ae-274">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="ac6ae-275">Všimněte si, že místo jediného cílového simulátoru, který má být použit více :::no-loc(Q#)::: operacemi, jsme pro každý z nich nastavili instanci.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-275">Notice that instead of a single target simulator to be used by multiple :::no-loc(Q#)::: operations, we have instantiated one for each.</span></span> <span data-ttu-id="ac6ae-276">Důvodem je to, že při použití jako cílové počítače jsou změněny samotné objekty a jejich výsledky lze následně načíst pomocí metody třídy `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-276">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="ac6ae-277">Pro spuštění operací na odhady prostředků používáme</span><span class="sxs-lookup"><span data-stu-id="ac6ae-277">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="ac6ae-278">a potom výsledky načtěte jako hodnoty hodnot TSV (tabulátor-revalues) s `estimatorSingleQ.ToTSV()` a `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-278">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="ac6ae-279">Úplný hostitelský program v jazyce C#, který používá jak `QuantumSimulator` a `ResourcesEstimator` může mít podobu:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-279">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="ac6ae-280">což by znamenalo výstup podobný</span><span class="sxs-lookup"><span data-stu-id="ac6ae-280">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="ac6ae-281">:::no-loc(Q#)::: Jupyter poznámkové bloky</span><span class="sxs-lookup"><span data-stu-id="ac6ae-281">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
<span data-ttu-id="ac6ae-282">:::no-loc(Q#)::: Jupyter poznámkové bloky využívají jádro I :::no-loc(Q#)::: , které umožňuje definovat, kompilovat a spouštět :::no-loc(Q#)::: volat v jednom poznámkovém bloku---všech společně s pokyny, poznámkami a dalšími obsahy.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-282">:::no-loc(Q#)::: Jupyter Notebooks make use of the I:::no-loc(Q#)::: kernel, which allows you to define, compile, and run :::no-loc(Q#)::: callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="ac6ae-283">To znamená, že přestože je možné importovat a používat obsah `*.qs` :::no-loc(Q#)::: souborů, nejsou v modelu spuštění nutné.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-283">This means that while it is possible to import and use the contents of `*.qs` :::no-loc(Q#)::: files, they are not necessary in the run model.</span></span>

<span data-ttu-id="ac6ae-284">Zde podrobně pomůžeme, jak spustit :::no-loc(Q#)::: výše uvedené operace, ale obecnější Úvod k používání :::no-loc(Q#)::: notebooků Jupyter je k dispozici na stránce [Úvod do :::no-loc(Q#)::: a Jupyter poznámkových blocích](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-284">Here, we will detail how to run the :::no-loc(Q#)::: operations defined above, but a more broad introduction to using :::no-loc(Q#)::: Jupyter Notebooks is provided at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="ac6ae-285">Definování operací</span><span class="sxs-lookup"><span data-stu-id="ac6ae-285">Defining operations</span></span>

<span data-ttu-id="ac6ae-286">V :::no-loc(Q#)::: Jupyter notebook zadáte :::no-loc(Q#)::: kód stejně jako v rámci oboru názvů :::no-loc(Q#)::: souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-286">In a :::no-loc(Q#)::: Jupyter Notebook, you enter :::no-loc(Q#)::: code just as we would from inside the namespace of a :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="ac6ae-287">Proto můžeme povolit přístup k volat ze [ :::no-loc(Q#)::: standardních knihoven](xref:microsoft.quantum.qsharplibintro) s `open` příkazy pro jejich příslušné obory názvů.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-287">So, we can enable access to callables from the [:::no-loc(Q#)::: standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="ac6ae-288">Po spuštění buňky s takovým příkazem jsou definice z těchto oborů názvů dostupné v celém pracovním prostoru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-288">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ae-289">Pro operace definované [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) v [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) rámci buněk v :::no-loc(Q#)::: poznámkových blocích Jupyter se budou automaticky přivolat z Microsoft. probíhajících. vnitřní a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-289">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in :::no-loc(Q#)::: Jupyter Notebooks.</span></span>
> <span data-ttu-id="ac6ae-290">Nicméně to není pravdivé pro kód převedený z externích :::no-loc(Q#)::: zdrojových souborů (proces zobrazený v [úvodu do :::no-loc(Q#)::: a Jupyter poznámkových bloků](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-290">However, this is not true for code brought in from external :::no-loc(Q#)::: source files (a process shown at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="ac6ae-291">Podobně definování operací vyžaduje pouze zápis :::no-loc(Q#)::: kódu a spuštění buňky.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-291">Similarly, defining operations requires only writing the :::no-loc(Q#)::: code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining :::no-loc(Q#)::: operations" width="773">

<span data-ttu-id="ac6ae-292">Výstup pak obsahuje seznam operací, které je možné volat z budoucích buněk.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-292">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="ac6ae-293">Cílové počítače</span><span class="sxs-lookup"><span data-stu-id="ac6ae-293">Target machines</span></span>

<span data-ttu-id="ac6ae-294">Funkce pro spouštění operací na konkrétních cílových počítačích je poskytována prostřednictvím [ :::no-loc(Q#)::: příkazů I Magic](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-294">The functionality to run operations on specific target machines is provided via [I:::no-loc(Q#)::: Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="ac6ae-295">Například využívá `%simulate` `QuantumSimulator` a `%estimate` používá `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="ac6ae-295">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="ac6ae-296">Předávání vstupů do funkcí a operací</span><span class="sxs-lookup"><span data-stu-id="ac6ae-296">Passing inputs to functions and operations</span></span>

<span data-ttu-id="ac6ae-297">Aby :::no-loc(Q#)::: bylo možné do operací předat vstupy, argumenty lze předat jako `key=value` páry k příkazu Spustit Magic.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-297">To pass inputs to the :::no-loc(Q#)::: operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="ac6ae-298">Takže pokud chcete spustit `MeasureSuperpositionArray` se čtyřmi qubits, můžeme spustit `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="ac6ae-298">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation with arguments" width="773">

<span data-ttu-id="ac6ae-299">Tento model lze použít podobně jako `%estimate` a jiné příkazy pro spuštění.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-299">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="ac6ae-300">Použití :::no-loc(Q#)::: kódu z jiných projektů nebo balíčků</span><span class="sxs-lookup"><span data-stu-id="ac6ae-300">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="ac6ae-301">Ve výchozím nastavení :::no-loc(Q#)::: Jupyter notebook načítá všechny `.qs` soubory v aktuální složce a zpřístupňuje jejich :::no-loc(Q#)::: operace a funkce pro použití v rámci poznámkového bloku.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-301">By default, a :::no-loc(Q#)::: Jupyter Notebook loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="ac6ae-302">[ `%who` Příkaz Magic](xref:microsoft.quantum.iqsharp.magic-ref.who) vypíše všechny aktuálně dostupné :::no-loc(Q#)::: operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-302">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available :::no-loc(Q#)::: operations and functions.</span></span>

<span data-ttu-id="ac6ae-303">Chcete-li načíst :::no-loc(Q#)::: kód z jiné složky, lze pomocí [ `%project` příkazu Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) přidat odkaz na `.csproj` soubor pro :::no-loc(Q#)::: projekt (tj. projekt, který odkazuje na `Microsoft.Quantum.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-303">To load :::no-loc(Q#)::: code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="ac6ae-304">Tento příkaz zkompiluje všechny `.qs` soubory ve složce obsahující `.csproj` (a podsložek).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-304">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="ac6ae-305">Bude také rekurzivně načítat jakékoli balíčky, na které se odkazuje přes `PackageReference` :::no-loc(Q#)::: , nebo `ProjectReference` na projekty, na které se odkazuje v tomto `.csproj` souboru.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-305">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="ac6ae-306">Například následující buňky simulují :::no-loc(Q#)::: operaci z externího projektu, kde je odkazováno na cestu k projektu vzhledem k aktuální složce:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-306">As an example, the following cells simulate a :::no-loc(Q#)::: operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation from an external project" width="773">

<span data-ttu-id="ac6ae-307">Pokud chcete načíst externí balíčky obsahující :::no-loc(Q#)::: kód, použijte [ `%package` příkaz Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-307">To load external packages containing :::no-loc(Q#)::: code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="ac6ae-308">Načtení balíčku také zpřístupní všechny vlastní příkazy Magic nebo zobrazovací kodéry, které jsou obsaženy ve všech sestaveních, která jsou součástí balíčku.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-308">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="ac6ae-309">Pokud chcete načíst externí balíčky nebo :::no-loc(Q#)::: projekty v průběhu inicializace poznámkového bloku, ujistěte se, že složka Poznámkový blok obsahuje `.csproj` soubor, který odkazuje na `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-309">To load external packages or :::no-loc(Q#)::: projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="ac6ae-310">V takovém `.csproj` případě přidejte vlastnost `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` do `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="ac6ae-310">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="ac6ae-311">Tím se dá dát :::no-loc(Q#)::: k rekurzivnímu načítání libovolných `ProjectReference` `PackageReference` položek nebo nalezených v `.csproj` době načítání poznámkového bloku.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-311">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="ac6ae-312">Například tady je jednoduchý `.csproj` soubor, který způsobí, že :::no-loc(Q#)::: se má automaticky načíst `Microsoft.Quantum.Chemistry` balíček:</span><span class="sxs-lookup"><span data-stu-id="ac6ae-312">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="ac6ae-313">V současné době `<IQSharpLoadAutomatically>` je tato vlastní vlastnost požadována :::no-loc(Q#)::: Jupyter notebook hostiteli, ale v budoucnu se to může stát výchozím chováním pro `.csproj` soubor umístěný ve stejné složce jako soubor poznámkového bloku.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-313">Currently this custom `<IQSharpLoadAutomatically>` property is required by :::no-loc(Q#)::: Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ae-314">V současné době `<QsharpCompile>` je nastavení v rozhraní `.csproj` ignorováno :::no-loc(Q#)::: Jupyter notebook hostitelé a všechny `.qs` soubory ve složce `.csproj` (včetně podsložek) jsou načteny a kompilovány.</span><span class="sxs-lookup"><span data-stu-id="ac6ae-314">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by :::no-loc(Q#)::: Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="ac6ae-315">`.csproj`V budoucnu se zlepší podpora nastavení (další podrobnosti najdete v tématu [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).</span><span class="sxs-lookup"><span data-stu-id="ac6ae-315">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>

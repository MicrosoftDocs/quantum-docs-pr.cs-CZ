---
title: Prostředky pro procesory Estimator – pro vývojová prostředí
description: Přečtěte si o QDK prostředcích Microsoft Estimator, které vyodhadují prostředky potřebné ke spuštění dané instance Q# operace na počítači s více operačními systémy.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57f6602effd25fff353a8fee7f27acc529ce82af
ms.sourcegitcommit: c3c892ef35eae6926d0c4339d9d26bfd8be77e9a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/30/2020
ms.locfileid: "96318486"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="182e5-103">Prostředky QDK (estimatoring Development Kit)</span><span class="sxs-lookup"><span data-stu-id="182e5-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="182e5-104">Jak název implikuje, `ResourcesEstimator` Třída odhadne prostředky potřebné ke spuštění dané instance Q# operace v počítači s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="182e5-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="182e5-105">To dosahuje tím, že spustí operaci bez skutečného simulace stavu počítače s více operačními systémy. z tohoto důvodu odhaduje prostředky pro Q# operace, které používají tisíce qubits, za předpokladu, že klasická část kódu běží v rozumnou dobu.</span><span class="sxs-lookup"><span data-stu-id="182e5-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="182e5-106">Prostředky Estimator jsou postavené na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)pro stav, který poskytuje bohatší sadu metrik a nástrojů pro ladění Q# programů.</span><span class="sxs-lookup"><span data-stu-id="182e5-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="182e5-107">Vyvolání a spuštění prostředků Estimator</span><span class="sxs-lookup"><span data-stu-id="182e5-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="182e5-108">Pomocí prostředků Estimator můžete spustit jakoukoli Q# operaci.</span><span class="sxs-lookup"><span data-stu-id="182e5-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="182e5-109">Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="182e5-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="182e5-110">Vyvolání prostředků estimator z C #</span><span class="sxs-lookup"><span data-stu-id="182e5-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="182e5-111">Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `ResourceEstimator` a předáte ji jako první parametr metody `Run` příslušné operace.</span><span class="sxs-lookup"><span data-stu-id="182e5-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="182e5-112">Na rozdíl od třídy `QuantumSimulator` ale třída `ResourceEstimator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="182e5-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="182e5-113">Jak ukazuje příklad, `ResourcesEstimator` poskytuje `ToTSV()` metodu, která generuje tabulku s hodnotami oddělenými tabulátory (TSV).</span><span class="sxs-lookup"><span data-stu-id="182e5-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="182e5-114">Tabulku můžete uložit do souboru nebo zobrazit v konzole pro účely analýzy.</span><span class="sxs-lookup"><span data-stu-id="182e5-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="182e5-115">Následuje ukázkový výstup z předchozího programu:</span><span class="sxs-lookup"><span data-stu-id="182e5-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="182e5-116">`ResourcesEstimator`Instance neresetuje své výpočty při každém spuštění.</span><span class="sxs-lookup"><span data-stu-id="182e5-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="182e5-117">Použijete-li stejnou instanci pro spuštění jiné operace, agreguje nové výsledky s existujícími výsledky.</span><span class="sxs-lookup"><span data-stu-id="182e5-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="182e5-118">Pokud potřebujete resetovat výpočty mezi běhy, vytvořte novou instanci pro každé spuštění.</span><span class="sxs-lookup"><span data-stu-id="182e5-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="182e5-119">Vyvolání prostředků estimator z Pythonu</span><span class="sxs-lookup"><span data-stu-id="182e5-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="182e5-120">Použijte metodu [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou Q# operací:</span><span class="sxs-lookup"><span data-stu-id="182e5-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="182e5-121">Vyvolání prostředků estimator z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="182e5-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="182e5-122">Při spuštění Q# programu z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k určení `ResourcesEstimator` cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="182e5-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="182e5-123">Následující příkaz spustí program pomocí Estimator prostředků:</span><span class="sxs-lookup"><span data-stu-id="182e5-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="182e5-124">Vyvolání prostředků estimator z poznámkových bloků Juptyer</span><span class="sxs-lookup"><span data-stu-id="182e5-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="182e5-125">Q#Pro spuštění operace použijte [odhad](xref:microsoft.quantum.iqsharp.magic-ref.simulate) příkazu I Magic% Q# .</span><span class="sxs-lookup"><span data-stu-id="182e5-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="182e5-126">Programové načítání odhadovaných dat</span><span class="sxs-lookup"><span data-stu-id="182e5-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="182e5-127">Kromě tabulky TSV můžete programově načíst prostředky odhadované během běhu prostřednictvím `Data` vlastnosti prostředků Estimator.</span><span class="sxs-lookup"><span data-stu-id="182e5-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="182e5-128">`Data`Vlastnost poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum` , indexované názvy metrik.</span><span class="sxs-lookup"><span data-stu-id="182e5-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="182e5-129">Následující kód ukazuje, jak načíst a vytisknout celkový počet `QubitClifford` `T` `CNOT` operací využívaných Q# operací:</span><span class="sxs-lookup"><span data-stu-id="182e5-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="182e5-130">Hlášené metriky</span><span class="sxs-lookup"><span data-stu-id="182e5-130">Metrics Reported</span></span>

<span data-ttu-id="182e5-131">Prostředky Estimator sledují následující metriky:</span><span class="sxs-lookup"><span data-stu-id="182e5-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="182e5-132">Metric</span><span class="sxs-lookup"><span data-stu-id="182e5-132">Metric</span></span>|<span data-ttu-id="182e5-133">Popis</span><span class="sxs-lookup"><span data-stu-id="182e5-133">Description</span></span>|
|----|----|
|<span data-ttu-id="182e5-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="182e5-134">__CNOT__</span></span>    |<span data-ttu-id="182e5-135">Počet spuštění `CNOT` operací (označovaný také jako řízené operace Pauli X).</span><span class="sxs-lookup"><span data-stu-id="182e5-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="182e5-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="182e5-136">__QubitClifford__</span></span> |<span data-ttu-id="182e5-137">Počet spuštění všech qubitch operací Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="182e5-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="182e5-138">__Míra__</span><span class="sxs-lookup"><span data-stu-id="182e5-138">__Measure__</span></span>    |<span data-ttu-id="182e5-139">Počet spuštění všech měření.</span><span class="sxs-lookup"><span data-stu-id="182e5-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="182e5-140">__R__</span><span class="sxs-lookup"><span data-stu-id="182e5-140">__R__</span></span>    |<span data-ttu-id="182e5-141">Počet spuštění všech rotací s jedním qubit, s výjimkou `T` operací Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="182e5-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="182e5-142">__T__</span><span class="sxs-lookup"><span data-stu-id="182e5-142">__T__</span></span>    |<span data-ttu-id="182e5-143">Počet spuštění `T` operací a jejich sdružených, včetně `T` operací, T_x = H. t. h a T_y = hy. t. hy.</span><span class="sxs-lookup"><span data-stu-id="182e5-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="182e5-144">__Úrovní__</span><span class="sxs-lookup"><span data-stu-id="182e5-144">__Depth__</span></span>|<span data-ttu-id="182e5-145">Hloubka okruhu nečinnosti, kterou spouští Q# operace (viz [níže](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="182e5-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="182e5-146">Ve výchozím nastavení metrika hloubky počítá jenom `T` brány.</span><span class="sxs-lookup"><span data-stu-id="182e5-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="182e5-147">Další podrobnosti najdete v tématu s [čítačem hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="182e5-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="182e5-148">__Délk__</span><span class="sxs-lookup"><span data-stu-id="182e5-148">__Width__</span></span>|<span data-ttu-id="182e5-149">Šířka okruhu nečinnosti, kterou spouští Q# operace (viz [níže](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="182e5-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="182e5-150">Ve výchozím nastavení metrika hloubky počítá jenom `T` brány.</span><span class="sxs-lookup"><span data-stu-id="182e5-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="182e5-151">Další podrobnosti najdete v tématu o [čítači šířky](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="182e5-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="182e5-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="182e5-152">__QubitCount__</span></span>    |<span data-ttu-id="182e5-153">Dolní mez pro maximální počet qubits přidělených během běhu Q# operace.</span><span class="sxs-lookup"><span data-stu-id="182e5-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="182e5-154">Tato metrika nemusí být kompatibilní s __hloubkou__ (viz níže).</span><span class="sxs-lookup"><span data-stu-id="182e5-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="182e5-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="182e5-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="182e5-156">Maximální počet qubits, které byly v rámci operace vypůjčeny Q# .</span><span class="sxs-lookup"><span data-stu-id="182e5-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="182e5-157">Hloubka, Šířka a QubitCount</span><span class="sxs-lookup"><span data-stu-id="182e5-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="182e5-158">Vykázaný odhad hloubky a šířky jsou vzájemně kompatibilní.</span><span class="sxs-lookup"><span data-stu-id="182e5-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="182e5-159">(Dřív bylo možné dosáhnout obou čísel, ale pro hloubku a šířku se vyžadovaly různé okruhy.) V současné době je možné obě metriky v této dvojici dosáhnout stejným okruhem.</span><span class="sxs-lookup"><span data-stu-id="182e5-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="182e5-160">Nahlásí se následující metriky:</span><span class="sxs-lookup"><span data-stu-id="182e5-160">The following metrics are reported:</span></span>

<span data-ttu-id="182e5-161">__Hloubka:__ Pro kořenovou operaci – čas potřebný ke spuštění předpokládá konkrétní dobu brány.</span><span class="sxs-lookup"><span data-stu-id="182e5-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="182e5-162">Pro operace nazvané nebo následné operace – rozdíl mezi nejnovější qubitou dostupnosti na začátku a koncem operace.</span><span class="sxs-lookup"><span data-stu-id="182e5-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="182e5-163">__Šířka:__ Pro kořenovou operaci – počet qubits, které se skutečně používají ke spuštění (a operace, kterou volá).</span><span class="sxs-lookup"><span data-stu-id="182e5-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="182e5-164">Pro operace nazvané nebo následné operace – kolik dalších qubits bylo použito pro qubits, které již bylo na začátku operace použito.</span><span class="sxs-lookup"><span data-stu-id="182e5-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="182e5-165">Upozorňujeme, že znovu použitý qubits nepřispívá k tomuto číslu.</span><span class="sxs-lookup"><span data-stu-id="182e5-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="182e5-166">To znamená, že pokud před zahájením operace A zadáte několik qubits, a všechny qubit vyžádané touto operací a (a operace volané z A) byly splněné znovu pomocí dříve vydaných verzí qubits, Šířka operace A je hlášena jako 0.</span><span class="sxs-lookup"><span data-stu-id="182e5-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="182e5-167">Úspěšně se vypůjčila qubits, která nepřispívá k šířce.</span><span class="sxs-lookup"><span data-stu-id="182e5-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="182e5-168">__QubitCount:__ Pro kořenovou operaci – minimální počet qubits, který by byl dostatečný pro provedení této operace (a operací, které se z něho volaly).</span><span class="sxs-lookup"><span data-stu-id="182e5-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="182e5-169">Pro operace, které volaly nebo následné operace – minimální počet qubits, který by byl dostatečný pro provedení této operace samostatně.</span><span class="sxs-lookup"><span data-stu-id="182e5-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="182e5-170">Toto číslo nezahrnuje vstupní qubits.</span><span class="sxs-lookup"><span data-stu-id="182e5-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="182e5-171">Zahrnuje vypůjčené qubits.</span><span class="sxs-lookup"><span data-stu-id="182e5-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="182e5-172">Podporují se dva režimy provozu.</span><span class="sxs-lookup"><span data-stu-id="182e5-172">Two modes of operation are supported.</span></span> <span data-ttu-id="182e5-173">Režim je vybrán nastavením QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="182e5-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="182e5-174">__OptimizeDepth = true:__ QubitManager se nedoporučuje používat k opakovanému použití qubit a přiděluje nové qubit pokaždé, když se výzva k qubit.</span><span class="sxs-lookup"><span data-stu-id="182e5-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="182e5-175">__Hloubka__ kořenové operace se změní na minimální hloubku (s nižší mezí).</span><span class="sxs-lookup"><span data-stu-id="182e5-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="182e5-176">Pro tuto hloubku je uvedena kompatibilní __Šířka__ (je možné dosáhnout současně).</span><span class="sxs-lookup"><span data-stu-id="182e5-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="182e5-177">Všimněte si, že tato šířka pravděpodobně nebude optimální vzhledem k této hloubce.</span><span class="sxs-lookup"><span data-stu-id="182e5-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="182e5-178">__QubitCount__ může být pro kořenovou operaci nižší než šířka, protože předpokládá opakované použití.</span><span class="sxs-lookup"><span data-stu-id="182e5-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="182e5-179">__OptimizeDepth = false:__ QubitManager se doporučuje znovu použít qubits a pak znovu použít vydaný qubits před přidělením nových.</span><span class="sxs-lookup"><span data-stu-id="182e5-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="182e5-180">__Šířka__ kořenové operace se změní na minimální šířku (s nižší mezí).</span><span class="sxs-lookup"><span data-stu-id="182e5-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="182e5-181">Je hlášena kompatibilní __Hloubka__ , na které je možné dosáhnout.</span><span class="sxs-lookup"><span data-stu-id="182e5-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="182e5-182">__QubitCount__ bude stejná jako __Šířka__ pro kořenovou operaci, při které se nepředpokládá žádné výpůjčky.</span><span class="sxs-lookup"><span data-stu-id="182e5-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="182e5-183">Určování pravděpodobnosti výsledků měření</span><span class="sxs-lookup"><span data-stu-id="182e5-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="182e5-184">Můžete použít <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z <xref:Microsoft.Quantum.Diagnostics> oboru názvů k poskytnutí informací o očekávané pravděpodobnosti operace měření.</span><span class="sxs-lookup"><span data-stu-id="182e5-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="182e5-185">Další informace najdete v části [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="182e5-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="182e5-186">Viz také</span><span class="sxs-lookup"><span data-stu-id="182e5-186">See also</span></span>

- [<span data-ttu-id="182e5-187">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="182e5-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="182e5-188">Kvantový simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="182e5-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="182e5-189">Simulátor celkového kvantového stavu</span><span class="sxs-lookup"><span data-stu-id="182e5-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 

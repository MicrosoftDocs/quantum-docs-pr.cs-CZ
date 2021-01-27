---
title: Prostředky pro procesory Estimator – pro vývojová prostředí
description: Přečtěte si o QDK prostředcích Microsoft Estimator, které vyodhadují prostředky potřebné ke spuštění dané instance Q# operace na počítači s více operačními systémy.
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847467"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="7053e-103">Prostředky QDK (estimatoring Development Kit)</span><span class="sxs-lookup"><span data-stu-id="7053e-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="7053e-104">Jak název implikuje, `ResourcesEstimator` Třída odhadne prostředky potřebné ke spuštění dané instance Q# operace v počítači s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="7053e-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="7053e-105">To dosahuje tím, že spustí operaci bez skutečného simulace stavu počítače s více operačními systémy. z tohoto důvodu odhaduje prostředky pro Q# operace, které používají tisíce qubits, za předpokladu, že klasická část kódu běží v rozumnou dobu.</span><span class="sxs-lookup"><span data-stu-id="7053e-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="7053e-106">Prostředky Estimator jsou postavené na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)pro stav, který poskytuje bohatší sadu metrik a nástrojů pro ladění Q# programů.</span><span class="sxs-lookup"><span data-stu-id="7053e-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="7053e-107">Vyvolání a spuštění prostředků Estimator</span><span class="sxs-lookup"><span data-stu-id="7053e-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="7053e-108">Pomocí prostředků Estimator můžete spustit jakoukoli Q# operaci.</span><span class="sxs-lookup"><span data-stu-id="7053e-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="7053e-109">Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="7053e-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="7053e-110">Vyvolání prostředků estimator z C #</span><span class="sxs-lookup"><span data-stu-id="7053e-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="7053e-111">Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `ResourcesEstimator` a předáte ji jako první parametr metody `Run` příslušné operace.</span><span class="sxs-lookup"><span data-stu-id="7053e-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="7053e-112">Na rozdíl od třídy `QuantumSimulator` ale třída `ResourcesEstimator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="7053e-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="7053e-113">Jak ukazuje příklad, `ResourcesEstimator` poskytuje `ToTSV()` metodu, která generuje tabulku s hodnotami oddělenými tabulátory (TSV).</span><span class="sxs-lookup"><span data-stu-id="7053e-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="7053e-114">Tabulku můžete uložit do souboru nebo zobrazit v konzole pro účely analýzy.</span><span class="sxs-lookup"><span data-stu-id="7053e-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="7053e-115">Následuje ukázkový výstup z předchozího programu:</span><span class="sxs-lookup"><span data-stu-id="7053e-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="7053e-116">`ResourcesEstimator`Instance neresetuje své výpočty při každém spuštění.</span><span class="sxs-lookup"><span data-stu-id="7053e-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="7053e-117">Použijete-li stejnou instanci pro spuštění jiné operace, agreguje nové výsledky s existujícími výsledky.</span><span class="sxs-lookup"><span data-stu-id="7053e-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="7053e-118">Pokud potřebujete resetovat výpočty mezi běhy, vytvořte novou instanci pro každé spuštění.</span><span class="sxs-lookup"><span data-stu-id="7053e-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="7053e-119">Vyvolání prostředků estimator z Pythonu</span><span class="sxs-lookup"><span data-stu-id="7053e-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="7053e-120">Použijte metodu [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou Q# operací:</span><span class="sxs-lookup"><span data-stu-id="7053e-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="7053e-121">Vyvolání prostředků estimator z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="7053e-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="7053e-122">Při spuštění Q# programu z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k určení `ResourcesEstimator` cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="7053e-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="7053e-123">Následující příkaz spustí program pomocí Estimator prostředků:</span><span class="sxs-lookup"><span data-stu-id="7053e-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="7053e-124">Vyvolání prostředků estimator z poznámkových bloků Juptyer</span><span class="sxs-lookup"><span data-stu-id="7053e-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="7053e-125">Q#Pro spuštění operace použijte [odhad](xref:microsoft.quantum.iqsharp.magic-ref.simulate) příkazu I Magic% Q# .</span><span class="sxs-lookup"><span data-stu-id="7053e-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="7053e-126">Programové načítání odhadovaných dat</span><span class="sxs-lookup"><span data-stu-id="7053e-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="7053e-127">Kromě tabulky TSV můžete programově načíst prostředky odhadované během běhu prostřednictvím `Data` vlastnosti prostředků Estimator.</span><span class="sxs-lookup"><span data-stu-id="7053e-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="7053e-128">`Data`Vlastnost poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum` , indexované názvy metrik.</span><span class="sxs-lookup"><span data-stu-id="7053e-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="7053e-129">Následující kód ukazuje, jak načíst a vytisknout celkový počet `QubitClifford` `T` `CNOT` operací využívaných Q# operací:</span><span class="sxs-lookup"><span data-stu-id="7053e-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="7053e-130">Hlášené metriky</span><span class="sxs-lookup"><span data-stu-id="7053e-130">Metrics Reported</span></span>

<span data-ttu-id="7053e-131">Prostředky Estimator sledují následující metriky:</span><span class="sxs-lookup"><span data-stu-id="7053e-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="7053e-132">Metric</span><span class="sxs-lookup"><span data-stu-id="7053e-132">Metric</span></span>|<span data-ttu-id="7053e-133">Popis</span><span class="sxs-lookup"><span data-stu-id="7053e-133">Description</span></span>|
|----|----|
|<span data-ttu-id="7053e-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="7053e-134">__CNOT__</span></span>    |<span data-ttu-id="7053e-135">Počet spuštění `CNOT` operací (označovaný také jako řízené operace Pauli X).</span><span class="sxs-lookup"><span data-stu-id="7053e-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="7053e-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="7053e-136">__QubitClifford__</span></span> |<span data-ttu-id="7053e-137">Počet spuštění všech qubitch operací Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="7053e-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="7053e-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="7053e-138">__Measure__</span></span>    |<span data-ttu-id="7053e-139">Počet spuštění všech měření.</span><span class="sxs-lookup"><span data-stu-id="7053e-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="7053e-140">__R__</span><span class="sxs-lookup"><span data-stu-id="7053e-140">__R__</span></span>    |<span data-ttu-id="7053e-141">Počet spuštění všech rotací s jedním qubit, s výjimkou `T` operací Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="7053e-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="7053e-142">__T__</span><span class="sxs-lookup"><span data-stu-id="7053e-142">__T__</span></span>    |<span data-ttu-id="7053e-143">Počet spuštění `T` operací a jejich sdružených, včetně `T` operací, T_x = H. t. h a T_y = hy. t. hy.</span><span class="sxs-lookup"><span data-stu-id="7053e-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="7053e-144">__Úrovní__</span><span class="sxs-lookup"><span data-stu-id="7053e-144">__Depth__</span></span>|<span data-ttu-id="7053e-145">Hloubka okruhu nečinnosti, kterou spouští Q# operace (viz [níže](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="7053e-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="7053e-146">Ve výchozím nastavení metrika hloubky počítá jenom `T` brány.</span><span class="sxs-lookup"><span data-stu-id="7053e-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="7053e-147">Další podrobnosti najdete v tématu s [čítačem hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="7053e-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="7053e-148">__Width (Šířka)__</span><span class="sxs-lookup"><span data-stu-id="7053e-148">__Width__</span></span>|<span data-ttu-id="7053e-149">Šířka okruhu nečinnosti, kterou spouští Q# operace (viz [níže](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="7053e-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="7053e-150">Ve výchozím nastavení metrika hloubky počítá jenom `T` brány.</span><span class="sxs-lookup"><span data-stu-id="7053e-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="7053e-151">Další podrobnosti najdete v tématu o [čítači šířky](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="7053e-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="7053e-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="7053e-152">__QubitCount__</span></span>    |<span data-ttu-id="7053e-153">Dolní mez pro maximální počet qubits přidělených během běhu Q# operace.</span><span class="sxs-lookup"><span data-stu-id="7053e-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="7053e-154">Tato metrika nemusí být kompatibilní s __hloubkou__ (viz níže).</span><span class="sxs-lookup"><span data-stu-id="7053e-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="7053e-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="7053e-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="7053e-156">Maximální počet qubits, které byly v rámci operace vypůjčeny Q# .</span><span class="sxs-lookup"><span data-stu-id="7053e-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="7053e-157">Hloubka, Šířka a QubitCount</span><span class="sxs-lookup"><span data-stu-id="7053e-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="7053e-158">Vykázaný odhad hloubky a šířky jsou vzájemně kompatibilní.</span><span class="sxs-lookup"><span data-stu-id="7053e-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="7053e-159">(Dřív bylo možné dosáhnout obou čísel, ale pro hloubku a šířku se vyžadovaly různé okruhy.) V současné době je možné obě metriky v této dvojici dosáhnout stejným okruhem.</span><span class="sxs-lookup"><span data-stu-id="7053e-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="7053e-160">Nahlásí se následující metriky:</span><span class="sxs-lookup"><span data-stu-id="7053e-160">The following metrics are reported:</span></span>

<span data-ttu-id="7053e-161">__Hloubka:__ Pro kořenovou operaci – čas potřebný ke spuštění za předpokladu, že se nakonfigurovali časy brány.</span><span class="sxs-lookup"><span data-stu-id="7053e-161">__Depth:__ For the root operation - time it takes to execute it assuming configured gate times.</span></span>
<span data-ttu-id="7053e-162">Pro operace nazvané nebo následné operace rozdílového času mezi nejnovějším časem dostupnosti qubit na začátku a na konci operace.</span><span class="sxs-lookup"><span data-stu-id="7053e-162">For operations called or subsequent operations - time difference between the latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="7053e-163">__Šířka:__ Pro kořenovou operaci – počet qubits, které se skutečně používají ke spuštění (a operace, kterou volá).</span><span class="sxs-lookup"><span data-stu-id="7053e-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="7053e-164">Pro operace nazvané nebo následné operace – kolik dalších qubits bylo použito pro qubits, které již bylo na začátku operace použito.</span><span class="sxs-lookup"><span data-stu-id="7053e-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="7053e-165">Upozorňujeme, že znovu použitý qubits nepřispívá k tomuto číslu.</span><span class="sxs-lookup"><span data-stu-id="7053e-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="7053e-166">To znamená, že pokud před zahájením operace A zadáte několik qubits, a všechny qubit vyžádané touto operací a (a operace volané z A) byly splněné znovu pomocí dříve vydaných verzí qubits, Šířka operace A je hlášena jako 0.</span><span class="sxs-lookup"><span data-stu-id="7053e-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="7053e-167">Úspěšně se vypůjčila qubits, která nepřispívá k šířce.</span><span class="sxs-lookup"><span data-stu-id="7053e-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="7053e-168">__QubitCount:__ Pro kořenovou operaci – minimální počet qubits, který by byl dostatečný pro provedení této operace (a operací, které se z něho volaly).</span><span class="sxs-lookup"><span data-stu-id="7053e-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="7053e-169">Pro operace, které volaly nebo následné operace – minimální počet qubits, který by byl dostatečný pro provedení této operace samostatně.</span><span class="sxs-lookup"><span data-stu-id="7053e-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="7053e-170">Toto číslo nezahrnuje vstupní qubits.</span><span class="sxs-lookup"><span data-stu-id="7053e-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="7053e-171">Zahrnuje vypůjčené qubits.</span><span class="sxs-lookup"><span data-stu-id="7053e-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="7053e-172">Podporují se dva režimy provozu.</span><span class="sxs-lookup"><span data-stu-id="7053e-172">Two modes of operation are supported.</span></span> <span data-ttu-id="7053e-173">Režim je vybrán nastavením QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="7053e-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="7053e-174">__OptimizeDepth = false:__ Toto je výchozí režim.</span><span class="sxs-lookup"><span data-stu-id="7053e-174">__OptimizeDepth=false:__ This is the default mode.</span></span> <span data-ttu-id="7053e-175">QubitManager se doporučuje znovu použít qubits a pak znovu použít vydaný qubits před přidělením nových.</span><span class="sxs-lookup"><span data-stu-id="7053e-175">QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="7053e-176">__Šířka__ kořenové operace se změní na minimální šířku (s nižší mezí).</span><span class="sxs-lookup"><span data-stu-id="7053e-176">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="7053e-177">Je hlášena kompatibilní __Hloubka__ , na které je možné dosáhnout.</span><span class="sxs-lookup"><span data-stu-id="7053e-177">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="7053e-178">__QubitCount__ bude stejná jako __Šířka__ pro kořenovou operaci, při které se nepředpokládá žádné výpůjčky.</span><span class="sxs-lookup"><span data-stu-id="7053e-178">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

<span data-ttu-id="7053e-179">__OptimizeDepth = true:__ QubitManager se nedoporučuje z qubit opětovného použití a optimalizace založené na heuristikě pro qubit opakované použití se provádí během a po spuštění.</span><span class="sxs-lookup"><span data-stu-id="7053e-179">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and heuristic-based optimization for qubit reuse is performed during and after execution.</span></span> <span data-ttu-id="7053e-180">__Hloubka__ kořenové operace se změní na minimální hloubku (s nižší mezí).</span><span class="sxs-lookup"><span data-stu-id="7053e-180">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="7053e-181">Pro tuto hloubku je uvedena kompatibilní __Šířka__ (je možné dosáhnout současně).</span><span class="sxs-lookup"><span data-stu-id="7053e-181">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="7053e-182">Z důvodu optimalizace šířky můžou být brány, které se později v programu naplánovaly, naplánované předtím, než se dříve v programu nastaly, ale qubits se naplánují tak, aby se znovu použily tak, že hloubka zůstane minimální.</span><span class="sxs-lookup"><span data-stu-id="7053e-182">To optimize width, gates encountered later in the program may be scheduled before the gates encountered earlier in the program, but qubits are scheduled to be reused in such a way that the depth remains minimal.</span></span> <span data-ttu-id="7053e-183">Jak se qubits opakovaně používají na základě časových hodnot, doporučuje se, aby časy v bráně byly nakonfigurované jako celočíselné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="7053e-183">As qubits are reused based on time values, it is recommended that the gate times are configured to be integer values.</span></span> <span data-ttu-id="7053e-184">Není zaručena optimální __Šířka__ .</span><span class="sxs-lookup"><span data-stu-id="7053e-184">__Width__ is not guaranteed to be optimal.</span></span> <span data-ttu-id="7053e-185">Další informace najdete v části [Šířka a hloubka](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)dokumentu White Paper v trasování.</span><span class="sxs-lookup"><span data-stu-id="7053e-185">More information can be found in the whitepaper [Width and Depth in the Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="7053e-186">Určování pravděpodobnosti výsledků měření</span><span class="sxs-lookup"><span data-stu-id="7053e-186">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="7053e-187">Můžete použít <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z <xref:Microsoft.Quantum.Diagnostics> oboru názvů k poskytnutí informací o očekávané pravděpodobnosti operace měření.</span><span class="sxs-lookup"><span data-stu-id="7053e-187">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="7053e-188">Další informace najdete v části [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="7053e-188">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="7053e-189">Viz také</span><span class="sxs-lookup"><span data-stu-id="7053e-189">See also</span></span>

- [<span data-ttu-id="7053e-190">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="7053e-190">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="7053e-191">Kvantový simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="7053e-191">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="7053e-192">Simulátor celkového kvantového stavu</span><span class="sxs-lookup"><span data-stu-id="7053e-192">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 

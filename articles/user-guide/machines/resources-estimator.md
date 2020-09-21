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
ms.openlocfilehash: 6138c098a4efe2797c7d7360573ddcb9cb70a6c1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835923"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="d8752-103">Prostředky QDK (estimatoring Development Kit)</span><span class="sxs-lookup"><span data-stu-id="d8752-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="d8752-104">Jak název implikuje, `ResourcesEstimator` Třída odhadne prostředky potřebné ke spuštění dané instance Q# operace v počítači s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="d8752-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="d8752-105">To dosahuje tím, že spustí operaci bez skutečného simulace stavu počítače s více operačními systémy. z tohoto důvodu odhaduje prostředky pro Q# operace, které používají tisíce qubits, za předpokladu, že klasická část kódu běží v rozumnou dobu.</span><span class="sxs-lookup"><span data-stu-id="d8752-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="d8752-106">Prostředky Estimator jsou postavené na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)pro stav, který poskytuje bohatší sadu metrik a nástrojů pro ladění Q# programů.</span><span class="sxs-lookup"><span data-stu-id="d8752-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="d8752-107">Vyvolání a spuštění prostředků Estimator</span><span class="sxs-lookup"><span data-stu-id="d8752-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="d8752-108">Pomocí prostředků Estimator můžete spustit jakoukoli Q# operaci.</span><span class="sxs-lookup"><span data-stu-id="d8752-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="d8752-109">Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="d8752-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="d8752-110">Vyvolání prostředků estimator z C #</span><span class="sxs-lookup"><span data-stu-id="d8752-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="d8752-111">Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `ResourceEstimator` a předáte ji jako první parametr metody `Run` příslušné operace.</span><span class="sxs-lookup"><span data-stu-id="d8752-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="d8752-112">Na rozdíl od třídy `QuantumSimulator` ale třída `ResourceEstimator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="d8752-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="d8752-113">Jak ukazuje příklad, `ResourcesEstimator` poskytuje `ToTSV()` metodu, která generuje tabulku s hodnotami oddělenými tabulátory (TSV).</span><span class="sxs-lookup"><span data-stu-id="d8752-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="d8752-114">Tabulku můžete uložit do souboru nebo zobrazit v konzole pro účely analýzy.</span><span class="sxs-lookup"><span data-stu-id="d8752-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="d8752-115">Následuje ukázkový výstup z předchozího programu:</span><span class="sxs-lookup"><span data-stu-id="d8752-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="d8752-116">`ResourcesEstimator`Instance neresetuje své výpočty při každém spuštění.</span><span class="sxs-lookup"><span data-stu-id="d8752-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="d8752-117">Použijete-li stejnou instanci pro spuštění jiné operace, agreguje nové výsledky s existujícími výsledky.</span><span class="sxs-lookup"><span data-stu-id="d8752-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="d8752-118">Pokud potřebujete resetovat výpočty mezi běhy, vytvořte novou instanci pro každé spuštění.</span><span class="sxs-lookup"><span data-stu-id="d8752-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="d8752-119">Vyvolání prostředků estimator z Pythonu</span><span class="sxs-lookup"><span data-stu-id="d8752-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="d8752-120">Použijte metodu [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou Q# operací:</span><span class="sxs-lookup"><span data-stu-id="d8752-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="d8752-121">Vyvolání prostředků estimator z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="d8752-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="d8752-122">Při spuštění Q# programu z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k určení `ResourcesEstimator` cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="d8752-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="d8752-123">Následující příkaz spustí program pomocí Estimator prostředků:</span><span class="sxs-lookup"><span data-stu-id="d8752-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="d8752-124">Vyvolání prostředků estimator z poznámkových bloků Juptyer</span><span class="sxs-lookup"><span data-stu-id="d8752-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="d8752-125">Q#Pro spuštění operace použijte [odhad](xref:microsoft.quantum.iqsharp.magic-ref.simulate) příkazu I Magic% Q# .</span><span class="sxs-lookup"><span data-stu-id="d8752-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="d8752-126">Programové načítání odhadovaných dat</span><span class="sxs-lookup"><span data-stu-id="d8752-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="d8752-127">Kromě tabulky TSV můžete programově načíst prostředky odhadované během běhu prostřednictvím `Data` vlastnosti prostředků Estimator.</span><span class="sxs-lookup"><span data-stu-id="d8752-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="d8752-128">`Data`Vlastnost poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum` , indexované názvy metrik.</span><span class="sxs-lookup"><span data-stu-id="d8752-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="d8752-129">Následující kód ukazuje, jak načíst a vytisknout celkový počet `QubitClifford` `T` `CNOT` operací využívaných Q# operací:</span><span class="sxs-lookup"><span data-stu-id="d8752-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="d8752-130">Hlášené metriky</span><span class="sxs-lookup"><span data-stu-id="d8752-130">Metrics Reported</span></span>

<span data-ttu-id="d8752-131">Prostředky Estimator sledují následující metriky:</span><span class="sxs-lookup"><span data-stu-id="d8752-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="d8752-132">Metrika</span><span class="sxs-lookup"><span data-stu-id="d8752-132">Metric</span></span>|<span data-ttu-id="d8752-133">Popis</span><span class="sxs-lookup"><span data-stu-id="d8752-133">Description</span></span>|
|----|----|
|<span data-ttu-id="d8752-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="d8752-134">__CNOT__</span></span>    |<span data-ttu-id="d8752-135">Počet spuštění `CNOT` operací (označovaný také jako řízené operace Pauli X).</span><span class="sxs-lookup"><span data-stu-id="d8752-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="d8752-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="d8752-136">__QubitClifford__</span></span> |<span data-ttu-id="d8752-137">Počet spuštění všech qubitch operací Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="d8752-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="d8752-138">__Míra__</span><span class="sxs-lookup"><span data-stu-id="d8752-138">__Measure__</span></span>    |<span data-ttu-id="d8752-139">Počet spuštění všech měření.</span><span class="sxs-lookup"><span data-stu-id="d8752-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="d8752-140">__R__</span><span class="sxs-lookup"><span data-stu-id="d8752-140">__R__</span></span>    |<span data-ttu-id="d8752-141">Počet spuštění všech rotací s jedním qubit, s výjimkou `T` operací Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="d8752-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="d8752-142">__T__</span><span class="sxs-lookup"><span data-stu-id="d8752-142">__T__</span></span>    |<span data-ttu-id="d8752-143">Počet spuštění `T` operací a jejich sdružených, včetně `T` operací, T_x = H. t. h a T_y = hy. t. hy.</span><span class="sxs-lookup"><span data-stu-id="d8752-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="d8752-144">__Úrovní__</span><span class="sxs-lookup"><span data-stu-id="d8752-144">__Depth__</span></span>|<span data-ttu-id="d8752-145">Dolní mez pro hloubku okruhu provozu, kterou Q# operace spouští.</span><span class="sxs-lookup"><span data-stu-id="d8752-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="d8752-146">Ve výchozím nastavení metrika hloubky počítá jenom `T` brány.</span><span class="sxs-lookup"><span data-stu-id="d8752-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="d8752-147">Další podrobnosti najdete v tématu s [čítačem hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="d8752-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="d8752-148">__Délk__</span><span class="sxs-lookup"><span data-stu-id="d8752-148">__Width__</span></span>    |<span data-ttu-id="d8752-149">Dolní mez pro maximální počet qubits přidělených během běhu Q# operace.</span><span class="sxs-lookup"><span data-stu-id="d8752-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="d8752-150">Možná nebude možné dosáhnout současně __hloubkové__ a __šířky__ dolní meze.</span><span class="sxs-lookup"><span data-stu-id="d8752-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="d8752-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="d8752-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="d8752-152">Maximální počet qubits, které byly v rámci operace vypůjčeny Q# .</span><span class="sxs-lookup"><span data-stu-id="d8752-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="d8752-153">Určování pravděpodobnosti výsledků měření</span><span class="sxs-lookup"><span data-stu-id="d8752-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="d8752-154">Můžete použít <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z <xref:microsoft.quantum.diagnostics> oboru názvů k poskytnutí informací o očekávané pravděpodobnosti operace měření.</span><span class="sxs-lookup"><span data-stu-id="d8752-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="d8752-155">Další informace najdete v části [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="d8752-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="d8752-156">Viz také</span><span class="sxs-lookup"><span data-stu-id="d8752-156">See also</span></span>

- [<span data-ttu-id="d8752-157">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="d8752-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="d8752-158">Kvantový simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="d8752-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="d8752-159">Simulátor celkového kvantového stavu</span><span class="sxs-lookup"><span data-stu-id="d8752-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
---
title: Estimator prostředky pro vývoj pro všechna ta
description: 'Přečtěte si o Estimatorech prostředků, které odhadují prostředky potřebné ke spuštění dané instance operace Q # v počítači s více operačními systémy.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 37c901e5a861f0e8a10cdc911ad1d84ddd3e6e00
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907048"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="15f72-103">Cílový počítač ResourcesEstimator</span><span class="sxs-lookup"><span data-stu-id="15f72-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="15f72-104">Jak název napovídá, `ResourcesEstimator` odhaduje prostředky potřebné ke spuštění dané instance operace Q # v počítači s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="15f72-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="15f72-105">To dosahuje provedením operace s neskutečným simulací stavu počítače s více operačními počítači. z tohoto důvodu může odhadnout prostředky pro operace Q #, které používají tisíce qubits.</span><span class="sxs-lookup"><span data-stu-id="15f72-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="15f72-106">Využití</span><span class="sxs-lookup"><span data-stu-id="15f72-106">Usage</span></span>

<span data-ttu-id="15f72-107">`ResourcesEstimator` je pouze jiný typ cílového počítače, takže jej lze použít ke spuštění jakékoli operace Q #.</span><span class="sxs-lookup"><span data-stu-id="15f72-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="15f72-108">Podobně jako u jiných cílových počítačů je možné ji použít C# v hostitelském programu vytvořit instanci a předat ji jako první parametr `Run` metody operace:</span><span class="sxs-lookup"><span data-stu-id="15f72-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="15f72-109">Jak ukazuje příklad, `ResourcesEstimator` poskytuje `ToTSV()` metodu pro generování tabulky s hodnotami oddělenými tabulátory (TSV), které je možné uložit do souboru nebo zapsat do konzoly pro účely analýzy.</span><span class="sxs-lookup"><span data-stu-id="15f72-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="15f72-110">Výstup výše uvedeného programu by měl vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="15f72-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="15f72-111">`ResourcesEstimator` neresetuje své výpočty při každém spuštění, pokud se stejná instance používá ke spuštění jiné operace, bude mít za následek agregaci počtů nad stávajícími výsledky.</span><span class="sxs-lookup"><span data-stu-id="15f72-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="15f72-112">Pokud potřebujete resetovat výpočty mezi běhy, vytvořte novou instanci pro každé spuštění.</span><span class="sxs-lookup"><span data-stu-id="15f72-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="15f72-113">Programové načítání odhadovaných dat</span><span class="sxs-lookup"><span data-stu-id="15f72-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="15f72-114">Kromě tabulky TSV lze odhadované prostředky načíst programově prostřednictvím vlastnosti `Data` `ResourcesEstimator`.</span><span class="sxs-lookup"><span data-stu-id="15f72-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="15f72-115">`Data` poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum`, indexované názvy metrik.</span><span class="sxs-lookup"><span data-stu-id="15f72-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="15f72-116">Následující kód ukazuje, jak načíst a vytisknout celkový počet `QubitClifford`, `T` a `CNOT` Branch, které používá operace Q #:</span><span class="sxs-lookup"><span data-stu-id="15f72-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="15f72-117">Hlášené metriky</span><span class="sxs-lookup"><span data-stu-id="15f72-117">Metrics Reported</span></span>

<span data-ttu-id="15f72-118">Níže je seznam metrik odhadovaných `ResourcesEstimator`:</span><span class="sxs-lookup"><span data-stu-id="15f72-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="15f72-119">__CNOT__: počet spuštěných bran Pauli X pro CNOT (označovaný také jako řízená ovládaná brána X).</span><span class="sxs-lookup"><span data-stu-id="15f72-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="15f72-120">__QubitClifford__: počet spuštěných jednotlivých bran qubit Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="15f72-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="15f72-121">__Measure__: počet provedených měření.</span><span class="sxs-lookup"><span data-stu-id="15f72-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="15f72-122">__R__: počet spuštěných jednoduchých qubit otočení s výjimkou bran T, Clifford a Pauli.</span><span class="sxs-lookup"><span data-stu-id="15f72-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="15f72-123">__T__: Počet bran t a jejich sdružených, včetně brány T, T_x = H. t. H a T_y = hy. T. hy, proveden.</span><span class="sxs-lookup"><span data-stu-id="15f72-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="15f72-124">__Hloubka__: Hloubka okruhu nečinnosti, kterou provede operace Q #.</span><span class="sxs-lookup"><span data-stu-id="15f72-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="15f72-125">Ve výchozím nastavení se tato hloubka počítá jenom u bran T. Podrobnosti najdete v části s informacemi o [čítači hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="15f72-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="15f72-126">__Width__: maximální počet qubits přidělených během provádění operace Q #.</span><span class="sxs-lookup"><span data-stu-id="15f72-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="15f72-127">__BorrowedWidth__: maximální počet qubitsů v rámci operace Q # byl vypůjčen.</span><span class="sxs-lookup"><span data-stu-id="15f72-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="15f72-128">Určování pravděpodobnosti výsledků měření</span><span class="sxs-lookup"><span data-stu-id="15f72-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="15f72-129"><xref:microsoft.quantum.intrinsic.assertprob> z oboru názvů <xref:microsoft.quantum.intrinsic> lze použít k poskytnutí informací o očekávané pravděpodobnosti měření, které vám pomůžou při provádění programu Q #.</span><span class="sxs-lookup"><span data-stu-id="15f72-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="15f72-130">Ilustruje to následující příklad:</span><span class="sxs-lookup"><span data-stu-id="15f72-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="15f72-131">Když `ResourcesEstimator` narazí `AssertProb`, bude nahrávat `PauliZ` na `source` a `q` by měl být uveden výsledek `Zero` s pravděpodobností 0,5.</span><span class="sxs-lookup"><span data-stu-id="15f72-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="15f72-132">Když se spustí `M` později, nalezne zaznamenané hodnoty pravděpodobnosti výsledku a `M` vrátí `Zero` nebo `One` s pravděpodobností 0,5.</span><span class="sxs-lookup"><span data-stu-id="15f72-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="15f72-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="15f72-133">See also</span></span>

<span data-ttu-id="15f72-134">`ResourcesEstimator` je postaven na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů s procesorem, který poskytuje bohatší sadu metrik, schopnost nahlásit metriky na plný graf volání a funkce, jako je například [Kontrola různých vstupů](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , pomůžou najít chyby v programech Q #.</span><span class="sxs-lookup"><span data-stu-id="15f72-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="15f72-135">Další informace najdete v dokumentaci [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="15f72-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>


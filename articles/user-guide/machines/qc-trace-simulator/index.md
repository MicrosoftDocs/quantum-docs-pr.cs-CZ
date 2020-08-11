---
title: Simulátor kvantového trasování – Quantum Development Kit
description: Naučte se používat simulátor kvantového trasování od Microsoftu k ladění klasického kódu a odhadu požadavků na prostředky v programu v Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d5efef037ff236bd040dfd88e94f7f3dd331aef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868215"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="4a7cc-103">Simulátor kvantového trasování sady Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="4a7cc-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="4a7cc-104">Třída <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> v QDK spouští kvantové programy, aniž by simulovala stav kvantového počítače.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="4a7cc-105">Z tohoto důvodu může simulátor kvantového trasování spouštět kvantové programy, které používají tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="4a7cc-106">To je užitečné ze dvou hlavních důvodů:</span><span class="sxs-lookup"><span data-stu-id="4a7cc-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="4a7cc-107">Ladění klasického kódu, který je součástí kvantového programu.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="4a7cc-108">Odhad prostředků potřebných ke spuštění dané instance kvantového programu v kvantovém počítači.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="4a7cc-109">[Estimátor prostředků](xref:microsoft.quantum.machines.resources-estimator), který poskytuje omezenější sadu metrik, je ve skutečnosti založený na simulátoru trasování.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="4a7cc-110">Vyvolání simulátoru kvantového trasování</span><span class="sxs-lookup"><span data-stu-id="4a7cc-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="4a7cc-111">Simulátor kvantového trasování můžete využít ke spuštění libovolné operace Q#.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="4a7cc-112">Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `QCTraceSimulator` a předáte ji jako první parametr metody `Run` příslušné operace.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="4a7cc-113">Na rozdíl od třídy `QuantumSimulator` ale třída `QCTraceSimulator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="4a7cc-114">Určování pravděpodobnosti výsledků měření</span><span class="sxs-lookup"><span data-stu-id="4a7cc-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="4a7cc-115">Vzhledem k tomu, že simulátor kvantového trasování nesimuluje skutečný kvantový stav, není možné vypočítat pravděpodobnost výsledků měření v rámci operace.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="4a7cc-116">Proto pokud operace obsahuje měření, je nutné explicitně poskytnout tyto pravděpodobnosti pomocí operace <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z oboru názvů <xref:microsoft.quantum.diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="4a7cc-117">Ilustruje to následující příklad:</span><span class="sxs-lookup"><span data-stu-id="4a7cc-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="4a7cc-118">Když simulátor kvantového trasování narazí na operaci `AssertMeasurementProbability`, zaznamená, že pro měření `PauliZ` v umístění `source` a `q` by měl být uveden výstup `Zero` s pravděpodobností **0,5**.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="4a7cc-119">Když později spustí operaci `M`, najde zaznamenané hodnoty pravděpodobnosti výsledků a `M` vrátí `Zero` nebo `One`, a to s pravděpodobností **0,5**.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="4a7cc-120">Pokud stejný kód běží v simulátoru, který sleduje kvantový stav, tento simulátor ověří správnost pravděpodobností v rámci operace `AssertMeasurementProbability`.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="4a7cc-121">Mějte na paměti, že pokud alespoň jedna operace měření nemá anotaci vytvořenou pomocí `AssertMeasurementProbability`, simulátor vygeneruje [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="4a7cc-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="4a7cc-122">Nástroje simulátoru kvantového trasování</span><span class="sxs-lookup"><span data-stu-id="4a7cc-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="4a7cc-123">Sada QDK zahrnuje pět nástrojů, které můžete použít se simulátorem kvantového trasování k detekci chyb ve vašich programech a provádění odhadů prostředků kvantových programů:</span><span class="sxs-lookup"><span data-stu-id="4a7cc-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="4a7cc-124">Nástroj</span><span class="sxs-lookup"><span data-stu-id="4a7cc-124">Tool</span></span> | <span data-ttu-id="4a7cc-125">Popis</span><span class="sxs-lookup"><span data-stu-id="4a7cc-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="4a7cc-126">Kontrola odlišných vstupů</span><span class="sxs-lookup"><span data-stu-id="4a7cc-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="4a7cc-127">Kontroluje možné konflikty se sdílenými qubity.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="4a7cc-128">Kontrola použití neplatných qubitů</span><span class="sxs-lookup"><span data-stu-id="4a7cc-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="4a7cc-129">Kontroluje, jestli program používá operaci na qubit, který už je vydaný.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="4a7cc-130">Čítač primitivních operací</span><span class="sxs-lookup"><span data-stu-id="4a7cc-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="4a7cc-131">Zjišťuje počet primitivních spuštění použitých všemi operacemi vyvolanými kvantovým programem.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-131">Counts the number of primitive executions used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="4a7cc-132">Čítač hloubky</span><span class="sxs-lookup"><span data-stu-id="4a7cc-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="4a7cc-133">Shromažďuje počty, které reprezentují dolní hranici hloubky operací vyvolaných v kvantovém programu.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="4a7cc-134">Čítač šířky</span><span class="sxs-lookup"><span data-stu-id="4a7cc-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="4a7cc-135">Zjišťuje počet qubitů přidělených a vypůjčených jednotlivými operacemi v kvantovém programu.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="4a7cc-136">Každý z těchto nástrojů se aktivuje nastavením příslušných příznaků v `QCTraceSimulatorConfiguration` a následným předáním této konfigurace do deklarace `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="4a7cc-137">Informace o použití každého z těchto nástrojů najdete pod odkazy v předchozím seznamu.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="4a7cc-138">Další informace týkající se konfigurace `QCTraceSimulator` najdete v tématu [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4a7cc-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="4a7cc-139">Metody QCTraceSimulatoru</span><span class="sxs-lookup"><span data-stu-id="4a7cc-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="4a7cc-140">`QCTraceSimulator` má několik předdefinovaných metod pro načtení hodnot metrik trasovaných během kvantové operace.</span><span class="sxs-lookup"><span data-stu-id="4a7cc-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="4a7cc-141">Příklady metod [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) a [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) najdete ve článcích [Čítač primitivních operací](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Čítač hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) a [Čítač šířky](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="4a7cc-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="4a7cc-142">Další informace o veškerých dostupných metodách najdete v referenčních informacích k rozhraní API pro Q# v tématu [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator).</span><span class="sxs-lookup"><span data-stu-id="4a7cc-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4a7cc-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="4a7cc-143">See also</span></span>

- [<span data-ttu-id="4a7cc-144">Estimátor kvantových prostředků</span><span class="sxs-lookup"><span data-stu-id="4a7cc-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="4a7cc-145">Kvantový simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="4a7cc-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="4a7cc-146">Simulátor celkového kvantového stavu</span><span class="sxs-lookup"><span data-stu-id="4a7cc-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
---
title: Simulátor trasování kvantového počítače
description: Naučte se používat simulátor kvantového trasování od Microsoftu k ladění klasického kódu a odhadu požadavků na prostředky v kvantovém programu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 4cec688da35951271d87396d9b6a8fed744defc6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273325"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="cbaac-103">Simulátor kvantového trasování</span><span class="sxs-lookup"><span data-stu-id="cbaac-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="cbaac-104">Simulátor trasování kvantového počítače od Microsoftu spouští kvantový program, aniž by ve skutečnosti simuloval stav kvantového počítače.</span><span class="sxs-lookup"><span data-stu-id="cbaac-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="cbaac-105">Simulátor trasování proto může spouštět kvantové programy, které používají tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="cbaac-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="cbaac-106">To je užitečné ze dvou hlavních důvodů:</span><span class="sxs-lookup"><span data-stu-id="cbaac-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="cbaac-107">Ladění klasického kódu, který je součástí kvantového programu.</span><span class="sxs-lookup"><span data-stu-id="cbaac-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="cbaac-108">Odhad prostředků potřebných ke spuštění dané instance kvantového programu v kvantovém počítači.</span><span class="sxs-lookup"><span data-stu-id="cbaac-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="cbaac-109">Simulátor trasování je závislý na dalších informacích poskytovaných uživatelem, když je třeba provést měření.</span><span class="sxs-lookup"><span data-stu-id="cbaac-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="cbaac-110">Podrobnější informace najdete v části [Určování pravděpodobnosti výsledků měření](#providing-the-probability-of-measurement-outcomes).</span><span class="sxs-lookup"><span data-stu-id="cbaac-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="cbaac-111">Určování pravděpodobnosti výsledků měření</span><span class="sxs-lookup"><span data-stu-id="cbaac-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="cbaac-112">V kvantových algoritmech se provádějí dva druhy měření.</span><span class="sxs-lookup"><span data-stu-id="cbaac-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="cbaac-113">První druh má doplňující roli tam, kde uživatel zpravidla zná pravděpodobnost výsledků.</span><span class="sxs-lookup"><span data-stu-id="cbaac-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="cbaac-114">V takovém případě může uživatel tuto znalost vyjádřit zapsáním operace <xref:microsoft.quantum.intrinsic.assertprob> z oboru názvů <xref:microsoft.quantum.intrinsic>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="cbaac-115">Ilustruje to následující příklad:</span><span class="sxs-lookup"><span data-stu-id="cbaac-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="cbaac-116">Když simulátor trasování provede operaci `AssertProb`, zaznamená, že pro měření `PauliZ` v umístění `source` a `q` by měl být uveden výstup `Zero` s pravděpodobností 0,5.</span><span class="sxs-lookup"><span data-stu-id="cbaac-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="cbaac-117">Když simulátor později provede akci `M`, najde zaznamenané hodnoty pravděpodobnosti výstupu a akce `M` vrátí hodnotu `Zero` nebo `One` s pravděpodobností 0,5.</span><span class="sxs-lookup"><span data-stu-id="cbaac-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="cbaac-118">Když je stejný kód spuštěn v simulátoru, který sleduje kvantový stav, tento simulátor ověří správnost pravděpodobností v rámci operace `AssertProb`.</span><span class="sxs-lookup"><span data-stu-id="cbaac-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="cbaac-119">Spuštění programu v simulátoru trasování kvantového počítače</span><span class="sxs-lookup"><span data-stu-id="cbaac-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="cbaac-120">Simulátor trasování kvantového počítače lze vnímat pouze jako další cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="cbaac-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="cbaac-121">Program ovladače C# pro jeho použití je velmi podobný programu pro jakýkoli jiný kvantový simulátor.</span><span class="sxs-lookup"><span data-stu-id="cbaac-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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

<span data-ttu-id="cbaac-122">Mějte na paměti, že pokud alespoň jedno měření nemá anotaci vytvořenou operací `AssertProb`, simulátor vygeneruje výjimku `UnconstrainedMeasurementException` z oboru názvů `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="cbaac-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="cbaac-123">Podrobnější informace najdete v dokumentaci k rozhraní API pro výjimku [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).</span><span class="sxs-lookup"><span data-stu-id="cbaac-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="cbaac-124">Kromě spouštění kvantových programů je simulátor trasování vybaven pěti komponentami pro zjišťování chyb v programech a zjišťování odhadů prostředků kvantových programů:</span><span class="sxs-lookup"><span data-stu-id="cbaac-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="cbaac-125">Kontrola odlišných vstupů</span><span class="sxs-lookup"><span data-stu-id="cbaac-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="cbaac-126">Kontrola použití neplatných qubitů</span><span class="sxs-lookup"><span data-stu-id="cbaac-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="cbaac-127">Čítač primitivních operací</span><span class="sxs-lookup"><span data-stu-id="cbaac-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="cbaac-128">Čítač hloubky okruhu</span><span class="sxs-lookup"><span data-stu-id="cbaac-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="cbaac-129">Čítač šířky okruhu</span><span class="sxs-lookup"><span data-stu-id="cbaac-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="cbaac-130">Každou z těchto komponent je možné povolit nastavením příslušných příznaků v rámci třídy `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="cbaac-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="cbaac-131">Podrobnější informace o používání jednotlivých komponent jsou k dispozici v příslušných referenčních souborech.</span><span class="sxs-lookup"><span data-stu-id="cbaac-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="cbaac-132">Konkrétní podrobnosti najdete v dokumentaci k rozhraní API pro třídu [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="cbaac-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbaac-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="cbaac-133">See also</span></span>
<span data-ttu-id="cbaac-134">Reference ke kódu C# [simulátoru trasování](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) kvantového počítače</span><span class="sxs-lookup"><span data-stu-id="cbaac-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 


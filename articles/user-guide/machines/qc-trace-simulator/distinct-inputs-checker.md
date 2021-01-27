---
title: Kontrola různých vstupů – pro vývojová prostředí
description: Přečtěte si o kontrolách různých vstupů Microsoft QDK, které používají simulátor trasování doby využívání, ke kontrole Q# kódu pro potenciální konflikty se sdílenými qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8076a705b1960ae8e23be4cea87e613329a24f77
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858644"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="cd3a0-103">Simulátor trasování doby využití: Kontrola různých vstupů</span><span class="sxs-lookup"><span data-stu-id="cd3a0-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="cd3a0-104">Nástroj pro kontrolu různých vstupů je součástí nástroje pro vývoj po částech. [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="cd3a0-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="cd3a0-105">Můžete ji použít ke zjištění potenciálních chyb v kódu způsobených konflikty se sdílenými qubits.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="cd3a0-106">Konflikty se sdílenými qubits</span><span class="sxs-lookup"><span data-stu-id="cd3a0-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="cd3a0-107">Zvažte následující část Q# kódu pro ilustraci problémů zjištěných nástrojem pro kontrolu různých vstupů:</span><span class="sxs-lookup"><span data-stu-id="cd3a0-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="cd3a0-108">Když se podíváte na tento program, můžete předpokládat, že pořadí, ve kterém se volá `op1` `op2` , nezáleží na tom, protože `q1` a `q2` jsou různé qubits a operace fungující na různých qubits dojíždění.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="cd3a0-109">Nyní vezměte v úvahu tento příklad:</span><span class="sxs-lookup"><span data-stu-id="cd3a0-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="cd3a0-110">Všimněte si, že `op1` a `op2` jsou získány pomocí částečné aplikace a sdílejí qubit.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="cd3a0-111">Při volání `ApplyBoth` v tomto příkladu výsledek operace závisí na pořadí `op1` a `op2` uvnitř `ApplyBoth` Not, co byste měli očekávat.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="cd3a0-112">Povolíte-li nástroj pro kontrolu různých vstupů, detekuje takové situace a vyvolá `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="cd3a0-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="cd3a0-113">Další informace najdete v tématu <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> v Q# knihovně rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-113">For more information, see <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="cd3a0-114">Vyvolání kontroly různých vstupů</span><span class="sxs-lookup"><span data-stu-id="cd3a0-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="cd3a0-115">Chcete-li spustit simulátor trasování doby provozu s nástrojem pro kontrolu různých vstupů, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UseDistinctInputsChecker` vlastnost na **hodnotu true** a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="cd3a0-116">Použití kontroly různých vstupů v hostitelském programu C#</span><span class="sxs-lookup"><span data-stu-id="cd3a0-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="cd3a0-117">Následuje příklad hostitelského programu C#, který používá simulátor trasování doby využívání, se zapnutou kontrolou různých vstupů:</span><span class="sxs-lookup"><span data-stu-id="cd3a0-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="cd3a0-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="cd3a0-118">See also</span></span>

- <span data-ttu-id="cd3a0-119">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="cd3a0-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="cd3a0-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="cd3a0-122"><xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="cd3a0-122">The <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> API reference.</span></span>

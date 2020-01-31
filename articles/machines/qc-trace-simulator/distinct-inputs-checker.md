---
title: Kontrola různých vstupů | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování kvantového počítače
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820959"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="a8669-103">Kontrola různých vstupů</span><span class="sxs-lookup"><span data-stu-id="a8669-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="a8669-104">`Distinct Inputs Checker` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.</span><span class="sxs-lookup"><span data-stu-id="a8669-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="a8669-105">Je navržena pro detekci potenciálních chyb v kódu.</span><span class="sxs-lookup"><span data-stu-id="a8669-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="a8669-106">Zvažte následující část kódu Q # pro ilustraci problémů zjištěných tímto balíčkem:</span><span class="sxs-lookup"><span data-stu-id="a8669-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="a8669-107">Když uživatel tento program prohlíží, předpokládá se, že pořadí, ve kterém `op1` a `op2` jsou volána, nezáleží na tom, že `q1` a `q2` jsou různé qubits a operace fungující na různých qubitsích dojíždění.</span><span class="sxs-lookup"><span data-stu-id="a8669-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="a8669-108">Nyní si představte, že jsme si vybrali příklad, kde se tato operace používá:</span><span class="sxs-lookup"><span data-stu-id="a8669-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="a8669-109">Nyní `op1` a `op2` jsou získány pomocí částečné aplikace a sdílejí qubit.</span><span class="sxs-lookup"><span data-stu-id="a8669-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="a8669-110">Pokud uživatel volá `ApplyBoth` v příkladu výše, výsledkem operace bude záviset na pořadí `op1` a `op2` v `ApplyBoth`.</span><span class="sxs-lookup"><span data-stu-id="a8669-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="a8669-111">To znamená, že nebudete mít k tomu uživatele očekávat.</span><span class="sxs-lookup"><span data-stu-id="a8669-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="a8669-112">`Distinct Inputs Checker` zjistí takové situace, pokud jsou povoleny, a vyvolá `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="a8669-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="a8669-113">Další podrobnosti najdete v dokumentaci k rozhraní API v [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="a8669-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="a8669-114">Použití kontroly různých vstupů v C# programu</span><span class="sxs-lookup"><span data-stu-id="a8669-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="a8669-115">Tady je příklad kódu C# ovladače pro použití simulátoru trasování počítače v% s povolenou možností `Distinct Inputs Checker`:</span><span class="sxs-lookup"><span data-stu-id="a8669-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="a8669-116">Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a může být poskytnuta jako argument pro `QCTraceSimulator` konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a8669-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="a8669-117">Pokud je `useDistinctInputsChecker` nastaveno na hodnotu true, je povolen `Distinct Inputs Checker`.</span><span class="sxs-lookup"><span data-stu-id="a8669-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="a8669-118">Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="a8669-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8669-119">Další informace najdete v tématech</span><span class="sxs-lookup"><span data-stu-id="a8669-119">See also</span></span>

- <span data-ttu-id="a8669-120">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="a8669-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>

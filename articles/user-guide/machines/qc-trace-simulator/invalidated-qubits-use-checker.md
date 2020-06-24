---
title: Kontrola použití neplatných qubitů
description: 'Přečtěte si o nástroji QDK s neplatnými Qubits pro Microsoft, který kontroluje kód Q # pro potenciálně neplatnou Qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274573"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="d0419-103">Kontrola použití neověřené Qubits</span><span class="sxs-lookup"><span data-stu-id="d0419-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="d0419-104">`Invalidated Qubits Use Checker`Je součástí [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítače, který je navržen pro detekci potenciálních chyb v kódu.</span><span class="sxs-lookup"><span data-stu-id="d0419-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="d0419-105">Vezměte v úvahu následující část kódu Q # pro ilustraci problémů zjištěných nástrojem `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="d0419-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="d0419-106">Při `H` použití na `q[0]` odkazuje na již vydaný qubit.</span><span class="sxs-lookup"><span data-stu-id="d0419-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="d0419-107">To může způsobit nedefinované chování.</span><span class="sxs-lookup"><span data-stu-id="d0419-107">This can cause undefined behavior.</span></span> <span data-ttu-id="d0419-108">Když `Invalidated Qubits Use Checker` je povolená, výjimka se `InvalidatedQubitsUseCheckerException` vyvolá, pokud se operace použije na už vydaný qubit.</span><span class="sxs-lookup"><span data-stu-id="d0419-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="d0419-109">Další podrobnosti najdete v dokumentaci k rozhraní API v [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="d0419-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="d0419-110">Použití funkce Qubits s neověřeným použitím nástroje pro kontrolu použití v programu v C#</span><span class="sxs-lookup"><span data-stu-id="d0419-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="d0419-111">Následuje příklad kódu ovladače C# pro použití počítače s příznakem pro práci `Trace
Simulator` s `Invalidated Qubits Use Checker` povoleným:</span><span class="sxs-lookup"><span data-stu-id="d0419-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="d0419-112">Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a je možné ho zadat jako argument pro `QCTraceSimulator` konstruktor.</span><span class="sxs-lookup"><span data-stu-id="d0419-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="d0419-113">Když `useInvalidatedQubitsUseChecker` je nastavená hodnota true, `Invalidated Qubits Use Checker` je povolený.</span><span class="sxs-lookup"><span data-stu-id="d0419-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="d0419-114">Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="d0419-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0419-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="d0419-115">See also</span></span> ##

- <span data-ttu-id="d0419-116">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="d0419-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
